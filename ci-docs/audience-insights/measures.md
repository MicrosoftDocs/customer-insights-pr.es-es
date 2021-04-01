---
title: Crear y administrar medidas
description: Defina medidas para analizar y reflejar el rendimiento y el estado de su negocio.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654753"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="bc34c-103">Definir y administrar medidas</span><span class="sxs-lookup"><span data-stu-id="bc34c-103">Define and manage measures</span></span>

<span data-ttu-id="bc34c-104">Las medidas le ayudan a comprender mejor el comportamiento de los clientes y el rendimiento de la empresa recuperando valores relevantes de los [perfiles unificados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="bc34c-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="bc34c-105">Por ejemplo, una empresa quiere ver el *gasto total por cliente* para comprender el historial de compras de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="bc34c-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="bc34c-106">O medir las *ventas totales de la empresa* para comprender los ingresos a globales en la totalidad de la empresa.</span><span class="sxs-lookup"><span data-stu-id="bc34c-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="bc34c-107">Las medidas se crean utilizando el generador de medidas, una plataforma de consulta de datos con varios operadores y opciones de asignación sencillas.</span><span class="sxs-lookup"><span data-stu-id="bc34c-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="bc34c-108">Le permite filtrar los datos, agrupar resultados, detectar [rutas de relaciones de entidades](relationships.md) y obtener una vista previa de los resultados.</span><span class="sxs-lookup"><span data-stu-id="bc34c-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="bc34c-109">Utilice el generador de medidas para planificar actividades comerciales consultando datos de clientes y extraiga información.</span><span class="sxs-lookup"><span data-stu-id="bc34c-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="bc34c-110">Por ejemplo, crear una medida del *gasto total por cliente* y el *retorno total por cliente* ayuda a identificar un grupo de clientes con un alto gasto pero que aporta alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bc34c-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="bc34c-111">Puede [crear un segmento](segments.md) para impulsar las acciones más convenientes.</span><span class="sxs-lookup"><span data-stu-id="bc34c-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="bc34c-112">Crear una medida</span><span class="sxs-lookup"><span data-stu-id="bc34c-112">Create a measure</span></span>

<span data-ttu-id="bc34c-113">Esta sección le guía a través de la creación de nuevas medidas desde cero.</span><span class="sxs-lookup"><span data-stu-id="bc34c-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="bc34c-114">Puede crear una medida con atributos de datos a partir de entidades de datos que tengan una relación configurada para conectarse con la entidad Cliente.</span><span class="sxs-lookup"><span data-stu-id="bc34c-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="bc34c-115">En las informaciones de público, vaya a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="bc34c-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="bc34c-116">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bc34c-116">Select **New**.</span></span>

1. <span data-ttu-id="bc34c-117">Seleccione **Editar nombre** y proporcione un **Nombre** para la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="bc34c-118">Si su nueva configuración de medida tiene solo dos campos, por ejemplo, CustomerID y un cálculo, la salida se agregará como una nueva columna a la entidad generada por el sistema llamada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="bc34c-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="bc34c-119">Y podrá ver el valor de la medida en el perfil del cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="bc34c-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="bc34c-120">Otras medidas generarán sus entidades propias.</span><span class="sxs-lookup"><span data-stu-id="bc34c-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="bc34c-121">En el área de configuración, elija la función de agregación en el menú desplegable **Seleccionar función**.</span><span class="sxs-lookup"><span data-stu-id="bc34c-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="bc34c-122">Las funciones de agregación incluyen:</span><span class="sxs-lookup"><span data-stu-id="bc34c-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="bc34c-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="bc34c-123">**Sum**</span></span>
   - <span data-ttu-id="bc34c-124">**Media**</span><span class="sxs-lookup"><span data-stu-id="bc34c-124">**Average**</span></span>
   - <span data-ttu-id="bc34c-125">**Contar**</span><span class="sxs-lookup"><span data-stu-id="bc34c-125">**Count**</span></span>
   - <span data-ttu-id="bc34c-126">**Contar únicos**</span><span class="sxs-lookup"><span data-stu-id="bc34c-126">**Count Unique**</span></span>
   - <span data-ttu-id="bc34c-127">**Máximo**</span><span class="sxs-lookup"><span data-stu-id="bc34c-127">**Max**</span></span>
   - <span data-ttu-id="bc34c-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="bc34c-128">**Min**</span></span>
   - <span data-ttu-id="bc34c-129">**Primero**: toma el primer valor del registro de datos</span><span class="sxs-lookup"><span data-stu-id="bc34c-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="bc34c-130">**Último**: toma el último valor que se agregó al registro de datos</span><span class="sxs-lookup"><span data-stu-id="bc34c-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. <span data-ttu-id="bc34c-132">Seleccione **Agregar atributo** para seleccionar los datos que necesita para crear esta medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="bc34c-133">Seleccione la pestaña **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="bc34c-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="bc34c-134">Entidad de datos: elija la entidad que incluye el atributo que desea medir.</span><span class="sxs-lookup"><span data-stu-id="bc34c-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="bc34c-135">Atributo de datos: elija el atributo que desea utilizar en la función de suma para calcular la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="bc34c-136">Puede seleccionar solo un atributo a la vez.</span><span class="sxs-lookup"><span data-stu-id="bc34c-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="bc34c-137">También puede seleccionar un atributo de datos en una medida existente seleccionando la pestaña **Medidas**. O bien, puede buscar una entidad o nombre de medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="bc34c-138">Seleccione **Agregar** para agregar el atributo seleccionado a la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccione un atributo para usar en los cálculos.":::

1. <span data-ttu-id="bc34c-140">Para construir medidas más complejas, puede agregar más atributos o usar operadores matemáticos en su función de medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cree una medida compleja con operadores matemáticos.":::

1. <span data-ttu-id="bc34c-142">Para agregar filtros, seleccione la opción **Filtrar** en el área de configuración.</span><span class="sxs-lookup"><span data-stu-id="bc34c-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="bc34c-143">En la sección **Agregar atributo** del panel **Filtros**, seleccione el atributo que desea utilizar para crear filtros.</span><span class="sxs-lookup"><span data-stu-id="bc34c-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="bc34c-144">Configure los operadores de filtro para definir el filtro para cada atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bc34c-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="bc34c-145">Seleccione **Aplicar** para agregar los filtros para la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="bc34c-146">Para agregar dimensiones, seleccione la opción **Dimensión** en el área de configuración.</span><span class="sxs-lookup"><span data-stu-id="bc34c-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="bc34c-147">Las dimensiones se mostrarán a modo de columnas en la entidad de los resultados de la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="bc34c-148">Seleccione **Editar dimensiones** para agregar los atributos de datos según los cuales desea agrupar los valores de medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="bc34c-149">Por ejemplo, ciudad o género.</span><span class="sxs-lookup"><span data-stu-id="bc34c-149">For example, city or gender.</span></span> <span data-ttu-id="bc34c-150">De forma predeterminada, la dimensión *CustomerID* se selecciona crear *medidas a nivel de cliente*.</span><span class="sxs-lookup"><span data-stu-id="bc34c-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="bc34c-151">Puede eliminar la dimensión predeterminada si desea crear *medidas a nivel empresarial*.</span><span class="sxs-lookup"><span data-stu-id="bc34c-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="bc34c-152">Seleccione **Listo** para agregar dimensiones a la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="bc34c-153">Si hay varias rutas entre la entidad de datos que asignó y la entidad *Cliente*, debe elegir una de las [rutas de relación de entidad identificadas](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="bc34c-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="bc34c-154">Los resultados de la medición pueden variar según la ruta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bc34c-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="bc34c-155">Seleccione **Preferencias de datos** y elija la ruta de la entidad que se debe utilizar para identificar su medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="bc34c-156">Si solo hay un camino hacia la entidad *Cliente*, este control no se mostrará.</span><span class="sxs-lookup"><span data-stu-id="bc34c-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="bc34c-157">Seleccione **Listo** para aplicar su selección.</span><span class="sxs-lookup"><span data-stu-id="bc34c-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccione la ruta de la entidad para la medida.":::

1. <span data-ttu-id="bc34c-159">Para agregar más cálculos para la medida, seleccione **Nuevo cálculo**.</span><span class="sxs-lookup"><span data-stu-id="bc34c-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="bc34c-160">Solo puede usar entidades en la misma ruta de la entidad para los nuevos cálculos.</span><span class="sxs-lookup"><span data-stu-id="bc34c-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="bc34c-161">Aparecerán más cálculos a modo de columnas nuevas en la entidad de los resultados de la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="bc34c-162">Seleccione **...** en el cálculo para **Duplicar**, **Cambiar el nombre**, o **Eliminar** un cálculo de una medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="bc34c-163">En el área **Vista previa**, verá el esquema de datos de la entidad de los resultados de la medida, incluidos los filtros y las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="bc34c-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="bc34c-164">La vista previa reacciona dinámicamente a los cambios en la configuración.</span><span class="sxs-lookup"><span data-stu-id="bc34c-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="bc34c-165">Seleccione **Ejecutar** para calcular los resultados de la medida configurada.</span><span class="sxs-lookup"><span data-stu-id="bc34c-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="bc34c-166">Seleccione **Guardar y cerrar** si desea mantener la configuración actual y ejecutar la medida más tarde.</span><span class="sxs-lookup"><span data-stu-id="bc34c-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="bc34c-167">Vaya a **Medidas** para ver la medida recién creada en la lista.</span><span class="sxs-lookup"><span data-stu-id="bc34c-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="bc34c-168">Administrar sus medidas</span><span class="sxs-lookup"><span data-stu-id="bc34c-168">Manage your measures</span></span>

<span data-ttu-id="bc34c-169">Después de [crear una medida](#create-a-measure), verá una lista de medidas en la página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="bc34c-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="bc34c-170">Encontrará información sobre el tipo de medida, el creador, la fecha de creación y el estado.</span><span class="sxs-lookup"><span data-stu-id="bc34c-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="bc34c-171">Cuando selecciona una medida de la lista, puede obtener una vista previa del resultado y descargar un archivo .CSV.</span><span class="sxs-lookup"><span data-stu-id="bc34c-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="bc34c-172">Para actualizar todas sus medidas al mismo tiempo, seleccione **Actualizar todo** sin seleccionar una medida específica.</span><span class="sxs-lookup"><span data-stu-id="bc34c-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bc34c-173">![Acciones para gestionar medidas individuales](media/measure-actions.png "Acciones para gestionar medidas individuales")</span><span class="sxs-lookup"><span data-stu-id="bc34c-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="bc34c-174">Seleccione una medida de la lista para las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="bc34c-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="bc34c-175">Seleccione el nombre de la medida para ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="bc34c-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="bc34c-176">**Editar** la configuración de la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="bc34c-177">**Actualizar** la medida en función de los últimos datos.</span><span class="sxs-lookup"><span data-stu-id="bc34c-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="bc34c-178">**Cambiar nombre** de la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-178">**Rename** the measure.</span></span>
- <span data-ttu-id="bc34c-179">**Eliminar** la medida.</span><span class="sxs-lookup"><span data-stu-id="bc34c-179">**Delete** the measure.</span></span>
- <span data-ttu-id="bc34c-180">**Activar** o **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="bc34c-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="bc34c-181">Las medidas inactivas no se actualizarán durante una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bc34c-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="bc34c-182">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="bc34c-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bc34c-183">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bc34c-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bc34c-184">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="bc34c-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bc34c-185">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="bc34c-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="bc34c-186">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="bc34c-186">Next step</span></span>

<span data-ttu-id="bc34c-187">Puede utilizar medidas existentes para crear [un segmento de cliente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bc34c-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]