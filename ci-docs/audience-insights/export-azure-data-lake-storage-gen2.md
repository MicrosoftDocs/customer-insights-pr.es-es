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
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="c69b0-103">Configurar la conexión a Azure Data Lake Storage Gen2 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c69b0-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="c69b0-104">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="c69b0-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c69b0-105">Seleccione **Agregar conexión** y elija **Azure Data Lake Gen2** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="c69b0-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="c69b0-106">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="c69b0-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c69b0-107">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c69b0-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c69b0-108">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="c69b0-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c69b0-109">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c69b0-109">Choose who can use this connection.</span></span> <span data-ttu-id="c69b0-110">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="c69b0-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c69b0-111">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c69b0-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c69b0-112">Especifique el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="c69b0-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="c69b0-113">Para aprender a crear una cuenta de almacenamiento para usar con Azure Data Lake Storage Gen2, vea [Crear cuenta de almacenamiento](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="c69b0-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="c69b0-114">Para obtener más información sobre cómo encontrar el nombre y la clave de la cuenta de Azure Data Lake Storage Gen2, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c69b0-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="c69b0-115">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="c69b0-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="c69b0-116">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="c69b0-116">Configure an export</span></span>

<span data-ttu-id="c69b0-117">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="c69b0-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c69b0-118">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c69b0-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c69b0-119">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="c69b0-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c69b0-120">Para crear una nueva exportación, **Agregar exportación**.</span><span class="sxs-lookup"><span data-stu-id="c69b0-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c69b0-121">En el campo **Conexión para exportación**, elija una conexión de la sección **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="c69b0-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="c69b0-122">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="c69b0-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c69b0-123">Seleccione la casilla junto a cada una de las entidades que desea exportar a este destino.</span><span class="sxs-lookup"><span data-stu-id="c69b0-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c69b0-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c69b0-124">Select **Save**.</span></span>

<span data-ttu-id="c69b0-125">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c69b0-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c69b0-126">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c69b0-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c69b0-127">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c69b0-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="c69b0-128">Los datos exportados se almacenan en el contenedor de almacenamiento de Azure Data Lake Storage Gen2 que configuró.</span><span class="sxs-lookup"><span data-stu-id="c69b0-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
