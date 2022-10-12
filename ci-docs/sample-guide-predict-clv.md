---
title: Guía de muestra de la predicción (CLV) del valor de por vida del cliente
description: Utilice esta guía de muestra para probar el modelo de valor de vida útil del cliente predicción.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609659"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guía de muestra de la predicción (CLV) del valor de por vida del cliente

Esta guía le lleva por un ejemplo de extremo a extremo de la predicción del valor de vida útil del cliente (CLV) en Customer Insights utilizando datos de muestra. Le recomendamos que pruebe esta predicción en [un nuevo entorno](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad. Venden los productos a través de su sitio web Contoso Coffee. La empresa quiere comprender el valor (ingresos) que sus clientes pueden generar en los próximos 12 meses. Conocer el valor esperado de sus clientes en los próximos 12 meses les ayudará a dirigir sus esfuerzos de marketing hacia clientes de alto valor.

## <a name="prerequisites"></a>Requisitos previos

- Al menos [permisos de colaborador](permissions.md).

## <a name="task-1---ingest-data"></a>Tarea 1: ingerir datos

Revise los artículos [acerca de la ingestión de datos](data-sources.md) y la [conexión a un origen de datos de Power Query](connect-power-query.md). La siguiente información asume que está familiarizado con la ingesta de datos en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir datos de clientes de una plataforma de comercio electrónico

1. Cree un origen de datos de Power query llamado **Comercio electrónico** y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **CreatedOn**: fecha/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar la fecha de nacimiento a fecha.":::

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de Consulta a **eCommerceContacts**

1. **Guarde** el origen de datos.

### <a name="ingest-online-purchase-data"></a>Ingerir datos de compras en línea

1. Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**. Elija el conector **Texto/CSV** de nuevo.

1. Introduzca la URL para datos de **Compras en línea** https://aka.ms/ciadclassonline.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **PurchasedOn**: fecha/hora
   - **TotalPrice**: moneda

1. En el campo **Nombre** del panel lateral cambie el nombre de su origen de datos de Consulta a **eCommercePurchases**.

1. **Guarde** el origen de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme** y seleccione el conector **Texto/CSV**.

1. Ingrese la URL para clientes leales https://aka.ms/ciadclasscustomerloyalty.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos a **loyCustomers**.

1. **Guarde** el origen de datos.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir datos de clientes de revisiones del sitio web

1. Cree un origen de datos llamado **Website** y seleccione el conector **Texto/CSV**.

1. Escriba la dirección URL para las revisiones del sitio web https://aka.ms/CI-ILT/WebReviews.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **ReviewRating**: Número decimal
   - **ReviewDate**: fecha

1. En el campo **Nombre** del panel derecho, cambie el nombre de su origen de datos de Consulta a **Reseñas**.

1. **Guarde** el origen de datos.

## <a name="task-2---data-unification"></a>Tarea 2: unificación de datos

Revise el artículo [acerca de la unificación de datos](data-unification.md). La siguiente información asume que está familiarizado con la unificación de datos en general.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarea 3: Crear una actividad del historial de transacciones

Revise el artículo [sobre las actividades del cliente](activities.md). La siguiente información asume que está familiarizado con la creación de actividades en general.

1. Crear una actividad llamada **eCommercePurchases** con la entidad *eCommercePurchases:eCommerce* y su clave principal, **PurchaseId**.

1. Crear una relación entre *eCommercePurchases:eCommerce* y *eCommerceContacts:eCommerce* con **ContactID** como clave externa para conectar las dos entidades.

1. Seleccione **TotalPrice** para **EventActivity** y **PurchasedOn** para **TimeStamp**.

1. Seleccione **SalesOrderLine** para **Tipo de actividad** y asigne semánticamente los datos de actividad.

1. Ejecute la actividad.

1. Agregue otra actividad y asigne los nombres de sus campos a los campos correspondientes:
   - **Entidad de actividad**: Reviews:Website
   - **Clave principal**: ReviewId
   - **Marca de tiempo**: ReviewDate
   - **Actividad del evento**: Visualización del tipo de actividad
   - **Detalle adicional** : Calificación de revisión
   - **Tipo de actividad**: Revisión

1. Ejecute la actividad.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tarea 4: configurar el valor de vida útil del cliente predicción

Con los perfiles de cliente unificados en su lugar y la actividad creada, ahora podemos ejecutar la predicción del valor de vida útil del cliente (CLV). Para conocer los pasos detallados, vea [Predicción del valor de vida del cliente](predict-customer-lifetime-value.md).

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Valor de vida útil del cliente**.

1. Seleccione **Comenzar**.

1. Nombre el modelo **OOB eCommerce CLV predicción** y la entidad de salida **OOBeCommerceCLVPrediction**.

1. Definir preferencias de modelo:
   - **Período de tiempo de predicción**: **12 meses o 1 año** para definir durante qué período en el futuro quiere predecir el CLV.
   - **Clientes activos**: **Deje que el modelo calcule el intervalo de compra** que es el período de tiempo en el que un cliente debe haber tenido al menos una transacción para ser considerado activo.
   - **Cliente de alto valor**: defina manualmente los clientes de alto valor como **30% superior de los clientes activos**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Paso de preferencias en la experiencia guiada para el modelo CLV.":::

1. Seleccione **Siguiente**.

1. En el paso **Datos necesarios**, seleccione **Agregar datos** para proporcionar los datos del historial de transacciones.

    :::image type="content" source="media/clv-model-required.png" alt-text="Agregue el paso de datos requerido en la experiencia guiada para el modelo CLV.":::

1. Seleccione **Línea de pedido de ventas** y la entidad eCommercePurchases y seleccione **Siguiente**. Los datos requeridos se rellenan automáticamente desde la actividad. Seleccione **Guardar** y, a continuación, **Siguiente**.

1. El paso **Datos adicionales (opcional)** le permite agregar más datos de actividad del cliente para obtener más información sobre las interacciones del cliente. Para este ejemplo, seleccione **Agregar datos** y agregue la actividad de revisión web.

1. Seleccione **Siguiente**.

1. En el paso **Actualizaciones de datos**, seleccione **Mensual** para el programa modelo.

1. Seleccione **Siguiente**.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarea 5: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Revisar los [resultados y las explicaciones del modelo CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tarea 6: crear un segmento de clientes de alto valor

La ejecución del modelo crea una nueva entidad, que se enumera en **Datos** > **Entidades**. Puede crear un nuevo segmento de clientes basado en la entidad creada por el modelo.

1. En la página de resultados, seleccione **Crear segmento**.

1. Cree una regla mediante la entidad **OOBeCommerceCLVPrediction** y defina el segmento:
   - **Campo**: CLVScore
   - **Operador**: mayor que
   - **Valor**: 1500

1. Seleccione **Guardar** y **ejecute** el segmento.

Ahora tiene un segmento que identifica a los clientes que se prevé que generarán más de 1500 $ de ingresos en los próximos 12 meses. Este segmento se actualiza dinámicamente si se ingieren más datos. Para obtener más información, vea [Crear y administrar segmentos](segments.md).

> [!TIP]
> También puede crear un segmento para un modelo predicción desde la página **Segmentos** seleccionando **Nuevo** y eligiendo **Crear desde** > **Inteligencia**. Para obtener más información, consulte [Crear un nuevo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
