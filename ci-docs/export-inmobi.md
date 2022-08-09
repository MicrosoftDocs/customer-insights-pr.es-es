---
title: Exporte datos de Customer Insights a InMobi
description: Aprenda a configurar la conexión y a exportar a InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195909"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exporte datos de Customer Insights a InMobi (versión preliminar)

Exporte listas de segmentos u otros datos de su instancia de Customer Insights a [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Requisitos previos

- Una [Cuenta de InMobi](https://www.inmobi.com/) y credenciales de administrador.
- Un nombre y clave de [cuenta de Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar el nombre y la clave, consulte [Gestionar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).
- Un [contenedor de Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) para exportar datos a InMobi.
- InMobi creará una conexión directa a su Blob Storage y configurará una importación automática de sus datos a InMobi. Comuníquese con su representante de InMobi para iniciar el proceso.

## <a name="known-limitations"></a>Limitaciones conocidas

- Para Azure Blob Storage, puede elegir entre [nivel de rendimiento estándar y nivel de rendimiento Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si elige el nivel de rendimiento Premium, seleccione los [blobs de bloque premium como tipo de cuenta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configurar la conexión a Azure Blob Storage

[Configurar una conexión a Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurar una exportación

[Configure una exportación](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
