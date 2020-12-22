---
title: Ingerir datos a través de un conector de Power Query
description: Conectores para orígenes de datos basados en Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407028"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="c2d5d-103">Conectar un origen de datos de Power Query</span><span class="sxs-lookup"><span data-stu-id="c2d5d-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="c2d5d-104">Power Query ofrece un amplio conjunto de conectores para ingerir datos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="c2d5d-105">La mayoría de estos conectores son compatibles con Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="c2d5d-106">Agregar orígenes de datos basados en conectores de Power Query generalmente sigue los pasos descritos en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="c2d5d-107">Sin embargo, según el conector que utilice, se requiere información diferente.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="c2d5d-108">Para obtener más información, consulte la documentación sobre conectores individuales en la [Referencia del conector de Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="c2d5d-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="c2d5d-109">Crear un nuevo origen de datos</span><span class="sxs-lookup"><span data-stu-id="c2d5d-109">Create a new data source</span></span>

1. <span data-ttu-id="c2d5d-110">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="c2d5d-111">Seleccione **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="c2d5d-112">Elija el método **Importar datos** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="c2d5d-113">Proporcione un **Nombre** para el origen de datos y seleccione **Siguiente** para crear el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="c2d5d-114">Elija uno de los [conectores disponibles](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="c2d5d-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="c2d5d-115">Para este ejemplo, seleccionamos el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c2d5d-116">Ingrese los detalles requeridos en la **Configuraciónde conexión** para el conector seleccionado y seleccione **Siguiente** para ver una vista previa de los datos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="c2d5d-117">Seleccione **Transformar datos**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-117">Select **Transform data**.</span></span> <span data-ttu-id="c2d5d-118">En este paso va a agregar entidades a su origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="c2d5d-119">Las entidades son conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-119">Entities are datasets.</span></span> <span data-ttu-id="c2d5d-120">Si tiene una base de datos que incluye múltiples conjuntos de datos, cada conjunto de datos es su propia entidad.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="c2d5d-121">El diálogo **Power Query - Editar consultas** le permite revisar y refinar los datos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="c2d5d-122">Las entidades que los sistemas identificaron en el origen de datos seleccionado se muestran en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2d5d-123">![Diálogo Editar consultas](media/data-manager-configure-edit-queries.png "Diálogo Editar consultas")</span><span class="sxs-lookup"><span data-stu-id="c2d5d-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="c2d5d-124">También puede transformar los datos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-124">You can also transform your data.</span></span> <span data-ttu-id="c2d5d-125">Seleccione una entidad para editarla o transformarla.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="c2d5d-126">Utilice las opciones de la ventana Power Query para aplicar transformaciones.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="c2d5d-127">Cada transformación se enumera en **Pasos aplicados**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="c2d5d-128">Power Query proporciona numerosas opciones de transformación prediseñadas.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="c2d5d-129">Para obtener más información, vea [Transformaciones de Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="c2d5d-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="c2d5d-130">Puede agregar entidades adicionales a su origen de datos seleccionando **Obtener datos** en el cuadro de diálogo **Editar consultas**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="c2d5d-131">Estas transformaciones son muy recomendables:</span><span class="sxs-lookup"><span data-stu-id="c2d5d-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="c2d5d-132">Si está ingiriendo datos de un archivo CSV, la primera fila suele contener encabezados.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="c2d5d-133">Vaya a **Transformar tabla** y seleccione **Usar encabezados como primera fila**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="c2d5d-134">Asegúrese de que el tipo de datos esté configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="c2d5d-135">Seleccione **Guardar** en la esquina inferior derecha de la ventana Power Query para guardar las transformaciones.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="c2d5d-136">Después de guardar, encontrará su origen de datos en **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="c2d5d-137">En la página **Orígenes de datos** observará que el nuevo origen de datos está en estado **Actualizando**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="c2d5d-138">Orígenes de datos de Power Query disponibles</span><span class="sxs-lookup"><span data-stu-id="c2d5d-138">Available Power Query data sources</span></span>

<span data-ttu-id="c2d5d-139">Vea la [Referencia del conector de Power Query](https://docs.microsoft.com/power-query/connectors/) para obtener una lista actualizada de conectores que puede seleccionar para importar datos a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="c2d5d-140">Los conectores con una marca de verificación en la columna **Customer Insights (flujos de datos)** están disponibles para crear nuevos orígenes de datos basados en Power Query.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="c2d5d-141">Revise la documentación de un conector específico para obtener más información sobre sus requisitos previos, limitaciones y otros detalles.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="c2d5d-142">Editar orígenes de datos de Power Query</span><span class="sxs-lookup"><span data-stu-id="c2d5d-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="c2d5d-143">Es posible que no se puedan realizar cambios en los orígenes de datos que se están utilizando actualmente en uno de los procesos de la aplicación ( *segmentación*, *coincidencia* o *combinación*, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="c2d5d-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="c2d5d-144">En la página **Configuración** puede realizar un seguimiento del progreso de cada uno de los procesos activos.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="c2d5d-145">Cuando se completa un proceso, puede volver a la página **Orígenes de datos** y hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="c2d5d-146">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c2d5d-147">Seleccione los puntos suspensivos verticales junto al origen de datos que desea cambiar y seleccione **Editar** desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2d5d-148">![Editar opción](media/edit-option-data-sources.png "Editar opción")</span><span class="sxs-lookup"><span data-stu-id="c2d5d-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="c2d5d-149">Aplique sus cambios y transformaciones en el diálogo **Power Query - Editar consultas** como se describe en la sección [Crear un origen de datos nuevo](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="c2d5d-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="c2d5d-150">Seleccione **Guardar** en Power Query después de completar sus ediciones para guardar sus cambios.</span><span class="sxs-lookup"><span data-stu-id="c2d5d-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
