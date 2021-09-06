---
title: Conectar con una cuenta de Azure Data Lake Storage mediante una entidad de servicio
description: Use una entidad de servicio de Azure para conectar con su propio lago de datos.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461169"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectar con una cuenta de Azure Data Lake Storage mediante una entidad de servicio de Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Las herramientas automatizadas que utilizan los servicios de Azure siempre deben tener permisos restringidos. En lugar de que las aplicaciones inicien sesión como un usuario con todos los privilegios, Azure ofrece entidades de servicio. Siga leyendo para aprender cómo conectar Dynamics 365 Customer Insights con una cuenta de Azure Data Lake Storage mediante una entidad de servicio de Azure en lugar de las claves de la cuenta de almacenamiento. 

Puede usar la entidad de servicio para [agregar o editar una carpeta de Common Data Model como origen de datos](connect-common-data-model.md) o [crear o actualizar un entorno](get-started-paid.md) de forma segura.<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - La cuenta de Data Lake Storage que usará<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> la entidad de servicio debe tener un [espacio de nombres jerárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace).
> - Necesita permisos de administrador para su suscripción de Azure para crear la entidad de servicio.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear una entidad de servicio de Azure para Customer Insights

Antes de crear una nueva entidad de servicio para conclusiones del público o conclusiones sobre la interacción, verifique si ya existe en su organización.

### <a name="look-for-an-existing-service-principal"></a>Buscar una entidad de servicio existente

1. Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.

2. En los **servicios de Azure**, seleccione **Azure Active Directory**.

3. En **Gestionar**, seleccione **Aplicaciones empresariales**.

4. Busque el Id. de<!--note from editor: Via Microsoft Writing Style Guide.--> aplicación de Microsoft:
   - Conclusiones del público: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` con el nombre `Dynamics 365 AI for Customer Insights`
   - Conclusiones sobre la interacción: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` con el nombre `Dynamics 365 AI for Customer Insights engagement insights`

5. Si encuentra un registro coincidente, significa que la entidad de servicio ya existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que muestra una entidad de servicio existente.":::
   
6. Si no se devuelven resultados, cree una nueva entidad de servicio.

>[!NOTE]
>Para hacer uso de todo el poder de Dynamics 365 Customer Insights, le sugerimos que agregue ambas aplicaciones a la entidad de servicio.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Crear una nueva entidad de servicio
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Instale la versión más reciente de PowerShell de Azure Active Directory para Graph. Para obtener más información, vaya a [Instalar PowerShell de Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2).

   1. En su PC, seleccione la tecla de Windows en su teclado, busque **Windows PowerShell** y seleccione **Ejecutar como Administrador**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.

2. Cree la entidad de servicio para Customer Insights con el módulo PowerShell de Azure AD.

   1. En la ventana de PowerShell, introduzca `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Sustituya *"[el identificador de inquilino]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> con el identificador real de su inquilino donde desea crear la entidad de servicio. El parámetro de nombre de entorno `AzureEnvironmentName` es opcional.
  
   1. Introduzca `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea la entidad de servicio para información de público en el inquilino seleccionado. 

   1. Introduzca `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Este comando crea la entidad de servicio para conclusiones sobre la interacción<!--note from editor: Edit okay?--> en el inquilino seleccionado.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Otorgar permisos a la entidad de servicio para acceder a la cuenta de almacenamiento

Vaya a Azure Portal para otorgar permisos a la entidad de servicio para la cuenta de almacenamiento que desea usar en la información de público.

1. Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.

1. Abra la cuenta de almacenamiento a la que desea que tenga acceso la entidad de servicio para la información de público.

1. En el panel izquierdo, seleccione **Control de acceso (IAM)** y, a continuación, seleccione **Agregar** > **Agregar asignación de roles**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que muestra el portal de Azure al agregar una asignación de roles.":::

1. En el panel **Agregar asignación de roles**, establezca las siguientes propiedades:
   - Rol: **Colaborador de datos de blob de almacenamiento**
   - Asignar acceso a: **usuario, grupo o entidad de servicio**
   - Seleccione: **Dynamics 365 AI para Customer Insights** y **Conclusiones sobre la interacción de Dynamics 365 AI for Customer Insights** (las dos [entidades de servicio](#create-a-new-service-principal) que creó anteriormente en este procedimiento)

1.  Seleccione **Guardar**.

La propagación de los cambios puede tardar hasta 15 minutos.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduzca el id. de recurso de Azure o los detalles de la suscripción de Azure en el archivo adjunto de la cuenta de almacenamiento de conclusiones del público.

El usuario puede<!--note from editor: Edit suggested only if this section is optional.--> adjuntar una cuenta de Data Lake Storage en conclusiones del público para [almacenar datos de salida](manage-environments.md) o [usarla como origen de datos](connect-common-data-service-lake.md). Esta opción le permite elegir entre un enfoque basado en recursos o uno basado en suscripción. Dependiendo del enfoque que elija, siga el procedimiento en una de las siguientes secciones.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Conexión de cuenta de almacenamiento basada en recursos

1. Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.

1. En el panel izquierdo, vaya a **Configuración** > **Propiedades**.

1. Copie el valor de id. de recurso de la cuenta de almacenamiento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie el valor de id. de recurso de la cuenta de almacenamiento.":::

1. En las conclusiones del público, inserte el Id. del recurso en el campo del recurso que se muestra en la pantalla de conexión de la cuenta de almacenamiento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduzca el valor de id. de recurso de la cuenta de almacenamiento.":::   

1. Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.

### <a name="subscription-based-storage-account-connection"></a>Conexión de cuenta de almacenamiento basada en suscripción

1. Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.

1. En el panel izquierdo, vaya a **Configuración** > **Propiedades**.

1. Revise la **Suscripción**, el **Grupo de recursos** y el **Nombre** de la cuenta de almacenamiento para asegurarse de seleccionar los valores correctos en la información de público.

1. En las conclusiones del público, elija los valores para los campos correspondientes al adjuntar la cuenta de almacenamiento.

1. Continúe con los pasos restantes en la información de público para adjuntar la cuenta de almacenamiento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]