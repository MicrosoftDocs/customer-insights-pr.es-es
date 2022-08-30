---
title: Conectar con una cuenta de Azure Data Lake Storage mediante una entidad de servicio de Azure
description: Use una entidad de servicio de Azure para conectar con su propio lago de datos.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304218"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectar con una cuenta de Azure Data Lake Storage mediante una entidad de servicio de Azure

Dynamics 365 Customer Insights proporciona una opción para conectarse con una cuenta de Azure Data Lake Storage mediante una entidad de servicio de Azure en lugar de las claves de la cuenta de almacenamiento.

Las herramientas automatizadas que utilizan los servicios de Azure deben tener permisos restringidos. En lugar de que las aplicaciones inicien sesión como un usuario con todos los privilegios, Azure ofrece entidades de servicio. Use las entidades de servicio para [agregar o editar una carpeta de modelo de datos común como origen de datos](connect-common-data-model.md) o [crear o actualizar un entorno](create-environment.md).

## <a name="prerequisites"></a>Requisitos previos

- La cuenta de Data Lake Storage que usará la entidad de servicio debe ser Gen2. Las cuentas de almacenamiento de Azure Data Lake de 1.ª generación no son compatibles.
- La cuenta de Data Lake Storage tiene el [espacio de nombres jerárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace).
- Permisos de administrador para su inquilino de Azure si tiene que crear una entidad de servicio nueva.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear una entidad de servicio de Azure para Customer Insights

Antes de crear una nueva entidad de servicio para Customer Insights, verifique si ya existe en su organización. En la mayoría de los casos, ya existe.

### <a name="look-for-an-existing-service-principal"></a>Buscar una entidad de servicio existente

1. Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.

2. En los **servicios de Azure**, seleccione **Azure Active Directory**.

3. En **Administrar**, seleccione **Aplicación de Microsoft**.

