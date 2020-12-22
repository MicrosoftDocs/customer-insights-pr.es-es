---
title: Crear y gestionar segmentos
description: Cree segmentos de clientes para agruparlos en función de diversos atributos.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407056"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="42d2d-103">Crear y gestionar segmentos</span><span class="sxs-lookup"><span data-stu-id="42d2d-103">Create and manage segments</span></span>

<span data-ttu-id="42d2d-104">Los segmentos le permite agrupar a los clientes según los atributos demográficos, transaccionales o de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="42d2d-105">Puede usar segmentos para dirigir a los clientes campañas promocionales, actividades de ventas y acciones de atención al cliente con el fin de lograr sus objetivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="42d2d-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="42d2d-106">Puede definir filtros complejos alrededor de la entidad Perfil del cliente y sus entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="42d2d-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="42d2d-107">Cada segmento, después del procesamiento, crea un conjunto de registros de entidades del cliente que puede exportar y sobre los que puede actuar.</span><span class="sxs-lookup"><span data-stu-id="42d2d-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="42d2d-108">Se aplican algunos [límites de servicio](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="42d2d-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="42d2d-109">A menos que se indique lo contrario, todos los segmentos son **Segmentos dinámicos**, que se actualizan con programación periódica.</span><span class="sxs-lookup"><span data-stu-id="42d2d-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="42d2d-110">El siguiente ejemplo ilustra la capacidad de segmentación.</span><span class="sxs-lookup"><span data-stu-id="42d2d-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="42d2d-111">Hemos definido un segmento para clientes que pidieron bienes por una cantidad mínima de $500 en los últimos 90 días *y* que participaron en una llamada de servicio al cliente que se escaló.</span><span class="sxs-lookup"><span data-stu-id="42d2d-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42d2d-112">![Varios grupos](media/segmentation-group1-2.png "Varios grupos")</span><span class="sxs-lookup"><span data-stu-id="42d2d-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="42d2d-113">Crear un nuevo segmento</span><span class="sxs-lookup"><span data-stu-id="42d2d-113">Create a new segment</span></span>

<span data-ttu-id="42d2d-114">Los segmentos se gestionan en la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="42d2d-115">En las informaciones de público, vaya a la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="42d2d-116">Seleccione **Nuevo** > **Segmento en blanco**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="42d2d-117">En el panel **Nuevo segmento**, elija un tipo de segmento y proporcione un **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="42d2d-118">Opcionalmente, proporcione un nombre y una descripción que ayude a identificar el segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="42d2d-119">Seleccione **Siguiente** para llegar a la página **Generador de segmentos**, donde define un grupo.</span><span class="sxs-lookup"><span data-stu-id="42d2d-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="42d2d-120">Un grupo es un conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="42d2d-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="42d2d-121">Elija la entidad que incluye el atributo por la que desea segmentar.</span><span class="sxs-lookup"><span data-stu-id="42d2d-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="42d2d-122">Elija el atributo de segmentación.</span><span class="sxs-lookup"><span data-stu-id="42d2d-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="42d2d-123">Este atributo puede tener uno de los cuatro tipos de valores siguientes: numérico, cadena, fecha o booleano.</span><span class="sxs-lookup"><span data-stu-id="42d2d-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="42d2d-124">Elija un operador y un valor para el atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="42d2d-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42d2d-125">![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo del cliente")</span><span class="sxs-lookup"><span data-stu-id="42d2d-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="42d2d-126">Número</span><span class="sxs-lookup"><span data-stu-id="42d2d-126">Number</span></span> |<span data-ttu-id="42d2d-127">Definición</span><span class="sxs-lookup"><span data-stu-id="42d2d-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="42d2d-128">1</span><span class="sxs-lookup"><span data-stu-id="42d2d-128">1</span></span>     |<span data-ttu-id="42d2d-129">Entity</span><span class="sxs-lookup"><span data-stu-id="42d2d-129">Entity</span></span>          |
   |<span data-ttu-id="42d2d-130">2</span><span class="sxs-lookup"><span data-stu-id="42d2d-130">2</span></span>     |<span data-ttu-id="42d2d-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="42d2d-131">Attribute</span></span>          |
   |<span data-ttu-id="42d2d-132">3</span><span class="sxs-lookup"><span data-stu-id="42d2d-132">3</span></span>    |<span data-ttu-id="42d2d-133">Operador</span><span class="sxs-lookup"><span data-stu-id="42d2d-133">Operator</span></span>         |
   |<span data-ttu-id="42d2d-134">4</span><span class="sxs-lookup"><span data-stu-id="42d2d-134">4</span></span>    |<span data-ttu-id="42d2d-135">valor</span><span class="sxs-lookup"><span data-stu-id="42d2d-135">Value</span></span>         |

