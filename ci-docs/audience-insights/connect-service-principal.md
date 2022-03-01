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
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692134"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Conectarse a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure para obtener información de público

Las herramientas automatizadas que utilizan los servicios de Azure siempre deben tener permisos restringidos. En lugar de que las aplicaciones inicien sesión como un usuario con todos los privilegios, Azure ofrece entidades de servicio. Siga leyendo para saber cómo conectar la información de público de una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure en lugar de claves de cuenta de almacenamiento. 

Puede utilizar la entidad de servicio para [agregar o editar una carpeta de Common Data Model como origen de datos](connect-common-data-model.md) o [crear un entorno nuevo o actualizar uno existente](get-started-paid.md).

> [!IMPORTANT]
> - La cuenta de almacenamiento de Azure Data Lake Gen2 que pretende usar la entidad de servicio debe tener habilitado el [Espacio de nombres jerárquico (HNS)](/azure/storage/blobs/data-lake-storage-namespace).
> - Necesita permisos de administrador para su suscripción de Azure para crear la entidad de servicio.

## <a name="create-azure-service-principal-for-audience-insights"></a>Crear una entidad de servicio de Azure para información de público

Antes de crear una nueva entidad de servicio para información de público, compruebe si ya existe en su organización.

### <a name="look-for-an-existing-service-principal"></a>Buscar una entidad de servicio existente

1. Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.

2. Seleccione **Azure Active Directory** en los servicios de Azure.

3. En **Gestionar**, seleccione **Aplicaciones empresariales**.

4. Busque el id. de la aplicación propia de información de público `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o el nombre `Dynamics 365 AI for Customer Insights`.

5. Si encuentra un registro coincidente, significa que existe la entidad de servicio para información de público. No necesita volver a crearla.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que muestra la entidad de servicio existente.":::
   
6. Si no se devuelven resultados, cree una nueva entidad de servicio.

### <a name="create-a-new-service-principal"></a>Crear una nueva entidad de servicio

1. Instale la última versión del **Azure Active Directory PowerShell para Graph**. Para obtener más información, consulte [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   - En su PC, seleccione la tecla de Windows en su teclado, busque **Windows PowerShell** y **Ejecutar como Administrador**.
   
   - En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.

2. Cree la entidad de servicio para informaciones de audiencia con el módulo de Azure AD PowerShell.
   - En la ventana de PowerShell, introduzca `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Reemplace “su id. de inquilino” con el id. real del inquilino donde desea crear la entidad de servicio. El parámetro de nombre de entorno `AzureEnvironmentName` es opcional.
  
   - Introduzca `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea la entidad de servicio para información de público en el inquilino seleccionado.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Otorgar permisos a la entidad de servicio para acceder a la cuenta de almacenamiento

Vaya a Azure Portal para otorgar permisos a la entidad de servicio para la cuenta de almacenamiento que desea usar en la información de público.

1. Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.

1. Abra la cuenta de almacenamiento a la que desea que tenga acceso la entidad de servicio para la información de público.

1. Seleccione **Control de acceso (IAM)** en el panel de navegación y seleccione **Agregar** > **Agregar asignación de roles**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que muestra Azure Portal al agregar una asignación de roles.":::
   
1. En el panel **Agregar asignación de roles**, establezca las siguientes propiedades:
   - Rol: *Colaborador de datos de blob de almacenamiento*
   - Asignar acceso a: *usuario, grupo o entidad de servicio*
   - Seleccione: *Dynamics 365 AI para Customer Insights* (la [entidad de servicio que creó](#create-a-new-service-principal))

1.  Seleccione **Guardar**.

La propagación de los cambios puede tardar hasta 15 minutos.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduzca el id. de recurso de Azure o los detalles de la suscripción de Azure en el archivo adjunto de la cuenta de almacenamiento de Audience Insights.

Adjunte una cuenta de almacenamiento de Azure Data Lake en la información de público para [almacenar datos de salida](manage-environments.md) o [úsela como origen de datos](connect-dataverse-managed-lake.md). La elección de la opción de Azure Data Lake le permite elegir entre un enfoque basado en recursos o basado en suscripción.

Siga los pasos a continuación para proporcionar la información requerida sobre el enfoque seleccionado.

### <a name="resource-based-storage-account-connection"></a>Conexión de cuenta de almacenamiento basada en recursos

1. Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.

1. Vaya a **Configuración** > **Propiedades** en el panel de navegación.

1. Copie el valor de id. de recurso de la cuenta de almacenamiento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie el valor de id. de recurso de la cuenta de almacenamiento.":::

1. En la información de público, inserte el id. del recurso en el campo de recurso que se muestra en la pantalla de conexión de la cuenta de almacenamiento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduzca el valor de id. de recurso de la cuenta de almacenamiento.":::   
   
1. Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.

### <a name="subscription-based-storage-account-connection"></a>Conexión de cuenta de almacenamiento basada en suscripción

1. Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.

1. Vaya a **Configuración** > **Propiedades** en el panel de navegación.

1. Revise la **Suscripción**, el **Grupo de recursos** y el **Nombre** de la cuenta de almacenamiento para asegurarse de seleccionar los valores correctos en la información de público.

1. En la información de público, elija los valores o los campos correspondientes al adjuntar la cuenta de almacenamiento.
   
1. Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]