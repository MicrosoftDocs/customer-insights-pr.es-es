---
title: Conector de Power BI
description: Aprenda a usar el conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596060"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="1282c-103">Conector para Power BI (vista previa)</span><span class="sxs-lookup"><span data-stu-id="1282c-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="1282c-104">Cree visualizaciones para sus datos con Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="1282c-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="1282c-105">Genere información adicional y cree informes con sus datos de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="1282c-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1282c-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1282c-106">Prerequisites</span></span>

- <span data-ttu-id="1282c-107">Tiene perfiles de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="1282c-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="1282c-108">La última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada en su ordenador.</span><span class="sxs-lookup"><span data-stu-id="1282c-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="1282c-109">[Más información acerca de Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="1282c-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="1282c-110">Configurar el conector para Power BI</span><span class="sxs-lookup"><span data-stu-id="1282c-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="1282c-111">En Power BI Desktop, seleccione **Archivo** > **Obtener datos**.</span><span class="sxs-lookup"><span data-stu-id="1282c-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="1282c-112">Seleccione **Ver más** y busque **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="1282c-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="1282c-113">Seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1282c-113">Select **Connect**.</span></span>

1. <span data-ttu-id="1282c-114">**Inicie sesión** con la misma cuenta de organización que usa para Customer Insights y seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1282c-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1282c-115">La cuenta que indique en este paso se usa para obtener datos de Customer Insights y no necesita ser la misma en la que inició sesión en Power BI.</span><span class="sxs-lookup"><span data-stu-id="1282c-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="1282c-116">Para restablecer la cuenta que se utiliza para la recuperación de datos, abra Power BI y vaya a **Archivo** > **Opciones** > **Configuración** > **Configuración de origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="1282c-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="1282c-117">En la lista de orígenes de datos, seleccione **Inicio de sesión de Dynamics 365 Customer Insights** y seleccione **Borrar permisos**.</span><span class="sxs-lookup"><span data-stu-id="1282c-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="1282c-118">En el cuadro de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="1282c-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="1282c-119">puede ver la lista de todos los entornos a los que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="1282c-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="1282c-120">Expanda un entorno y abra cualquiera de las carpetas (entidades, medidas, segmentos, enriquecimientos).</span><span class="sxs-lookup"><span data-stu-id="1282c-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="1282c-121">Por ejemplo, abra la carpeta **Entidades** para ver todas las entidades que puede importar.</span><span class="sxs-lookup"><span data-stu-id="1282c-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="1282c-122">![Navegador de conectores de Power BI](media/power-bi-navigator.png "Navegador de conectores de Power BI")</span><span class="sxs-lookup"><span data-stu-id="1282c-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="1282c-123">Seleccione las casillas de verificación junto a las entidades que quiere incluir y **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="1282c-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="1282c-124">Puede seleccionar varias entidades de múltiples entornos.</span><span class="sxs-lookup"><span data-stu-id="1282c-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="1282c-125">Verá un cuadro de diálogo de carga mientras se cargan las entidades.</span><span class="sxs-lookup"><span data-stu-id="1282c-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="1282c-126">Una vez que se hayan cargado todas las entidades seleccionadas, puede utilizar las capacidades de Power BI para visualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="1282c-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="1282c-127">Conjuntos de datos de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="1282c-127">Large data sets</span></span>

<span data-ttu-id="1282c-128">El conector Customer Insights para Power BI está diseñado para funcionar con conjuntos de datos que contienen hasta 1 millón de perfiles de clientes.</span><span class="sxs-lookup"><span data-stu-id="1282c-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="1282c-129">La importación de conjuntos de datos más grandes puede funcionar, pero lleva mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="1282c-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="1282c-130">Además, el proceso podría agotar un tiempo de espera debido a las limitaciones de Power BI.</span><span class="sxs-lookup"><span data-stu-id="1282c-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="1282c-131">Para más información, vea [Power BI: Recomendaciones para grandes conjuntos de datos](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="1282c-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="1282c-132">Trabajar con un subconjunto de datos</span><span class="sxs-lookup"><span data-stu-id="1282c-132">Work with a subset of data</span></span>

<span data-ttu-id="1282c-133">Considere trabajar con un subconjunto de sus datos.</span><span class="sxs-lookup"><span data-stu-id="1282c-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="1282c-134">Por ejemplo, puede crear [segmentos](segments.md) en lugar de exportar todos los registros de clientes a Power BI.</span><span class="sxs-lookup"><span data-stu-id="1282c-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1282c-135">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1282c-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="1282c-136">El entorno de Customer Insights no aparece en Power BI</span><span class="sxs-lookup"><span data-stu-id="1282c-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="1282c-137">Los entornos que tienen más de una [relación](relationships.md) definidas entre dos entidades idénticas en las informaciones del público no estarán disponibles en el conector de Power BI.</span><span class="sxs-lookup"><span data-stu-id="1282c-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="1282c-138">Puede identificar y eliminar las relaciones duplicadas.</span><span class="sxs-lookup"><span data-stu-id="1282c-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="1282c-139">En las informaciones del público, vaya a **Datos** > **Relaciones** en el entorno que le falta en Power BI.</span><span class="sxs-lookup"><span data-stu-id="1282c-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="1282c-140">Identifique relaciones duplicadas:</span><span class="sxs-lookup"><span data-stu-id="1282c-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="1282c-141">Compruebe si hay más de una relación definida entre las mismas dos entidades.</span><span class="sxs-lookup"><span data-stu-id="1282c-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="1282c-142">Compruebe si existe una relación creada entre dos entidades que están incluidas en el proceso de unificación.</span><span class="sxs-lookup"><span data-stu-id="1282c-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="1282c-143">Existe una relación implícita definida entre todas las entidades incluidas en el proceso de unificación.</span><span class="sxs-lookup"><span data-stu-id="1282c-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="1282c-144">Elimine las relaciones duplicadas identificadas que haya.</span><span class="sxs-lookup"><span data-stu-id="1282c-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="1282c-145">Después de eliminar las relaciones duplicadas, intente volver a configurar el conector de Power BI.</span><span class="sxs-lookup"><span data-stu-id="1282c-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="1282c-146">El entorno debería estar disponible ahora.</span><span class="sxs-lookup"><span data-stu-id="1282c-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]