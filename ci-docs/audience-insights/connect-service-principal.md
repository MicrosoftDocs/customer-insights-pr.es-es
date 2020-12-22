---
title: Conectarse a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio
description: Use una entidad de servicio de Azure para que la información de público se conecte a su propio lago de datos al adjuntarlo a la información de público.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644109"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="86992-103">Conectarse a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure para obtener información de público</span><span class="sxs-lookup"><span data-stu-id="86992-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="86992-104">Las herramientas automatizadas que utilizan los servicios de Azure siempre deben tener permisos restringidos.</span><span class="sxs-lookup"><span data-stu-id="86992-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="86992-105">En lugar de que las aplicaciones inicien sesión como un usuario con todos los privilegios, Azure ofrece entidades de servicio.</span><span class="sxs-lookup"><span data-stu-id="86992-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="86992-106">Siga leyendo para saber cómo conectar la información de público de una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure en lugar de claves de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="86992-107">Puede utilizar la entidad de servicio para [agregar o editar una carpeta de Common Data Model como origen de datos](connect-common-data-model.md) o [crear un entorno nuevo o actualizar uno existente](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="86992-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="86992-108">Necesita permisos de administrador para su suscripción de Azure para crear la entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="86992-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="86992-109">Crear una entidad de servicio de Azure para información de público</span><span class="sxs-lookup"><span data-stu-id="86992-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="86992-110">Antes de crear una nueva entidad de servicio para información de público, compruebe si ya existe en su organización.</span><span class="sxs-lookup"><span data-stu-id="86992-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="86992-111">Buscar una entidad de servicio existente</span><span class="sxs-lookup"><span data-stu-id="86992-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="86992-112">Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.</span><span class="sxs-lookup"><span data-stu-id="86992-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="86992-113">Seleccione **Azure Active Directory** en los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="86992-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="86992-114">En **Gestionar**, seleccione **Aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="86992-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="86992-115">Busque el id. de la aplicación propia de información de público `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o el nombre `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="86992-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="86992-116">Si encuentra un registro coincidente, significa que existe la entidad de servicio para información de público.</span><span class="sxs-lookup"><span data-stu-id="86992-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="86992-117">No necesita volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="86992-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que muestra la entidad de servicio existente.":::
   
6. <span data-ttu-id="86992-119">Si no se devuelven resultados, cree una nueva entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="86992-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="86992-120">Crear una nueva entidad de servicio</span><span class="sxs-lookup"><span data-stu-id="86992-120">Create a new service principal</span></span>

1. <span data-ttu-id="86992-121">Instale la última versión del **Azure Active Directory PowerShell para Graph**.</span><span class="sxs-lookup"><span data-stu-id="86992-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="86992-122">Para obtener más información, consulte [Instalar Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="86992-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="86992-123">En su PC, seleccione la tecla de Windows en su teclado, busque **Windows PowerShell** y **Ejecutar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="86992-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="86992-124">En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="86992-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="86992-125">Cree la entidad de servicio para informaciones de audiencia con el módulo de Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86992-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="86992-126">En la ventana de PowerShell, introduzca `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="86992-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="86992-127">Reemplace “su id. de inquilino” con el id. real del inquilino donde desea crear la entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="86992-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="86992-128">El parámetro de nombre de entorno `AzureEnvironmentName` es opcional.</span><span class="sxs-lookup"><span data-stu-id="86992-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="86992-129">Introduzca `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="86992-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="86992-130">Este comando crea la entidad de servicio para información de público en el inquilino seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86992-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="86992-131">Otorgar permisos a la entidad de servicio para acceder a la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="86992-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="86992-132">Vaya a Azure Portal para otorgar permisos a la entidad de servicio para la cuenta de almacenamiento que desea usar en la información de público.</span><span class="sxs-lookup"><span data-stu-id="86992-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="86992-133">Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.</span><span class="sxs-lookup"><span data-stu-id="86992-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="86992-134">Abra la cuenta de almacenamiento a la que desea que tenga acceso la entidad de servicio para la información de público.</span><span class="sxs-lookup"><span data-stu-id="86992-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="86992-135">Seleccione **Control de acceso (IAM)** en el panel de navegación y seleccione **Agregar** > **Agregar asignación de roles**.</span><span class="sxs-lookup"><span data-stu-id="86992-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que muestra Azure Portal al agregar una asignación de roles.":::
   
1. <span data-ttu-id="86992-137">En el panel **Agregar asignación de roles**, establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="86992-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="86992-138">Rol: *Colaborador de datos de blob de almacenamiento*</span><span class="sxs-lookup"><span data-stu-id="86992-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="86992-139">Asignar acceso a: *usuario, grupo o entidad de servicio*</span><span class="sxs-lookup"><span data-stu-id="86992-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="86992-140">Seleccione: *Dynamics 365 AI para Customer Insights* (la [entidad de servicio que creó](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="86992-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="86992-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86992-141">Select **Save**.</span></span>

<span data-ttu-id="86992-142">La propagación de los cambios puede tardar hasta 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="86992-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="86992-143">Introduzca el id. de recurso de Azure o los detalles de la suscripción de Azure en el archivo adjunto de la cuenta de almacenamiento de Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="86992-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="86992-144">Adjunte una cuenta de almacenamiento de Azure Data Lake en la información de público para [almacenar datos de salida](manage-environments.md) o [úsela como origen de datos](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="86992-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="86992-145">La elección de la opción de Azure Data Lake le permite elegir entre un enfoque basado en recursos o basado en suscripción.</span><span class="sxs-lookup"><span data-stu-id="86992-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="86992-146">Siga los pasos a continuación para proporcionar la información requerida sobre el enfoque seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86992-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="86992-147">Conexión de cuenta de almacenamiento basada en recursos</span><span class="sxs-lookup"><span data-stu-id="86992-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="86992-148">Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="86992-149">Vaya a **Configuración** > **Propiedades** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="86992-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="86992-150">Copie el valor de id. de recurso de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie el valor de id. de recurso de la cuenta de almacenamiento.":::

1. <span data-ttu-id="86992-152">En la información de público, inserte el id. del recurso en el campo de recurso que se muestra en la pantalla de conexión de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduzca el valor de id. de recurso de la cuenta de almacenamiento.":::   
   
1. <span data-ttu-id="86992-154">Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="86992-155">Conexión de cuenta de almacenamiento basada en suscripción</span><span class="sxs-lookup"><span data-stu-id="86992-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="86992-156">Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="86992-157">Vaya a **Configuración** > **Propiedades** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="86992-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="86992-158">Revise la **Suscripción**, el **Grupo de recursos** y el **Nombre** de la cuenta de almacenamiento para asegurarse de seleccionar los valores correctos en la información de público.</span><span class="sxs-lookup"><span data-stu-id="86992-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="86992-159">En la información de público, elija los valores o los campos correspondientes al adjuntar la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Introduzca el valor de id. de recurso de la cuenta de almacenamiento.":::
   
1. <span data-ttu-id="86992-161">Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="86992-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
