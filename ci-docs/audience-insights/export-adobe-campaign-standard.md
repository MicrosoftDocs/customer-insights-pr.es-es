---
title: Exportar datos de Customer Insights a Adobe Campaign Standard
description: Descubra cómo utilizar los segmentos de información de público en Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596336"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="99de9-103">Usar los segmentos de Customer Insights en Adobe Campaign Standard (vista previa)</span><span class="sxs-lookup"><span data-stu-id="99de9-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="99de9-104">Como usuario de información de público para Dynamics 365 Customer Insights, es posible que haya creado segmentos para hacer que sus campañas de marketing sean más eficientes al dirigirse a públicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="99de9-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="99de9-105">Para utilizar un segmento de información de público en Adobe Experience Platform y aplicaciones como Adobe Campaign Standard, debe seguir los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="99de9-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso de los pasos descritos en este artículo.":::

## <a name="prerequisites"></a><span data-ttu-id="99de9-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="99de9-107">Prerequisites</span></span>

-   <span data-ttu-id="99de9-108">Licencia de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="99de9-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="99de9-109">Licencia de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="99de9-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="99de9-110">Cuenta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="99de9-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="99de9-111">Información general de la campaña</span><span class="sxs-lookup"><span data-stu-id="99de9-111">Campaign Overview</span></span>

<span data-ttu-id="99de9-112">Para comprender mejor cómo puede usar segmentos de información de público en Adobe Experience Platform, veamos una campaña de muestra ficticia.</span><span class="sxs-lookup"><span data-stu-id="99de9-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="99de9-113">Supongamos que su empresa ofrece un servicio mensual por suscripción a sus clientes en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="99de9-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="99de9-114">Desea identificar a los clientes cuyas suscripciones deben renovarse en los próximos ocho días pero que aún no han renovado su suscripción.</span><span class="sxs-lookup"><span data-stu-id="99de9-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="99de9-115">Para conservar a estos clientes, desea enviarles una oferta promocional por correo electrónico, utilizando Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="99de9-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="99de9-116">En este ejemplo, queremos ejecutar la campaña de correo electrónico promocional una vez.</span><span class="sxs-lookup"><span data-stu-id="99de9-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="99de9-117">Este artículo no cubre el caso de uso de ejecutar la campaña más de una vez.</span><span class="sxs-lookup"><span data-stu-id="99de9-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="99de9-118">Sin embargo, la información de público y Adobe Campaign Standard también se pueden configurar para que funcionen en un escenario de campaña recurrente.</span><span class="sxs-lookup"><span data-stu-id="99de9-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="99de9-119">Identifique su público objetivo</span><span class="sxs-lookup"><span data-stu-id="99de9-119">Identify your target audience</span></span>

<span data-ttu-id="99de9-120">En nuestro escenario, asumimos que las direcciones de correo electrónico de los clientes están disponibles en información de público y sus preferencias promocionales fueron analizadas para identificar a los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="99de9-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="99de9-121">El [segmento que definió en información de público](segments.md) se llama **ChurnProneCustomers** y planea enviar a estos clientes la promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="99de9-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la página de segmentos con el segmento ChurnProneCustomers creado.":::

<span data-ttu-id="99de9-123">El correo electrónico de oferta que desea enviar contendrá el nombre de pila, apellido y la fecha de finalización de la suscripción del cliente.</span><span class="sxs-lookup"><span data-stu-id="99de9-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="99de9-124">Informa a los clientes sobre el descuento que obtendrán si renuevan su suscripción antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="99de9-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="99de9-125">Exporte su público objetivo</span><span class="sxs-lookup"><span data-stu-id="99de9-125">Export your target audience</span></span>

<span data-ttu-id="99de9-126">Con nuestro público objetivo identificado, podemos configurar la exportación desde información de público a una cuenta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="99de9-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="99de9-127">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="99de9-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="99de9-128">En el mosaico de **Adobe Campaign**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="99de9-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuración de Adobe Campaign Standard.":::

1. <span data-ttu-id="99de9-130">Proporcione un **Nombre para mostrar** para este nuevo destino de exportación y luego introduzca el **Nombre de la cuenta**, **Clave de cuenta** y **Contenedor** de la cuenta de Azure Blob Storage a la que desea exportar el segmento.</span><span class="sxs-lookup"><span data-stu-id="99de9-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuración de cuenta de almacenamiento. "::: 

   - <span data-ttu-id="99de9-132">Para obtener más información sobre cómo encontrar el nombre y la clave de cuenta de almacenamiento de blobs de Azure, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="99de9-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="99de9-133">Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="99de9-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="99de9-134">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="99de9-134">Select **Next**.</span></span>

1. <span data-ttu-id="99de9-135">Elija el segmento que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="99de9-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="99de9-136">En este ejemplo, es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="99de9-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfaz de usuario de selección de segmento con el segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="99de9-138">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="99de9-138">Select **Next**.</span></span>

