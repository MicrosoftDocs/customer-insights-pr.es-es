---
title: Actividades del cliente
description: Defina las actividades del cliente y visualícelas en la escala de tiempo del cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596750"
---
# <a name="customer-activities"></a><span data-ttu-id="a9ec7-103">Actividades del cliente</span><span class="sxs-lookup"><span data-stu-id="a9ec7-103">Customer activities</span></span>

<span data-ttu-id="a9ec7-104">Combine las actividades del cliente de [varias fuentes de datos](data-sources.md) en Dynamics 365 Customer Insights para crear una línea de tiempo del cliente que enumere las actividades en orden cronológico.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="a9ec7-105">Puede incluir la escala de tiempo en las aplicaciones de involucración del cliente en Dynamics 365 a través del [Complemento de tarjeta de cliente](customer-card-add-in.md), o en un panel Power BI.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="a9ec7-106">Definir una actividad</span><span class="sxs-lookup"><span data-stu-id="a9ec7-106">Define an activity</span></span>

<span data-ttu-id="a9ec7-107">Sus orígenes de datos incluyen entidades con datos transaccionales y de actividad procedentes de varios orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="a9ec7-108">Identifique estas entidades y seleccione las actividades que desea ver en la escala de tiempo del cliente.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="a9ec7-109">Elija la entidad que incluye las actividades de destino.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="a9ec7-110">En informaciones del público, vaya a **Datos** > **Ocupaciones**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="a9ec7-111">Seleccione **Agregar actividad**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a9ec7-112">Una entidad debe tener como mínimo un atributo de tipo **Fecha** que se debe incluir en una escala de tiempo de cliente, y no se pueden agregar entidades sin campos de **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="a9ec7-113">El control **Agregar actividad** está deshabilitado si no se encuentra esa entidad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="a9ec7-114">En el panel **Agregar actividad**, establezca los valores de los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="a9ec7-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="a9ec7-115">**Entidad**: seleccione una entidad que incluya datos transaccionales o de actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="a9ec7-116">**Clave principal**: seleccione el campo que identifica de manera única un registro.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="a9ec7-117">No debe contener valores duplicados, valores vacíos ni valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="a9ec7-118">**Marca de tiempo**: seleccione el campo que representa la hora de inicio de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="a9ec7-119">**Evento**: seleccione el campo que es el evento de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="a9ec7-120">**Dirección web**: Seleccione el campo que representa una URL proporcionando información adicional sobre esta actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="a9ec7-121">Por ejemplo, el sistema transaccional que origina esta actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="a9ec7-122">Esta URL puede ser cualquier campo de origen de datos, o puede construirse como un nuevo campo utilizando una transformación de Power Query.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="a9ec7-123">Estos datos de URL se almacenarán en la entidad de Interfaz unificada, que se puede consumir en sentido descendente utilizando API.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="a9ec7-124">**Detalles**: opcionalmente, seleccione el campo que se agrega para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="a9ec7-125">**Icono**: opcionalmente, seleccione el icono que representa esta actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="a9ec7-126">**Tipo de actividad**: Defina la referencia del tipo de actividad como Common Data Model que mejor describe la definición semántica de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="a9ec7-127">En la sección **Configurar relación**, configure los detalles que se utilizarán para conectar los datos de actividad a su cliente correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="a9ec7-128">**Campo de entidad de actividad**: seleccione el campo en su entidad Actividad que se utilizará para establecer una relación con otra entidad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="a9ec7-129">**Entidad de cliente**: seleccione la entidad de cliente origen correspondiente con la que estará relacionada su entidad de actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="a9ec7-130">Puede relacionarse solo con aquellas entidades de clientes de origen que se utilizan en el proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="a9ec7-131">**Campo de entidad de cliente**: este campo muestra la clave principal de la entidad del cliente de origen seleccionada en el proceso de asignación.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="a9ec7-132">Este campo de clave principal en la entidad del cliente de origen se utiliza para establecer una relación con la entidad de actividad.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="a9ec7-133">**Nombre**: si ya existe una relación entre esta entidad de actividad y la entidad de cliente de origen seleccionada, el nombre de la relación estará en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="a9ec7-134">Si no existe tal relación, se creará una nueva relación con el nombre proporcionado aquí.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9ec7-135">![Definir la relación de entidad](media/activities-entities-define.png "Definir la relación de entidad")</span><span class="sxs-lookup"><span data-stu-id="a9ec7-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="a9ec7-136">Seleccione **Guardar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="a9ec7-137">En la página **Actividades**, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="a9ec7-138">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a9ec7-139">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a9ec7-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a9ec7-140">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a9ec7-141">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="a9ec7-142">Editar una actividad</span><span class="sxs-lookup"><span data-stu-id="a9ec7-142">Edit an activity</span></span>

1. <span data-ttu-id="a9ec7-143">En informaciones del público, vaya a **Datos** > **Ocupaciones**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="a9ec7-144">Seleccione la entidad de la actividad que quiere editar y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="a9ec7-145">O bien, puede pasar el cursor sobre la fila de la entidad y seleccionar el icono **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="a9ec7-146">Haga clic en el icono **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="a9ec7-147">En el panel **Editar actividad**, actualice los valores y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="a9ec7-148">En la página **Actividades**, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="a9ec7-149">Eliminar una actividad</span><span class="sxs-lookup"><span data-stu-id="a9ec7-149">Delete an activity</span></span>

1. <span data-ttu-id="a9ec7-150">En informaciones del público, vaya a **Datos** > **Ocupaciones**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="a9ec7-151">Seleccione la entidad de la actividad que quiere quitar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="a9ec7-152">O bien, puede pasar el cursor sobre la fila de la entidad y seleccionar el icono **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="a9ec7-153">Además, puede seleccionar varias entidades de actividad para eliminarlas a la vez.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9ec7-154">![Editar o eliminar las relaciones entre entidades](media/activities-entities-edit-delete.png "Editar o eliminar las relaciones entre entidades")</span><span class="sxs-lookup"><span data-stu-id="a9ec7-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="a9ec7-155">Seleccione el icono **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="a9ec7-156">Confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="a9ec7-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]