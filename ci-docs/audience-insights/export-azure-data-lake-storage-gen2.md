---
title: Exportar datos de Customer Insights a Azure Data Lake Storage Gen2
description: Aprenda a configurar la conexión a Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596661"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Conector para Azure Data Lake Storage Gen2 (versión preliminar)

Almacene los datos de Customer Insights en Azure Data Lake Storage Gen2 o utilícelo para transferir los datos a otras aplicaciones.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configure el conector para Azure Data Lake Storage Gen2

1. En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.

1. En **Azure Data Lake Storage Gen2**, seleccione **Configurar**.

1. Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.

1. Especifique el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para Azure Data Lake Storage Gen2.
    - Para aprender a crear una cuenta de almacenamiento para usar con Azure Data Lake Storage Gen2, vea [Crear cuenta de almacenamiento](/azure/storage/blobs/create-data-lake-storage-account). 
    - Para obtener más información sobre cómo encontrar el nombre de la cuenta de almacenamiento y la clave de la cuenta de Azure Data Lake Gen2, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).

1. Seleccione **Siguiente**.

1. Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md#export-data-on-demand). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).