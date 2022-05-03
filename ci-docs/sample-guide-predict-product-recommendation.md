---
title: Guía de ejemplo de predicción de recomendaciones de producto
description: Utilice esta guía de ejemplo para probar el modelo de predicción de recomendaciones de producto predefinida.
ms.date: 02/10/2021
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
ms.openlocfilehash: 1115bab13bdca4a308a8d9eb5a1dc270801d16be
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647828"
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

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **CreatedOn**: fecha/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar la fecha de nacimiento a fecha.":::

5. En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**

6. **Guarde** el origen de datos.

### <a name="ingest-online-purchase-data"></a>Ingerir datos de compras en línea

1. Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**. Elija el conector **Texto/CSV** de nuevo.

1. Introduzca la URL para datos de **Compras en línea** https://aka.ms/ciadclassonline.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **PurchasedOn**: fecha/hora
   - **TotalPrice**: moneda

1. En el campo **Nombre** del panel lateral cambie el nombre de su origen de datos de **Consulta** a **eCommercePurchases**.

1. **Guarde** el origen de datos.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.

1. **Guarde** el origen de datos.

## <a name="task-2---data-unification"></a>Tarea 2: unificación de datos

Después de ingerir los datos, ahora comenzamos el proceso de unificación de datos para crear un perfil de cliente unificado. Para obtener más información, consulte [Unificación de datos](data-unification.md).

### <a name="map"></a>Asignar

1. Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes. Vaya a **Datos** > **Unificar** > **Mapa**.

2. Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**.

   ![unificar las fuentes de datos de comercio electrónico y fidelización.](media/unify-ecommerce-loyalty.png)

3. Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.

   ![Unifique LoyaltyId como clave principal.](media/unify-loyaltyid.png)

### <a name="match"></a>Coincidir

1. Vaya a la pestaña **Coincidir** y seleccione **Establecer orden**.

2. En la lista desplegable **Principal**, seleccione **eCommerceContacts: eCommerce** como el origen principal en incluya todos los registros.

3. En la lista desplegable **Entidad 2**, seleccione **loyCustomers: LoyaltyScheme** e incluya todos los registros.

   ![Unifique la coincidencia de comercio electrónico y fidelización.](media/unify-match-order.png)

4. Seleccione **Crear nueva regla**

5. Agregue su primera condición con FullName.

   - Para eCommerceContacts, seleccione **FullName** en el menú desplegable.
   - Para loyCustomers, seleccione **FullName** en el menú desplegable.
   - Seleccione el desplegable **Normalizar** y elija **Tipo (teléfono, nombre, dirección...)**.
   - Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.

6. Introduzca el nombre **FullName, Email** para la nueva regla.

   - Agregar una segunda condición para la dirección de correo electrónico seleccionando **Agregar condición**
   - Para la entidad eCommerceContacts, elija **Correo electrónico** en el menú desplegable.
   - Para la entidad loyCustomers, elija **Correo electrónico** en el menú desplegable.
   - Deje Normalizar en blanco.
   - Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.

   ![Unifique la regla de coincidencia para el nombre y el correo electrónico.](media/unify-match-rule.png)

7. Seleccione **Guardar** y **Ejecutar**.

### <a name="merge"></a>Fusionar mediante combinación

1. Vaya a la pestaña **Fusionar**.

1. En **ContactId** de la entidad **loyCustomers**, cambie el nombre para mostrar a **ContactIdLOYALTY** para diferenciarlo de los otros id. ingeridos.

   ![cambie el nombre de contactid a partir del id. de fidelidad.](media/unify-merge-contactid.png)

1. Seleccione **Guardar** y **Ejecutar** para iniciar el proceso de fusión.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarea 3: Configurar la predicción de recomendaciones de producto

Con los perfiles de clientes unificados en su lugar, ahora podemos ejecutar la predicción de cancelación de suscripción.

1. Vaya a **Inteligencia** > **Predicción** y elija **Recomendación de producto**.

1. Seleccione **Comenzar**.

1. Asigne al modelo el nombre **OOB Product Recommendation Model Prediction** y a la entidad de salida **OOBProductRecommendationModelPrediction**.

1. Defina tres condiciones para el modelo:

   - **Número de productos**: establezca este valor en **5**. Esta configuración define cuántos productos desea recomendar a sus clientes.

   - **Se espera que se repitan las compras**: seleccione **sí** para indicar que desea incluir productos en la recomendación que sus clientes hayan comprado anteriormente.

   - **Ventana para mirar atrás**: seleccione al menos **365 días**. Este valor define el período hacia el pasado de la actividad del cliente que va a contemplar el modelo para usarlo como entrada para sus recomendaciones.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias del modelo para el modelo de recomendación de producto.":::

1. Seleccione **Datos requeridos** y seleccione **Agregar datos** para el historial de compras.

1. Añada la entidad **eCommercePurchases : eCommerce** y asigne los campos de comercio electrónico a los campos correspondientes requeridos por el modelo.

1. Únase a la entidad **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.

   ![Únase a entidades de comercio electrónico.](media/model-purchase-join.png)

1. Seleccione **Siguiente** para establecer la programación del modelo.

   El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se ingieren nuevos datos. En este ejemplo, seleccione **Mensualmente**.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.


## <a name="task-4---review-model-results-and-explanations"></a>Tarea 4: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Ahora puede revisar las explicaciones del modelo de recomendación de productos. Para más información, consulte [Revisar un estado de predicción y los resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarea 5: Crear un segmento de productos muy comprados

La ejecución del modelo de producción crea una nueva entidad que puede ver en **Datos** > **Entidades**.

Puede crear un nuevo segmento basado en la entidad creada por el modelo.

1. Vaya a **Segmentos**. Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**.

   ![Creación de un segmento con la salida del modelo.](media/segment-intelligence.png)

1. Seleccione el punto de conexión **OOBProductRecommendationModelPrediction** y defina el segmento:

   - Campo: ProductID
   - Operador: Valor
   - Valor: seleccione los tres identificadores de producto principales

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cree un segmento a partir de los resultados del modelo.":::

Ahora tiene un segmento que se actualiza dinámicamente, que identifica a los clientes que están más dispuestos a comprar los tres productos más recomendados. 

Para obtener más información, vea [Crear y administrar segmentos](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
