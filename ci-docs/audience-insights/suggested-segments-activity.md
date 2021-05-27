---
title: Segmentos sugeridos según la actividad.
description: Deje que el aprendizaje automático le ayude a encontrar segmentos nuevos e interesantes según la actividad de los clientes.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034117"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="c8573-103">Segmentos sugeridos según los datos de actividad (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c8573-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="c8573-104">Descubra segmentos interesantes de sus clientes en función de los datos de actividad de los clientes que se ingieren en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c8573-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="c8573-105">Algunos ejemplos de datos de actividad son las transacciones, la duración de las llamadas de asistencia, las compras o las devoluciones.</span><span class="sxs-lookup"><span data-stu-id="c8573-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="c8573-106">Para sugerir segmentos, los datos de actividad se analizan en cuanto a actualidad, frecuencia y valor monetario (o duración).</span><span class="sxs-lookup"><span data-stu-id="c8573-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="c8573-107">Alternativamente, puede generar [segmentos sugeridos para mejorar una medida o comprender mejor qué influye en un atributo](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="c8573-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Pestaña de segmentos sugeridos que muestra sugerencias de segmentos para segmentos basados en actividades y basados en atributos.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="c8573-109">Categorizar a los clientes por actividad</span><span class="sxs-lookup"><span data-stu-id="c8573-109">Categorize customers by activity</span></span>

<span data-ttu-id="c8573-110">Con los [datos de actividad](activities.md) disponibles en Customer Insights, podemos generar sugerencias que representen grupos de clientes:</span><span class="sxs-lookup"><span data-stu-id="c8573-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="c8573-111">clientes más activos</span><span class="sxs-lookup"><span data-stu-id="c8573-111">most active customers</span></span> 
- <span data-ttu-id="c8573-112">clientes que han realizado más compras</span><span class="sxs-lookup"><span data-stu-id="c8573-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="c8573-113">clientes que generaron la mayor cantidad de ingresos</span><span class="sxs-lookup"><span data-stu-id="c8573-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="c8573-114">clientes que no han estado activos últimamente</span><span class="sxs-lookup"><span data-stu-id="c8573-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="c8573-115">clientes que interactúan frecuentemente con su negocio</span><span class="sxs-lookup"><span data-stu-id="c8573-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="c8573-116">Si tiene un negocio minorista, puede averiguar qué clientes generan más ingresos y recompensarlos con un cupón.</span><span class="sxs-lookup"><span data-stu-id="c8573-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="c8573-117">O bien, puede identificar clientes ocasionales y ofrecerles que se unan a un programa de recompensas para que visiten su negocio con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="c8573-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="c8573-118">Si está en el negocio de la atención médica, brinda atención médica pública y su objetivo es minimizar los gastos para pacientes individuales.</span><span class="sxs-lookup"><span data-stu-id="c8573-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="c8573-119">Una forma de hacerlo podría ser reducir las visitas periódicas, proporcionando la mejor atención posible en el menor número de visitas posible.</span><span class="sxs-lookup"><span data-stu-id="c8573-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="c8573-120">En este caso, su objetivo es mantener baja la frecuencia de las visitas y minimizar los costes periódicos para los pacientes.</span><span class="sxs-lookup"><span data-stu-id="c8573-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="c8573-121">Si no, puede identificar segmentos de pacientes que tienen citas frecuentes y altos costos periódicos y analizar estos casos para mejorar el tratamiento del individuo.</span><span class="sxs-lookup"><span data-stu-id="c8573-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="c8573-122">Datos necesarios</span><span class="sxs-lookup"><span data-stu-id="c8573-122">Required data</span></span>

<span data-ttu-id="c8573-123">Las sugerencias se generan en función de los datos de entrada seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c8573-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="c8573-124">Perfiles de clientes: todos los clientes o miembros de un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="c8573-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="c8573-125">Período de tiempo: el mes pasado, el año pasado o cualquier plazo de tiempo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c8573-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="c8573-126">Tipo de actividad: compras, transacciones minoristas, transacciones en línea, casos de atención al cliente, suscripciones, etc.</span><span class="sxs-lookup"><span data-stu-id="c8573-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="c8573-127">Entidad en Customer Insights que contiene los datos de la actividad: la entidad UnifiedActivity o la entidad para una actividad específica.</span><span class="sxs-lookup"><span data-stu-id="c8573-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="c8573-128">Dimensiones a incluir: actualidad, frecuencia o dimensión monetaria, según los requisitos de su empresa.</span><span class="sxs-lookup"><span data-stu-id="c8573-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="c8573-129">Generar segmentos sugeridos</span><span class="sxs-lookup"><span data-stu-id="c8573-129">Generate suggested segments</span></span>