8. <span data-ttu-id="42d2d-136">Si la entidad está conectada a la entidad unificada del cliente a través de [relaciones](relationships.md), debe definir la ruta de relación para crear un segmento válido.</span><span class="sxs-lookup"><span data-stu-id="42d2d-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="42d2d-137">Agregue las entidades de la ruta de relación hasta que pueda seleccionar la entidad **Customer : CustomerInsights** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="42d2d-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="42d2d-138">Luego escoja **Todos los registros** para cada condición.</span><span class="sxs-lookup"><span data-stu-id="42d2d-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42d2d-139">![Ruta de relación durante la creación del segmento](media/segments-multiple-relationships.png "Ruta de relación durante la creación del segmento")</span><span class="sxs-lookup"><span data-stu-id="42d2d-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="42d2d-140">Seleccione **Guardar** para guardar el segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="42d2d-141">Su segmento se guardará y procesará si se validan todos los requisitos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="42d2d-142">De lo contrario, se guardará como borrador.</span><span class="sxs-lookup"><span data-stu-id="42d2d-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="42d2d-143">Seleccione **Volver a Segmentos** para volver a la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="42d2d-144">Administrar segmentos existentes</span><span class="sxs-lookup"><span data-stu-id="42d2d-144">Manage existing segments</span></span>

<span data-ttu-id="42d2d-145">En la página **Segmentos** puede ver todos sus segmentos guardados y administrarlos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="42d2d-146">Cada segmento está representado por una fila que incluye información adicional sobre el segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="42d2d-147">Puede ordenar los segmentos en una columna seleccionando el encabezado de la columna.</span><span class="sxs-lookup"><span data-stu-id="42d2d-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="42d2d-148">Use el cuadro **Buscar** en la esquina superior derecha para filtrar los segmentos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42d2d-149">![Opciones para administrar un segmento ya existente](media/segments-selected-segment.png "Opciones para administrar un segmento ya existente")</span><span class="sxs-lookup"><span data-stu-id="42d2d-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="42d2d-150">Las siguientes acciones están disponibles cuando selecciona un segmento:</span><span class="sxs-lookup"><span data-stu-id="42d2d-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="42d2d-151">**Ver** los detalles del segmento, incluida la tendencia del recuento de miembros de una vista previa de los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="42d2d-152">**Editar** el segmento para cambiar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="42d2d-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="42d2d-153">**Actualizar** el segmento para incluir los últimos datos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="42d2d-154">**Activar** o **Desactivar** el segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="42d2d-155">Los segmentos tienen dos estados posibles: activo o inactivo.</span><span class="sxs-lookup"><span data-stu-id="42d2d-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="42d2d-156">Estos estados resultan útiles al editar un segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="42d2d-157">Para los segmentos inactivos, existe la definición de segmento, pero aún no contiene ningún cliente.</span><span class="sxs-lookup"><span data-stu-id="42d2d-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="42d2d-158">Cuando activa un segmento, su estado cambia de "inactivo" a "activo" y comienza a buscar clientes que coincidan con la definición del segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="42d2d-159">Si una [actualización programada](system.md#schedule-tab) está configurada, los segmentos inactivos tienen el **Estado** catalogado como **Omitido**, lo que indica que ni siquiera se intentó una actualización.</span><span class="sxs-lookup"><span data-stu-id="42d2d-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="42d2d-160">Cuando se activa un segmento inactivo, se actualizará y se incluirá en las actualizaciones programadas.</span><span class="sxs-lookup"><span data-stu-id="42d2d-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="42d2d-161">Alternativamente, puede usar la funcionalidad **Programar más tarde** en el desplegable **Activar/Desactivar** para especificar una fecha y hora futuras para la activación y desactivación de un segmento en particular.</span><span class="sxs-lookup"><span data-stu-id="42d2d-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="42d2d-162">**Cambiar nombre** de segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-162">**Rename** the segment.</span></span>
- <span data-ttu-id="42d2d-163">**Descargar** la lista de miembros como archivo .CSV.</span><span class="sxs-lookup"><span data-stu-id="42d2d-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="42d2d-164">La opción **Agregar a** envía la lista de ID de cliente en el segmento para su procesamiento en otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="42d2d-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="42d2d-165">**Eliminar** el segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="42d2d-166">Actualizar segmentos</span><span class="sxs-lookup"><span data-stu-id="42d2d-166">Refresh segments</span></span>

