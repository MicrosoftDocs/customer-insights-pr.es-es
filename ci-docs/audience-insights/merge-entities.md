---
title: Fusionar entidades en la unificación de datos
description: Fusionar entidades para crear perfiles de cliente unificados.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085597"
---
# <a name="merge-entities"></a><span data-ttu-id="cf473-103">Combinar entidades</span><span class="sxs-lookup"><span data-stu-id="cf473-103">Merge entities</span></span>

<span data-ttu-id="cf473-104">La fase de combinación es la última fase del proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="cf473-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="cf473-105">Su propósito es conciliar datos en conflicto.</span><span class="sxs-lookup"><span data-stu-id="cf473-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="cf473-106">Los ejemplos de datos en conflicto podrían incluir un nombre de cliente que se encuentra en dos de sus conjuntos de datos pero que se muestra de manera un poco diferente en cada uno ("Grant Marshall" y "Grant Marshal"), o un número de teléfono que difiere en formato (617-803-091X y 617803091X).</span><span class="sxs-lookup"><span data-stu-id="cf473-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="cf473-107">La combinación de esos puntos de datos en conflicto se realiza atributo por atributo.</span><span class="sxs-lookup"><span data-stu-id="cf473-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Página de combinación en el proceso de unificación de datos que muestra una tabla con campos combinados que definen el perfil de cliente unificado.":::

<span data-ttu-id="cf473-109">Después de completar la [fase de coincidencia](match-entities.md), comience la fase de combinación seleccionando la ventana **Combinar** en la página **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="cf473-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="cf473-110">Revisar recomendaciones del sistema</span><span class="sxs-lookup"><span data-stu-id="cf473-110">Review system recommendations</span></span>

<span data-ttu-id="cf473-111">En **Datos** > **Unificar** > **Combinar**, elija y excluya atributos a fusionar dentro de su entidad de perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="cf473-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="cf473-112">El perfil de cliente unificado es el resultado del proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="cf473-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="cf473-113">El sistema combina automáticamente algunos atributos.</span><span class="sxs-lookup"><span data-stu-id="cf473-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="cf473-114">Para ver los atributos que se incluyen en uno de sus atributos combinados automáticamente, seleccione ese atributo combinado en la pestaña **Campos de clientes** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="cf473-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="cf473-115">Los dos atributos que componen ese atributo combinado aparecen en dos filas nuevas debajo del atributo combinado.</span><span class="sxs-lookup"><span data-stu-id="cf473-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="cf473-116">Separar, renombrar, excluir y editar campos combinados</span><span class="sxs-lookup"><span data-stu-id="cf473-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="cf473-117">Puede cambiar la forma en que el sistema procesa los atributos combinados para generar el perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="cf473-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="cf473-118">Seleccione **Mostrar más** y elija lo que quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="cf473-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opciones en el menú desplegable Mostrar más para administrar atributos combinados.":::

<span data-ttu-id="cf473-120">Para obtener más información, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="cf473-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="cf473-121">Separar campos combinados</span><span class="sxs-lookup"><span data-stu-id="cf473-121">Separate merged fields</span></span>

<span data-ttu-id="cf473-122">Para separar los campos combinados, busque el atributo en la tabla.</span><span class="sxs-lookup"><span data-stu-id="cf473-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="cf473-123">Los campos separados se muestran como puntos de datos individuales en el perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="cf473-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="cf473-124">Seleccione el campo combinado.</span><span class="sxs-lookup"><span data-stu-id="cf473-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="cf473-125">Seleccione **Mostrar más** y elija **Separar campos**.</span><span class="sxs-lookup"><span data-stu-id="cf473-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="cf473-126">Confirme la separación.</span><span class="sxs-lookup"><span data-stu-id="cf473-126">Confirm the separation.</span></span>

1. <span data-ttu-id="cf473-127">Seleccione **Guardar** y **Ejecutar** para procesar los cambios.</span><span class="sxs-lookup"><span data-stu-id="cf473-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="cf473-128">Cambiar el nombre de los campos combinados</span><span class="sxs-lookup"><span data-stu-id="cf473-128">Rename merged fields</span></span>

<span data-ttu-id="cf473-129">Cambie el nombre para mostrar de los atributos combinados.</span><span class="sxs-lookup"><span data-stu-id="cf473-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="cf473-130">No puede cambiar el nombre de la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="cf473-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="cf473-131">Seleccione el campo combinado.</span><span class="sxs-lookup"><span data-stu-id="cf473-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="cf473-132">Seleccione **Mostrar más** y elija **Renombrar**.</span><span class="sxs-lookup"><span data-stu-id="cf473-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="cf473-133">Confirme el nombre para mostrar cambiado.</span><span class="sxs-lookup"><span data-stu-id="cf473-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="cf473-134">Seleccione **Guardar** y **Ejecutar** para procesar los cambios.</span><span class="sxs-lookup"><span data-stu-id="cf473-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="cf473-135">Excluir campos combinados</span><span class="sxs-lookup"><span data-stu-id="cf473-135">Exclude merged fields</span></span>

