---
title: Ingerir datos a través de un conector de Power Query
description: Conectores para orígenes de datos basados en Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596934"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="3f145-103">Conectar un origen de datos de Power Query</span><span class="sxs-lookup"><span data-stu-id="3f145-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="3f145-104">Power Query ofrece un amplio conjunto de conectores para ingerir datos.</span><span class="sxs-lookup"><span data-stu-id="3f145-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="3f145-105">La mayoría de estos conectores son compatibles con Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3f145-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="3f145-106">Agregar orígenes de datos basados en conectores de Power Query generalmente sigue los pasos descritos en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="3f145-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="3f145-107">Sin embargo, según el conector que utilice, se requiere información diferente.</span><span class="sxs-lookup"><span data-stu-id="3f145-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="3f145-108">Para obtener más información, consulte la documentación sobre conectores individuales en la [Referencia del conector de Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="3f145-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="3f145-109">Crear un nuevo origen de datos</span><span class="sxs-lookup"><span data-stu-id="3f145-109">Create a new data source</span></span>

1. <span data-ttu-id="3f145-110">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="3f145-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="3f145-111">Seleccione **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="3f145-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="3f145-112">Elija el método **Importar datos** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3f145-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="3f145-113">Proporcione un **Nombre** para el origen de datos y seleccione **Siguiente** para crear el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3f145-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="3f145-114">Directrices de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="3f145-114">Name guidelines:</span></span> 
   - <span data-ttu-id="3f145-115">Empiece con una letra.</span><span class="sxs-lookup"><span data-stu-id="3f145-115">Start with a letter.</span></span>
   - <span data-ttu-id="3f145-116">Utilice solo letras y números.</span><span class="sxs-lookup"><span data-stu-id="3f145-116">Use letters and numbers only.</span></span> <span data-ttu-id="3f145-117">No se permiten caracteres especiales ni espacios.</span><span class="sxs-lookup"><span data-stu-id="3f145-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="3f145-118">Utilice entre 3 y 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3f145-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="3f145-119">Elija uno de los [conectores disponibles](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="3f145-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="3f145-120">Para este ejemplo, seleccionamos el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="3f145-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3f145-121">Ingrese los detalles requeridos en la **Configuraciónde conexión** para el conector seleccionado y seleccione **Siguiente** para ver una vista previa de los datos.</span><span class="sxs-lookup"><span data-stu-id="3f145-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="3f145-122">Seleccione **Transformar datos**.</span><span class="sxs-lookup"><span data-stu-id="3f145-122">Select **Transform data**.</span></span> <span data-ttu-id="3f145-123">En este paso va a agregar entidades a su origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3f145-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="3f145-124">Las entidades son conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="3f145-124">Entities are datasets.</span></span> <span data-ttu-id="3f145-125">Si tiene una base de datos que incluye múltiples conjuntos de datos, cada conjunto de datos es su propia entidad.</span><span class="sxs-lookup"><span data-stu-id="3f145-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="3f145-126">El diálogo **Power Query - Editar consultas** le permite revisar y refinar los datos.</span><span class="sxs-lookup"><span data-stu-id="3f145-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="3f145-127">Las entidades que los sistemas identificaron en el origen de datos seleccionado se muestran en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="3f145-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3f145-128">![Diálogo Editar consultas](media/data-manager-configure-edit-queries.png "Diálogo Editar consultas")</span><span class="sxs-lookup"><span data-stu-id="3f145-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="3f145-129">También puede transformar los datos.</span><span class="sxs-lookup"><span data-stu-id="3f145-129">You can also transform your data.</span></span> <span data-ttu-id="3f145-130">Seleccione una entidad para editarla o transformarla.</span><span class="sxs-lookup"><span data-stu-id="3f145-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="3f145-131">Utilice las opciones de la ventana Power Query para aplicar transformaciones.</span><span class="sxs-lookup"><span data-stu-id="3f145-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="3f145-132">Cada transformación se enumera en **Pasos aplicados**.</span><span class="sxs-lookup"><span data-stu-id="3f145-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="3f145-133">Power Query proporciona numerosas opciones de transformación prediseñadas.</span><span class="sxs-lookup"><span data-stu-id="3f145-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="3f145-134">Para obtener más información, vea [Transformaciones de Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="3f145-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="3f145-135">Puede agregar entidades adicionales a su origen de datos seleccionando **Obtener datos** en el cuadro de diálogo **Editar consultas**.</span><span class="sxs-lookup"><span data-stu-id="3f145-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="3f145-136">Estas transformaciones son muy recomendables:</span><span class="sxs-lookup"><span data-stu-id="3f145-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="3f145-137">Si está ingiriendo datos de un archivo CSV, la primera fila suele contener encabezados.</span><span class="sxs-lookup"><span data-stu-id="3f145-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="3f145-138">Vaya a **Transformar tabla** y seleccione **Usar encabezados como primera fila**.</span><span class="sxs-lookup"><span data-stu-id="3f145-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="3f145-139">Asegúrese de que el tipo de datos esté configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3f145-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="3f145-140">Seleccione **Guardar** en la esquina inferior derecha de la ventana Power Query para guardar las transformaciones.</span><span class="sxs-lookup"><span data-stu-id="3f145-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="3f145-141">Después de guardar, encontrará su origen de datos en **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="3f145-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="3f145-142">En la página **Orígenes de datos** observará que el nuevo origen de datos está en estado **Actualizando**.</span><span class="sxs-lookup"><span data-stu-id="3f145-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="3f145-143">Orígenes de datos de Power Query disponibles</span><span class="sxs-lookup"><span data-stu-id="3f145-143">Available Power Query data sources</span></span>

<span data-ttu-id="3f145-144">Vea la [Referencia del conector de Power Query](/power-query/connectors/) para obtener una lista actualizada de conectores que puede seleccionar para importar datos a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3f145-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="3f145-145">Los conectores con una marca de verificación en la columna **Customer Insights (flujos de datos)** están disponibles para crear nuevos orígenes de datos basados en Power Query.</span><span class="sxs-lookup"><span data-stu-id="3f145-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="3f145-146">Revise la documentación de un conector específico para obtener más información sobre sus requisitos previos, limitaciones y otros detalles.</span><span class="sxs-lookup"><span data-stu-id="3f145-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="3f145-147">Editar orígenes de datos de Power Query</span><span class="sxs-lookup"><span data-stu-id="3f145-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="3f145-148">Es posible que no se puedan realizar cambios en los orígenes de datos que se están utilizando actualmente en uno de los procesos de la aplicación ( *segmentación*, *coincidencia* o *combinación*, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="3f145-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="3f145-149">En la página **Configuración** puede realizar un seguimiento del progreso de cada uno de los procesos activos.</span><span class="sxs-lookup"><span data-stu-id="3f145-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="3f145-150">Cuando se completa un proceso, puede volver a la página **Orígenes de datos** y hacer cambios.</span><span class="sxs-lookup"><span data-stu-id="3f145-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="3f145-151">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="3f145-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="3f145-152">Seleccione los puntos suspensivos verticales junto al origen de datos que desea cambiar y seleccione **Editar** desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f145-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3f145-153">![Editar opción](media/edit-option-data-sources.png "Editar opción")</span><span class="sxs-lookup"><span data-stu-id="3f145-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="3f145-154">Aplique sus cambios y transformaciones en el diálogo **Power Query - Editar consultas** como se describe en la sección [Crear un origen de datos nuevo](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="3f145-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="3f145-155">Seleccione **Guardar** en Power Query después de completar sus ediciones para guardar sus cambios.</span><span class="sxs-lookup"><span data-stu-id="3f145-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]