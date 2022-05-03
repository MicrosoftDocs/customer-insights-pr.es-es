---
title: Exportar datos de Customer Insights a Azure Data Lake Storage Gen2
description: Aprenda a configurar la conexión a Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8b14992f8312d333d8a12501e8a28496c8434779
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647648"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar lista de segmentos y otros datos a Azure Data Lake Storage Gen2 (versión preliminar)

Almacene los datos de Customer Insights en una cuenta de Data Lake Storage Gen2 o utilícelo para transferir los datos a otras aplicaciones.

## <a name="known-limitations"></a>Limitaciones conocidas

1. Para Azure Data Lake Storage Gen2 puede elegir entre [nivel de rendimiento estándar y rendimiento premium](/azure/storage/blobs/create-data-lake-storage-account) cuando crea una cuenta de almacenamiento para su lago de datos. Si elige el nivel de rendimiento Premium, seleccione los blobs de bloque premium como tipo de cuenta. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Configurar la conexión con Azure Data Lake Storage Gen2 


1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Azure Data Lake Gen2** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para Azure Data Lake Storage Gen2.
    - Para aprender a crear una cuenta de almacenamiento para usar con Azure Data Lake Storage Gen2, vea [Crear cuenta de almacenamiento](/azure/storage/blobs/create-data-lake-storage-account). 
    - Para obtener más información sobre cómo encontrar el nombre y la clave de la cuenta de Azure Data Lake Storage Gen2, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección **Azure Data Lake**. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

Los datos exportados se almacenan en el contenedor de almacenamiento de Azure Data Lake Storage Gen2 que configuró. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
