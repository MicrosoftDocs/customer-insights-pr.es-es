---
title: Exportar datos de Customer Insights a Azure Data Lake Storage Gen2
description: Aprenda a configurar la conexión a Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477200"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Conector para Azure Data Lake Storage Gen2 (versión preliminar)

Almacene los datos de Customer Insights en Azure Data Lake Storage Gen2 o utilícelo para transferir los datos a otras aplicaciones.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configure el conector para Azure Data Lake Storage Gen2

1. En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.

1. En **Azure Data Lake Storage Gen2**, seleccione **Configurar**.

1. Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.

1. Especifique el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para Azure Data Lake Storage Gen2.
    - Para aprender a crear una cuenta de almacenamiento para usar con Azure Data Lake Storage Gen2, vea [Crear cuenta de almacenamiento](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Para obtener más información sobre cómo encontrar el nombre de la cuenta de almacenamiento y la clave de la cuenta de Azure Data Lake Gen2, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Seleccione **Siguiente**.

1. Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md#export-data-on-demand). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).
