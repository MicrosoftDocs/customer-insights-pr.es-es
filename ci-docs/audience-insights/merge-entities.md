---
title: Fusionar entidades en la unificación de datos
description: Fusionar entidades para crear perfiles de cliente unificados.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896532"
---
# <a name="merge-entities"></a><span data-ttu-id="a31e9-103">Combinar entidades</span><span class="sxs-lookup"><span data-stu-id="a31e9-103">Merge entities</span></span>

<span data-ttu-id="a31e9-104">La fase de combinación es la última fase del proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="a31e9-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="a31e9-105">Su propósito es conciliar datos en conflicto.</span><span class="sxs-lookup"><span data-stu-id="a31e9-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="a31e9-106">Los ejemplos de datos en conflicto podrían incluir un nombre de cliente que se encuentra en dos de sus conjuntos de datos pero que se muestra de manera un poco diferente en cada uno ("Grant Marshall" y "Grant Marshal"), o un número de teléfono que difiere en formato (617-803-091X y 617803091X).</span><span class="sxs-lookup"><span data-stu-id="a31e9-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="a31e9-107">La combinación de esos puntos de datos en conflicto se realiza atributo por atributo.</span><span class="sxs-lookup"><span data-stu-id="a31e9-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="a31e9-108">Después de completar la [fase de coincidencia](match-entities.md), comience la fase de combinación seleccionando la ventana **Combinar** en la página **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="a31e9-109">Revisar recomendaciones del sistema</span><span class="sxs-lookup"><span data-stu-id="a31e9-109">Review system recommendations</span></span>

<span data-ttu-id="a31e9-110">En la página **Combinar**, puede elegir y excluir los atributos que se combinarán en la entidad de perfil de cliente unificado (el resultado del proceso de configuración).</span><span class="sxs-lookup"><span data-stu-id="a31e9-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="a31e9-111">El sistema combina automáticamente algunos atributos.</span><span class="sxs-lookup"><span data-stu-id="a31e9-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="a31e9-112">Ver atributos combinados</span><span class="sxs-lookup"><span data-stu-id="a31e9-112">View merged attributes</span></span>

<span data-ttu-id="a31e9-113">Para ver los atributos que se incluyen en uno de sus atributos combinados automáticamente, seleccione ese atributo combinado.</span><span class="sxs-lookup"><span data-stu-id="a31e9-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="a31e9-114">Los dos atributos que componen ese atributo combinado aparecen en dos filas nuevas debajo del atributo combinado.</span><span class="sxs-lookup"><span data-stu-id="a31e9-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a31e9-115">![Seleccionar atributo combinado](media/configure-data-merge-profile-attributes.png "Seleccionar atributo combinado")</span><span class="sxs-lookup"><span data-stu-id="a31e9-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="a31e9-116">Separar atributos combinados</span><span class="sxs-lookup"><span data-stu-id="a31e9-116">Separate merged attributes</span></span>

<span data-ttu-id="a31e9-117">Para separar o combinar cualquiera de los atributos combinados automáticamente, busque el atributo en la tabla **Atributos del perfil**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="a31e9-118">Seleccione el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="a31e9-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="a31e9-119">En la lista desplegable, seleccione **Campos separados**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="a31e9-120">Quitar atributos combinados</span><span class="sxs-lookup"><span data-stu-id="a31e9-120">Remove merged attributes</span></span>

<span data-ttu-id="a31e9-121">Para excluir un atributo de la entidad del perfil del cliente final, búsquelo en la tabla **Atributos de perfil**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="a31e9-122">Seleccione el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="a31e9-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="a31e9-123">En la lista desplegable, seleccione **No combinar**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="a31e9-124">El atributo pasa a la sección **Quitado de los registros de cliente**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="a31e9-125">Agregar manualmente un atributo combinado</span><span class="sxs-lookup"><span data-stu-id="a31e9-125">Manually add a merged attribute</span></span>

