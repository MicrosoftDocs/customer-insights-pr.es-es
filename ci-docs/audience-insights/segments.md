---
title: Segmentos de conclusiones del público
description: Descripción general de los segmentos y cómo crearlos y gestionarlos.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306278"
---
# <a name="segments-overview"></a><span data-ttu-id="c28ca-103">Información general de los segmentos</span><span class="sxs-lookup"><span data-stu-id="c28ca-103">Segments overview</span></span>

<span data-ttu-id="c28ca-104">Los segmentos le permite agrupar a los clientes según los atributos demográficos, transaccionales o de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c28ca-105">Puede usar segmentos para dirigir a los clientes campañas promocionales, actividades de ventas y acciones de atención al cliente con el fin de lograr sus objetivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="c28ca-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c28ca-106">Los perfiles de clientes que coinciden con los filtros de una definición de segmento se denominan *miembros* de un segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="c28ca-107">Se aplican algunos [límites de servicio](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c28ca-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c28ca-108">Crear un nuevo segmento</span><span class="sxs-lookup"><span data-stu-id="c28ca-108">Create a new segment</span></span>

<span data-ttu-id="c28ca-109">Hay múltiples formas de crear un nuevo segmento:</span><span class="sxs-lookup"><span data-stu-id="c28ca-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="c28ca-110">Segmento complejo con creador de segmentos: [Segmento en blanco](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="c28ca-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="c28ca-111">Segmentos simples con un operador: [Segmento rápido](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="c28ca-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="c28ca-112">Forma con tecnología de IA para encontrar clientes similares: [Clientes similares](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="c28ca-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="c28ca-113">Sugerencias con tecnología de IA basadas en medidas o atributos: [Segmentos sugeridos para mejorar las medidas](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="c28ca-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="c28ca-114">Sugerencias basadas en actividades: [Segmentos sugeridos basados en la actividad del cliente](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="c28ca-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c28ca-115">Administrar segmentos existentes</span><span class="sxs-lookup"><span data-stu-id="c28ca-115">Manage existing segments</span></span>

<span data-ttu-id="c28ca-116">Vaya a la página **Segmentos** para ver todos los segmentos guardados y administrarlos.</span><span class="sxs-lookup"><span data-stu-id="c28ca-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="c28ca-117">Cada segmento está representado por una fila que incluye información adicional sobre el segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento seleccionado con lista desplegable de opciones y opciones disponibles.":::

<span data-ttu-id="c28ca-119">Las siguientes acciones están disponibles cuando selecciona un segmento:</span><span class="sxs-lookup"><span data-stu-id="c28ca-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c28ca-120">**Ver** los detalles del segmento, incluida la tendencia del recuento de miembros de una vista previa de los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c28ca-121">**Editar** el segmento para cambiar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="c28ca-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c28ca-122">**Crear duplicado** de un segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="c28ca-123">Puede elegir editar sus propiedades de inmediato o simplemente guardar el duplicado.</span><span class="sxs-lookup"><span data-stu-id="c28ca-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="c28ca-124">**Actualizar** el segmento para incluir los últimos datos.</span><span class="sxs-lookup"><span data-stu-id="c28ca-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c28ca-125">**Activar** o **Desactivar** el segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c28ca-126">Los segmentos tienen dos estados posibles: activo o inactivo.</span><span class="sxs-lookup"><span data-stu-id="c28ca-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c28ca-127">Estos estados resultan útiles al editar un segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c28ca-128">Para los segmentos inactivos, existe la definición de segmento, pero aún no contiene ningún cliente.</span><span class="sxs-lookup"><span data-stu-id="c28ca-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c28ca-129">Cuando activa un segmento, su estado cambia de "inactivo" a "activo" y comienza a buscar clientes que coincidan con la definición del segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c28ca-130">Si una [actualización programada](system.md#schedule-tab) está configurada, los segmentos inactivos tienen el **Estado** catalogado como **Omitido**, lo que indica que ni siquiera se intentó una actualización.</span><span class="sxs-lookup"><span data-stu-id="c28ca-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c28ca-131">Cuando se activa un segmento inactivo, se actualizará y se incluirá en las actualizaciones programadas.</span><span class="sxs-lookup"><span data-stu-id="c28ca-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c28ca-132">Alternativamente, puede usar la funcionalidad **Programar más tarde** en el desplegable **Activar/Desactivar** para especificar una fecha y hora futuras para la activación y desactivación de un segmento en particular.</span><span class="sxs-lookup"><span data-stu-id="c28ca-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c28ca-133">**Cambiar nombre** de segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-133">**Rename** the segment.</span></span>
- <span data-ttu-id="c28ca-134">**Descargar** la lista de miembros como archivo .CSV.</span><span class="sxs-lookup"><span data-stu-id="c28ca-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c28ca-135">**Gestionar exportaciones** para ver el segmento relacionado con las exportaciones y gestionarlas.</span><span class="sxs-lookup"><span data-stu-id="c28ca-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="c28ca-136">Más información sobre exportaciones.</span><span class="sxs-lookup"><span data-stu-id="c28ca-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="c28ca-137">**Eliminar** el segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c28ca-138">Actualizar segmentos</span><span class="sxs-lookup"><span data-stu-id="c28ca-138">Refresh segments</span></span>

<span data-ttu-id="c28ca-139">Puede actualizar todos los segmentos a la vez seleccionando **Actualizar todo** en la página **Segmentos** o puede actualizar uno o varios segmentos cuando los selecciona y elige **Actualizar** desde las opciones.</span><span class="sxs-lookup"><span data-stu-id="c28ca-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c28ca-140">Alternativamente, puede configurar una actualización periódica en **Administración** > **Sistema** > **Programar**.</span><span class="sxs-lookup"><span data-stu-id="c28ca-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c28ca-141">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="c28ca-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c28ca-142">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c28ca-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c28ca-143">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="c28ca-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c28ca-144">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="c28ca-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="c28ca-145">Exportar segmentos</span><span class="sxs-lookup"><span data-stu-id="c28ca-145">Export segments</span></span>

<span data-ttu-id="c28ca-146">Puede exportar un segmento desde la página de segmentos o la [página de exportaciones](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c28ca-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="c28ca-147">Vaya a la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="c28ca-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="c28ca-148">Seleccione **Mostrar más [...]** para el segmento que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="c28ca-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="c28ca-149">Seleccione **Gestionar exportaciones** de la lista desplegable de acciones.</span><span class="sxs-lookup"><span data-stu-id="c28ca-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="c28ca-150">La página **Exportaciones (vista previa) para segmento** se abre.</span><span class="sxs-lookup"><span data-stu-id="c28ca-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="c28ca-151">Puede ver todas las exportaciones configuradas agrupadas por exportaciones que contienen el segmento actual o no lo contienen.</span><span class="sxs-lookup"><span data-stu-id="c28ca-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="c28ca-152">Para agregar el segmento seleccionado a una exportación, seleccione la exportación en la lista y seleccione **Agregar segmento**.</span><span class="sxs-lookup"><span data-stu-id="c28ca-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="c28ca-153">Para crear una nueva exportación con el segmento seleccionado, seleccione **Agregar exportación**.</span><span class="sxs-lookup"><span data-stu-id="c28ca-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="c28ca-154">Para obtener más información sobre la creación de exportaciones, consulte [Configurar una nueva exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c28ca-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c28ca-155">Seleccione **Atrás** para volver a la página principal de los segmentos.</span><span class="sxs-lookup"><span data-stu-id="c28ca-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c28ca-156">Ver el historial de procesamiento y los miembros del segmento</span><span class="sxs-lookup"><span data-stu-id="c28ca-156">View processing history and segment members</span></span>

<span data-ttu-id="c28ca-157">Puede ver datos consolidados sobre un segmento revisando sus detalles.</span><span class="sxs-lookup"><span data-stu-id="c28ca-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c28ca-158">En la página **Segmentos**, seleccione el segmento que desea revisar.</span><span class="sxs-lookup"><span data-stu-id="c28ca-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c28ca-159">La parte superior de la página incluye un gráfico de tendencia que visualiza cambios en el recuento de miembros.</span><span class="sxs-lookup"><span data-stu-id="c28ca-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c28ca-160">Pase el puntero sobre los puntos de datos para ver el recuento de miembros en una fecha específica.</span><span class="sxs-lookup"><span data-stu-id="c28ca-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c28ca-161">Puede actualizar el período de tiempo de la visualización.</span><span class="sxs-lookup"><span data-stu-id="c28ca-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c28ca-162">![Segmentar intervalo de tiempo](media/segment-time-range.png "Segmentar intervalo de tiempo")</span><span class="sxs-lookup"><span data-stu-id="c28ca-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c28ca-163">La parte inferior contiene una lista de los miembros del segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c28ca-164">Los campos que aparecen en esta lista se basan en los atributos de las entidades de su segmento.</span><span class="sxs-lookup"><span data-stu-id="c28ca-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c28ca-165">La lista es una vista previa de los miembros del segmento coincidentes y muestra los primeros 100 registros de su segmento para que pueda evaluarlo rápidamente y revisar sus definiciones si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c28ca-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c28ca-166">Para ver todos los registros coincidentes, debe [exportar el segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c28ca-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
