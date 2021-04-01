---
title: Exportar datos de Customer Insights a Adobe Experience Platform
description: Descubra cómo utilizar los segmentos de información de público en Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596290"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="ab324-103">Usar los segmentos de Customer Insights en Adobe Experience Platform (vista previa)</span><span class="sxs-lookup"><span data-stu-id="ab324-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="ab324-104">Como usuario de información de público para Dynamics 365 Customer Insights, es posible que haya creado segmentos para hacer que sus campañas de marketing sean más eficientes al dirigirse a públicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="ab324-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="ab324-105">Para utilizar un segmento de información de público en Adobe Experience Platform y aplicaciones como Adobe Campaign Standard, debe seguir los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ab324-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso de los pasos descritos en este artículo.":::

## <a name="prerequisites"></a><span data-ttu-id="ab324-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ab324-107">Prerequisites</span></span>

-   <span data-ttu-id="ab324-108">Licencia de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ab324-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="ab324-109">Licencia de Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="ab324-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="ab324-110">Licencia de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="ab324-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="ab324-111">Cuenta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="ab324-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="ab324-112">Información general de la campaña</span><span class="sxs-lookup"><span data-stu-id="ab324-112">Campaign Overview</span></span>

<span data-ttu-id="ab324-113">Para comprender mejor cómo puede usar segmentos de información de público en Adobe Experience Platform, veamos una campaña de muestra ficticia.</span><span class="sxs-lookup"><span data-stu-id="ab324-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="ab324-114">Supongamos que su empresa ofrece un servicio mensual por suscripción a sus clientes en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="ab324-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="ab324-115">Desea identificar a los clientes cuyas suscripciones deben renovarse en los próximos ocho días pero que aún no han renovado su suscripción.</span><span class="sxs-lookup"><span data-stu-id="ab324-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="ab324-116">Para conservar a estos clientes, desea enviarles una oferta promocional por correo electrónico, utilizando Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="ab324-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="ab324-117">En este ejemplo, queremos ejecutar la campaña de correo electrónico promocional una vez.</span><span class="sxs-lookup"><span data-stu-id="ab324-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="ab324-118">Este artículo no cubre el caso de uso de ejecutar la campaña más de una vez.</span><span class="sxs-lookup"><span data-stu-id="ab324-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="ab324-119">Identifique su público objetivo</span><span class="sxs-lookup"><span data-stu-id="ab324-119">Identify your target audience</span></span>

<span data-ttu-id="ab324-120">En nuestro escenario, asumimos que las direcciones de correo electrónico de los clientes están disponibles en información de público y sus preferencias promocionales fueron analizadas para identificar a los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="ab324-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="ab324-121">El [segmento que definió en información de público](segments.md) se llama **ChurnProneCustomers** y planea enviar a estos clientes la promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ab324-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la página de segmentos con el segmento ChurnProneCustomers creado.":::

<span data-ttu-id="ab324-123">El correo electrónico de oferta que desea enviar contendrá el nombre de pila, apellido y la fecha de finalización de la suscripción del cliente.</span><span class="sxs-lookup"><span data-stu-id="ab324-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="ab324-124">Informa a los clientes sobre el descuento que obtendrán si renuevan su suscripción antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="ab324-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="ab324-125">Exporte su público objetivo</span><span class="sxs-lookup"><span data-stu-id="ab324-125">Export your target audience</span></span>

<span data-ttu-id="ab324-126">Con nuestro público objetivo identificado, podemos configurar la exportación desde información de público a una cuenta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="ab324-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="ab324-127">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="ab324-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ab324-128">En el mosaico **Azure Blob Storage**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="ab324-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuración para Azure Blob Storage.":::

1. <span data-ttu-id="ab324-130">Proporcione un **Nombre para mostrar** para este nuevo destino de exportación y luego introduzca el **Nombre de la cuenta**, **Clave de cuenta** y **Contenedor** de la cuenta de Azure Blob Storage a la que desea exportar el segmento.</span><span class="sxs-lookup"><span data-stu-id="ab324-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuración de cuenta de almacenamiento. "::: 

   - <span data-ttu-id="ab324-132">Para obtener más información sobre cómo encontrar el nombre y la clave de cuenta de almacenamiento de blobs de Azure, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="ab324-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="ab324-133">Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="ab324-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="ab324-134">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ab324-134">Select **Next**.</span></span>

1. <span data-ttu-id="ab324-135">Elija el segmento que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="ab324-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="ab324-136">En este ejemplo, es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ab324-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfaz de usuario de selección de segmento con el segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="ab324-138">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ab324-138">Select **Save**.</span></span>

<span data-ttu-id="ab324-139">Después de guardar el destino de exportación, lo encontrará en **Administración** > **Exportaciones** > **Mis destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="ab324-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de pantalla con lista de exportaciones y segmento de muestra resaltado.":::

<span data-ttu-id="ab324-141">Ahora puede [exportar el segmento bajo demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ab324-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="ab324-142">La exportación también se ejecutará con cada [actualización programada](system.md).</span><span class="sxs-lookup"><span data-stu-id="ab324-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ab324-143">Asegúrese de que la cantidad de registros en el segmento exportado esté dentro del límite permitido de su licencia de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="ab324-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="ab324-144">Los datos exportados se almacenan en el contenedor de almacenamiento de Azure Blob que configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ab324-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="ab324-145">La siguiente ruta de carpeta se crea automáticamente en su contenedor:</span><span class="sxs-lookup"><span data-stu-id="ab324-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="ab324-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="ab324-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="ab324-147">Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="ab324-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="ab324-148">El *model.json* para las entidades exportadas reside en el nivel *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="ab324-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="ab324-149">Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="ab324-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="ab324-150">Definir el modelo de datos de experiencia (XDM) en Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="ab324-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="ab324-151">Antes de que los datos exportados de información de público se puedan utilizar en Adobe Experience Platform, debemos definir el esquema de Experience Data Model y [configurar los datos para el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="ab324-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="ab324-152">Más información sobre [qué es XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) y entender los [conceptos básicos de la composición del esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="ab324-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="ab324-153">Importar datos a Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="ab324-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="ab324-154">Ahora que todo está en su lugar, debemos importar los datos preparados de audiencia de la información de audiencia en Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="ab324-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="ab324-155">Primero, [cree una conexión de origen de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="ab324-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="ab324-156">Tras definir la conexión de origen, [configure un flujo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para una conexión por lotes de almacenamiento en la nube para importar la salida del segmento de información de público en Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="ab324-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="ab324-157">Crear un público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="ab324-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="ab324-158">Para enviar el correo electrónico de esta campaña, usaremos Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="ab324-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="ab324-159">Tras importar los datos a Adobe Experience Platform, necesitamos [crear un público](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaign Standard utilizando los datos en Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="ab324-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="ab324-160">Aprenda a [usar el constructor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) en Adobe Campaign Standard para definir un público basado en los datos de Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="ab324-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="ab324-161">Crear y enviar el correo electrónico con Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="ab324-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="ab324-162">Cree el contenido del correo electrónico y luego [pruebe y envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ab324-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ejemplo de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::