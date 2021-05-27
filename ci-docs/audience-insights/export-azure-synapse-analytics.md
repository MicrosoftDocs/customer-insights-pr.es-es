---
title: Exportar datos de Customer Insights a Azure Synapse Analytics
description: Aprenda a configurar la conexión a Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977398"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="e4ac9-103">Exportar datos a Azure Synapse Analytics (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="e4ac9-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="e4ac9-104">Azure Synapse es un servicio de análisis que acelera el tiempo para obtener conclusiones sobre los almacenamientos de datos y los sistemas de macrodatos.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="e4ac9-105">Puede ingerir y utilizar sus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4ac9-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e4ac9-106">Prerequisites</span></span>

<span data-ttu-id="e4ac9-107">Se deben cumplir los siguientes requisitos previos para configurar la conexión de Customer Insights a Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="e4ac9-108">Asegúrese de configurar todas las **asignaciones de roles** como se describe.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="e4ac9-109">Requisitos previos en Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e4ac9-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="e4ac9-110">Debe tener un rol de **Administrador** en los conocimientos del público.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="e4ac9-111">Aprender más sobre [Establecer permisos de usuario en conocimientos del público](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="e4ac9-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="e4ac9-112">En Azure:</span><span class="sxs-lookup"><span data-stu-id="e4ac9-112">In Azure:</span></span> 

- <span data-ttu-id="e4ac9-113">Una suscripción de Azure activa.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-113">An active Azure subscription.</span></span>

- <span data-ttu-id="e4ac9-114">Si usa una nueva cuenta de Azure Data Lake Storage Gen2, la *entidad de servicio para conocimientos del público* necesita permisos de **Contribuyente de datos de Storage Blob**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="e4ac9-115">Más información sobre [conexión a una cuenta de Azure Data Lake Storage Gen2 con la entidad de servicio de Azure para conclusiones del público](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="e4ac9-116">Data Lake Storage Gen2 **debe** tener activado el [espacio de nombres jerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="e4ac9-117">En el grupo de recursos donde se encuentra el espacio de trabajo de Azure Synapse, la *entidad de servicio* y el *usuario para conclusiones del público* deben tener asignados al menos permisos de **Lector**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="e4ac9-118">Para más información, vea [Asignar roles de Azure mediante el portal de Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="e4ac9-119">El *usuario* necesita permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="e4ac9-120">Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="e4ac9-121">La *[identidad administrada del espacio de trabajo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necesita permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="e4ac9-122">Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="e4ac9-123">En el espacio de trabajo de Azure Synapse, la *entidad de servicio para conclusiones del público* necesita tener asignado el rol **Administrador de Synapse**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="e4ac9-124">Para más información, vea [Cómo configurar el control de acceso para su espacio de trabajo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="e4ac9-125">Configurar la conexión y exportar a Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="e4ac9-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="e4ac9-126">Configurar una conexión</span><span class="sxs-lookup"><span data-stu-id="e4ac9-126">Configure a connection</span></span>

1. <span data-ttu-id="e4ac9-127">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e4ac9-128">Seleccione **Agregar conexión** y elija **Azure Synapse Analytics**, o seleccione **Configurar** en el mosaico **Azure Synapse Analytics** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="e4ac9-129">Asigne a su conexión un nombre reconocible en el campo Nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="e4ac9-130">El nombre y el tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="e4ac9-131">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e4ac9-132">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-132">Choose who can use this connection.</span></span> <span data-ttu-id="e4ac9-133">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e4ac9-134">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e4ac9-135">Seleccione o busque la suscripción en la que desea utilizar los datos de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="e4ac9-136">Tan pronto como se seleccione una suscripción, también puede seleccionar **Espacio de trabajo**, **Cuenta de almacenamiento** y **Contenedor**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="e4ac9-137">Seleccione **Guardar** para guardar la conexión.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="e4ac9-138">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="e4ac9-138">Configure an export</span></span>

<span data-ttu-id="e4ac9-139">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e4ac9-140">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e4ac9-141">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4ac9-142">Para crear una nueva exportación, **Agregar exportación**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e4ac9-143">En el campo **Conexión para exportación**, elija una conexión de la sección **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="e4ac9-144">Si no ve este nombre de sección, es que no hay [conexiones](connections.md) de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="e4ac9-145">Proporcione un **Nombre para mostrar** reconocible para la exportación y un **Nombre de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="e4ac9-146">Seleccione a qué entidades desea exportar Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="e4ac9-147">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-147">Select **Save**.</span></span>

<span data-ttu-id="e4ac9-148">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e4ac9-149">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e4ac9-150">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e4ac9-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="e4ac9-151">Actualizar una exportación</span><span class="sxs-lookup"><span data-stu-id="e4ac9-151">Update an export</span></span>

1. <span data-ttu-id="e4ac9-152">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4ac9-153">Seleccione **Editar** en la exportación que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="e4ac9-154">**Agregue** o **Elimine** entidades de la selección.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="e4ac9-155">Si las entidades se eliminan de la selección, no se eliminan de la base de datos de Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="e4ac9-156">Sin embargo, las actualizaciones de datos futuras no actualizarán las entidades eliminadas en esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="e4ac9-157">**Cambio del nombre de la base de datos** crea una nueva base de datos de Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="e4ac9-158">La base de datos con el nombre que se configuró antes no recibirá ninguna actualización en futuras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="e4ac9-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
