---
title: Crear y editar medidas
description: Defina medidas relacionadas con el cliente para analizar y reflejar el rendimiento de ciertas áreas de negocio.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407047"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="f5ab0-103">Definir y administrar medidas</span><span class="sxs-lookup"><span data-stu-id="f5ab0-103">Define and manage measures</span></span>

<span data-ttu-id="f5ab0-104">**Medidas** representa indicadores clave de rendimiento (KPI) que reflejan el rendimiento y la salud de áreas comerciales específicas.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="f5ab0-105">Las informaciones de público proporcionan una experiencia intuitiva para crear diferentes tipos de medidas, utilizando un generador de consultas que no requiere que codifique o valide sus medidas manualmente.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="f5ab0-106">Puede realizar un seguimiento de sus medidas empresariales en la página **Inicio**, ver medidas para clientes específicos en la **Tarjeta de cliente** y utilizar medidas para definir segmentos de clientes en la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="f5ab0-107">Crear una medida</span><span class="sxs-lookup"><span data-stu-id="f5ab0-107">Create a measure</span></span>

<span data-ttu-id="f5ab0-108">Esta sección le guía a través de la creación de una medida desde cero.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="f5ab0-109">Puede crear medidas con datos de múltiples orígenes de datos que están conectadas a través de la entidad Cliente.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="f5ab0-110">Se aplican algunos [límites de servicio](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="f5ab0-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="f5ab0-111">En las informaciones de público, vaya a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="f5ab0-112">Seleccione **Nueva medida**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-112">Select **New measure**.</span></span>

3. <span data-ttu-id="f5ab0-113">Elija el **Tipo** de medida:</span><span class="sxs-lookup"><span data-stu-id="f5ab0-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="f5ab0-114">**Atributo de cliente**: Un campo único por cliente que refleja una puntuación, un valor o un estado para el cliente.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="f5ab0-115">Los atributos de cliente se crean como atributos en una nueva entidad generada por el sistema llamada **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="f5ab0-116">**Medida de cliente**: Información sobre el comportamiento del cliente con desglose por dimensiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="f5ab0-117">Se genera una nueva entidad para cada medida, potencialmente con múltiples registros por cliente.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="f5ab0-118">**Medida empresarial**: Realiza un seguimiento del rendimiento y la salud de su negocio.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="f5ab0-119">Las medidas empresariales pueden tener dos salidas diferentes: una salida numérica que se muestra en la página **Inicio** o una nueva entidad que se encuentra en la página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="f5ab0-120">Proporcione un **Nombre** y un **Nombre para mostrar** opcional y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="f5ab0-121">En la sección **Entidades**, seleccione la primera entidad en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="f5ab0-122">En este punto, debe decidir si se necesitan entidades adicionales como parte de su definición de medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5ab0-123">![Definición de la medida](media/measure-definition.png "Definición de la medida")</span><span class="sxs-lookup"><span data-stu-id="f5ab0-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="f5ab0-124">Para agregar más entidades, seleccione **Agregar entidad** y seleccione las entidades que desea usar para la medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f5ab0-125">Puede seleccionar solo las entidades que tienen relaciones con su entidad inicial.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="f5ab0-126">Para obtener más información sobre la definición de relaciones, vea [Relaciones](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f5ab0-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="f5ab0-127">Opcionalmente, puede configurar variables.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="f5ab0-128">En la sección **Variables**, seleccione **Nueva variable**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="f5ab0-129">Las variables son cálculos que se realizan en cada uno de los registros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="f5ab0-130">Por ejemplo, sumando ventas en el puntos de venta (POS) y en línea para cada uno de los registros de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="f5ab0-131">Especifique un **Nombre** para la variable.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="f5ab0-132">En el área **Expresión**, elija un campo con el que comenzar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="f5ab0-133">Escriba una expresión en el área **Expresión** mientras selecciona más campos para incluir en su cálculo.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f5ab0-134">Actualmente, solo se admiten expresiones aritméticas.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="f5ab0-135">Además, el cálculo de variables no es compatible con entidades de diferentes [rutas de entidad](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f5ab0-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="f5ab0-136">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-136">Select **Done**.</span></span>

11. <span data-ttu-id="f5ab0-137">En la sección **Definición de medida**, definirá cómo las entidades elegidas y las variables calculadas se agregan en una nueva entidad o atributo de medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="f5ab0-138">Seleccione **Nueva dimensión**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-138">Select **New dimension**.</span></span> <span data-ttu-id="f5ab0-139">Una dimensión se puede considerar como una función *agrupar por*.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="f5ab0-140">La salida de datos de su entidad o atributo de Medida se agrupará por todas sus dimensiones definidas.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f5ab0-141">![Elegir ciclo agregado](media/measures-businessreport-measure-definition2.png "Elegir ciclo agregado")</span><span class="sxs-lookup"><span data-stu-id="f5ab0-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="f5ab0-142">Seleccione o ingrese la siguiente información como parte de la definición de su dimensión:</span><span class="sxs-lookup"><span data-stu-id="f5ab0-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="f5ab0-143">**Entidad**: Si define una entidad de Medida, debe incluir al menos un atributo.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="f5ab0-144">Si define un atributo de Medida, incluirá solo un atributo de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="f5ab0-145">En esta selección se trata de elegir la entidad que incluye ese atributo.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="f5ab0-146">**Campo**: Elija el atributo específico que se incluirá en su entidad o atributo de Medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="f5ab0-147">**Cubo**: Elija si desea agregar datos diariamente, mensualmente o anualmente.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="f5ab0-148">Es una selección obligatoria solo si ha seleccionado un atributo de tipo Fecha.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="f5ab0-149">**Como**: Define el nombre de su nuevo campo.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="f5ab0-150">**Nombre para mostrar**: Define el nombre para mostrar del campo.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5ab0-151">Su medida empresarial se guardará como una entidad de un solo número y aparecerá en la página **Principal** a menos que agregue más dimensiones a su medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="f5ab0-152">Después de agregar más dimensiones, la medida *no* se mostrará en la página **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="f5ab0-153">Opcionalmente, agregue funciones de agregación.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="f5ab0-154">Cualquier agregación que cree produce un nuevo valor en su entidad o atributo de Medidas.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="f5ab0-155">Las funciones de agregación compatibles son: **Mín**, **Máx**, **Promedio**, **Mediana**, **Suma**, **Contar únicos**, **Primero** (toma el primer registro de un valor de dimensión) y **Último** (toma el último registro agregado a un valor de dimensión).</span><span class="sxs-lookup"><span data-stu-id="f5ab0-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="f5ab0-156">Seleccione **Guardar** para aplicar los cambios a la medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="f5ab0-157">Administrar sus medidas</span><span class="sxs-lookup"><span data-stu-id="f5ab0-157">Manage your measures</span></span>

<span data-ttu-id="f5ab0-158">Después de crear al menos una medida, verá una lista de medidas en la página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="f5ab0-159">Encontrará información sobre el tipo de medida, el creador, la fecha y hora de creación, la última fecha y hora de edición, el estado (si la medida está activa, inactiva o con error) y la última fecha y hora de actualización.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="f5ab0-160">Cuando selecciona una medida de la lista, puede ver una vista previa de su resultado.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="f5ab0-161">Para actualizar todas sus medidas al mismo tiempo, seleccione **Actualizar todo** sin seleccionar una medida específica.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f5ab0-162">![Acciones para gestionar medidas individuales](media/measure-actions.png "Acciones para gestionar medidas individuales")</span><span class="sxs-lookup"><span data-stu-id="f5ab0-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="f5ab0-163">Alternativamente, seleccione una medida de la lista y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f5ab0-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="f5ab0-164">Seleccione el nombre de la medida para ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="f5ab0-165">**Editar** la configuración de la medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="f5ab0-166">**Cambiar nombre** de la medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-166">**Rename** the measure.</span></span>
- <span data-ttu-id="f5ab0-167">**Eliminar** la medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-167">**Delete** the measure.</span></span>
- <span data-ttu-id="f5ab0-168">Seleccione los puntos suspensivos (...) y luego **Actualizar** para iniciar el proceso de actualización de la medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="f5ab0-169">Seleccione los puntos suspensivos (...) y luego **Descargar** para obtener un archivo .CSV de la medida.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="f5ab0-170">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f5ab0-171">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f5ab0-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f5ab0-172">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f5ab0-173">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5ab0-174">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f5ab0-174">Next step</span></span>

<span data-ttu-id="f5ab0-175">Puede utilizar medidas existentes para crear su primer segmento de clientes en la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="f5ab0-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="f5ab0-176">Para más información, vea [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f5ab0-176">For more information, see [Segments](segments.md).</span></span>
