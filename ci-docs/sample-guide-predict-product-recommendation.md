---
title: Guía de ejemplo de predicción de recomendaciones de producto
description: Utilice esta guía de ejemplo para probar el modelo de predicción de recomendaciones de producto predefinida.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762707"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guía de ejemplo de predicción de recomendaciones de producto

Le explicaremos un ejemplo completo de predicción de recomendaciones de producto utilizando los datos de muestra que se proporcionan a continuación.

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad, que venden a través de su sitio web Contoso Coffee. Su objetivo es comprender qué productos deben recomendar a sus clientes recurrentes. Saber qué clientes son más **proclives a comprar**, puede ayudarles a ahorrar esfuerzos de marketing al centrarse en elementos específicos.

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Le recomendamos que implemente los siguientes pasos [en un nuevo entorno](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarea 1: ingerir datos

Revise los artículos [acerca de la ingestión de datos](data-sources.md) y la [importación de orígenes de datos usando conectores de Power Query](connect-power-query.md) específicamente. La siguiente información asume que está familiarizado con la ingesta de datos en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir datos de clientes de una plataforma de comercio electrónico

1. Cree un origen de datos llamado **Comercio electrónico**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **CreatedOn**: fecha/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar la fecha de nacimiento a fecha.":::

1. En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**

1. **Guarde** el origen de datos.

### <a name="ingest-online-purchase-data"></a>Ingerir datos de compras en línea

1. Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**. Elija el conector **Texto/CSV** de nuevo.

1. Introduzca la URL para datos de **Compras en línea** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **PurchasedOn**: fecha/hora
   - **TotalPrice**: moneda

1. En el campo **Nombre** del panel lateral cambie el nombre de su origen de datos de **Consulta** a **eCommercePurchases**.

1. **Guarde** el origen de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.

1. **Guarde** el origen de datos.

## <a name="task-2---data-unification"></a>Tarea 2: unificación de datos

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarea 3: Configurar la predicción de recomendaciones de producto

Con los perfiles de clientes unificados en su lugar, ahora podemos ejecutar la predicción de recomendación de productos.

1. Vaya a **Inteligencia** > **Predicción** y elija **Recomendación de producto**.

1. Seleccione **Comenzar**.

1. Asigne al modelo el nombre **OOB Product Recommendation Model Prediction** y a la entidad de salida **OOBProductRecommendationModelPrediction**.

1. Defina tres condiciones para el modelo:

   - **Número de productos**: establezca este valor en **5**. Esta configuración define cuántos productos desea recomendar a sus clientes.

   - **Se espera que se repitan las compras**: seleccione **sí** para indicar que desea incluir productos en la recomendación que sus clientes hayan comprado anteriormente.

   - **Ventana para mirar atrás**: seleccione al menos **365 días**. Este valor define el período hacia el pasado de la actividad del cliente que va a contemplar el modelo para usarlo como entrada para sus recomendaciones.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias del modelo para el modelo de recomendación de producto.":::

1. En el paso **Añadir datos requeridos**, seleccione **Agregar datos**.

1. En el panel **Agregar datos**, elija **SalesOrderLine** como la entidad del historial de compras. En este punto, es probable que aún no esté configurado. Abra el enlace en el panel para crear la actividad con los siguientes pasos:
   1. Introduzca un **Nombre de actividad** y elija *eCommercePurchases:eCommerce* como **Entidad de actividad**. La columna **Clave principal** es *PurchaseId*.
   1. Defina y nombre la relación con *eCommerceContacts:eCommerce entity* y elija **ContactId** como clave foránea.
   1. Para la unificación de actividades, establezca **Actividad del evento** como *TotalPrice* y marca de tiempo para *PurchasedOn*. Puede especificar más campos como se describe en [Actividades del cliente](activities.md).
   1. Para **Tipo de actividad**, escoja *SalesOrderLine*. Asigne los siguientes campos de actividad:
      - Id. de línea de pedido: PurchaseId
      - Id. de pedido: PurchaseId
      - Datos de pedido: PurchasedOn
      - Id. de producto: ProductId
      - Importe: TotalPrice
   1. Revise y finalice la actividad antes de volver a la configuración del modelo.

1. De regreso en el paso **Seleccionar actividades**, elija la actividad recién creada en la sección **Actividades**. Seleccione **Siguiente** y la asignación de atributos ya está completa. Seleccione **Guardar**.

1. En esta guía de muestra, omitimos **Agregar información del producto** y **Filtros de productos** porque no tenemos datos de información del producto.

1. En el paso **Actualizaciones de datos**, establezca el programa modelo.

   El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se ingieren nuevos datos. En este ejemplo, seleccione **Mensualmente**.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**. Llevará unos minutos ejecutar el modelo por primera vez.

## <a name="task-4---review-model-results-and-explanations"></a>Tarea 4: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Ahora puede revisar las explicaciones del modelo de recomendación de productos. Para más información, consulte [Revisar un estado de predicción y los resultados](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarea 5: Crear un segmento de productos muy comprados

La ejecución del modelo de producción crea una nueva entidad que puede ver en **Datos** > **Entidades**.

Puede crear un nuevo segmento basado en la entidad creada por el modelo.

1. Vaya a **Segmentos**. Seleccione **Nuevo** y elija **Crear desde inteligencia**.

   ![Creación de un segmento con la salida del modelo.](media/segment-intelligence.png)

1. Seleccione el punto de conexión **OOBProductRecommendationModelPrediction** y defina el segmento:

   - Campo: ProductID
   - Valor: seleccione los tres identificadores de producto principales

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cree un segmento a partir de los resultados del modelo.":::

Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes que podrían estar interesados en comprar los tres productos más recomendados.

Para obtener más información, vea [Crear y administrar segmentos](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
