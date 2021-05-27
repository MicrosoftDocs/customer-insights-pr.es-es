---
title: Crear y gestionar segmentos
description: Cree segmentos de clientes para agruparlos en función de diversos atributos.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064958"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="e37ff-103">Crear y gestionar segmentos</span><span class="sxs-lookup"><span data-stu-id="e37ff-103">Create and manage segments</span></span>

<span data-ttu-id="e37ff-104">Defina filtros complejos basados en la entidad de cliente unificado y sus entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e37ff-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="e37ff-105">Cada segmento, después del procesamiento, crea un conjunto de registros de entidades del cliente que puede exportar y sobre los que puede actuar.</span><span class="sxs-lookup"><span data-stu-id="e37ff-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="e37ff-106">Los segmentos se gestionan en la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="e37ff-107">El siguiente ejemplo ilustra la capacidad de segmentación.</span><span class="sxs-lookup"><span data-stu-id="e37ff-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="e37ff-108">Hemos definido un segmento para clientes que pidieron bienes por una cantidad mínima de $500 en los últimos 90 días *y* que participaron en una llamada de servicio al cliente que se escaló.</span><span class="sxs-lookup"><span data-stu-id="e37ff-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de pantalla de la UI del generador de segmentos con dos grupos que especifican un segmento de clientes.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="e37ff-110">Crear un nuevo segmento</span><span class="sxs-lookup"><span data-stu-id="e37ff-110">Create a new segment</span></span>

