---
title: Guía de ejemplo de predicción de abandono de suscripción
description: Utilice esta guía de muestra para probar el modelo de predicción de cancelación de suscripción de uso inmediato.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741432"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guía de ejemplo de predicción de abandono de suscripción

Le explicaremos un ejemplo completo de predicción de cancelación de suscripción utilizando los datos de muestra que se proporcionan a continuación. 

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad, que venden a través de su sitio web Contoso Coffee. Recientemente, comenzaron un negocio de suscripción para que sus clientes obtengan café de forma regular. Su objetivo es conocer qué clientes suscritos podrían cancelar su suscripción en los próximos meses. Saber cuál de sus clientes es **probable que cancele**, puede ayudarle a ahorrar esfuerzos de marketing, centrándose en mantenerlos.

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

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**

1. Guarde el origen de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.

1. Guarde el origen de datos.

### <a name="ingest-subscription-information"></a>Ingerir información de suscripción

1. Cree un origen de datos llamado **SubscriptionHistory**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadchurnsubscriptionhistory.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **SubscriptioID**: número entero
   - **SubscriptionAmount** : moneda
   - **SubscriptionEndDate**: Fecha/hora
   - **SubscriptionStartDate**: fecha/hora
   - **TransactionDate** : fecha/hora
   - **IsRecurring**: verdadero/falso
   - **Is_auto_renew**: verdadero/falso
   - **RecurringFrequencyInMonths**: número entero

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **SubscriptionHistory**.

1. Guarde el origen de datos.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir datos de clientes de revisiones del sitio web

1. Cree un origen de datos llamado **Sitio web**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasswebsite.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **ReviewRating**: número entero
   - **ReviewDate**: fecha

1. En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **webReviews**.

## <a name="task-2---data-unification"></a>Tarea 2: unificación de datos

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tarea 3: configurar la predicción de abandono de suscripciones

Con los perfiles de clientes unificados en su lugar, ahora podemos ejecutar la predicción de cancelación de suscripción. Para conocer los pasos detallados, consulte el artículo [Predicción de abandono de suscripciones](predict-subscription-churn.md). 

1. Vaya a **Inteligencia** > **Descubrir** y seleccione usar el **Modelo de abandono de clientes**.

1. Seleccione la opción **Suscripción** y elija **Comenzar**.

1. Nombre el modelo como **Predicción de cancelación de suscripción OOB** y la entidad de salida como **OOBSubscriptionChurnPrediction**.

1. Defina dos condiciones para el modelo de abandono:

   * **Días desde que finalizó la suscripción**: **al menos 60** días. Si un cliente no renueva la suscripción durante este tiempo después de que finalizada su suscripción, se considerará que ha abandonado. 

   * **Definición de abandono**: **al menos 93** días. La duración del modelo predice qué clientes podrían abandonar. Cuanto más lejos mire en el futuro, menos precisos serán los resultados.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleccione las palancas de modelo Ventana de predicción y Definición de abandono.":::

1. Seleccione **Agregar datos requeridos** y seleccione **Agregar datos** para el historial de suscripciones.

1. Añada la entidad **Subscription : SubscriptionHistory** y asigne los campos de comercio electrónico a los campos correspondientes requeridos por el modelo.

1. Únase a la entidad **Subscription : SubscriptionHistory** con **eCommerceContacts : eCommerce**, y nombre la relación como **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Únase a entidades de comercio electrónico.":::

1. En Actividades del cliente, agregue la entidad **webReviews : Website** y asigne los campos de webReviews a los campos correspondientes requeridos por el modelo. 
   - Clave principal: ReviewId
   - Marca de tiempo: ReviewDate
   - Evento: ReviewRating

1. Configure una actividad para revisiones de sitios web. Seleccione la actividad **Revisión** y únase a la entidad **webReviews : Website** con **eCommerceContacts : eCommerce**.

1. Seleccione **Siguiente** para establecer la programación del modelo.

   El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se ingieren nuevos datos. En este ejemplo, seleccione **Mensualmente**.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarea 4: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Ahora puede revisar las explicaciones del modelo de cancelación de suscripción. Para más información, consulte [Revisar un estado de predicción y los resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarea 5: crear un segmento de clientes con alto riesgo de abandono

La ejecución del modelo de producción crea una nueva entidad que puede ver en **Datos** > **Entidades**.   

Puede crear un nuevo segmento basado en la entidad creada por el modelo.

1.  Vaya a **Segmentos**. Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación de un segmento con la salida del modelo.":::

1. Seleccione el punto de conexión **OOBSubscriptionChurnPrediction** y defina el segmento: 
   - Campo: ChurnScore
   - Operador: mayor que
   - Valor: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configure el segmento de cancelación de suscripción.":::

Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes con alto riesgo de abandono para este negocio de suscripción.

Para obtener más información, vea [Crear y administrar segmentos](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]