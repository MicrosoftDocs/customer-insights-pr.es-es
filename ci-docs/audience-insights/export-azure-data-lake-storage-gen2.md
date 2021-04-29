---
title: Exportar datos de Customer Insights a Azure Data Lake Storage Gen2
description: Aprenda a configurar la conexión a Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760072"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Configurar la conexión a Azure Data Lake Storage Gen2 (versión preliminar)

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