<span data-ttu-id="e37ff-111">Hay múltiples formas de crear un nuevo segmento.</span><span class="sxs-lookup"><span data-stu-id="e37ff-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="e37ff-112">Esta sección describe cómo crear un *segmento en blanco* desde cero.</span><span class="sxs-lookup"><span data-stu-id="e37ff-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="e37ff-113">También puede crear un *segmento rápido* basado en entidades existentes o hacer uso de modelos de aprendizaje automático para obtener *segmentos sugeridos*.</span><span class="sxs-lookup"><span data-stu-id="e37ff-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="e37ff-114">Más información: [Información general sobre los segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e37ff-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="e37ff-115">Mientras crea un segmento, puede guardar un borrador.</span><span class="sxs-lookup"><span data-stu-id="e37ff-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="e37ff-116">Se guardará como un segmento inactivo y no se podrá activar si termina con una configuración válida.</span><span class="sxs-lookup"><span data-stu-id="e37ff-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="e37ff-117">Vaya a la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="e37ff-118">Seleccione **Nuevo** > **Segmento en blanco**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="e37ff-119">En el panel **Nuevo segmento**, elija un tipo de segmento:</span><span class="sxs-lookup"><span data-stu-id="e37ff-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="e37ff-120">[Actualizar](segments.md#refresh-segments) **segmentos dinámicos** con programación periódica.</span><span class="sxs-lookup"><span data-stu-id="e37ff-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="e37ff-121">Los **segmentos estáticos** se ejecutan una vez, al crearlos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="e37ff-122">Facilite un **Nombre de la entidad de salida** para el segmento.</span><span class="sxs-lookup"><span data-stu-id="e37ff-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="e37ff-123">Opcionalmente, proporcione un nombre y una descripción que ayude a identificar el segmento.</span><span class="sxs-lookup"><span data-stu-id="e37ff-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="e37ff-124">Seleccione **Siguiente** para llegar a la página **Generador de segmentos**, donde define un grupo.</span><span class="sxs-lookup"><span data-stu-id="e37ff-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="e37ff-125">Un grupo es un conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="e37ff-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="e37ff-126">Elija la entidad que incluye el atributo por la que desea segmentar.</span><span class="sxs-lookup"><span data-stu-id="e37ff-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="e37ff-127">Elija el atributo de segmentación.</span><span class="sxs-lookup"><span data-stu-id="e37ff-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="e37ff-128">Este atributo puede tener uno de los cuatro tipos de valores siguientes: numérico, cadena, fecha o booleano.</span><span class="sxs-lookup"><span data-stu-id="e37ff-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="e37ff-129">Elija un operador y un valor para el atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e37ff-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e37ff-130">![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo del cliente")</span><span class="sxs-lookup"><span data-stu-id="e37ff-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="e37ff-131">Número</span><span class="sxs-lookup"><span data-stu-id="e37ff-131">Number</span></span> |<span data-ttu-id="e37ff-132">Definición</span><span class="sxs-lookup"><span data-stu-id="e37ff-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="e37ff-133">1</span><span class="sxs-lookup"><span data-stu-id="e37ff-133">1</span></span>     |<span data-ttu-id="e37ff-134">Entity</span><span class="sxs-lookup"><span data-stu-id="e37ff-134">Entity</span></span>          |
   |<span data-ttu-id="e37ff-135">2</span><span class="sxs-lookup"><span data-stu-id="e37ff-135">2</span></span>     |<span data-ttu-id="e37ff-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="e37ff-136">Attribute</span></span>          |
   |<span data-ttu-id="e37ff-137">3</span><span class="sxs-lookup"><span data-stu-id="e37ff-137">3</span></span>    |<span data-ttu-id="e37ff-138">Operador</span><span class="sxs-lookup"><span data-stu-id="e37ff-138">Operator</span></span>         |
   |<span data-ttu-id="e37ff-139">4</span><span class="sxs-lookup"><span data-stu-id="e37ff-139">4</span></span>    |<span data-ttu-id="e37ff-140">valor</span><span class="sxs-lookup"><span data-stu-id="e37ff-140">Value</span></span>         |

   1. <span data-ttu-id="e37ff-141">Para agregar más condiciones a un grupo, puede usar dos operadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="e37ff-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="e37ff-142">Operador **AND**: Ambas condiciones deben cumplirse como parte del proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="e37ff-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="e37ff-143">Esta opción es más útil cuando define condiciones en diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="e37ff-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="e37ff-144">Operador **OR**: Cualquiera de las condiciones debe cumplirse como parte del proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="e37ff-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="e37ff-145">Esta opción es más útil cuando define varias condiciones para la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="e37ff-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="e37ff-146">![Operador OR donde cualquiera de las condiciones debe cumplirse](media/segmentation-either-condition.png "Operador OR donde cualquiera de las condiciones debe cumplirse")</span><span class="sxs-lookup"><span data-stu-id="e37ff-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="e37ff-147">Actualmente es posible anidar una operador **OR** bajo un operador **AND**, pero no al revés.</span><span class="sxs-lookup"><span data-stu-id="e37ff-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="e37ff-148">Cada grupo coincide con un conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="e37ff-148">Each group matches set of customers.</span></span> <span data-ttu-id="e37ff-149">Puede combinar grupos para incluir los clientes necesarios para su caso comercial.</span><span class="sxs-lookup"><span data-stu-id="e37ff-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="e37ff-150">Seleccione **Agregar grupo**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="e37ff-151">![Grupo de clientes agregar grupo](media/customer-group-add-group.png "Grupo de clientes agregar grupo")</span><span class="sxs-lookup"><span data-stu-id="e37ff-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="e37ff-152">Seleccione uno de los operadores establecidos: **Unión**, **Intersección** o **Excepto**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e37ff-153">![Grupo de clientes agregar unión](media/customer-group-union.png "Grupo de clientes agregar unión")</span><span class="sxs-lookup"><span data-stu-id="e37ff-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="e37ff-154">**Unión** une los dos grupos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="e37ff-155">**Intersección** superpone los dos grupos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="e37ff-156">Solo se retienen en el grupo unificado los datos que *son comunes* a ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="e37ff-157">**Exceptuar** combina los dos grupos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-157">**Except** combines the two groups.</span></span> <span data-ttu-id="e37ff-158">Solo se retienen en el grupo A los datos que *no son comunes* a los datos del grupo B.</span><span class="sxs-lookup"><span data-stu-id="e37ff-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="e37ff-159">Si la entidad está conectada a la entidad unificada del cliente a través de [relaciones](relationships.md), debe definir la ruta de relación para crear un segmento válido.</span><span class="sxs-lookup"><span data-stu-id="e37ff-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="e37ff-160">Agregue las entidades de la ruta de relación hasta que pueda seleccionar la entidad **Customer : CustomerInsights** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="e37ff-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="e37ff-161">Entonces, escoja **Todos los registros** para cada paso.</span><span class="sxs-lookup"><span data-stu-id="e37ff-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e37ff-162">![Ruta de relación durante la creación del segmento](media/segments-multiple-relationships.png "Ruta de relación durante la creación del segmento")</span><span class="sxs-lookup"><span data-stu-id="e37ff-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="e37ff-163">De forma predeterminada, los segmentos generan una entidad de salida que contiene todos los atributos de los perfiles de clientes que coinciden con los filtros definidos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="e37ff-164">Si un segmento se basa en otras entidades distintas a la entidad *Cliente*, puede agregar más atributos de estas entidades a la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="e37ff-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="e37ff-165">Seleccione **Atributos del proyecto** para elegir los atributos que se agregarán a la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="e37ff-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="e37ff-166">Ejemplo: un segmento se basa en una entidad que contiene datos de actividad del cliente que están relacionados con la entidad *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="e37ff-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="e37ff-167">El segmento busca a todos los clientes que llamaron a la mesa de ayuda en los últimos 60 días.</span><span class="sxs-lookup"><span data-stu-id="e37ff-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="e37ff-168">Puede optar por agregar la duración de la llamada y el número de llamadas a todos los registros de clientes coincidentes en la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="e37ff-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="e37ff-169">Esta información puede resultar útil para enviar un correo electrónico con vínculos útiles a artículos de ayuda en línea y preguntas frecuentes a los clientes que llaman con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e37ff-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="e37ff-170">Los atributos proyectados solo funcionan para entidades que tienen una relación de uno a varios con la entidad del cliente.</span><span class="sxs-lookup"><span data-stu-id="e37ff-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="e37ff-171">Por ejemplo, un cliente puede tener varias suscripciones.</span><span class="sxs-lookup"><span data-stu-id="e37ff-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="e37ff-172">Solo puede proyectar atributos de una entidad que se utiliza en cada grupo de consulta de segmento que está creando.</span><span class="sxs-lookup"><span data-stu-id="e37ff-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="e37ff-173">Los atributos proyectados se tienen en cuenta al utilizar operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="e37ff-174">Seleccione **Guardar** para guardar el segmento.</span><span class="sxs-lookup"><span data-stu-id="e37ff-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="e37ff-175">Su segmento se guardará y procesará si se validan todos los requisitos.</span><span class="sxs-lookup"><span data-stu-id="e37ff-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="e37ff-176">De lo contrario, se guardará como borrador.</span><span class="sxs-lookup"><span data-stu-id="e37ff-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="e37ff-177">Seleccione **Volver a Segmentos** para volver a la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="e37ff-178">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="e37ff-178">Quick segments</span></span>

<span data-ttu-id="e37ff-179">Los segmentos rápidos le permiten crear segmentos simples con un solo operador rápidamente para obtener conocimientos de forma más rápida.</span><span class="sxs-lookup"><span data-stu-id="e37ff-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="e37ff-180">En la página **Segmentos**, seleccione **Nuevo** > **Crear desde**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="e37ff-181">Seleccione la opción **Perfiles** para construir un segmento basado en la entidad *cliente unificado*.</span><span class="sxs-lookup"><span data-stu-id="e37ff-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="e37ff-182">Seleccione la opción **Medidas** para construir un segmento alrededor de medidas que haya creado previamente.</span><span class="sxs-lookup"><span data-stu-id="e37ff-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="e37ff-183">Selecciona la opción **Inteligencia** para crear un segmento alrededor de una de las entidades de salida que generó con las capacidades **Predicciones** o **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="e37ff-184">En el cuadro de diálogo **Nuevo segmento rápido**, seleccione un atributo en el campo desplegable **Campo**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="e37ff-185">El sistema proporcionará información adicional que le ayudará a crear mejores segmentos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="e37ff-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="e37ff-186">Para los campos categóricos, mostraremos los 10 principales recuentos de clientes.</span><span class="sxs-lookup"><span data-stu-id="e37ff-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="e37ff-187">Elija un **Valor** y seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="e37ff-188">Para un atributo numérico, el sistema mostrará qué valor de atributo corresponde al percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="e37ff-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="e37ff-189">Elija un **Operador** y un **Valor**, luego seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="e37ff-190">El sistema le proporcionará un **Tamaño de segmento estimado**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="e37ff-191">Puede elegir si genera el segmento que ha definido o volver a visitarlo para obtener un tamaño de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="e37ff-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e37ff-192">![Nombre y estimación de un segmento rápido](media/quick-segment-name.png "Nombre y estimación de un segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="e37ff-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="e37ff-193">Dé un **Nombre** al segmento.</span><span class="sxs-lookup"><span data-stu-id="e37ff-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="e37ff-194">Opcionalmente, proporcione un **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="e37ff-195">Seleccione **Guardar** para crear el segmento.</span><span class="sxs-lookup"><span data-stu-id="e37ff-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="e37ff-196">Una vez que el segmento ha terminado de procesarse, puede verlo como cualquier otro segmento que haya creado.</span><span class="sxs-lookup"><span data-stu-id="e37ff-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e37ff-197">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e37ff-197">Next steps</span></span>

<span data-ttu-id="e37ff-198">[Exportar un segmento](export-destinations.md) y explorar la [Tarjeta de cliente](customer-card-add-in.md) y [Conectores](export-power-bi.md) para obtener información a nivel del cliente.</span><span class="sxs-lookup"><span data-stu-id="e37ff-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
