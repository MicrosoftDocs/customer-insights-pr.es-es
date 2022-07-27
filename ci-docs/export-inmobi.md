---
title: Exporte datos de Customer Insights a InMobi
description: Aprenda a configurar la conexión y a exportar a InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056551"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exportar lista de segmentos y otros datos a InMobi (versión preliminar)

Exporte listas de segmentos u otros datos de su instancia de Customer Insights a [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Requisitos previos

1. Tienes una [Cuenta InMobi](https://www.inmobi.com/) y credenciales de administrador.
1. Tiene un nombre de cuenta de Azure Blob Storage y la clave de cuenta correspondiente. Para más información, consulte [Gestionar la configuración de la cuenta de almacenamiento en el portal de Azure](/azure/storage/common/storage-account-manage). Hay un contenedor en la cuenta de almacenamiento para exportar datos de inMobi. Para obtener más información, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi creará una conexión directa a su Blob Storage y configurará una importación automática de sus datos a InMobi. Comuníquese con su representante de InMobi para iniciar el proceso.

## <a name="known-limitations"></a>Limitaciones conocidas

1. Para Azure Blob Storage, puede elegir entre [nivel de rendimiento estándar y rendimiento Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si elige el nivel de rendimiento Premium, seleccione los [blobs de bloque premium como tipo de cuenta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Configurar la conexión a Azure Blob Storage y configurar una exportación

1. Siga las instrucciones para [configurar una conexión a su Azure Blob Storage](export-azure-blob-storage.md).
2. Siga las instrucciones para [configurar una exportación](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
