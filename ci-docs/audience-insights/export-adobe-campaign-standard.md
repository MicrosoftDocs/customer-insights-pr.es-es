---
title: Exportar datos de Customer Insights a Adobe Campaign Standard
description: Descubra cómo utilizar los segmentos de información de público en Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760302"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="0de42-103">Usar los segmentos de Customer Insights en Adobe Campaign Standard (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0de42-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="0de42-104">Como usuario de información de público para Dynamics 365 Customer Insights, es posible que haya creado segmentos para hacer que sus campañas de marketing sean más eficientes al dirigirse a públicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="0de42-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="0de42-105">Para utilizar un segmento de información de público en Adobe Experience Platform y aplicaciones como Adobe Campaign Standard, debe seguir los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="0de42-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso de los pasos descritos en este artículo.":::

## <a name="prerequisites"></a><span data-ttu-id="0de42-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0de42-107">Prerequisites</span></span>

-   <span data-ttu-id="0de42-108">Licencia de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0de42-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="0de42-109">Licencia de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0de42-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="0de42-110">Cuenta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="0de42-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="0de42-111">Información general de la campaña</span><span class="sxs-lookup"><span data-stu-id="0de42-111">Campaign Overview</span></span>

<span data-ttu-id="0de42-112">Para comprender mejor cómo puede usar segmentos de información de público en Adobe Experience Platform, veamos una campaña de muestra ficticia.</span><span class="sxs-lookup"><span data-stu-id="0de42-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="0de42-113">Supongamos que su empresa ofrece un servicio mensual por suscripción a sus clientes en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="0de42-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="0de42-114">Desea identificar a los clientes cuyas suscripciones deben renovarse en los próximos ocho días pero que aún no han renovado su suscripción.</span><span class="sxs-lookup"><span data-stu-id="0de42-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="0de42-115">Para conservar a estos clientes, desea enviarles una oferta promocional por correo electrónico, utilizando Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0de42-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="0de42-116">En este ejemplo, queremos ejecutar la campaña de correo electrónico promocional una vez.</span><span class="sxs-lookup"><span data-stu-id="0de42-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="0de42-117">Este artículo no cubre el caso de uso de ejecutar la campaña más de una vez.</span><span class="sxs-lookup"><span data-stu-id="0de42-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="0de42-118">Sin embargo, la información de público y Adobe Campaign Standard también se pueden configurar para que funcionen en un escenario de campaña recurrente.</span><span class="sxs-lookup"><span data-stu-id="0de42-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="0de42-119">Identifique su público objetivo</span><span class="sxs-lookup"><span data-stu-id="0de42-119">Identify your target audience</span></span>

<span data-ttu-id="0de42-120">En nuestro escenario, asumimos que las direcciones de correo electrónico de los clientes están disponibles en información de público y sus preferencias promocionales fueron analizadas para identificar a los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="0de42-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="0de42-121">El [segmento que definió en información de público](segments.md) se llama **ChurnProneCustomers** y planea enviar a estos clientes la promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0de42-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la página de segmentos con el segmento ChurnProneCustomers creado.":::

<span data-ttu-id="0de42-123">El correo electrónico de oferta que desea enviar contendrá el nombre de pila, apellido y la fecha de finalización de la suscripción del cliente.</span><span class="sxs-lookup"><span data-stu-id="0de42-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="0de42-124">Informa a los clientes sobre el descuento que obtendrán si renuevan su suscripción antes de que finalice.</span><span class="sxs-lookup"><span data-stu-id="0de42-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="0de42-125">Exporte su público objetivo</span><span class="sxs-lookup"><span data-stu-id="0de42-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="0de42-126">Configurar una conexión</span><span class="sxs-lookup"><span data-stu-id="0de42-126">Configure a connection</span></span>

<span data-ttu-id="0de42-127">Con nuestro público objetivo identificado, podemos configurar la exportación desde información de público a una cuenta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="0de42-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="0de42-128">En Audience Insights, vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="0de42-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0de42-129">Seleccione **Agregar conexión** y elija **Adobe Campaign** para configurar la conexión o seleccione **Configurar** en la ventana **Adobe Campaign**.</span><span class="sxs-lookup"><span data-stu-id="0de42-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuración de Adobe Campaign Standard.":::

1. <span data-ttu-id="0de42-131">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="0de42-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0de42-132">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0de42-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0de42-133">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="0de42-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0de42-134">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0de42-134">Choose who can use this connection.</span></span> <span data-ttu-id="0de42-135">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="0de42-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0de42-136">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0de42-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0de42-137">Escriba el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** de la cuenta de Azure Blob Storage a la que desea exportar el segmento.</span><span class="sxs-lookup"><span data-stu-id="0de42-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuración de cuenta de almacenamiento. "::: 

   - <span data-ttu-id="0de42-139">Para obtener más información sobre cómo encontrar el nombre y la clave de cuenta de almacenamiento de blobs de Azure, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="0de42-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="0de42-140">Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="0de42-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="0de42-141">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="0de42-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="0de42-142">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="0de42-142">Configure an export</span></span>

