---
title: Crear un vínculo entre las conclusiones del público y las conclusiones sobre la interacción
description: Cree un vínculo entre las conclusiones del público y las conclusiones sobre la interacción para permitir el intercambio bidireccional de datos.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fdbc93292291814b2e1a62fee2c5ff796ae14e2
ms.sourcegitcommit: 4e5b7ec50c7612765a9ec2c8673e0cc43b357abb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "7487128"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Crear un vínculo entre las conclusiones del público y las conclusiones sobre la interacción

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La integración entre las conclusiones sobre la interacción y las conclusiones del público vincula los entornos de ambas capacidades y permite que los datos se compartan bidireccionalmente entre ellas.

Use perfiles y segmentos unificados de conclusiones del público para obtener más opciones de análisis en conclusiones sobre la interacción. Exporte eventos que tengan un alto valor comercial a partir de las conclusiones sobre la interacción. Utse estos eventos para agregar datos a perfiles unificados en conclusiones del público.

## <a name="prerequisites"></a>Requisitos previos

- Los perfiles de conclusiones del público se deben almacenar en una cuenta de Azure Data Lake Storage que posea o en un lago de datos almacenado de [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;. 
- Su entorno de conclusiones del público debe tener un entorno de Dataverse asociado. Y si ese entorno también está usando Dataverse para el almacenamiento de datos, asegúrese de marcar la opción **Habilitar el uso compartido de datos** opción en las conclusiones del público. Para más información, consulte [Creary configurar un entorno de pago en las conclusiones del público](../audience-insights/get-started-paid.md).
- Necesita permisos de administrador para los entornos de conclusiones sobre la interacción y conclusiones del público.
- Los entornos vinculados deben estar en la misma región geográfica.

> [!NOTE]
> - Si su suscripción a conclusiones del público es una prueba que usa un lago de datos administrado internamente de conclusiones del público, póngase en contacto con [pirequest@microsoft.com](mailto:pirequest@microsoft.com) para obtener asistencia. 
> - Si su entorno de conclusiones del público usa su propio Azure Data Lake Storage para almacenar datos, debe agregar una entidad de servicio de Azure de conclusiones sobre la interacción a su cuenta de almacenamiento. Para obtener más detalles, vaya a [Conectar con una cuenta de Azure Data Lake Storage con una entidad de servicio de Azure para conclusiones del público](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Crear un vínculo de entorno

Puede crear un vínculo de entorno actualizando la configuración de **Administrador** > **Entorno** en las conclusiones sobre la interacción.

**Para establecer un vínculo activo entre las conclusiones del público y las conclusiones sobre la interacción**

1. En la página **Administrador de entorno**, seleccione la pestaña **Vincular entornos**.

    :::image type="content" source="media/integrate1.png" alt-text="Configure un entorno.":::

1. Seleccione **Configurar entornos** en la esquina superior izquierda o en la parte inferior de la pantalla.

     :::image type="content" source="media/integrate2.png" alt-text="Seleccionar el entorno de conclusiones del público.":::

1. Seleccione un entorno de conclusiones del público y, a continuación, seleccione ***Siguiente** para finalizar. Ahora puede seleccionar funciones opcionales para los entornos vinculados.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Habilitar atributos y segmentos del perfil unificado de conclusiones del público

Después de vincular entornos, ahora puede seleccionar funciones opcionales para los entornos vinculados. Estas funciones permiten atributos y segmentos de perfil unificados a partir de las conclusiones del público para el análisis interactivo de los datos de los clientes.

**Analizar datos web en conclusiones sobre la interacción**

1. En la página **Administrador de entorno**, active **Compartir datos de las conclusiones del público con conclusiones sobre la interacción** y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="media/integrate4.png" alt-text="Seleccionar características.":::

1. Seleccione los atributos de los perfiles unificados que se convertirán en dimensiones en las conclusiones sobre la interacción. (No todos los atributos son dimensiones útiles. Por ejemplo, no es probable que necesite **Nombre de pila** o **Apellido** como atributo para el análisis de los eventos de su sitio web).

    :::image type="content" source="media/integrate5.png" alt-text="Organizar dimensiones.":::

   >[!NOTE]
   > Todos los atributos del perfil de conclusiones del público que representan identificadores (como **Id.** e **Id. alternativo**) se filtran de los atributos disponibles y se convierten en dimensiones de conclusiones sobre la interacción.

1. Cuando haya acabado de seleccionar atributos, seleccione **Siguiente**.
1. Agregue usuarios que puedan ver las dimensiones y segmentos del perfil de conclusiones del público en conclusiones sobre la interacción.

    :::image type="content" source="media/integrate6.png" alt-text="Administrar acceso a datos de cliente.":::

   > [!IMPORTANT]
   > Si no agrega usuarios explícitamente en este paso, los datos se ocultarán a los usuarios en las conclusiones sobre la interacción.
   > Para que los segmentos de conclusiones del público se muestren en conclusiones sobre la interacción, primero debe [ejecutar la combinación y los procesos subsiguientes](../audience-insights/merge-entities.md). Los procesos posteriores son importantes porque generan una tabla única que prepara los segmentos de iconclusiones del público para compartir con las conclusiones sobre la interacción. (Si se programa una actualización del sistema, incluirá automáticamente los procesos posteriores).

1. Revise su selección y, a continuación, seleccione **Finalizar**.

    :::image type="content" source="media/integrate7.png" alt-text="Revisar la configuración de datos del cliente.":::

## <a name="export-refined-events-to-audience-insights"></a>Exportar eventos refinados a conclusiones del público

Después de crear un vínculo entre entornos, puede exportar eventos refinados de conclusiones sobre la interacción a conclusiones del público e ingiéralos como un nuevo origen de datos. 

Para obtener más información, vaya a [Integrar datos web de conclusiones sobre la interacción con conclusiones del público](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
