---
title: Relaciones entre entidades y rutas de entidades
description: Cree y administre relaciones entre entidades de múltiples fuentes de datos.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171185"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="3406f-103">Relaciones entre entidades</span><span class="sxs-lookup"><span data-stu-id="3406f-103">Relationships between entities</span></span>

<span data-ttu-id="3406f-104">Las relaciones conectan entidades y definen un gráfico de sus datos cuando las entidades comparten un identificador común, una clave externa.</span><span class="sxs-lookup"><span data-stu-id="3406f-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="3406f-105">Se puede hacer referencia a esta clave externa de una entidad a otra.</span><span class="sxs-lookup"><span data-stu-id="3406f-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="3406f-106">Las entidades conectadas habilitan la definición de segmentos y medidas basadas en múltiples orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="3406f-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="3406f-107">Hay tres tipos de relaciones:</span><span class="sxs-lookup"><span data-stu-id="3406f-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="3406f-108">Sistema no editable de relaciones, creado por el sistema como parte del proceso de unificación de datos</span><span class="sxs-lookup"><span data-stu-id="3406f-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="3406f-109">Relaciones heredadas no editables, que se crean automáticamente a partir de la ingesta de fuentes de datos</span><span class="sxs-lookup"><span data-stu-id="3406f-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="3406f-110">Relaciones personalizadas editables, creadas y configuradas por usuarios</span><span class="sxs-lookup"><span data-stu-id="3406f-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="3406f-111">Relaciones no editables de sistema</span><span class="sxs-lookup"><span data-stu-id="3406f-111">Non-editable system relationships</span></span>

<span data-ttu-id="3406f-112">Durante la unificación de datos, las relaciones del sistema se crean automáticamente en función de la comparación inteligente.</span><span class="sxs-lookup"><span data-stu-id="3406f-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="3406f-113">Estas relaciones ayudan a relacionar los registros del perfil del cliente con los registros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3406f-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="3406f-114">El siguiente diagrama ilustra la creación de tres relaciones basadas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3406f-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="3406f-115">La entidad del cliente se empareja con otras entidades para producir la entidad unificada *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="3406f-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama con rutas de relación para la entidad cliente con tres 1-n Relaciones.":::

- <span data-ttu-id="3406f-117">La **relación *CustomerToContact*** fue creada entre la entidad *Cliente* y la entidad *Contacto*.</span><span class="sxs-lookup"><span data-stu-id="3406f-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="3406f-118">La entidad *Cliente* obtiene el campo de clave **Contact_contactID** para relacionarse con el campo de clave de la entidad *Contacto* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="3406f-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="3406f-119">La **relación *CustomerToContact*** fue creada entre la entidad *Cliente* y la entidad *Cuenta*.</span><span class="sxs-lookup"><span data-stu-id="3406f-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="3406f-120">La entidad *Cliente* obtiene el campo de clave **Account_accountId** para relacionarse con el campo de clave de la entidad *Cuenta* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="3406f-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="3406f-121">La **relación *CustomerToWebAccount*** fue creada entre la entidad *Cliente* y la entidad *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="3406f-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="3406f-122">La entidad *Cliente* obtiene el campo de clave **WebAccount_webaccountID** para relacionarse con el campo de clave de la entidad *WebAccount* **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="3406f-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="3406f-123">Relaciones no editables heredadas</span><span class="sxs-lookup"><span data-stu-id="3406f-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="3406f-124">Durante el proceso de ingestión de datos, el sistema verifica las fuentes de datos en busca de relaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="3406f-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="3406f-125">Si no existe ninguna relación, el sistema las crea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3406f-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="3406f-126">Estos relaciones también se utilizan en procesos posteriores.</span><span class="sxs-lookup"><span data-stu-id="3406f-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="3406f-127">Crear una relación personalizada</span><span class="sxs-lookup"><span data-stu-id="3406f-127">Create a custom relationship</span></span>