<span data-ttu-id="0de42-143">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="0de42-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0de42-144">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0de42-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0de42-145">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="0de42-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0de42-146">Para crear una nueva exportación, **Agregar exportación**.</span><span class="sxs-lookup"><span data-stu-id="0de42-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="0de42-147">En el campo **Conexión para exportación**, elija una conexión de la sección Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="0de42-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="0de42-148">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="0de42-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0de42-149">Elija el segmento que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="0de42-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="0de42-150">En este ejemplo, es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0de42-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfaz de usuario de selección de segmento con el segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="0de42-152">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0de42-152">Select **Next**.</span></span>

1. <span data-ttu-id="0de42-153">Ahora asignamos los campos **Origen** del segmento de información de público a los nombres de campo **Objetivo** en el esquema de perfil de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0de42-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campo para el conector de Adobe Campaign Standard.":::

   <span data-ttu-id="0de42-155">Si desea agregar más atributos, seleccione **Agregar atributo**.</span><span class="sxs-lookup"><span data-stu-id="0de42-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="0de42-156">El nombre de destino puede ser diferente del nombre del campo de origen, por lo que aún puede asignar la salida del segmento de información de público a Adobe Campaign Standard si los campos no tienen el mismo nombre en los dos sistemas.</span><span class="sxs-lookup"><span data-stu-id="0de42-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0de42-157">La dirección de correo electrónico se utiliza como campo de identidad, pero puede utilizar cualquier otro identificador de su perfil de cliente de información de público para asignar datos a Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0de42-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="0de42-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0de42-158">Select **Save**.</span></span>

<span data-ttu-id="0de42-159">Después de guardar el destino de la exportación, lo encontrará en **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="0de42-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="0de42-160">Ahora puede [exportar el segmento bajo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0de42-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="0de42-161">La exportación también se ejecutará con cada [actualización programada](system.md).</span><span class="sxs-lookup"><span data-stu-id="0de42-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0de42-162">Asegúrese de que la cantidad de registros en el segmento exportado esté dentro del límite permitido de su licencia de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0de42-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="0de42-163">Los datos exportados se almacenan en el contenedor de almacenamiento de Azure Blob que configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0de42-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="0de42-164">La siguiente ruta de carpeta se crea automáticamente en su contenedor:</span><span class="sxs-lookup"><span data-stu-id="0de42-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="0de42-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="0de42-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="0de42-166">Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="0de42-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="0de42-167">Configurar Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0de42-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="0de42-168">Cuando se exporta un segmento de información de público, contiene las columnas que seleccionó al definir el destino de exportación en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="0de42-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="0de42-169">Estos datos se pueden utilizar para [crear perfiles en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="0de42-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="0de42-170">Para utilizar el segmento en Adobe Campaign Standard, necesitamos ampliar el esquema de perfil en Adobe Campaign Standard para incluir dos campos adicionales.</span><span class="sxs-lookup"><span data-stu-id="0de42-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="0de42-171">Aprenda a [extender el recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con nuevos campos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0de42-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="0de42-172">En nuestro ejemplo, estos campos son *Nombre del segmento y Fecha del segmento (opcional).*</span><span class="sxs-lookup"><span data-stu-id="0de42-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="0de42-173">Usaremos estos campos para identificar los perfiles en Adobe Campaign Standard a los que queremos dirigirnos para esta campaña.</span><span class="sxs-lookup"><span data-stu-id="0de42-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="0de42-174">Si no hay otros registros en Adobe Campaign Standard, además de los que va a importar, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="0de42-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="0de42-175">Importar datos a Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0de42-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="0de42-176">Ahora que todo está en su lugar, debemos importar los datos preparados de audiencia de la información de audiencia en Adobe Campaign Standard para crear perfiles.</span><span class="sxs-lookup"><span data-stu-id="0de42-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="0de42-177">Aprenda [cómo importar perfiles en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0de42-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="0de42-178">El flujo de trabajo de importación de la imagen siguiente se ha configurado para ejecutarse cada 8 horas y busca segmentos de información de público exportados (archivo .csv en Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="0de42-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="0de42-179">El flujo de trabajo extrae el contenido del archivo .csv en un orden de columna específico.</span><span class="sxs-lookup"><span data-stu-id="0de42-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="0de42-180">Este flujo de trabajo se ha creado para realizar una gestión básica de errores y garantizar que cada registro tenga una dirección de correo electrónico antes de hidratar los datos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0de42-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="0de42-181">El flujo de trabajo también extrae el nombre del segmento del nombre del archivo antes de insertarlo en los datos del perfil ACS.</span><span class="sxs-lookup"><span data-stu-id="0de42-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla de un flujo de trabajo de importación en la interfaz de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="0de42-183">Recupere el público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0de42-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="0de42-184">Una vez que los datos se importan a Adobe Campaign Standard, [puede crear un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) y [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) los clientes basados en el *Nombre del segmento* y *Fecha de segmento* para seleccionar los perfiles que fueron identificados para nuestra campaña de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0de42-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="0de42-185">Crear y enviar el correo electrónico con Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0de42-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="0de42-186">Cree el contenido del correo electrónico y luego [pruebe y envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0de42-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ejemplo de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
