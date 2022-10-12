---
title: Guía de ejemplo de predicción de abandono de suscripción
description: Utilice esta guía de muestra para probar el modelo de predicción de cancelación de suscripción de uso inmediato.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610027"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guía de ejemplo de predicción de abandono de suscripción

Esta guía le acompañará por un ejemplo completo de predicción de cancelación de suscripción utilizando datos de muestra. Le recomendamos que pruebe esta predicción en [un nuevo entorno](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad. Venden los productos a través de su sitio web Contoso Coffee. Recientemente, comenzaron un negocio de suscripción para que sus clientes obtengan café de forma regular. Su objetivo es conocer qué clientes suscritos podrían cancelar su suscripción en los próximos meses. Saber cuál de sus clientes es **probable que cancele**, puede ayudarle a ahorrar esfuerzos de marketing, centrándose en mantenerlos.

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.

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

1. Guarde el origen de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme** y seleccione el conector **Texto/CSV**.

1. Ingrese la URL para clientes leales https://aka.ms/ciadclasscustomerloyalty.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos a **loyCustomers**.

1. Guarde el origen de datos.

### <a name="ingest-subscription-information"></a>Ingerir información de suscripción

1. Cree un origen de datos llamado **SubscriptionHistory** y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de las suscripciones https://aka.ms/ciadchurnsubscriptionhistory.

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

1. En el campo **Nombre** del panel derecho, cambie el nombre de su origen de datos a **SubscriptionHistory**.

1. Guarde el origen de datos.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir datos de clientes de revisiones del sitio web

1. Cree un origen de datos llamado **Website** y seleccione el conector **Texto/CSV**.

1. Escriba la dirección URL para las revisiones del sitio web https://aka.ms/ciadclasswebsite.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **ReviewRating**: número entero
   - **ReviewDate**: fecha

1. En el campo **Nombre** del panel derecho, cambie el nombre de su origen de datos a **webReviews**.

## <a name="task-2---data-unification"></a>Tarea 2: unificación de datos

Revise el artículo [acerca de la unificación de datos](data-unification.md). La siguiente información asume que está familiarizado con la unificación de datos en general.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarea 3: Crear una actividad del historial de transacciones

Revise el artículo [sobre las actividades del cliente](activities.md). La siguiente información asume que está familiarizado con la creación de actividades en general.

1. Crear una actividad llamada **SubscriptionHistory** con la entidad *Subscription* y su clave principal, **CustomerId**.

1. Crear una relación entre *SubscriptionHistory:Subscription* y *eCommerceContacts:eCommerce* con **CustomerID** como clave externa para conectar las dos entidades.

1. Seleccione **SubscriptionType** para **EventActivity** y **SubscriptionEndDate** para **TimeStamp**.

1. Seleccione **Subscription** para **Tipo de actividad** y asigne semánticamente los datos de actividad.

1. Ejecute la actividad.

1. Agregue otra actividad y asigne los nombres de sus campos a los campos correspondientes:
   - Entidad de actividad del cliente: Reviews:Website
   - Clave principal: Website.Reviews.ReviewId
   - Marca de tiempo: Website.Reviews.ReviewDate
   - Evento (nombre de la actividad): Website.Reviews.ActivityTypeDisplay
   - Detalles (cantidad o valor): Website.Reviews.ReviewRating

1. Ejecute la actividad.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tarea 4: configurar la predicción de abandono de suscripciones

Con los perfiles de clientes unificados en su lugar y la actividad creada, ejecute la predicción de cancelación de suscripción. Para conocer los pasos detallados, consulte [Predicción de abandono de suscripciones](predict-subscription-churn.md).

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Modelo de abandono de clientes**.

1. Seleccione **Suscripción** para el tipo de abandono y luego **Empezar**.

1. Nombre el modelo como **Predicción de cancelación de suscripción OOB** y la entidad de salida como **OOBSubscriptionChurnPrediction**.

1. Definir preferencias de modelo:
   - **Días desde que finalizó la suscripción**: **60** días para indicar que un cliente se considera cancelado si no renueva la suscripción en este período después de que finalizó su suscripción.
   - **Días para investigar el futuro para predecir la rotación**: **93** días, que es la duración que el modelo predice qué clientes podrían abandonar. Cuanto más lejos mire en el futuro, menos precisos serán los resultados.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleccione las preferencias de modelo y la definición de abandono.":::

1. Seleccione **Siguiente**.

1. En el paso **Datos necesarios**, seleccione **Agregar datos** para proporcionar el historial de suscripciones.

1. Seleccione **Suscripción** y la entidad SubscriptionHistory y seleccione **Siguiente**. Los datos requeridos se rellenan automáticamente desde la actividad. Seleccione **Guardar**.

1. Seleccione **Agregar datos** en Actividades del cliente.

1. Para este ejemplo, agregue la actividad de revisión web.

1. Seleccione **Siguiente**.

1. En el paso **Actualizaciones de datos**, seleccione **Mensual** para el programa modelo.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarea 5: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Revise las explicaciones del modelo de abandono de suscripción. Para más información, consulte [Ver los resultados de la predicción](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarea 6: crear un segmento de clientes con alto riesgo de abandono

La ejecución del modelo crea una nueva entidad, que se enumera en **Datos** > **Entidades**. Puede crear un nuevo segmento basado en la entidad creada por el modelo.

1. En la página de resultados, seleccione **Crear segmento**.

1. Cree una regla mediante la entidad **OOBSubscriptionChurnPrediction** y defina el segmento:
   - **Campo**: ChurnScore
   - **Operador**: mayor que
   - **Valor**: 0.6

1. Seleccione **Guardar** y **ejecute** el segmento.

Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes con alto riesgo de abandono para este negocio de suscripción. Para obtener más información, vea [Crear y administrar segmentos](segments.md).

> [!TIP]
> También puede crear un segmento para un modelo predicción desde la página **Segmentos** seleccionando **Nuevo** y eligiendo **Crear desde** > **Inteligencia**. Para obtener más información, consulte [Crear un nuevo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
