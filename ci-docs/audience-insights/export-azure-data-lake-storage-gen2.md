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
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="bfba1-103">Conector para Azure Data Lake Storage Gen2 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="bfba1-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="bfba1-104">Almacene los datos de Customer Insights en Azure Data Lake Storage Gen2 o utilícelo para transferir los datos a otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bfba1-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="bfba1-105">Configure el conector para Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="bfba1-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="bfba1-106">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="bfba1-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bfba1-107">En **Azure Data Lake Storage Gen2**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="bfba1-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="bfba1-108">Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="bfba1-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bfba1-109">Especifique el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="bfba1-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="bfba1-110">Para aprender a crear una cuenta de almacenamiento para usar con Azure Data Lake Storage Gen2, vea [Crear cuenta de almacenamiento](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="bfba1-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="bfba1-111">Para obtener más información sobre cómo encontrar el nombre de la cuenta de almacenamiento y la clave de la cuenta de Azure Data Lake Gen2, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bfba1-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="bfba1-112">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bfba1-112">Select **Next**.</span></span>

1. <span data-ttu-id="bfba1-113">Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.</span><span class="sxs-lookup"><span data-stu-id="bfba1-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="bfba1-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bfba1-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bfba1-115">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="bfba1-115">Export the data</span></span>

<span data-ttu-id="bfba1-116">Puede [exportar datos a petición](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bfba1-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="bfba1-117">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bfba1-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>