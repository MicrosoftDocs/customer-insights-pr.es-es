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
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="58c47-103">Conector para Azure Data Lake Storage Gen2 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="58c47-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="58c47-104">Almacene los datos de Customer Insights en Azure Data Lake Storage Gen2 o utilícelo para transferir los datos a otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="58c47-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="58c47-105">Configure el conector para Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="58c47-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="58c47-106">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="58c47-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="58c47-107">En **Azure Data Lake Storage Gen2**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="58c47-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="58c47-108">Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="58c47-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="58c47-109">Especifique el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="58c47-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="58c47-110">Para aprender a crear una cuenta de almacenamiento para usar con Azure Data Lake Storage Gen2, vea [Crear cuenta de almacenamiento](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="58c47-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="58c47-111">Para obtener más información sobre cómo encontrar el nombre de la cuenta de almacenamiento y la clave de la cuenta de Azure Data Lake Gen2, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="58c47-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="58c47-112">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="58c47-112">Select **Next**.</span></span>

1. <span data-ttu-id="58c47-113">Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.</span><span class="sxs-lookup"><span data-stu-id="58c47-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="58c47-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="58c47-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="58c47-115">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="58c47-115">Export the data</span></span>

<span data-ttu-id="58c47-116">Puede [exportar datos a petición](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="58c47-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="58c47-117">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="58c47-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
