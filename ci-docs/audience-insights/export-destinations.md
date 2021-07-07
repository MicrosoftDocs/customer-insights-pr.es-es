---
title: Exportar datos de Customer Insights
description: Administrar exportaciones para compartir datos.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305499"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="a4176-103">Información general del exportaciones (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a4176-103">Exports (preview) overview</span></span>

<span data-ttu-id="a4176-104">La página **Exportaciones** muestra todas las exportaciones configuradas.</span><span class="sxs-lookup"><span data-stu-id="a4176-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="a4176-105">Las exportaciones comparten datos específicos con varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a4176-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="a4176-106">Pueden incluir perfiles de clientes o entidades, esquemas y detalles de mapeo.</span><span class="sxs-lookup"><span data-stu-id="a4176-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="a4176-107">Cada exportación requiere una [conexión, configurada por un administrador, para administrar la autenticación y el acceso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="a4176-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="a4176-108">Vaya a **Datos** > **Exportaciones** para ver la página de exportaciones.</span><span class="sxs-lookup"><span data-stu-id="a4176-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="a4176-109">Todos los roles de usuario pueden ver las exportaciones configuradas.</span><span class="sxs-lookup"><span data-stu-id="a4176-109">All user roles can view configured exports.</span></span> <span data-ttu-id="a4176-110">Utilice el campo de búsqueda en la barra de comandos para buscar exportaciones por su nombre, nombre de conexión o tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="a4176-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="a4176-111">Configurar una nueva exportación</span><span class="sxs-lookup"><span data-stu-id="a4176-111">Set up a new export</span></span>

<span data-ttu-id="a4176-112">Para configurar o editar una exportación, debe tener conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="a4176-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="a4176-113">Las conexiones dependen de su [rol del usuario](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="a4176-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="a4176-114">Los administradores tienen acceso a todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="a4176-114">Administrators have access to all connections.</span></span> <span data-ttu-id="a4176-115">También pueden crear nuevas conexiones al configurar una exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="a4176-116">Los colaboradores pueden tener acceso a conexiones específicas.</span><span class="sxs-lookup"><span data-stu-id="a4176-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="a4176-117">Dependen de los administradores para configurar y compartir conexiones.</span><span class="sxs-lookup"><span data-stu-id="a4176-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="a4176-118">La lista de exportaciones muestra a los contribuyentes si pueden editar o solo ver una exportación en la columna **Sus permisos**.</span><span class="sxs-lookup"><span data-stu-id="a4176-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="a4176-119">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a4176-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="a4176-120">Los visores solo pueden ver las exportaciones existentes, pero no crearlas.</span><span class="sxs-lookup"><span data-stu-id="a4176-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="a4176-121">Definir una nueva exportación</span><span class="sxs-lookup"><span data-stu-id="a4176-121">Define a new export</span></span>

1. <span data-ttu-id="a4176-122">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4176-123">Para crear una nueva exportación, seleccione **Agregar exportación**.</span><span class="sxs-lookup"><span data-stu-id="a4176-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="a4176-124">En el panel **Configurar exportación**, seleccione qué conexión usar.</span><span class="sxs-lookup"><span data-stu-id="a4176-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="a4176-125">Las [conexiones](connections.md) son administradas por administradores.</span><span class="sxs-lookup"><span data-stu-id="a4176-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="a4176-126">Proporcione los detalles requeridos y seleccione **Guardar** para crear la exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="a4176-127">Definir una nueva exportación basada en una exportación existente</span><span class="sxs-lookup"><span data-stu-id="a4176-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="a4176-128">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4176-129">En la lista de exportaciones, seleccione la exportación que desea duplicar.</span><span class="sxs-lookup"><span data-stu-id="a4176-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="a4176-130">Seleccione **Crear duplicado** en la barra de comandos para abrir el panel **Configurar exportación** con los detalles de la exportación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a4176-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="a4176-131">Revise y adapte la exportación y seleccione **Guardar** para crear una nueva exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="a4176-132">Editar una exportación</span><span class="sxs-lookup"><span data-stu-id="a4176-132">Edit an export</span></span>

1. <span data-ttu-id="a4176-133">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4176-134">En la lista de exportaciones, seleccione la exportación que desea editar.</span><span class="sxs-lookup"><span data-stu-id="a4176-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="a4176-135">En la barra de comandos, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a4176-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="a4176-136">Cambie los valores que desea actualizar y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a4176-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="a4176-137">Ver exportaciones y detalles de exportación</span><span class="sxs-lookup"><span data-stu-id="a4176-137">View exports and export details</span></span>

<span data-ttu-id="a4176-138">Después de crear los destinos de la exportación, se enumeran en **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="a4176-139">Todos los usuarios pueden ver qué datos se comparten y su estado más reciente.</span><span class="sxs-lookup"><span data-stu-id="a4176-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="a4176-140">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4176-141">Los usuarios sin permisos de edición seleccionan **Vista** en lugar de **Editar** para ver los detalles de la exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="a4176-142">El panel lateral muestra la configuración de una exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="a4176-143">Sin permisos de edición, no puede cambiar valores.</span><span class="sxs-lookup"><span data-stu-id="a4176-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="a4176-144">Seleccione **Cerrar** para volver a la página de exportaciones.</span><span class="sxs-lookup"><span data-stu-id="a4176-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="a4176-145">Programar y ejecutar exportaciones</span><span class="sxs-lookup"><span data-stu-id="a4176-145">Schedule and run exports</span></span>

<span data-ttu-id="a4176-146">Cada exportación que configure tiene un programa de actualización.</span><span class="sxs-lookup"><span data-stu-id="a4176-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="a4176-147">Durante una actualización, el sistema busca datos nuevos o actualizados para incluirlos en una exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="a4176-148">De forma predeterminada, las exportaciones se ejecutan como parte de cada [actualización programada del sistema](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a4176-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a4176-149">Puede personalizar el programa de actualización o desactivarlo para ejecutar exportaciones manualmente.</span><span class="sxs-lookup"><span data-stu-id="a4176-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="a4176-150">Los programas de exportación dependen del estado de su entorno.</span><span class="sxs-lookup"><span data-stu-id="a4176-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="a4176-151">Si hay actualizaciones en curso en [dependencias](system.md#refresh-policies) cuando debe comenzar una exportación programada, el sistema primero completará las actualizaciones y luego ejecutará la exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="a4176-152">Puede ver cuándo se actualizó por última vez una exportación en la columna **Actualizado**.</span><span class="sxs-lookup"><span data-stu-id="a4176-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="a4176-153">Programar exportaciones</span><span class="sxs-lookup"><span data-stu-id="a4176-153">Schedule exports</span></span>

<span data-ttu-id="a4176-154">Usted puede definir programas de actualización personalizados para exportaciones individuales o varias exportaciones a la vez.</span><span class="sxs-lookup"><span data-stu-id="a4176-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="a4176-155">El horario definido actualmente se enumera en la columna **Programación** de la lista de exportación.</span><span class="sxs-lookup"><span data-stu-id="a4176-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="a4176-156">El permiso para cambiar el horario es el mismo que para [editar y definir exportaciones](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a4176-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="a4176-157">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4176-158">Seleccione la exportación que quiere programar.</span><span class="sxs-lookup"><span data-stu-id="a4176-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="a4176-159">En la barra de comandos, seleccione **Programar**.</span><span class="sxs-lookup"><span data-stu-id="a4176-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="a4176-160">En el panel **Exportación programada**, establezca **Programar ejecución** a **Activado** para ejecutar la exportación automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a4176-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="a4176-161">Establézcalo en **Desactivado** para actualizarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="a4176-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="a4176-162">Para exportaciones actualizadas automáticamente, elija un valor de **Periodicidad** y especifique los detalles para ello.</span><span class="sxs-lookup"><span data-stu-id="a4176-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="a4176-163">El tiempo definido se aplica a todas las instancias de una periodicidad.</span><span class="sxs-lookup"><span data-stu-id="a4176-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="a4176-164">Es el momento en que una exportación debería comenzar a actualizarse.</span><span class="sxs-lookup"><span data-stu-id="a4176-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="a4176-165">Aplique y active sus cambios seleccionando **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a4176-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="a4176-166">Al editar la programación de varias exportaciones, debe realizar una selección en **Mantener o invalidad programaciones**:</span><span class="sxs-lookup"><span data-stu-id="a4176-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="a4176-167">**Mantener programaciones individuales**: conserva la programación previamente definida para las exportaciones seleccionadas y solo deshabilitarlas o habilitarlas.</span><span class="sxs-lookup"><span data-stu-id="a4176-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="a4176-168">**Definir un nuevo programa para todas las exportaciones seleccionadas**: anula las programaciones existentes de las exportaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="a4176-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="a4176-169">Ejecutar exportaciones según las necesidades</span><span class="sxs-lookup"><span data-stu-id="a4176-169">Run exports on demand</span></span>

<span data-ttu-id="a4176-170">Para exportar datos sin esperar una actualización programada, vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="a4176-171">Para ejecutar todas las exportaciones, seleccione **Ejecutar todo** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="a4176-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="a4176-172">Esta acción solo ejecutará exportaciones que tengan una programación activa.</span><span class="sxs-lookup"><span data-stu-id="a4176-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="a4176-173">Para ejecutar una sola exportación, selecciónela en la lista y seleccione **Ejecutar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="a4176-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="a4176-174">Así es como se ejecutan las exportaciones sin una programación activa.</span><span class="sxs-lookup"><span data-stu-id="a4176-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="a4176-175">Quitar una exportación</span><span class="sxs-lookup"><span data-stu-id="a4176-175">Remove an Export</span></span>

1. <span data-ttu-id="a4176-176">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="a4176-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4176-177">Seleccione la exportación que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="a4176-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="a4176-178">En la barra de comandos, seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="a4176-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="a4176-179">Confirme la eliminación seleccionando **Quitar** en la pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="a4176-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
