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
ms.openlocfilehash: f206043298bdbf8a84b0ef37b47a43290653beba7d3d0e8b807ec74513614aa8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031954"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar datos a Azure Synapse Analytics (versión preliminar)

Azure Synapse es un servicio de análisis que acelera el tiempo para obtener conclusiones sobre los almacenamientos de datos y los sistemas de macrodatos. Puede ingerir y utilizar sus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

Se deben cumplir los siguientes requisitos previos para configurar la conexión de Customer Insights a Azure Synapse.

> [!NOTE]
> Asegúrese de configurar todas las **asignaciones de roles** como se describe.  

## <a name="prerequisites-in-customer-insights"></a>Requisitos previos en Customer Insights

* Debe tener un rol de **Administrador** en los conocimientos del público. Aprender más sobre [Establecer permisos de usuario en conocimientos del público](permissions.md#assign-roles-and-permissions)

En Azure: 

- Una suscripción de Azure activa.

- Si usa una nueva cuenta de Azure Data Lake Storage Gen2, la *entidad de servicio para conocimientos del público* necesita permisos de **Contribuyente de datos de Storage Blob**. Más información sobre [conexión a una cuenta de Azure Data Lake Storage Gen2 con la entidad de servicio de Azure para conclusiones del público](connect-service-principal.md). Data Lake Storage Gen2 **debe** tener activado el [espacio de nombres jerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- En el grupo de recursos donde se encuentra el espacio de trabajo de Azure Synapse, la *entidad de servicio* y el *usuario para conclusiones del público* deben tener asignados al menos permisos de **Lector**. Para más información, vea [Asignar roles de Azure mediante el portal de Azure](/azure/role-based-access-control/role-assignments-portal).

- El *usuario* necesita permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- La *[identidad administrada del espacio de trabajo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necesita permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- En el espacio de trabajo de Azure Synapse, la *entidad de servicio para conclusiones del público* necesita tener asignado el rol **Administrador de Synapse**. Para más información, vea [Cómo configurar el control de acceso para su espacio de trabajo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurar la conexión y exportar a Azure Synapse

### <a name="configure-a-connection"></a>Configurar una conexión

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Azure Synapse Analytics**, o seleccione **Configurar** en el mosaico **Azure Synapse Analytics** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo Nombre para mostrar. El nombre y el tipo de conexión describen esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione o busque la suscripción en la que desea utilizar los datos de Customer Insights. Tan pronto como se seleccione una suscripción, también puede seleccionar **Espacio de trabajo**, **Cuenta de almacenamiento** y **Contenedor**.

1. Seleccione **Guardar** para guardar la conexión.

### <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección **Azure Synapse Analytics**. Si no ve este nombre de sección, es que no hay [conexiones](connections.md) de este tipo disponibles para usted.

1. Proporcione un **Nombre para mostrar** reconocible para la exportación y un **Nombre de base de datos**.

1. Seleccione a qué entidades desea exportar Azure Synapse Analytics.
   > [!NOTE]
   > No se admiten orígenes de datos basados en una [carpeta de Common Data Model](connect-common-data-model.md).

2. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Actualizar una exportación

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Editar** en la exportación que desea actualizar.

   - **Agregue** o **Elimine** entidades de la selección. Si las entidades se eliminan de la selección, no se eliminan de la base de datos de Synapse Analytics. Sin embargo, las actualizaciones de datos futuras no actualizarán las entidades eliminadas en esa base de datos.

   - **Cambio del nombre de la base de datos** crea una nueva base de datos de Synapse Analytics. La base de datos con el nombre que se configuró antes no recibirá ninguna actualización en futuras actualizaciones.
