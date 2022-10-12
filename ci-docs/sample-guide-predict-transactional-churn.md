---
title: Guía de ejemplo de predicción de abandono de transacción
description: Utilice esta guía de ejemplo para probar el modelo de predicción de cancelación de transacción de uso inmediato.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609706"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guía de ejemplo de predicción de abandono de transacción

Esta guía le acompañará por un ejemplo completo de predicción de abandono de transacciones utilizando datos de muestra. Le recomendamos que pruebe esta predicción en [un nuevo entorno](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad. Venden los productos a través de su sitio web Contoso Coffee. Su objetivo es saber qué clientes que normalmente compran sus productos de forma regular, dejarán de ser clientes activos en los próximos 60 días. Saber cuál de sus clientes es **probable que cancele**, puede ayudarle a ahorrar esfuerzos de marketing, centrándose en mantenerlos.

## <a name="prerequisites"></a>Requisitos previos

- Al menos [permisos de colaborador](permissions.md).

## <a name="task-1---ingest-data"></a>Tarea 1: ingerir datos

Revise los artículos [acerca de la ingestión de datos](data-sources.md) y la [conexión a un origen de datos de Power Query](connect-power-query.md). La siguiente información asume que está familiarizado con la ingesta de datos en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir datos de clientes de una plataforma de comercio electrónico

1. Cree un origen de datos llamado **eCommerce** y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **DateOfBirth**: fecha
   - **CreatedOn**: fecha/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar DoB en Fecha.":::

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de Consulta a **eCommerceContacts**

1. Guarde el origen de datos.

### <a name="ingest-online-purchase-data"></a>Ingerir datos de compras en línea

1. Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**. Elija el conector **Texto/CSV** de nuevo.

1. Introduzca la URL para datos de compras en línea https://aka.ms/ciadclassonline.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **PurchasedOn**: fecha/hora
   - **TotalPrice**: moneda

1. En el campo **Nombre** del panel de la derecha, cambie el nombre del origen de datos a **eCommercePurchases**.

1. Guarde el origen de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme** y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos a **loyCustomers**.

1. Guarde el origen de datos.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Tarea 4: configurar la predicción de abandono de transacciones

Con los perfiles de clientes unificados en su lugar y la actividad, ahora podemos ejecutar la rotación de transacciones predicción.

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en el **Modelo de abandono de clientes**.

1. Seleccione **Transaccional** para el tipo de abandono y luego **Empezar**.

1. Nombre el modelo como **Predicción de cancelación de transacción de comercio electrónico OOB** y la entidad de salida como **OOBeCommerceChurnPrediction**.

1. Seleccione **Siguiente**.

1. Definir preferencias de modelo:

   - **Ventana de predicción**: **60** días para definir qué tan lejos en el futuro queremos predecir la rotación de clientes.

   - **Definición de abandono**: **60** días para indicar la duración sin compra después de la cual un cliente se considera abandonado.

     :::image type="content" source="media/model-levers.PNG" alt-text="Seleccione las preferencias de modelo Ventana de predicción y Definición de abandono.":::

1. Seleccione **Siguiente**.

1. Seleccione **Historial de compras (obligatorio)** y seleccione **Agregar datos** para el historial de compras.

1. Seleccione **Línea de pedido de ventas** y la entidad eCommercePurchases y seleccione **Siguiente**. Los datos requeridos se rellenan automáticamente desde la actividad. Seleccione **Guardar** y, a continuación, **Siguiente**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Únase a entidades de comercio electrónico.":::

1. Omita el paso **Datos adicionales (opcional)**.

1. En el paso **Actualizaciones de datos**, seleccione **Mensual** para el programa modelo.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarea 5: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Revise las explicaciones del modelo de abandono. Para más información, consulte [Ver los resultados de la predicción](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarea 6: crear un segmento de clientes con alto riesgo de abandono

La ejecución del modelo de producción crea una nueva entidad, que se enumera en **Datos** > **Entidades**. Puede crear un nuevo segmento basado en la entidad creada por el modelo.

1. En la página de resultados, seleccione **Crear segmento**.

1. Cree una regla mediante la entidad **OOBeCommerceChurnPrediction** y defina el segmento:
   - **Campo**: ChurnScore
   - **Operador**: mayor que
   - **Valor**: 0.6

1. Seleccione **Guardar** y **ejecute** el segmento.

Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes con alto riesgo de abandono. Para obtener más información, vea [Crear y administrar segmentos](segments.md).

> [!TIP]
> También puede crear un segmento para un modelo predicción desde la página **Segmentos** seleccionando **Nuevo** y eligiendo **Crear desde** > **Inteligencia**. Para obtener más información, consulte [Crear un nuevo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