<span data-ttu-id="42d2d-167">Puede actualizar todos los segmentos a la vez seleccionando **Actualizar todo** en la página **Segmentos** o puede actualizar uno o varios segmentos cuando los selecciona y elige **Actualizar** desde las opciones.</span><span class="sxs-lookup"><span data-stu-id="42d2d-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="42d2d-168">Alternativamente, puede configurar una actualización periódica en **Administración** > **Sistema** > **Programar**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="42d2d-169">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="42d2d-170">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="42d2d-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="42d2d-171">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="42d2d-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="42d2d-172">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="42d2d-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="42d2d-173">Descargar y exportar segmentos</span><span class="sxs-lookup"><span data-stu-id="42d2d-173">Download and export segments</span></span>

<span data-ttu-id="42d2d-174">Puede descargar segmentos a un archivo CSV o exportarlos a Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="42d2d-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="42d2d-175">Descargar segmentos en un archivo CSV</span><span class="sxs-lookup"><span data-stu-id="42d2d-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="42d2d-176">En las informaciones de público, vaya a la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="42d2d-177">Seleccione los puntos suspensivos en el mosaico de un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="42d2d-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="42d2d-178">Seleccione **Descargar como CSV** en la lista desplegable de acciones.</span><span class="sxs-lookup"><span data-stu-id="42d2d-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="42d2d-179">Exportar segmentos a Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="42d2d-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="42d2d-180">Antes de exportar segmentos a Dynamics 365 Sales, un administrador debe [crear el destino de exportación](export-destinations.md) para Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="42d2d-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="42d2d-181">En las informaciones de público, vaya a la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="42d2d-182">Seleccione los puntos suspensivos en el mosaico de un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="42d2d-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="42d2d-183">Seleccione **Agregar a** en la lista desplegable de acciones y seleccione el destino de exportación al que desee enviar los datos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="42d2d-184">Modo borrador para segmentos</span><span class="sxs-lookup"><span data-stu-id="42d2d-184">Draft mode for segments</span></span>

<span data-ttu-id="42d2d-185">Si no se cumplen todos los requisitos para procesar un segmento, puede guardar el segmento como borrador y acceder a él desde la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="42d2d-186">Se guardará como segmento inactivo y no se puede activar hasta que sea válido.</span><span class="sxs-lookup"><span data-stu-id="42d2d-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="42d2d-187">Agregar más condiciones a un grupo</span><span class="sxs-lookup"><span data-stu-id="42d2d-187">Add more conditions to a group</span></span>

