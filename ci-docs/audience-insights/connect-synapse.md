---
title: Ingerir datos de Azure Synapse Analytics
description: Use una base de datos de Azure Synapse como origen de datos en Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356031"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Conectar un origen de datos de Azure Synapse (versión preliminar)

Azure Synapse Analytics es un servicio de análisis empresarial que acelera el tiempo de obtención de información en los almacenamientos de datos y los sistemas de macrodatos. Azure Synapse Analytics reúne lo mejor de las tecnologías SQL usadas en el almacenamiento de datos empresariales, las tecnologías Spark utilizadas para macrodatos, explorador de datos para el análisis de registros y series temporales, canalizaciones para la integración de datos y ETL/ELT, y una profunda integración con otros servicios de Azure como Power BI, Cosmos DB y AzureML.

Para obtener más información, consulte [Vista general de Azure Synapse](/azure/synapse-analytics/overview-what-is)

## <a name="prerequisites"></a>Requisitos previos

Se deben cumplir los siguientes requisitos previos para configurar la conexión de Customer Insights a Azure Synapse.

> [!IMPORTANT]
> Asegúrese de configurar todas las **asignaciones de roles** como se describe.  

## <a name="prerequisites-in-customer-insights"></a>Requisitos previos en Customer Insights

* Tiene rol de **administrador** en Customer Insights. Más información acerca de [permisos de usuario en conclusiones del público](permissions.md#assign-roles-and-permissions).

En Azure: 

- Una suscripción de Azure activa.

- Si usa una nueva cuenta de Azure Data Lake Storage Gen2, la *entidad de servicio para conocimientos del público* necesita permisos de **Contribuyente de datos de Storage Blob**. Más información acerca de la [conexión a un Azure Data Lake Storage con una entidad de servicio para conclusiones del público](connect-service-principal.md). Data Lake Storage Gen2 **debe** tener activado el [espacio de nombres jerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- En el grupo de recursos donde se encuentra el espacio de trabajo de Azure Synapse, la *entidad de servicio* y el *usuario para conclusiones del público* deben tener asignados al menos permisos de **Lector**. Para más información, vea [Asignar roles de Azure mediante el portal de Azure](/azure/role-based-access-control/role-assignments-portal).

- El *usuario* necesita permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- La *[identidad administrada del espacio de trabajo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* necesita permisos de **Colaborador de datos de Storage Blob** en la cuenta de Azure Data Lake Storage Gen2 donde se ubican los datos y están vinculados al espacio de trabajo de Azure Synapse. Más información sobre [Uso del portal de Azure para asignar un rol de Azure para acceder a datos de blobs y colas](/azure/storage/common/storage-auth-aad-rbac-portal) y [Permisos de colaborador de datos de Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- En el espacio de trabajo de Azure Synapse, la *entidad de servicio para conclusiones del público* necesita tener asignado el rol **Administrador de Synapse**. Para más información, vea [Cómo configurar el control de acceso para su espacio de trabajo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Conectar a las bases de datos de lago de datos en Azure Synapse Analytics

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione **Agregar origen de datos**.

1. Elija el método **Azure Synapse Analytics (Versión preliminar)**.

1. Proporcione un **Nombre** para el origen de datos y seleccione **Siguiente** para crear el origen de datos. 

1. Elija una [conexión disponible](connections.md) a Azure Synapse Analytics o cree una nueva.

1. Elija una **base de datos de lago** del espacio de trabajo en la conexión de Azure Synapse Analytics seleccionada y seleccione **Siguiente**.

1. Seleccione las entidades que desea ingerir de la base de datos conectada. 

1. Opcionalmente, elija las entidades de datos sobre las que desea permitir la generación de perfiles de datos. 

1. Seleccione **Guardar** para aplicar su selección e iniciar la ingestión de los datos de su origen de datos recién creado y vinculado a las tablas de la base de datos de Azure Synapse Analytics.
