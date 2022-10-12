---
title: Guía de ejemplo de predicción de recomendaciones de producto
description: Utilice esta guía de ejemplo para probar el modelo de predicción de recomendaciones de producto predefinida.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610165"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guía de ejemplo de predicción de recomendaciones de producto

Esta guía le guía por un ejemplo completo de predicción de recomendaciones de producto utilizando datos de muestra. Le recomendamos que pruebe esta predicción en [un nuevo entorno](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad. Venden los productos a través de su sitio web Contoso Coffee. Su objetivo es comprender qué productos deben recomendar a sus clientes recurrentes. Saber qué clientes son más **proclives a comprar** puede ayudarles a ahorrar esfuerzos de marketing al centrarse en elementos específicos.

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.

## <a name="task-1---ingest-data"></a>Tarea 1: ingerir datos

Revise los artículos [acerca de la ingestión de datos](data-sources.md) y la [conexión a un origen de datos de Power Query](connect-power-query.md). La siguiente información asume que está familiarizado con la ingesta de datos en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir datos de clientes de una plataforma de comercio electrónico

1. Cree un origen de datos de Power query llamado **Comercio electrónico** y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico: https://aka.ms/ciadclasscontacts.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **CreatedOn**: fecha/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar la fecha de nacimiento a fecha.":::

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de Consulta a **eCommerceContacts**.

1. **Guarde** el origen de datos.

### <a name="ingest-online-purchase-data"></a>Ingerir datos de compras en línea

1. Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**. Elija el conector **Texto/CSV** de nuevo.

1. Introduzca la URL para datos de compras en línea https://aka.ms/ciadclassonline.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Tarea 4: Configurar la predicción de recomendaciones de producto

Con los perfiles de clientes unificados en su lugar y la actividad creada, ejecute la predicción de recomendación de productos.

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Recomendaciones de producto (versión preliminar)**.

1. Seleccione **Comenzar**.

1. Asigne al modelo el nombre **OOB Product Recommendation Model Prediction** y a la entidad de salida **OOBProductRecommendationModelPrediction**.

1. Seleccione **Siguiente**.

1. Definir preferencias de modelo:
   - **Número de productos**: **5** para definir cuántos productos desea recomendar a sus clientes.
   - **Se esperan compras repetidas**: **Sí** para incluir productos comprados previamente en la recomendación.
   - **Mirar ventana trasera:** **365 dias** para definir hasta dónde mirará hacia atrás el modelo antes de volver a recomendar un producto.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias del modelo para el modelo de recomendación de producto.":::

1. Seleccione **Siguiente**.

1. En el paso **Añadir historial de compras**, seleccione **Agregar datos**.

1. Seleccione **Línea de pedido de ventas** y la entidad eCommercePurchases y seleccione **Siguiente**. Los datos requeridos se rellenan automáticamente desde la actividad. Seleccione **Guardar** y, a continuación, **Siguiente**.

1. Omita los pasos **Agregar información del producto** y **Filtros de productos** porque no tenemos datos de información del producto.

1. En el paso **Actualizaciones de datos**, seleccione **Mensual** para el programa modelo.

1. Seleccione **Siguiente**.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarea 5: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Revise las [explicaciones del modelo de recomendación de productos](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tarea 6: Crear un segmento de productos muy comprados

La ejecución del modelo crea una nueva entidad, que se enumera en **Datos** > **Entidades**. Puede crear un nuevo segmento basado en la entidad creada por el modelo.

1. En la página de resultados, seleccione **Crear segmento**.

1. Cree una regla mediante la entidad **OOBProductRecommendationModelPrediction** y defina el segmento:
   - **Campo**: ProductID
   - **Valor**: seleccione los tres identificadores de producto principales

1. Seleccione **Guardar** y **ejecute** el segmento.

Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes que podrían estar interesados en comprar los cinco productos más recomendados. Para obtener más información, vea [Crear y administrar segmentos](segments.md).

> [!TIP]
> También puede crear un segmento para un modelo predicción desde la página **Segmentos** seleccionando **Nuevo** y eligiendo **Crear desde** > **Inteligencia**. Para obtener más información, consulte [Crear un nuevo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
