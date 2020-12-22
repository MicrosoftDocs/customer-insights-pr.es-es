---
title: Conector de Power BI
description: Aprenda a usar el conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407009"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="25fc8-103">Conector para Power BI (vista previa)</span><span class="sxs-lookup"><span data-stu-id="25fc8-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="25fc8-104">Cree visualizaciones para sus datos con Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="25fc8-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="25fc8-105">Genere información adicional y cree informes con sus datos de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="25fc8-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25fc8-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="25fc8-106">Prerequisites</span></span>

- <span data-ttu-id="25fc8-107">Tiene perfiles de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="25fc8-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="25fc8-108">La última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalado en su equipo.</span><span class="sxs-lookup"><span data-stu-id="25fc8-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="25fc8-109">[Más información acerca de Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="25fc8-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="25fc8-110">Configurar el conector para Power BI</span><span class="sxs-lookup"><span data-stu-id="25fc8-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="25fc8-111">En Power BI Desktop, seleccione **Archivo** > **Obtener datos**.</span><span class="sxs-lookup"><span data-stu-id="25fc8-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="25fc8-112">Seleccione **Ver más** y busque **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="25fc8-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="25fc8-113">Seleccione el resultado y seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="25fc8-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="25fc8-114">**Inicie sesión** con la misma cuenta de organización que usa para Customer Insights y seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="25fc8-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="25fc8-115">La cuenta que indique en este paso se usa para obtener datos de Customer Insights y no necesita ser la misma en la que inició sesión en Power BI.</span><span class="sxs-lookup"><span data-stu-id="25fc8-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="25fc8-116">Para restablecer la cuenta que se utiliza para la recuperación de datos, abra Power BI y vaya a **Archivo** > **Opciones** > **Configuración** > **Configuración de origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="25fc8-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="25fc8-117">En la lista de orígenes de datos, seleccione **Inicio de sesión de Dynamics 365 Customer Insights** y seleccione **Borrar permisos**.</span><span class="sxs-lookup"><span data-stu-id="25fc8-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="25fc8-118">En el cuadro de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="25fc8-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="25fc8-119">puede ver la lista de todos los entornos a los que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="25fc8-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="25fc8-120">Expanda un entorno y abra cualquiera de las carpetas (entidades, medidas, segmentos, enriquecimientos).</span><span class="sxs-lookup"><span data-stu-id="25fc8-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="25fc8-121">Por ejemplo, abra la carpeta **Entidades** para ver todas las entidades que puede importar.</span><span class="sxs-lookup"><span data-stu-id="25fc8-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="25fc8-122">![Navegador de conectores de Power BI](media/power-bi-navigator.png "Navegador de conectores de Power BI")</span><span class="sxs-lookup"><span data-stu-id="25fc8-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="25fc8-123">Seleccione las casillas de verificación junto a las entidades que quiere incluir y **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="25fc8-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="25fc8-124">Puede seleccionar varias entidades de múltiples entornos.</span><span class="sxs-lookup"><span data-stu-id="25fc8-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="25fc8-125">Verá un cuadro de diálogo de carga mientras se cargan las entidades.</span><span class="sxs-lookup"><span data-stu-id="25fc8-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="25fc8-126">Una vez que se hayan cargado todas las entidades seleccionadas, puede utilizar las capacidades de Power BI para visualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="25fc8-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="25fc8-127">Conjuntos de datos de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="25fc8-127">Large data sets</span></span>

<span data-ttu-id="25fc8-128">El conector Customer Insights para Power BI está diseñado para funcionar con conjuntos de datos que contienen hasta 1 millón de perfiles de clientes.</span><span class="sxs-lookup"><span data-stu-id="25fc8-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="25fc8-129">La importación de conjuntos de datos más grandes puede funcionar, pero lleva mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="25fc8-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="25fc8-130">Además, el proceso podría agotar un tiempo de espera debido a las limitaciones de Power BI.</span><span class="sxs-lookup"><span data-stu-id="25fc8-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="25fc8-131">Para más información, vea [Power BI: Recomendaciones para grandes conjuntos de datos](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="25fc8-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="25fc8-132">Trabajar con un subconjunto de datos</span><span class="sxs-lookup"><span data-stu-id="25fc8-132">Work with a subset of data</span></span>

<span data-ttu-id="25fc8-133">Considere trabajar con un subconjunto de sus datos.</span><span class="sxs-lookup"><span data-stu-id="25fc8-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="25fc8-134">Por ejemplo, puede crear [segmentos](segments.md) en lugar de exportar todos los registros de clientes a Power BI.</span><span class="sxs-lookup"><span data-stu-id="25fc8-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
