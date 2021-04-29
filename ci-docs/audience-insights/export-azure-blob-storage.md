---
title: Exportar datos de Customer Insights a Azure Blob Storage
description: Aprenda a configurar la conexión y a exportar a Blob Storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760256"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="08317-103">Exportar la lista de segmentos y otros datos a Azure Blob Storage (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="08317-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="08317-104">Almacene los datos de Customer Insights en Blob Storage o utilícelo para transferir los datos a otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="08317-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="08317-105">Configurar la conexión a Blob Storage</span><span class="sxs-lookup"><span data-stu-id="08317-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="08317-106">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="08317-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="08317-107">Seleccione **Agregar conexión** y elija **Azure Blob Storage** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="08317-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="08317-108">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="08317-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="08317-109">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="08317-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="08317-110">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="08317-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="08317-111">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="08317-111">Choose who can use this connection.</span></span> <span data-ttu-id="08317-112">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="08317-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="08317-113">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="08317-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="08317-114">Escriba el **Nombre de la cuenta**, la **Clave de la cuenta** y el **Contenedor** para su cuenta de Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="08317-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="08317-115">Para obtener más información sobre cómo encontrar el nombre y la clave de la cuenta de Blob Storage, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="08317-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="08317-116">Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="08317-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="08317-117">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="08317-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="08317-118">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="08317-118">Configure an export</span></span>

<span data-ttu-id="08317-119">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="08317-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="08317-120">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="08317-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="08317-121">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="08317-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08317-122">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="08317-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="08317-123">En el campo **Conexión para exportación**, elija una conexión de la sección Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="08317-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="08317-124">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="08317-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="08317-125">Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.</span><span class="sxs-lookup"><span data-stu-id="08317-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="08317-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="08317-126">Select **Save**.</span></span>

<span data-ttu-id="08317-127">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="08317-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="08317-128">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08317-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="08317-129">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="08317-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="08317-130">Los datos exportados se almacenan en el contenedor de Blob Storage que configuró.</span><span class="sxs-lookup"><span data-stu-id="08317-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="08317-131">Las siguientes rutas de acceso a carpetas se crean automáticamente en el contenedor:</span><span class="sxs-lookup"><span data-stu-id="08317-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="08317-132">Para entidades fuente y entidades generadas por el sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="08317-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="08317-133">Ejemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="08317-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="08317-134">El model.json para las entidades exportadas estará en el nivel %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="08317-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="08317-135">Ejemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="08317-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
