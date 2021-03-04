---
title: Exportar datos de Customer Insights a Azure Blob Storage
description: Aprenda a configurar la conexión al Azure Blob Storage.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269213"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Conector para Azure Blob Storage (versión preliminar)

Almacene los datos de Customer Insights en Azure Blob Storage o úselos para transferir los datos a otras aplicaciones.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configurar el conector para Azure Blob Storage

1. En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.

1. En **Azure Blob Storage**, seleccione **Configurar**.

1. Especifique los valores de **Nombre de cuenta**, **Clave de cuenta** y **Contenedor** para su cuenta de Azure Blob Storage.
    - Para obtener más información sobre cómo encontrar el nombre y la clave de cuenta de almacenamiento de blobs de Azure, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.

1. Seleccione **Siguiente**.

1. Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.

1. Seleccione **Guardar**.

Los datos exportados se almacenan en el contenedor de Azure Blob Storage que configuró. Las siguientes rutas de acceso a carpetas se crean automáticamente en el contenedor:

- Para entidades fuente y entidades generadas por el sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Ejemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- El model.json de las entidades exportadas residirá en el nivel %ExportDestinationName%
  - Ejemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md#export-data-on-demand). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]