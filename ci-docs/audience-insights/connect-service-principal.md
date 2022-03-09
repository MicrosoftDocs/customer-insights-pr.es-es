---
title: Conectar con una cuenta de Azure Data Lake Storage mediante una entidad de servicio
description: Use una entidad de servicio de Azure para conectar con su propio lago de datos.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d593880b06bd21e96826039a67382b75a4296a87
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354211"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectar con una cuenta de Azure Data Lake Storage mediante una entidad de servicio de Azure

Este artículo explica cómo conectar Dynamics 365 Customer Insights con una cuenta de Azure Data Lake Storage mediante el uso de una entidad de servicio de Azure en lugar de claves de cuenta de almacenamiento. 

Las herramientas automatizadas que utilizan los servicios de Azure siempre deben tener permisos restringidos. En lugar de que las aplicaciones inicien sesión como un usuario con todos los privilegios, Azure ofrece entidades de servicio. Puede utilizar las entidades de servicio para [agregar o editar una carpeta de modelo de datos común como origen de datos](connect-common-data-model.md) o [crear o actualizar un entorno](create-environment.md).

> [!IMPORTANT]
> - La cuenta de Data Lake Storage que usará la entidad de servicio debe ser de 2.ª generación y tener el [espacio de nombres jerárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace). Las cuentas de almacenamiento de Azure Data Lake de 1.ª generación no son compatibles.
> - Necesita permisos de administrador para su suscripción de Azure para crear una entidad de servicio.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear una entidad de servicio de Azure para Customer Insights

Antes de crear una nueva entidad de servicio para Customer Insights, verifique si ya existe en su organización.

### <a name="look-for-an-existing-service-principal"></a>Buscar una entidad de servicio existente

1. Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.

2. En los **servicios de Azure**, seleccione **Azure Active Directory**.

3. En **Gestionar**, seleccione **Aplicaciones empresariales**.

4. Busque el id. de la aplicación de Microsoft:
   - Conclusiones del público: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` con el nombre `Dynamics 365 AI for Customer Insights`
   - Conclusiones sobre la interacción: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` con el nombre `Dynamics 365 AI for Customer Insights engagement insights`

5. Si encuentra un registro coincidente, significa que la entidad de servicio ya existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que muestra una entidad de servicio existente.":::
   
6. Si no se devuelven resultados, cree una nueva entidad de servicio.

>[!NOTE]
>Para hacer uso de todo el poder de Dynamics 365 Customer Insights, le sugerimos que agregue ambas aplicaciones a la entidad de servicio.

### <a name="create-a-new-service-principal"></a>Crear una nueva entidad de servicio

1. Instale la versión más reciente de PowerShell de Azure Active Directory para Graph. Para obtener más información, vaya a [Instalar PowerShell de Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2).

   1. En su PC, seleccione la tecla de Windows en su teclado, busque **Windows PowerShell** y seleccione **Ejecutar como Administrador**.
   
   1. En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.

2. Cree la entidad de servicio para Customer Insights con el módulo PowerShell de Azure AD.

   1. En la ventana de PowerShell, introduzca `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Reemplace *[su id. de inquilino]* con el id. real del inquilino donde desea crear la entidad de servicio. El parámetro de nombre de entorno `AzureEnvironmentName` es opcional.
  
   1. Introduzca `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea la entidad de servicio para información de público en el inquilino seleccionado. 

   1. Introduzca `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Este comando crea la entidad de servicio para conclusiones sobre interacción en el inquilino seleccionado.

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

Puede adjuntar una cuenta de Data Lake Storage en conclusiones del público para [almacenar datos de salida](manage-environments.md) o [usarla como origen de datos](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). Esta opción le permite elegir entre un enfoque basado en recursos o uno basado en suscripción. Dependiendo del enfoque que elija, siga el procedimiento en una de las siguientes secciones.

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