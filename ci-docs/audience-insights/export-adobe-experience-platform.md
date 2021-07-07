---
title: Exportar datos de Customer Insights a Adobe Experience Platform
description: Aprenda a utilizar los segmentos de Audience Insights en Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305545"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="d7e0c-103">Usar los segmentos de Customer Insights en Adobe Experience Platform (vista previa)</span><span class="sxs-lookup"><span data-stu-id="d7e0c-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="d7e0c-104">Como usuario de Audience Insights en Dynamics 365 Customer Insights, es posible que haya creado segmentos para hacer que sus campañas de marketing sean más eficientes al dirigirse a audiencias relevantes.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="d7e0c-105">Para utilizar un segmento de información de público en Adobe Experience Platform y aplicaciones como Adobe Campaign Standard, debe seguir los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso de los pasos descritos en este artículo.":::

## <a name="prerequisites"></a><span data-ttu-id="d7e0c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d7e0c-107">Prerequisites</span></span>

-   <span data-ttu-id="d7e0c-108">Licencia de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d7e0c-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="d7e0c-109">Licencia de Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="d7e0c-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="d7e0c-110">Licencia de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d7e0c-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="d7e0c-111">Cuenta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="d7e0c-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="d7e0c-112">Información general de la campaña</span><span class="sxs-lookup"><span data-stu-id="d7e0c-112">Campaign Overview</span></span>

<span data-ttu-id="d7e0c-113">Para comprender mejor cómo puede usar segmentos de información de público en Adobe Experience Platform, veamos una campaña de muestra ficticia.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="d7e0c-114">Supongamos que su empresa ofrece un servicio mensual por suscripción a sus clientes en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="d7e0c-115">Desea identificar a los clientes cuyas suscripciones deben renovarse en los próximos ocho días pero que aún no han renovado su suscripción.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="d7e0c-116">Para conservar a estos clientes, desea enviarles una oferta promocional por correo electrónico, utilizando Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="d7e0c-117">En este ejemplo, queremos ejecutar la campaña de correo electrónico promocional una vez.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="d7e0c-118">Este artículo no cubre el caso de uso de ejecutar la campaña más de una vez.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="d7e0c-119">Identifique su público objetivo</span><span class="sxs-lookup"><span data-stu-id="d7e0c-119">Identify your target audience</span></span>

<span data-ttu-id="d7e0c-120">En nuestro escenario, asumimos que las direcciones de correo electrónico de los clientes están disponibles en información de público y sus preferencias promocionales fueron analizadas para identificar a los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="d7e0c-121">El [segmento que definió en información de público](segments.md) se llama **ChurnProneCustomers** y planea enviar a estos clientes la promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la página de segmentos con el segmento ChurnProneCustomers creado.":::

<span data-ttu-id="d7e0c-123">El correo electrónico de oferta que desea enviar contendrá el nombre de pila, apellido y la fecha de finalización de la suscripción del cliente.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="d7e0c-124">Informa a los clientes sobre el descuento que obtendrán si renuevan su suscripción antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="d7e0c-125">Exporte su público objetivo</span><span class="sxs-lookup"><span data-stu-id="d7e0c-125">Export your target audience</span></span>

<span data-ttu-id="d7e0c-126">Con nuestro público objetivo identificado, podemos configurar la exportación desde información de público a una cuenta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="d7e0c-127">Configurar una conexión</span><span class="sxs-lookup"><span data-stu-id="d7e0c-127">Configure a connection</span></span>

1. <span data-ttu-id="d7e0c-128">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d7e0c-129">Seleccione **Agregar conexión** y elija **Azure Blob Storage** para configurar la conexión o seleccione **Configurar** en la ventana **Azure Blob Storage** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuración para Azure Blob Storage."::: 

1. <span data-ttu-id="d7e0c-131">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d7e0c-132">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d7e0c-133">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d7e0c-134">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-134">Choose who can use this connection.</span></span> <span data-ttu-id="d7e0c-135">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d7e0c-136">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d7e0c-137">Escriba el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para la cuenta de Blob Storage a la que desea exportar el segmento.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuración de cuenta de almacenamiento. "::: 
   
    - <span data-ttu-id="d7e0c-139">Para obtener más información sobre cómo encontrar el nombre y la clave de la cuenta de Blob Storage, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="d7e0c-140">Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d7e0c-141">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="d7e0c-142">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="d7e0c-142">Configure an export</span></span>

<span data-ttu-id="d7e0c-143">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d7e0c-144">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d7e0c-145">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d7e0c-146">Para crear una nueva exportación, **Agregar exportación**.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="d7e0c-147">En el campo **Conexión para exportación**, elija una conexión de la sección Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="d7e0c-148">Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="d7e0c-149">Elija el segmento que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="d7e0c-150">En este ejemplo, es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfaz de usuario de selección de segmento con el segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="d7e0c-152">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-152">Select **Save**.</span></span>

<span data-ttu-id="d7e0c-153">Después de guardar el destino de la exportación, lo encontrará en **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="d7e0c-154">Ahora puede [exportar el segmento bajo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="d7e0c-155">La exportación también se ejecutará con cada [actualización programada](system.md).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7e0c-156">Asegúrese de que la cantidad de registros en el segmento exportado esté dentro del límite permitido de su licencia de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="d7e0c-157">Los datos exportados se almacenan en el contenedor Azure Blob Storage que configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="d7e0c-158">La siguiente ruta de carpeta se crea automáticamente en su contenedor:</span><span class="sxs-lookup"><span data-stu-id="d7e0c-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="d7e0c-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="d7e0c-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="d7e0c-160">Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="d7e0c-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="d7e0c-161">El *model.json* para las entidades exportadas reside en el nivel *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="d7e0c-162">Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="d7e0c-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="d7e0c-163">Definir el modelo de datos de experiencia (XDM) en Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="d7e0c-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="d7e0c-164">Antes de que los datos exportados de información de público se puedan utilizar en Adobe Experience Platform, debemos definir el esquema de Experience Data Model y [configurar los datos para el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="d7e0c-165">Más información sobre [qué es XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) y entender los [conceptos básicos de la composición del esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="d7e0c-166">Importar datos a Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="d7e0c-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="d7e0c-167">Ahora que todo está en su lugar, debemos importar los datos preparados de audiencia de la información de audiencia en Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="d7e0c-168">Primero, [cree una conexión de origen de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="d7e0c-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="d7e0c-169">Tras definir la conexión de origen, [configure un flujo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para una conexión por lotes de almacenamiento en la nube para importar la salida del segmento de información de público en Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="d7e0c-170">Crear un público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d7e0c-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="d7e0c-171">Para enviar el correo electrónico de esta campaña, usaremos Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="d7e0c-172">Tras importar los datos a Adobe Experience Platform, necesitamos [crear un público](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaign Standard utilizando los datos en Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="d7e0c-173">Aprenda a [usar el constructor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) en Adobe Campaign Standard para definir un público basado en los datos de Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="d7e0c-174">Crear y enviar el correo electrónico con Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d7e0c-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="d7e0c-175">Cree el contenido del correo electrónico y luego [pruebe y envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d7e0c-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ejemplo de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