<span data-ttu-id="3406f-128">La relación consiste en una *entidad fuente* que contiene la clave externa y una *entidad objetivo* al que apunta la clave externa de la entidad de origen.</span><span class="sxs-lookup"><span data-stu-id="3406f-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="3406f-129">En las informaciones de público, vaya a **Datos** > **Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="3406f-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="3406f-130">Selecciona **Nueva relación**.</span><span class="sxs-lookup"><span data-stu-id="3406f-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="3406f-131">En el panel **Nueva relación**, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3406f-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Nuevo panel lateral de relaciones con campos de entrada vacíos.":::

   - <span data-ttu-id="3406f-133">**Nombre de la relación**: nombre que refleja el propósito de la relación.</span><span class="sxs-lookup"><span data-stu-id="3406f-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="3406f-134">Ejemplo: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="3406f-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="3406f-135">**Descripción**: Descripción de la relación.</span><span class="sxs-lookup"><span data-stu-id="3406f-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="3406f-136">**Entidad origen**: entidad que se utiliza como origen en la relación.</span><span class="sxs-lookup"><span data-stu-id="3406f-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="3406f-137">Ejemplo: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="3406f-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="3406f-138">**Entidad destino**: entidad que se utiliza como destino en la relación.</span><span class="sxs-lookup"><span data-stu-id="3406f-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="3406f-139">Ejemplo: Cliente.</span><span class="sxs-lookup"><span data-stu-id="3406f-139">Example: Customer.</span></span>
   - <span data-ttu-id="3406f-140">**Cardinalidad de fuente**: especifique la cardinalidad de la entidad fuente.</span><span class="sxs-lookup"><span data-stu-id="3406f-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="3406f-141">La cardinalidad describe el número de elementos posibles en un conjunto.</span><span class="sxs-lookup"><span data-stu-id="3406f-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="3406f-142">Siempre se relaciona con la cardinalidad del objetivo.</span><span class="sxs-lookup"><span data-stu-id="3406f-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="3406f-143">Puedes elegir entre **Uno** y **Muchos**.</span><span class="sxs-lookup"><span data-stu-id="3406f-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="3406f-144">Solo se admiten relaciones de varios a uno y de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="3406f-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="3406f-145">Varios a uno: varios registros de origen pueden relacionarse con un registro de destino.</span><span class="sxs-lookup"><span data-stu-id="3406f-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="3406f-146">Ejemplo: varios casos de soporte de un solo cliente.</span><span class="sxs-lookup"><span data-stu-id="3406f-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="3406f-147">Uno a uno: un registro de origen único se relaciona con un registro de destino.</span><span class="sxs-lookup"><span data-stu-id="3406f-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="3406f-148">Ejemplo: un ID de fidelidad para un solo cliente.</span><span class="sxs-lookup"><span data-stu-id="3406f-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3406f-149">Puede crear una relación de varios a varios creando dos relaciones de varios a uno y una entidad de vinculación que conecte la entidad de origen y la entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="3406f-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="3406f-150">**Cardinalidad de destino**: Seleccione la cardinalidad de los registros de la entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="3406f-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="3406f-151">**Campo de clave de origen**: el campo de clave externa en la entidad de origen.</span><span class="sxs-lookup"><span data-stu-id="3406f-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="3406f-152">Ejemplo: SupportCase podría usar CaseID como un campo de clave externa.</span><span class="sxs-lookup"><span data-stu-id="3406f-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="3406f-153">**Campo clave de destino**: el campo clave de la entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="3406f-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="3406f-154">Ejemplo el cliente podría usar el campo clave **CustomerID** campo clave.</span><span class="sxs-lookup"><span data-stu-id="3406f-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="3406f-155">Seleccione **Guardar** para crear la relación personalizada.</span><span class="sxs-lookup"><span data-stu-id="3406f-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="3406f-156">Vista de relaciones</span><span class="sxs-lookup"><span data-stu-id="3406f-156">View relationships</span></span>

<span data-ttu-id="3406f-157">La página Relaciones enumera todos los Relaciones que se han creado.</span><span class="sxs-lookup"><span data-stu-id="3406f-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="3406f-158">Cada fila representa una relación, que también incluye detalles sobre la entidad de origen, la entidad de destino y la cardinalidad.</span><span class="sxs-lookup"><span data-stu-id="3406f-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de Relaciones y opciones en la barra de acciones de la página Relaciones.":::

<span data-ttu-id="3406f-160">Esta página ofrece un conjunto de opciones para relaciones existentes y nuevas:</span><span class="sxs-lookup"><span data-stu-id="3406f-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="3406f-161">**Nueva relación**: [Crear una relación personalizada](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="3406f-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="3406f-162">**Visualizador**: [Explore el visualizador de relaciones](#explore-the-relationship-visualizer) para ver un diagrama de red de relaciones existente y su cardinalidad.</span><span class="sxs-lookup"><span data-stu-id="3406f-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="3406f-163">**Filtrado por**: elija el tipo de Relaciones para mostrar en la lista.</span><span class="sxs-lookup"><span data-stu-id="3406f-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="3406f-164">**Buscar Relaciones**: utilice una búsqueda basada en texto en las propiedades de Relaciones.</span><span class="sxs-lookup"><span data-stu-id="3406f-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="3406f-165">Explore el visualizador de relaciones</span><span class="sxs-lookup"><span data-stu-id="3406f-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="3406f-166">El visualizador de relaciones muestra un diagrama de red de relaciones existente entre entidades conectadas y su cardinalidad.</span><span class="sxs-lookup"><span data-stu-id="3406f-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="3406f-167">Para personalizar la vista, puede cambiar la posición de los cuadros arrastrándolos en el lienzo.</span><span class="sxs-lookup"><span data-stu-id="3406f-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla del diagrama de red del visualizador de relaciones con conexiones entre entidades relacionadas.":::

<span data-ttu-id="3406f-169">Opciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="3406f-169">Available options:</span></span> 
- <span data-ttu-id="3406f-170">**Exportar como imagen**: guarda la vista actual como un archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="3406f-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="3406f-171">**Cambiar a diseño horizontal / vertical**: cambia la alineación de las entidades y relaciones.</span><span class="sxs-lookup"><span data-stu-id="3406f-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="3406f-172">**Editar**: actualiza las propiedades de relaciones personalizadas en el panel de edición y guarda los cambios.</span><span class="sxs-lookup"><span data-stu-id="3406f-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="3406f-173">Administrar las relaciones existentes</span><span class="sxs-lookup"><span data-stu-id="3406f-173">Manage existing relationships</span></span> 

<span data-ttu-id="3406f-174">En la página Relaciones, cada relación está representada por una fila.</span><span class="sxs-lookup"><span data-stu-id="3406f-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="3406f-175">Seleccione una relación y elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3406f-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="3406f-176">**Editar**: actualiza las propiedades de relaciones personalizadas en el panel de edición y guarda los cambios.</span><span class="sxs-lookup"><span data-stu-id="3406f-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="3406f-177">**Eliminar**: elimina relaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3406f-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="3406f-178">**Vista**: ver relaciones creadas por el sistema y heredadas.</span><span class="sxs-lookup"><span data-stu-id="3406f-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="3406f-179">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="3406f-179">Next step</span></span>

<span data-ttu-id="3406f-180">Las relaciones del sistema y personalizadas se utilizan para [crear segmentos](segments.md) basados en varios orígenes de datos que ya no están en desconectados.</span><span class="sxs-lookup"><span data-stu-id="3406f-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