1. <span data-ttu-id="99de9-139">Ahora asignamos los campos **Origen** del segmento de información de público a los nombres de campo **Objetivo** en el esquema de perfil de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="99de9-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campo para el conector de Adobe Campaign Standard.":::

   <span data-ttu-id="99de9-141">Si desea agregar más atributos, seleccione **Agregar atributo**.</span><span class="sxs-lookup"><span data-stu-id="99de9-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="99de9-142">El nombre de destino puede ser diferente del nombre del campo de origen, por lo que aún puede asignar la salida del segmento de información de público a Adobe Campaign Standard si los campos no tienen el mismo nombre en los dos sistemas.</span><span class="sxs-lookup"><span data-stu-id="99de9-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="99de9-143">La dirección de correo electrónico se utiliza como campo de identidad, pero puede utilizar cualquier otro identificador de su perfil de cliente de información de público para asignar datos a Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="99de9-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="99de9-144">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="99de9-144">Select **Save**.</span></span>

<span data-ttu-id="99de9-145">Después de guardar el destino de exportación, lo encontrará en **Administración** > **Exportaciones** > **Mis destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="99de9-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captura de pantalla con lista de exportaciones y segmento de muestra resaltado.":::

<span data-ttu-id="99de9-147">Ahora puede [exportar el segmento bajo demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="99de9-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="99de9-148">La exportación también se ejecutará con cada [actualización programada](system.md).</span><span class="sxs-lookup"><span data-stu-id="99de9-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="99de9-149">Asegúrese de que la cantidad de registros en el segmento exportado esté dentro del límite permitido de su licencia de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="99de9-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="99de9-150">Los datos exportados se almacenan en el contenedor de almacenamiento de Azure Blob que configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="99de9-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="99de9-151">La siguiente ruta de carpeta se crea automáticamente en su contenedor:</span><span class="sxs-lookup"><span data-stu-id="99de9-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="99de9-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="99de9-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="99de9-153">Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="99de9-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="99de9-154">Configurar Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="99de9-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="99de9-155">Cuando se exporta un segmento de información de público, contiene las columnas que seleccionó al definir el destino de exportación en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="99de9-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="99de9-156">Estos datos se pueden utilizar para [crear perfiles en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="99de9-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="99de9-157">Para utilizar el segmento en Adobe Campaign Standard, necesitamos ampliar el esquema de perfil en Adobe Campaign Standard para incluir dos campos adicionales.</span><span class="sxs-lookup"><span data-stu-id="99de9-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="99de9-158">Aprenda a [extender el recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con nuevos campos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="99de9-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="99de9-159">En nuestro ejemplo, estos campos son *Nombre del segmento y Fecha del segmento (opcional).*</span><span class="sxs-lookup"><span data-stu-id="99de9-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="99de9-160">Usaremos estos campos para identificar los perfiles en Adobe Campaign Standard a los que queremos dirigirnos para esta campaña.</span><span class="sxs-lookup"><span data-stu-id="99de9-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="99de9-161">Si no hay otros registros en Adobe Campaign Standard, además de los que va a importar, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="99de9-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="99de9-162">Importar datos a Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="99de9-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="99de9-163">Ahora que todo está en su lugar, debemos importar los datos preparados de audiencia de la información de audiencia en Adobe Campaign Standard para crear perfiles.</span><span class="sxs-lookup"><span data-stu-id="99de9-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="99de9-164">Aprenda [cómo importar perfiles en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="99de9-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="99de9-165">El flujo de trabajo de importación de la imagen siguiente se ha configurado para ejecutarse cada 8 horas y busca segmentos de información de público exportados (archivo .csv en Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="99de9-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="99de9-166">El flujo de trabajo extrae el contenido del archivo .csv en un orden de columna específico.</span><span class="sxs-lookup"><span data-stu-id="99de9-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="99de9-167">Este flujo de trabajo se ha creado para realizar una gestión básica de errores y garantizar que cada registro tenga una dirección de correo electrónico antes de hidratar los datos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="99de9-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="99de9-168">El flujo de trabajo también extrae el nombre del segmento del nombre del archivo antes de insertarlo en los datos del perfil ACS.</span><span class="sxs-lookup"><span data-stu-id="99de9-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla de un flujo de trabajo de importación en la interfaz de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="99de9-170">Recupere el público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="99de9-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="99de9-171">Una vez que los datos se importan a Adobe Campaign Standard, [puede crear un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) y [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) los clientes basados en el *Nombre del segmento* y *Fecha de segmento* para seleccionar los perfiles que fueron identificados para nuestra campaña de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="99de9-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="99de9-172">Crear y enviar el correo electrónico con Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="99de9-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="99de9-173">Cree el contenido del correo electrónico y luego [pruebe y envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="99de9-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ejemplo de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::