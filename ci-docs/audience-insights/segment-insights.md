---
title: Información sobre segmentos para segmentos existentes
description: Obtenga información sobre los segmentos existentes para ver las diferencias y los puntos en común.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 92e1b05dd08588a5da446af5b17b2d6ce57490ce
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407049"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="aae4f-103">Información detallada de segmentos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="aae4f-103">Segment insights (preview)</span></span>

<span data-ttu-id="aae4f-104">Descubra información adicional y conocimientos sobre sus segmentos existentes.</span><span class="sxs-lookup"><span data-stu-id="aae4f-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="aae4f-105">Descubra qué diferencia a dos segmentos o qué tienen en común.</span><span class="sxs-lookup"><span data-stu-id="aae4f-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="aae4f-106">Superposición de segmento</span><span class="sxs-lookup"><span data-stu-id="aae4f-106">Segment overlap</span></span>

<span data-ttu-id="aae4f-107">El análisis de superposición de segmentos muestra cuántos y qué clientes son comunes a dos o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="aae4f-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="aae4f-108">Por ejemplo, cómo un segmento de clientes frecuentes se superpone a un segmento que contiene clientes que están satisfechos con su servicio o producto.</span><span class="sxs-lookup"><span data-stu-id="aae4f-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="aae4f-109">También puede analizar cómo cambia la superposición para atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="aae4f-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="aae4f-110">Ejecutar un análisis de superposición</span><span class="sxs-lookup"><span data-stu-id="aae4f-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="aae4f-111">Vaya a **Segmentos** y seleccione la pestaña **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="aae4f-112">Seleccione **Nuevo** y elija la opción **Superposición** en el panel **Elegir tipo de información**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="aae4f-113">Elija los segmentos de interés y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="aae4f-114">Opcionalmente, elija uno o más campos de interés para analizar superposiciones para cada valor de campo posible y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="aae4f-115">Proporcione un nombre para su análisis de superposición, un nombre para mostrar opcional y una descripción.</span><span class="sxs-lookup"><span data-stu-id="aae4f-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="aae4f-116">Seleccione **Guardar** para comenzar el análisis.</span><span class="sxs-lookup"><span data-stu-id="aae4f-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="aae4f-117">El análisis de superposición está listo cuando el estado cambia de Actualizando a Correcto.</span><span class="sxs-lookup"><span data-stu-id="aae4f-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="aae4f-118">Ver y optimizar un análisis de superposición</span><span class="sxs-lookup"><span data-stu-id="aae4f-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="aae4f-119">Después de completar el análisis, busque detalles sobre esta información en **Segmentos** > **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalles de información de superposición de segmentos":::

<span data-ttu-id="aae4f-121">Seleccione una información para ver los resultados del análisis:</span><span class="sxs-lookup"><span data-stu-id="aae4f-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="aae4f-122">El número de miembros que se superponen a los segmentos seleccionados para el análisis.</span><span class="sxs-lookup"><span data-stu-id="aae4f-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="aae4f-123">El número de miembros incluidos en uno de los segmentos pero no en el resto de los segmentos.</span><span class="sxs-lookup"><span data-stu-id="aae4f-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="aae4f-124">Si seleccionó campos mientras configuraba el análisis de superposición, los encontrará en las pestañas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="aae4f-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="aae4f-125">Puede usar el menú desplegable de filtro para seleccionar cualquier nivel de atributo de interés y la tabla en la parte inferior mostrará los datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="aae4f-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="aae4f-126">Diferenciadores de segmentos</span><span class="sxs-lookup"><span data-stu-id="aae4f-126">Segment differentiators</span></span>

<span data-ttu-id="aae4f-127">Los diferenciadores de segmento lo ayudan a descubrir qué diferencia un segmento del resto de sus clientes o de otro segmento.</span><span class="sxs-lookup"><span data-stu-id="aae4f-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="aae4f-128">Solo tiene que seleccionar un segmento y el sistema identificará los atributos del perfil y las medidas que distinguen el segmento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aae4f-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="aae4f-129">Ejecutar un análisis diferenciador</span><span class="sxs-lookup"><span data-stu-id="aae4f-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="aae4f-130">Vaya a **Segmentos** y seleccione la pestaña **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="aae4f-131">Seleccione **Nuevo** y elija la opción **Superposición** en el panel **Elegir tipo de información**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="aae4f-132">Elija el segmento que desea analizar como **Segmento primario** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="aae4f-133">Elija **Todos los clientes** o un **Segmento secundario** para comparar su segmento primario y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="aae4f-134">Opcionalmente, elija uno o más campos de interés para enfocar el análisis en atributos específicos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="aae4f-135">Proporcione un nombre para su análisis de superposición, un nombre para mostrar opcional y una descripción.</span><span class="sxs-lookup"><span data-stu-id="aae4f-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="aae4f-136">Seleccione **Guardar** para comenzar el análisis.</span><span class="sxs-lookup"><span data-stu-id="aae4f-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="aae4f-137">El análisis de superposición está listo cuando el estado cambia de Actualizando a Correcto.</span><span class="sxs-lookup"><span data-stu-id="aae4f-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="aae4f-138">Ver y optimizar un análisis de diferenciadores</span><span class="sxs-lookup"><span data-stu-id="aae4f-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="aae4f-139">Después de completar el análisis, busque detalles sobre esta información en **Segmentos** > **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="aae4f-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalles de información de diferenciador de segmentos":::

<span data-ttu-id="aae4f-141">Seleccione una información para ver los resultados del análisis.</span><span class="sxs-lookup"><span data-stu-id="aae4f-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="aae4f-142">Un análisis de diferenciador incluye dos pestañas.</span><span class="sxs-lookup"><span data-stu-id="aae4f-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="aae4f-143">La pestaña **Atributos** enumera los atributos de perfil considerados como diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="aae4f-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="aae4f-144">La pestaña **Medidas** enumera los diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="aae4f-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="aae4f-145">Cada pestaña incluye los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="aae4f-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="aae4f-146">Lista clasificada de diferenciadores, ordenados por puntuación de diferencia.</span><span class="sxs-lookup"><span data-stu-id="aae4f-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="aae4f-147">La **Puntuación de diferencia** para cada diferenciador.</span><span class="sxs-lookup"><span data-stu-id="aae4f-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="aae4f-148">La puntuación de diferencia representa el grado de diferencia de un atributo entre dos segmentos.</span><span class="sxs-lookup"><span data-stu-id="aae4f-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="aae4f-149">Cuanto mayor sea la puntuación de diferencia, más difieren los atributos entre los dos segmentos.</span><span class="sxs-lookup"><span data-stu-id="aae4f-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="aae4f-150">Seleccione una puntuación para abrir el panel **Puntuación de diferencia** con las distribuciones de valores para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="aae4f-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="aae4f-151">Administrar información de segmentos</span><span class="sxs-lookup"><span data-stu-id="aae4f-151">Manage segment insights</span></span>

<span data-ttu-id="aae4f-152">Puede usar las siguientes opciones en la información desde la barra de comandos:</span><span class="sxs-lookup"><span data-stu-id="aae4f-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="aae4f-153">**Volver** para regresar a la lista de conocimientos</span><span class="sxs-lookup"><span data-stu-id="aae4f-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="aae4f-154">**Actualizar** para ejecutar el análisis nuevamente</span><span class="sxs-lookup"><span data-stu-id="aae4f-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="aae4f-155">**Eliminar** para eliminar esta información</span><span class="sxs-lookup"><span data-stu-id="aae4f-155">**Delete** to remove this insight</span></span>