<span data-ttu-id="a31e9-126">Para agregar un atributo combinado, vaya a la página **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="a31e9-127">Seleccione **Agregar atributo combinado**.</span><span class="sxs-lookup"><span data-stu-id="a31e9-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="a31e9-128">Proporcione un **Nombre** para identificarlo en la página **Combinar** más tarde.</span><span class="sxs-lookup"><span data-stu-id="a31e9-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="a31e9-129">Opcionalmente, proporcione un **Nombre para mostrar** que aparece en la entidad del perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="a31e9-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="a31e9-130">Configure **Seleccionar atributos duplicados** para seleccionar los atributos que desea combinar desde las entidades coincidentes.</span><span class="sxs-lookup"><span data-stu-id="a31e9-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="a31e9-131">También puede buscar atributos.</span><span class="sxs-lookup"><span data-stu-id="a31e9-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="a31e9-132">Establezca **Clasificar por importancia** para priorizar un atributo sobre los demás.</span><span class="sxs-lookup"><span data-stu-id="a31e9-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="a31e9-133">Por ejemplo, si la entidad *WebAccountCSV* incluye los datos más precisos sobre el atributo *Nombres completos*, podría priorizar esta entidad sobre *ContactCSV* seleccionando *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="a31e9-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="a31e9-134">Por ello, *WebAccountCSV* pasa a primera prioridad, mientras que *ContactCSV* pasa a la segunda prioridad al extraer valores para el atributo *Nombre completo*.</span><span class="sxs-lookup"><span data-stu-id="a31e9-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="a31e9-135">Ejecutar la combinación</span><span class="sxs-lookup"><span data-stu-id="a31e9-135">Run your merge</span></span>

<span data-ttu-id="a31e9-136">Tanto si combina manualmente atributos como si deja que el sistema los combine, siempre puede ejecutar su combinación.</span><span class="sxs-lookup"><span data-stu-id="a31e9-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="a31e9-137">Seleccione **Ejecutar** en la página **Combinación** para iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="a31e9-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a31e9-138">![Guardar y ejecutar combinación de datos](media/configure-data-merge-save-run.png "Guardar y ejecutar combinación de datos")</span><span class="sxs-lookup"><span data-stu-id="a31e9-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="a31e9-139">Para realizar cambios adicionales y volver a ejecutar el paso, puede cancelar una fusión en curso.</span><span class="sxs-lookup"><span data-stu-id="a31e9-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="a31e9-140">Seleccione **Actualizando...** y seleccione **Cancelar trabajo** en el panel lateral que aparece.</span><span class="sxs-lookup"><span data-stu-id="a31e9-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="a31e9-141">Después de **Actualizando...**, los cambios del texto cambian a **Correcto**. La fusión se ha completado y se han resuelto las contradicciones en los datos de acuerdo con las directivas que definió.</span><span class="sxs-lookup"><span data-stu-id="a31e9-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="a31e9-142">Los atributos fusionados y no fusionados se incluyen en la entidad de perfil unificada.</span><span class="sxs-lookup"><span data-stu-id="a31e9-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="a31e9-143">Los atributos excluidos no se incluyen en la entidad de perfil unificada.</span><span class="sxs-lookup"><span data-stu-id="a31e9-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="a31e9-144">Si no fue la primera vez que ejecutó una fusión con éxito, todos los procesos posteriores, incluidos el enriquecimiento, la segmentación y las medidas, se volverán a ejecutar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a31e9-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="a31e9-145">Después de que se hayan vuelto a ejecutar todos los procesos posteriores, los perfiles de los clientes reflejan los cambios que haya realizado.</span><span class="sxs-lookup"><span data-stu-id="a31e9-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="a31e9-146">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="a31e9-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a31e9-147">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a31e9-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a31e9-148">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a31e9-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a31e9-149">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="a31e9-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="a31e9-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a31e9-150">Next Step</span></span>

<span data-ttu-id="a31e9-151">Configure las [actividades](activities.md), el [enriquecimiento](enrichment-hub.md) o las [relaciones](relationships.md) para obtener más información sobre sus clientes.</span><span class="sxs-lookup"><span data-stu-id="a31e9-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="a31e9-152">Si ya configuró las actividades, el enriquecimiento o las relaciones o si definió los segmentos, se procesarán automáticamente para usar los últimos datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="a31e9-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]