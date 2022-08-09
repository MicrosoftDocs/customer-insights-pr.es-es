---
title: Exportar datos a Azure Blob Storage (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Blob Storage.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195725"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportar datos a Azure Blob Storage (versión preliminar)

Almacene los datos de Customer Insights en Blob Storage o utilícelo para transferir los datos a otras aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

- Un nombre y clave de [cuenta de Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar el nombre y la clave, consulte [Gestionar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).
- Un [contenedor de Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitaciones conocidas

- Para Azure Blob Storage, puede elegir entre [nivel de rendimiento estándar y nivel de rendimiento Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si elige el nivel de rendimiento Premium, seleccione los [blobs de bloque premium como tipo de cuenta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Configurar la conexión a Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Azure Blob Storage**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escriba el **Nombre de la cuenta**, la **Clave de la cuenta** y el **Contenedor** para su cuenta de Blob Storage.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Para configurar esta exportación, debe tener [permiso](export-destinations.md#set-up-a-new-export) para este tipo de conexión.

> [!IMPORTANT]
> Si activó la [configuración de eliminación temporal](/azure/storage/blobs/soft-delete-blob-enable) para la cuenta de Azure Blob Storage, se producirán errores en las exportaciones. Desactive la eliminación temporal para exportar datos a blobs.

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Azure Blob Storage. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Introduzca el nombre de la carpeta para Blob Storage.

1. Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Los datos exportados se almacenan en el contenedor de Blob Storage que configuró. Las siguientes rutas de acceso a carpetas se crean automáticamente en el contenedor:

- Para entidades fuente y entidades generadas por el sistema:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > La exportación de entidades que contienen una gran cantidad de datos puede generar varios archivos CSV en la misma carpeta para cada exportación. La división de las exportaciones se produce por motivos de rendimiento para minimizar el tiempo que tarda en completarse una exportación.

- El model.json para las entidades exportadas reside en el nivel *%ExportDestinationName%*.  
  
  Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
