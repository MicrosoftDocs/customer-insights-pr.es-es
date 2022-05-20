---
title: Exportar datos de Customer Insights a Azure Synapse Analytics
description: Aprenda a configurar la conexión a Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741524"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportación de datos a Azure Synapse Analytics (Versión preliminar)

Azure Synapse es un servicio de análisis que acelera el tiempo para obtener conclusiones sobre los almacenamientos de datos y los sistemas de macrodatos. Puede ingerir y utilizar sus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

Se deben cumplir los siguientes requisitos previos para configurar la conexión de Customer Insights a Azure Synapse.

> [!NOTE]
> Asegúrese de configurar todas las **asignaciones de roles** como se describe.  

## <a name="prerequisites-in-customer-insights"></a>Requisitos previos en Customer Insights

* Su cuenta de usuario de Azure Active Directory (AD) tiene un rol de **Administrador** en Customer Insights. Aprenda más sobre la [configuración de permisos de usuario](permissions.md#assign-roles-and-permissions).

En Azure: 

- Una suscripción de Azure activa.

- Si usa una nueva cuenta de Azure Data Lake Storage Gen2, la *entidad de servicio para Customer Insights* necesita permisos de **colaborador de datos de Storage Blob**. Más información sobre la [conexión a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure para Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **debe** tener activado el [espacio de nombres jerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- En el grupo de recursos donde se encuentra Azure Synapse workspace, la *entidad de servicio* y el *usuario de Azure AD con permisos de administrador en Customer Insights* necesitan que se le asignen permisos de **Lector**. Para más información, vea [Asignar roles de Azure mediante el portal de Azure](/azure/role-based-access-control/role-assignments-portal).

- El *usuario de Azure AD con permisos de administrador en Customer Insights* necesita permisos de **colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se encuentran los datos y se vinculan a Azure Synapse workspace. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- La *[identidad administrada del espacio de trabajo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necesita permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- En Azure Synapse workspace, la *entidad de servicio para Customer Insights* necesita que se le asigne el rol de **Administrador de Synapse**. Para más información, vea [Cómo configurar el control de acceso para su espacio de trabajo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurar la conexión y exportar a Azure Synapse

### <a name="configure-a-connection"></a>Configurar una conexión

Para crear una conexión, la entidad de servicio y la cuenta de usuario en Customer Insights necesitan permisos de **Lector** en el *grupo de recursos* donde se encuentra el espacio de trabajo de Synapse Analytics. Además, la entidad de servicio y el usuario en el área de trabajo de Synapse Analytics necesitan permisos **Administrador de Synapse**. 

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Azure Synapse Analytics** o seleccione **Configurar** en la ventana **Azure Synapse Analytics** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo Nombre para mostrar. El nombre y el tipo de conexión describen esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione o busque la suscripción en la que desea utilizar los datos de Customer Insights. Tan pronto como se seleccione una suscripción, también puede seleccionar **Espacio de trabajo**, **Cuenta de almacenamiento** y **Contenedor**.

1. Seleccione **Guardar** para guardar la conexión.

### <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para configurar la exportación con una conexión compartida, necesita al menos permisos de **Colaborador** en Customer Insights. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión desde la sección **Azure Synapse Analytics**. Si no ve este nombre de sección, es que no hay [conexiones](connections.md) de este tipo disponibles para usted.

1. Proporcione un **Nombre para mostrar** reconocible para la exportación y un **Nombre de base de datos**.

1. Seleccione qué entidades desea exportar a Azure Synapse Analytics.
   > [!NOTE]
   > No se admiten orígenes de datos basados en una [carpeta de Common Data Model](connect-common-data-model.md).

2. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).

Para consultar los datos que se exportaron a Synapse Analytics, necesita acceso al **Lector de datos de blob de almacenamiento** del almacenamiento de destino en el espacio de trabajo de exportaciones. 

### <a name="update-an-export"></a>Actualizar una exportación

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Editar** en la exportación que desea actualizar.

   - **Agregue** o **Elimine** entidades de la selección. Si las entidades se eliminan de la selección, no se eliminan de la base de datos de Synapse Analytics. Sin embargo, las actualizaciones de datos futuras no actualizarán las entidades eliminadas en esa base de datos.

   - **Cambio del nombre de la base de datos** crea una nueva base de datos de Synapse Analytics. La base de datos con el nombre que se configuró antes no recibirá ninguna actualización en futuras actualizaciones.