<span data-ttu-id="cf473-136">Excluya un atributo del perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="cf473-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="cf473-137">Si el campo se utiliza en otros procesos, por ejemplo en un segmento, elimínelo de estos procesos antes de excluirlo del perfil del cliente.</span><span class="sxs-lookup"><span data-stu-id="cf473-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="cf473-138">Seleccione el campo combinado.</span><span class="sxs-lookup"><span data-stu-id="cf473-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="cf473-139">Seleccione **Mostrar más** y elija **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="cf473-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="cf473-140">Confirme la exclusión.</span><span class="sxs-lookup"><span data-stu-id="cf473-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="cf473-141">Seleccione **Guardar** y **Ejecutar** para procesar los cambios.</span><span class="sxs-lookup"><span data-stu-id="cf473-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="cf473-142">En la página **Combinar**, seleccione **Campos excluidos** para ver la lista de todos los campos excluidos.</span><span class="sxs-lookup"><span data-stu-id="cf473-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="cf473-143">Este panel le permite volver a agregar campos excluidos.</span><span class="sxs-lookup"><span data-stu-id="cf473-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="cf473-144">Combinar campos manualmente</span><span class="sxs-lookup"><span data-stu-id="cf473-144">Manually combine fields</span></span>

<span data-ttu-id="cf473-145">Especifique un atributo combinado manualmente.</span><span class="sxs-lookup"><span data-stu-id="cf473-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="cf473-146">En la página **Combinar**, seleccione **Combinar campos**.</span><span class="sxs-lookup"><span data-stu-id="cf473-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="cf473-147">Proporcione un **Nombre** y un **Nombre del campo de salida**.</span><span class="sxs-lookup"><span data-stu-id="cf473-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="cf473-148">Elija un campo a agregar.</span><span class="sxs-lookup"><span data-stu-id="cf473-148">Choose a field to add.</span></span> <span data-ttu-id="cf473-149">Seleccione **Agregar campos** para combinar más campos.</span><span class="sxs-lookup"><span data-stu-id="cf473-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="cf473-150">Confirme la exclusión.</span><span class="sxs-lookup"><span data-stu-id="cf473-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="cf473-151">Seleccione **Guardar** y **Ejecutar** para procesar los cambios.</span><span class="sxs-lookup"><span data-stu-id="cf473-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="cf473-152">Cambiar el orden de los campos</span><span class="sxs-lookup"><span data-stu-id="cf473-152">Change the order of fields</span></span>

<span data-ttu-id="cf473-153">Algunas entidades contienen más detalles que otras.</span><span class="sxs-lookup"><span data-stu-id="cf473-153">Some entities contain more details than others.</span></span> <span data-ttu-id="cf473-154">Si una entidad incluye los datos más recientes sobre un campo, puede priorizarlo sobre otras entidades al combinar valores.</span><span class="sxs-lookup"><span data-stu-id="cf473-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="cf473-155">Seleccione el campo combinado.</span><span class="sxs-lookup"><span data-stu-id="cf473-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="cf473-156">Seleccione **Mostrar más** y elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cf473-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="cf473-157">En el panel **Combinar campos**, seleccione **Mover hacia arriba/abajo** para establecer el orden o arrastrarlos y soltarlos en la posición deseada.</span><span class="sxs-lookup"><span data-stu-id="cf473-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="cf473-158">Confirme el cambio.</span><span class="sxs-lookup"><span data-stu-id="cf473-158">Confirm the change.</span></span>

1. <span data-ttu-id="cf473-159">Seleccione **Guardar** y **Ejecutar** para procesar los cambios.</span><span class="sxs-lookup"><span data-stu-id="cf473-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="cf473-160">Ejecutar la combinación</span><span class="sxs-lookup"><span data-stu-id="cf473-160">Run your merge</span></span>

<span data-ttu-id="cf473-161">Tanto si combina manualmente atributos como si deja que el sistema los combine, siempre puede ejecutar su combinación.</span><span class="sxs-lookup"><span data-stu-id="cf473-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="cf473-162">Seleccione **Ejecutar** en la página **Combinación** para iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="cf473-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cf473-163">![Guardar y ejecutar combinación de datos](media/configure-data-merge-save-run.png "Guardar y ejecutar combinación de datos")</span><span class="sxs-lookup"><span data-stu-id="cf473-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="cf473-164">Escoja **Ejecutar solo la combinación** si solo desea ver la salida reflejada en la entidad de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="cf473-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="cf473-165">Los procesos posteriores se actualizarán como esté [definido en el programa de actualización](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cf473-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="cf473-166">Escoja **Ejecutar procesos de combinación y posteriores** para actualizar el sistema con sus cambios.</span><span class="sxs-lookup"><span data-stu-id="cf473-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="cf473-167">Todos los procesos, incluido el enriquecimiento, los segmentos y las medidas, se volverán a ejecutar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="cf473-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="cf473-168">Una vez finalizados todos los procesos posteriores, los perfiles del cliente reflejan cualquier cambio que haya realizado.</span><span class="sxs-lookup"><span data-stu-id="cf473-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="cf473-169">Para realizar más cambios y volver a ejecutar el paso, puede cancelar una combinación en curso.</span><span class="sxs-lookup"><span data-stu-id="cf473-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="cf473-170">Seleccione **Actualizando...** y seleccione **Cancelar trabajo** en el panel lateral que aparece.</span><span class="sxs-lookup"><span data-stu-id="cf473-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="cf473-171">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="cf473-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cf473-172">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="cf473-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cf473-173">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="cf473-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cf473-174">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="cf473-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="cf473-175">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="cf473-175">Next Step</span></span>

<span data-ttu-id="cf473-176">Configure las [actividades](activities.md), el [enriquecimiento](enrichment-hub.md) o las [relaciones](relationships.md) para obtener más información sobre sus clientes.</span><span class="sxs-lookup"><span data-stu-id="cf473-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="cf473-177">Si ya configuró actividades, enriquecimiento o segmentos, se procesarán automáticamente para utilizar los datos más recientes del cliente.</span><span class="sxs-lookup"><span data-stu-id="cf473-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
