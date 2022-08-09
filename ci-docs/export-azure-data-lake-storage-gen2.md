---
title: Exportar datos a Azure Data Lake Storage Gen2 (vista previa)
description: Aprenda a configurar la conexión a Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196461"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar datos a Azure Data Lake Storage Gen2 (vista previa)

Almacene los datos de Customer Insights en una cuenta de Data Lake Storage Gen2 o utilícelo para transferir los datos a otras aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de almacenamiento para usar con Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar el nombre y la clave de la cuenta de almacenamiento, consulte [Gestionar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).
- Un [contenedor de Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitaciones conocidas

- Para Azure Data Lake Storage Gen2, elija entre [nivel de rendimiento estándar y nivel de rendimiento Premium](/azure/storage/blobs/create-data-lake-storage-account). Si elige el nivel de rendimiento Premium, seleccione los [blobs de bloque premium como tipo de cuenta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Configurar la conexión con Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Azure Data Lake Gen 2**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para Azure Data Lake Storage Gen2.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Azure Data Lake. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Introduzca el nombre de la carpeta del almacenamiento de Azure Data Lake Storage Gen2.

1. Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Los datos exportados se almacenan en el contenedor de almacenamiento de Azure Data Lake Storage Gen2 que configuró.

> [!TIP]
> La exportación de entidades que contienen una gran cantidad de datos puede generar varios archivos CSV en la misma carpeta para cada exportación. La división de las exportaciones se produce por motivos de rendimiento para minimizar el tiempo que tarda en completarse una exportación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