<span data-ttu-id="42d2d-188">Para agregar más condiciones a un grupo, puede usar dos operadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="42d2d-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="42d2d-189">Operador **AND**: Ambas condiciones deben cumplirse como parte del proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="42d2d-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="42d2d-190">Esta opción es más útil cuando define condiciones en diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="42d2d-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="42d2d-191">Operador **OR**: Cualquiera de las condiciones debe cumplirse como parte del proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="42d2d-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="42d2d-192">Esta opción es más útil cuando define varias condiciones para la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="42d2d-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42d2d-193">![Operador OR donde cualquiera de las condiciones debe cumplirse](media/segmentation-either-condition.png "Operador OR donde cualquiera de las condiciones debe cumplirse")</span><span class="sxs-lookup"><span data-stu-id="42d2d-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="42d2d-194">Actualmente es posible anidar una operador **OR** bajo un operador **AND**, pero no al revés.</span><span class="sxs-lookup"><span data-stu-id="42d2d-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="42d2d-195">Combinar varios grupos</span><span class="sxs-lookup"><span data-stu-id="42d2d-195">Combine multiple groups</span></span>

<span data-ttu-id="42d2d-196">Cada grupo produce un conjunto específico de clientes.</span><span class="sxs-lookup"><span data-stu-id="42d2d-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="42d2d-197">Puede combinar estos grupos para incluir a los clientes necesarios para su caso de negocios.</span><span class="sxs-lookup"><span data-stu-id="42d2d-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="42d2d-198">En las informaciones de público, vaya a la página **Segmentos** y seleccione un segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="42d2d-199">Seleccione **Agregar grupo**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42d2d-200">![Grupo de clientes agregar grupo](media/customer-group-add-group.png "Grupo de clientes agregar grupo")</span><span class="sxs-lookup"><span data-stu-id="42d2d-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="42d2d-201">Seleccione uno de los siguientes operadores de conjuntos: **Unión**, **Intersección** o **Excepto**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42d2d-202">![Grupo de clientes agregar unión](media/customer-group-union.png "Grupo de clientes agregar unión")</span><span class="sxs-lookup"><span data-stu-id="42d2d-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="42d2d-203">Seleccione un operador de conjuntos para definir un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="42d2d-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="42d2d-204">Guarde diferentes grupos para determinar qué datos se mantienen:</span><span class="sxs-lookup"><span data-stu-id="42d2d-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="42d2d-205">**Unión** une los dos grupos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="42d2d-206">**Intersección** superpone los dos grupos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="42d2d-207">Solo se retienen en el grupo unificado los datos que *son comunes* a ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="42d2d-208">**Exceptuar** combina los dos grupos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-208">**Except** combines the two groups.</span></span> <span data-ttu-id="42d2d-209">Solo se retienen en el grupo A los datos que *no son comunes* a los datos del grupo B.</span><span class="sxs-lookup"><span data-stu-id="42d2d-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="42d2d-210">Ver el historial de procesamiento y los miembros del segmento</span><span class="sxs-lookup"><span data-stu-id="42d2d-210">View processing history and segment members</span></span>