4. Añada un filtro para **El ID de la aplicación comienza con** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` o busque el nombre `Dynamics 365 AI for Customer Insights`.

5. Si encuentra un registro coincidente, significa que la entidad de servicio ya existe. [Otorgar permisos](#grant-permissions-to-the-service-principal-to-access-the-storage-account) para la entidad de servicio para acceder a la cuenta de almacenamiento.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que muestra una entidad de servicio existente.":::

6. Si no se devuelven resultados, [cree una nueva entidad de servicio](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Crear una nueva entidad de servicio

1. Instale la versión más reciente de PowerShell de Azure Active Directory para Graph. Para obtener más información, vaya a [Instalar PowerShell de Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2).

   1. En su PC, pulse la tecla Windows de su teclado y busque **Windows PowerShell** y seleccione **Ejecutar como administrador**.

   1. En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.

2. Cree la entidad de servicio para Customer Insights con el módulo PowerShell de Azure AD.

   1. En la ventana de PowerShell, introduzca `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Reemplace *[su ID de directorio]* con el identificador de directorio real de su suscripción de Azure donde desea crear la entidad de servicio. El parámetro de nombre de entorno `AzureEnvironmentName` es opcional.
  
   1. Introduzca `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea la entidad de servicio para Customer Insights en la suscripción de Azure seleccionada.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Otorgar permisos a la entidad de servicio para acceder a la cuenta de almacenamiento

Para otorgar permisos a la entidad de servicio para la cuenta de almacenamiento que desea usar en Customer Insights, se debe asignar uno de los siguientes roles a la cuenta de almacenamiento o al contenedor:

|Credencial|Requisitos|
|----------|------------|
|Usuario actualmente conectado|**Rol**: Lector de Datos de Storage Blob, Colaborador de Storage Blob colaborador o Propietario de Storage Blob.<br>**Nivel**: permisos otorgados en la cuenta de almacenamiento o en el contenedor.</br>|
|Entidad de servicio Customer Insights -<br>Uso de Azure Data Lake Storage como origen de datos</br>|Opción 1<ul><li>**Rol**: Lector de Datos de Storage Blob, Colaborador de datos de Storage Blob colaborador o Propietario de datos de Storage Blob.</li><li>**Nivel**: permisos otorgados en la cuenta de almacenamiento.</li></ul>Opcion 2 *(sin compartir el acceso de la entidad principal de servicio a la cuenta de almacenamiento)*<ul><li>**Rol 1**: Lector de Datos de Storage Blob, Colaborador de datos de Storage Blob colaborador o Propietario de datos de Storage Blob.</li><li>**Nivel**: permisos otorgados en el contenedor.</li><li>**Rol 2**: delegador de datos de Storage Blob.</li><li>**Nivel**: permisos otorgados en la cuenta de almacenamiento.</li></ul>|
|Entidad de servicio Customer Insights - <br>Usar Azure Data Lake Storage como salida o destino</br>|Opción 1<ul><li>**Rol**: Colaborador de Storage Blob colaborador o Propietario de Storage Blob.</li><li>**Nivel**: permisos otorgados en la cuenta de almacenamiento.</li></ul>Opcion 2 *(sin compartir el acceso de la entidad principal de servicio a la cuenta de almacenamiento)*<ul><li>**Rol**: Colaborador de Storage Blob colaborador o Propietario de Storage Blob.</li><li>**Nivel**: permisos otorgados en el contenedor.</li><li>**Rol 2**: delegador de Storage Blob.</li><li>**Nivel**: permisos otorgados en la cuenta de almacenamiento.</li></ul>|

1. Vaya al [Portal de administración de Azure](https://portal.azure.com) e inicie sesión en su organización.

1. Abra la cuenta de almacenamiento a la que desea que tenga acceso la entidad de servicio para Customer Insights.

1. En el panel izquierdo, seleccione **Control de acceso (IAM)** y, a continuación, seleccione **Agregar** > **Agregar asignación de roles**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que muestra el portal de Azure al agregar una asignación de roles.":::

1. En el panel **Agregar asignación de roles**, establezca las siguientes propiedades:
   - **Rol**: Lector de Datos de Storage Blob, Colaborador de datos de Storage Blob colaborador o Propietario de datos de Storage Blob basado en las credenciales anteriores.
   - **Asignar acceso a**: **usuario, grupo o entidad de servicio**
   - **Seleccionar** miembros: **Dynamics 365 AI para Customer Insights** (la [entidad de servicio](#create-a-new-service-principal) que examinó anteriormente en este procedimiento)

1. Seleccione **Revisar + asignar**.

La propagación de los cambios puede tardar hasta 15 minutos.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Ingrese el ID de recurso de Azure o los detalles de la suscripción de Azure en el archivo adjunto de la cuenta de almacenamiento a Customer Insights

Adjuntar una cuenta de Data Lake Storage en Customer Insights para [almacenar datos de salida](manage-environments.md) o [usarla como origen de datos](connect-dataverse-managed-lake.md). Elija entre un enfoque [basado en recursos](#resource-based-storage-account-connection) o uno [basado en suscripción](#subscription-based-storage-account-connection) y siga esos pasos.

### <a name="resource-based-storage-account-connection"></a>Conexión de cuenta de almacenamiento basada en recursos

1. Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.

1. En el panel izquierdo, vaya a **Configuración** > **Extremos**.

1. Copie el valor de id. de recurso de la cuenta de almacenamiento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie el valor de id. de recurso de la cuenta de almacenamiento.":::

1. En Customer Insights, inserte el identificador de recurso en el campo de recursos que se muestra en la pantalla de conexión de la cuenta de almacenamiento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Introduzca el valor de id. de recurso de la cuenta de almacenamiento.":::

1. Continúe con los pasos restantes en Customer Insights para adjuntar la cuenta de almacenamiento.

### <a name="subscription-based-storage-account-connection"></a>Conexión de cuenta de almacenamiento basada en suscripción

1. Vaya al [Portal de administración de Azure](https://portal.azure.com), inicie sesión en su suscripción y abra la cuenta de almacenamiento.

1. En el panel izquierdo, vaya a **Configuración** > **Propiedades**.

1. Revise la **Suscripción**, **Grupo de recursos**, y el **Nombre** de la cuenta de almacenamiento para asegurarse de seleccionar los valores correctos en Customer Insights.

1. En Customer Insights, elija los valores para los campos correspondientes al adjuntar la cuenta de almacenamiento.

1. Continúe con los pasos restantes en Customer Insights para adjuntar la cuenta de almacenamiento.

[!INCLUDE [footer-include](includes/footer-banner.md)]
