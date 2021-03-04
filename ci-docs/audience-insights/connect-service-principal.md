---
title: Conectarse a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio
description: Use una entidad de servicio de Azure para que la información de público se conecte a su propio lago de datos al adjuntarlo a la información de público.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267743"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="74e56-103">Conectarse a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure para obtener información de público</span><span class="sxs-lookup"><span data-stu-id="74e56-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="74e56-104">Las herramientas automatizadas que utilizan los servicios de Azure siempre deben tener permisos restringidos.</span><span class="sxs-lookup"><span data-stu-id="74e56-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="74e56-105">En lugar de que las aplicaciones inicien sesión como un usuario con todos los privilegios, Azure ofrece entidades de servicio.</span><span class="sxs-lookup"><span data-stu-id="74e56-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="74e56-106">Siga leyendo para saber cómo conectar la información de público de una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure en lugar de claves de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="74e56-107">Puede utilizar la entidad de servicio para [agregar o editar una carpeta de Common Data Model como origen de datos](connect-common-data-model.md) o [crear un entorno nuevo o actualizar uno existente](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="74e56-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="74e56-108">La cuenta de almacenamiento de Azure Data Lake Gen2 que pretende usar la entidad de servicio debe tener habilitado el [Espacio de nombres jerárquico (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="74e56-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="74e56-109">Necesita permisos de administrador para su suscripción de Azure para crear la entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="74e56-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="74e56-110">Crear una entidad de servicio de Azure para información de público</span><span class="sxs-lookup"><span data-stu-id="74e56-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="74e56-111">Antes de crear una nueva entidad de servicio para información de público, compruebe si ya existe en su organización.</span><span class="sxs-lookup"><span data-stu-id="74e56-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="74e56-112">Buscar una entidad de servicio existente</span><span class="sxs-lookup"><span data-stu-id="74e56-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="74e56-113">Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.</span><span class="sxs-lookup"><span data-stu-id="74e56-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="74e56-114">Seleccione **Azure Active Directory** en los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="74e56-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="74e56-115">En **Gestionar**, seleccione **Aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="74e56-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="74e56-116">Busque el id. de la aplicación propia de información de público `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o el nombre `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="74e56-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="74e56-117">Si encuentra un registro coincidente, significa que existe la entidad de servicio para información de público.</span><span class="sxs-lookup"><span data-stu-id="74e56-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="74e56-118">No necesita volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="74e56-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que muestra la entidad de servicio existente.":::
   
6. <span data-ttu-id="74e56-120">Si no se devuelven resultados, cree una nueva entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="74e56-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="74e56-121">Crear una nueva entidad de servicio</span><span class="sxs-lookup"><span data-stu-id="74e56-121">Create a new service principal</span></span>

1. <span data-ttu-id="74e56-122">Instale la última versión del **Azure Active Directory PowerShell para Graph**.</span><span class="sxs-lookup"><span data-stu-id="74e56-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="74e56-123">Para obtener más información, consulte [Instalar Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="74e56-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="74e56-124">En su PC, seleccione la tecla de Windows en su teclado, busque **Windows PowerShell** y **Ejecutar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="74e56-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="74e56-125">En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="74e56-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="74e56-126">Cree la entidad de servicio para informaciones de audiencia con el módulo de Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74e56-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="74e56-127">En la ventana de PowerShell, introduzca `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="74e56-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="74e56-128">Reemplace “su id. de inquilino” con el id. real del inquilino donde desea crear la entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="74e56-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="74e56-129">El parámetro de nombre de entorno `AzureEnvironmentName` es opcional.</span><span class="sxs-lookup"><span data-stu-id="74e56-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="74e56-130">Introduzca `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="74e56-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="74e56-131">Este comando crea la entidad de servicio para información de público en el inquilino seleccionado.</span><span class="sxs-lookup"><span data-stu-id="74e56-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="74e56-132">Otorgar permisos a la entidad de servicio para acceder a la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="74e56-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="74e56-133">Vaya a Azure Portal para otorgar permisos a la entidad de servicio para la cuenta de almacenamiento que desea usar en la información de público.</span><span class="sxs-lookup"><span data-stu-id="74e56-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="74e56-134">Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.</span><span class="sxs-lookup"><span data-stu-id="74e56-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="74e56-135">Abra la cuenta de almacenamiento a la que desea que tenga acceso la entidad de servicio para la información de público.</span><span class="sxs-lookup"><span data-stu-id="74e56-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="74e56-136">Seleccione **Control de acceso (IAM)** en el panel de navegación y seleccione **Agregar** > **Agregar asignación de roles**.</span><span class="sxs-lookup"><span data-stu-id="74e56-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que muestra Azure Portal al agregar una asignación de roles.":::
   
1. <span data-ttu-id="74e56-138">En el panel **Agregar asignación de roles**, establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="74e56-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="74e56-139">Rol: *Colaborador de datos de blob de almacenamiento*</span><span class="sxs-lookup"><span data-stu-id="74e56-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="74e56-140">Asignar acceso a: *usuario, grupo o entidad de servicio*</span><span class="sxs-lookup"><span data-stu-id="74e56-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="74e56-141">Seleccione: *Dynamics 365 AI para Customer Insights* (la [entidad de servicio que creó](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="74e56-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="74e56-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="74e56-142">Select **Save**.</span></span>

<span data-ttu-id="74e56-143">La propagación de los cambios puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="74e56-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="74e56-144">Introduzca el id. de recurso de Azure o los detalles de la suscripción de Azure en el archivo adjunto de la cuenta de almacenamiento de Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="74e56-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="74e56-145">Adjunte una cuenta de almacenamiento de Azure Data Lake en la información de público para [almacenar datos de salida](manage-environments.md) o [úsela como origen de datos](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="74e56-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="74e56-146">La elección de la opción de Azure Data Lake le permite elegir entre un enfoque basado en recursos o basado en suscripción.</span><span class="sxs-lookup"><span data-stu-id="74e56-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="74e56-147">Siga los pasos a continuación para proporcionar la información requerida sobre el enfoque seleccionado.</span><span class="sxs-lookup"><span data-stu-id="74e56-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="74e56-148">Conexión de cuenta de almacenamiento basada en recursos</span><span class="sxs-lookup"><span data-stu-id="74e56-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="74e56-149">Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="74e56-150">Vaya a **Configuración** > **Propiedades** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="74e56-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="74e56-151">Copie el valor de id. de recurso de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie el valor de id. de recurso de la cuenta de almacenamiento.":::

1. <span data-ttu-id="74e56-153">En la información de público, inserte el id. del recurso en el campo de recurso que se muestra en la pantalla de conexión de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduzca el valor de id. de recurso de la cuenta de almacenamiento.":::   
   
1. <span data-ttu-id="74e56-155">Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="74e56-156">Conexión de cuenta de almacenamiento basada en suscripción</span><span class="sxs-lookup"><span data-stu-id="74e56-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="74e56-157">Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="74e56-158">Vaya a **Configuración** > **Propiedades** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="74e56-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="74e56-159">Revise la **Suscripción**, el **Grupo de recursos** y el **Nombre** de la cuenta de almacenamiento para asegurarse de seleccionar los valores correctos en la información de público.</span><span class="sxs-lookup"><span data-stu-id="74e56-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="74e56-160">En la información de público, elija los valores o los campos correspondientes al adjuntar la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="74e56-161">Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="74e56-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]