---
title: Exportación de datos a Azure Synapse Analytics (versión preliminar)
description: Aprenda a configurar la conexión a Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196415"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportación de datos a Azure Synapse Analytics (versión preliminar)

Azure Synapse es un servicio de análisis que acelera el tiempo para obtener conclusiones sobre los almacenamientos de datos y los sistemas de macrodatos. Puede ingerir y utilizar sus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

> [!NOTE]
> Asegúrese de configurar todas las **asignaciones de roles** como se describe.

- En Customer Insights, su cuenta de usuario de Azure Active Directory (AD) debe tener un [rol de administrador](permissions.md#assign-roles-and-permissions).

En Azure:

- Una suscripción de Azure activa.

- Si usa una nueva cuenta de Azure Data Lake Storage Gen2, la [entidad de servicio para Customer Insights](connect-service-principal.md) tiene permisos de **Colaborador de datos de Storage Blob**. Data Lake Storage Gen2 **debe** tener activado el [espacio de nombres jerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- En el grupo de recursos donde se encuentra Azure Synapse workspace, la *entidad de servicio* y el usuario de *Azure AD con permisos de administrador en Customer Insights* deben asignarse al menos con [permisos](/azure/role-based-access-control/role-assignments-portal) de **lectura**.

- El usuario de *Azure AD con permisos de administrador en Customer Insights* tiene permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se encuentran los datos y se vinculan al Azure Synapse workspace. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- La *[identidad administrada del Azure Synapse workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tiene permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- En Azure Synapse workspace, la *entidad de servicio para Customer Insights* tiene [rol asignado](/azure/synapse-analytics/security/how-to-set-up-access-control) de **Administrador de Synapse**.

## <a name="set-up-connection-to-azure-synapse"></a>Configurar conexiones para Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Azure Synapse Analytics**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describen esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione o busque la suscripción en la que desea utilizar los datos de Customer Insights. Tan pronto como se seleccione una suscripción, también puede seleccionar **Espacio de trabajo**, **Cuenta de almacenamiento** y **Contenedor**.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)] Para configurar la exportación con una conexión compartida, necesita al menos permisos de **Colaborador** en Customer Insights.

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Azure Synapse Analytics. Contacte con un administrador si no hay conexión disponible.

1. Proporcione un **Nombre para mostrar** reconocible para la exportación y un **Nombre de base de datos**. La exportación creará una nueva [base de datos de lago de Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) en el espacio de trabajo definido en la conexión.

1. Seleccione qué entidades desea exportar a Azure Synapse Analytics.
   > [!NOTE]
   > No se admiten orígenes de datos basados en una [carpeta de Common Data Model](connect-common-data-model.md).

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Para consultar los datos que se exportaron a Synapse Analytics, necesita acceso al **Lector de datos de blob de almacenamiento** del almacenamiento de destino en el espacio de trabajo de exportaciones.

## <a name="update-an-export"></a>Actualizar una exportación

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Editar** en la exportación que desea actualizar.

   - **Agregue** o **Elimine** entidades de la selección. Si las entidades se eliminan de la selección, no se eliminan de la base de datos de Synapse Analytics. Sin embargo, las actualizaciones de datos futuras no actualizarán las entidades eliminadas en esa base de datos.

   - **Cambio del nombre de la base de datos** crea una nueva base de datos de Synapse Analytics. La base de datos con el nombre que se configuró antes no recibirá ninguna actualización en futuras actualizaciones.

[!INCLUDE [footer-include](includes/footer-banner.md)]
