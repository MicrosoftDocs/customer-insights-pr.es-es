---
title: Exportar datos de Customer Insights a Azure Blob Storage
description: Aprenda a configurar la conexión y a exportar a Blob Storage.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 42095f369c47553e5ddf5fada54e559202c943a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647748"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportar la lista de segmentos y otros datos a Azure Blob Storage (versión preliminar)

Almacene los datos de Customer Insights en Blob Storage o utilícelo para transferir los datos a otras aplicaciones.

## <a name="known-limitations"></a>Limitaciones conocidas

1. Para Azure Blob Storage, puede elegir entre [nivel de rendimiento estándar y rendimiento Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si elige el nivel de rendimiento Premium, seleccione los [blobs de bloque premium como tipo de cuenta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Configurar la conexión a Blob Storage

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Azure Blob Storage** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escriba el **Nombre de la cuenta**, la **Clave de la cuenta** y el **Contenedor** para su cuenta de Blob Storage.
    - Para obtener más información sobre cómo encontrar el nombre y la clave de la cuenta de Blob Storage, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).
    - Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Si activó la configuración de eliminación temporal para la cuenta de Azure Blob Storage, se producirán errores en las exportaciones. Desactive la eliminación temporal para exportar datos a blobs. Para obtener más información, consulte [Habilitar la eliminación temporal de blobs](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Azure Blob Storage. Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.

1. Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).     

Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

Los datos exportados se almacenan en el contenedor de Blob Storage que configuró. Las siguientes rutas de acceso a carpetas se crean automáticamente en el contenedor:

- Para entidades fuente y entidades generadas por el sistema:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Ejemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- El model.json para las entidades exportadas estará en el nivel %ExportDestinationName%.  
  - Ejemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