<span data-ttu-id="42d2d-211">Puede ver datos consolidados sobre un segmento revisando sus detalles.</span><span class="sxs-lookup"><span data-stu-id="42d2d-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="42d2d-212">En la página **Segmentos**, seleccione el segmento que desea revisar.</span><span class="sxs-lookup"><span data-stu-id="42d2d-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="42d2d-213">La parte superior de la página incluye un gráfico de tendencia que visualiza cambios en el recuento de miembros.</span><span class="sxs-lookup"><span data-stu-id="42d2d-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="42d2d-214">Pase el puntero sobre los puntos de datos para ver el recuento de miembros en una fecha específica.</span><span class="sxs-lookup"><span data-stu-id="42d2d-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="42d2d-215">Puede actualizar el período de tiempo de la visualización.</span><span class="sxs-lookup"><span data-stu-id="42d2d-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42d2d-216">![Segmentar intervalo de tiempo](media/segment-time-range.png "Segmentar intervalo de tiempo")</span><span class="sxs-lookup"><span data-stu-id="42d2d-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="42d2d-217">La parte inferior contiene una lista de los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="42d2d-218">Los campos que aparecen en esta lista se basan en los atributos de las entidades de su segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="42d2d-219">La lista es una vista previa de los miembros del segmento coincidentes y muestra los primeros 100 registros de su segmento para que pueda evaluarlo rápidamente y revisar sus definiciones si es necesario.</span><span class="sxs-lookup"><span data-stu-id="42d2d-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="42d2d-220">Para ver todos los registros coincidentes, debe [exportar el segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="42d2d-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="42d2d-221">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="42d2d-221">Quick segments</span></span>

<span data-ttu-id="42d2d-222">Además del generador de segmentos, hay otra ruta para crear segmentos.</span><span class="sxs-lookup"><span data-stu-id="42d2d-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="42d2d-223">Los segmentos rápidos le permiten crear segmentos simples con un solo operador rápidamente y con información instantánea.</span><span class="sxs-lookup"><span data-stu-id="42d2d-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="42d2d-224">En la página **Segmentos**, seleccione **Nuevo** > **Crear rápidamente desde**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="42d2d-225">Seleccione la opción **Perfiles** para construir un segmento basado en la entidad del cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="42d2d-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="42d2d-226">Seleccione la opción **Medidas** para crear un segmento alrededor de cada uno de los tipos de medidas de Atributo del cliente que haya creado previamente en la página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="42d2d-227">Selecciona la opción **Inteligencia** para crear un segmento alrededor de una de las entidades de salida que generó con las capacidades **Predicciones** o **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="42d2d-228">En el cuadro de diálogo **Nuevo segmento rápido**, seleccione un atributo en el campo desplegable **Campo**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="42d2d-229">El sistema proporcionará información adicional que le ayudará a crear mejores segmentos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="42d2d-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="42d2d-230">Para los campos categóricos, mostraremos los 10 principales recuentos de clientes.</span><span class="sxs-lookup"><span data-stu-id="42d2d-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="42d2d-231">Elija un **Valor** y seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="42d2d-232">Para un atributo numérico, el sistema mostrará qué valor de atributo corresponde al percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="42d2d-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="42d2d-233">Elija un **Operador** y un **Valor**, luego seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="42d2d-234">El sistema le proporcionará un **Tamaño de segmento estimado**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="42d2d-235">Puede elegir si genera el segmento que ha definido o volver a visitarlo para obtener un tamaño de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="42d2d-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="42d2d-236">![Nombre y estimación de un segmento rápido](media/quick-segment-name.png "Nombre y estimación de un segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="42d2d-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="42d2d-237">Dé un **Nombre** al segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="42d2d-238">Opcionalmente, proporcione un **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="42d2d-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="42d2d-239">Seleccione **Guardar** para crear el segmento.</span><span class="sxs-lookup"><span data-stu-id="42d2d-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="42d2d-240">Una vez que el segmento ha terminado de procesarse, puede verlo como cualquier otro segmento que haya creado.</span><span class="sxs-lookup"><span data-stu-id="42d2d-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="42d2d-241">Para los siguientes escenarios, recomendamos utilizar el generador de segmentos en lugar de la capacidad de segmentos recomendada:</span><span class="sxs-lookup"><span data-stu-id="42d2d-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="42d2d-242">Crear segmentos con filtros en campos categóricos donde el operador es diferente al operador **Es**</span><span class="sxs-lookup"><span data-stu-id="42d2d-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="42d2d-243">Crear segmentos con filtros en campos numéricos donde el operador es diferente a los operadores **Entre**, **Mayor que** y **Menor que**</span><span class="sxs-lookup"><span data-stu-id="42d2d-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="42d2d-244">Crear segmentos con filtros en campos de tipo de fecha</span><span class="sxs-lookup"><span data-stu-id="42d2d-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="42d2d-245">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="42d2d-245">Next steps</span></span>

<span data-ttu-id="42d2d-246">[Exportar un segmento](export-destinations.md) y explorar la [Tarjeta de cliente](customer-card-add-in.md) y [Conectores](export-power-bi.md) para obtener información a nivel del cliente.</span><span class="sxs-lookup"><span data-stu-id="42d2d-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