1. <span data-ttu-id="c8573-130">Vaya a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="c8573-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="c8573-131">Seleccione la pestaña **Sugerencias (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="c8573-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="c8573-132">Seleccione **Buscar nuevas sugerencias** y elija **Ver o anticipar el comportamiento del cliente**.</span><span class="sxs-lookup"><span data-stu-id="c8573-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="c8573-133">Seleccione **Iniciar** para empezar la experiencia guiada.</span><span class="sxs-lookup"><span data-stu-id="c8573-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primer paso del asistente de configuración para un segmento sugerido según la actividad.":::

1. <span data-ttu-id="c8573-135">Proporcione los datos de entrada necesarios y seleccione **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="c8573-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="c8573-136">Elegir clientes: incluya todos los clientes o un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="c8573-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="c8573-137">Elegir actividad: seleccione el tipo de actividad y las entidades que describen la actividad.</span><span class="sxs-lookup"><span data-stu-id="c8573-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="c8573-138">Preferencias: establezca el período de tiempo a considerar, los factores para las sugerencias y asigne los atributos.</span><span class="sxs-lookup"><span data-stu-id="c8573-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="c8573-139">Revise su entrada y seleccione **Ejecutar** para ejecutar el modelo y generar sugerencias.</span><span class="sxs-lookup"><span data-stu-id="c8573-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="c8573-140">Dependiendo de la cantidad de perfiles de clientes y de las actividades seleccionadas, puede tardar unos minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="c8573-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="c8573-141">Después de generar las sugerencias, puede filtrarlas por la dimensión o el valor que más le interese.</span><span class="sxs-lookup"><span data-stu-id="c8573-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="c8573-142">Ver detalles de un segmento sugerido</span><span class="sxs-lookup"><span data-stu-id="c8573-142">View details of a suggested segment</span></span>

<span data-ttu-id="c8573-143">Una vez generadas las sugerencias, las encontrará enumeradas en **Segmentos** > **Sugerencias (versión preliminar)** en la sección **Sugerencias basadas en actividades**.</span><span class="sxs-lookup"><span data-stu-id="c8573-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panel lateral ampliado que muestra datos detallados de un segmento sugerido.":::

<span data-ttu-id="c8573-145">Seleccione **Ver sugerencia** en un segmento sugerido para ver los detalles de ese segmento.</span><span class="sxs-lookup"><span data-stu-id="c8573-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="c8573-146">El panel lateral proporciona detalles como la extensión de cada dimensión en comparación con el grupo objetivo.</span><span class="sxs-lookup"><span data-stu-id="c8573-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="c8573-147">También resalta el número de miembros potenciales en el segmento y el porcentaje correspondiente del total de clientes.</span><span class="sxs-lookup"><span data-stu-id="c8573-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="c8573-148">Si desea mantener la sugerencia como un segmento, seleccione **Crear segmento**.</span><span class="sxs-lookup"><span data-stu-id="c8573-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="c8573-149">Guardar una sugerencia como segmento</span><span class="sxs-lookup"><span data-stu-id="c8573-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="c8573-150">Vaya a **Segmentos** > **Sugerencias (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="c8573-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="c8573-151">Seleccione el segmento que desea guardar.</span><span class="sxs-lookup"><span data-stu-id="c8573-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="c8573-152">En el panel lateral, seleccione **Crear segmento**.</span><span class="sxs-lookup"><span data-stu-id="c8573-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="c8573-153">Después de guardar el segmento, se mostrará en la lista de segmentos, en la pestaña **Todos los segmentos**. Ahora puede [actualizarse o eliminarse, como cualquier otro segmento](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c8573-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="c8573-154">No puede editar los detalles del segmento.</span><span class="sxs-lookup"><span data-stu-id="c8573-154">You can't edit the segment details.</span></span> <span data-ttu-id="c8573-155">Sin embargo, puede cambiar los criterios de entrada para las sugerencias y generar sugerencias diferentes.</span><span class="sxs-lookup"><span data-stu-id="c8573-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="c8573-156">Actualizar o editar un conjunto de sugerencias</span><span class="sxs-lookup"><span data-stu-id="c8573-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="c8573-157">vaya a **Segmentos** > **Sugerencias (versión preliminar)** y busque el segmento en la sección **Sugerencias basadas en actividades**.</span><span class="sxs-lookup"><span data-stu-id="c8573-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="c8573-158">Seleccione **Actualizar sugerencias** para actualizar las sugerencias manteniendo los atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="c8573-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="c8573-159">O seleccione **Editar sugerencias** para modificar los atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="c8573-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="c8573-160">El sistema volverá a ejecutar el proceso, generará sugerencias de segmento basadas en los datos más recientes y reemplazará las sugerencias actuales.</span><span class="sxs-lookup"><span data-stu-id="c8573-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
