---
title: Asignar entidades para la unificación de datos
description: Mapa de datos para crear perfiles de cliente unificados.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267056"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="125be-103">Correlacionar entidades y atributos</span><span class="sxs-lookup"><span data-stu-id="125be-103">Map entities and attributes</span></span>

<span data-ttu-id="125be-104">**Mapa** es la primera etapa en el proceso de unificación de datos de informaciones de público.</span><span class="sxs-lookup"><span data-stu-id="125be-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="125be-105">La asignación consta de tres fases:</span><span class="sxs-lookup"><span data-stu-id="125be-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="125be-106">*Selección de entidades*: identifique las entidades combinables que conducen a un conjunto de datos con información más completa sobre sus clientes.</span><span class="sxs-lookup"><span data-stu-id="125be-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="125be-107">*Selección de atributos*: para cada entidad, identifique las columnas que desea combinar y conciliar en las fases de *coincidencia* y *combinación*.</span><span class="sxs-lookup"><span data-stu-id="125be-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="125be-108">Estas columnas se llaman *Atributos*.</span><span class="sxs-lookup"><span data-stu-id="125be-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="125be-109">*Selección de clave principal y tipo semántico*: Para cada entidad, identifique un atributo que desee definir como clave principal para esa entidad, y para cada atributo, identifique un tipo semántico que mejor describa ese atributo.</span><span class="sxs-lookup"><span data-stu-id="125be-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="125be-110">Para obtener más información sobre el flujo general de unificación de datos, consulte [Unificar](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="125be-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="125be-111">Seleccione las primeras entidades</span><span class="sxs-lookup"><span data-stu-id="125be-111">Select the first entities</span></span>

1. <span data-ttu-id="125be-112">En las informaciones de público, vaya a **Datos** > **Unificar** > **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="125be-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="125be-113">Inicie la fase de mapa seleccionando **Seleccionar entidades**.</span><span class="sxs-lookup"><span data-stu-id="125be-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="125be-114">Seleccione las entidades y atributos que desea utilizar en las fases *coincidencia* y *combinación*.</span><span class="sxs-lookup"><span data-stu-id="125be-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="125be-115">Puede seleccionar los atributos requeridos individualmente de una entidad o incluir todos los atributos de una entidad seleccionando la casilla **Incluir todos los campos** en el nivel de entidad.</span><span class="sxs-lookup"><span data-stu-id="125be-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="125be-116">Se recomienda seleccionar al menos dos entidades para beneficiarse del proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="125be-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="125be-117">![Ejemplo de agregar entidades](media/data-manager-configure-map-add-entities-example.png "Ejemplo de agregar entidades")</span><span class="sxs-lookup"><span data-stu-id="125be-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="125be-118">En este ejemplo, agregamos las entidades **eCommerceContactos** y **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="125be-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="125be-119">Al elegir estas entidades, puede obtener información sobre cuáles de los clientes comerciales en línea son miembros del programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="125be-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="125be-120">Puede buscar palabras clave en todos los atributos y entidades para seleccionar los atributos necesarios que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="125be-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="125be-121">![Ejemplo de campos de búsqueda](media/data-manager-configure-map-search-fields-example.png "Ejemplo de campos de búsqueda")</span><span class="sxs-lookup"><span data-stu-id="125be-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="125be-122">Seleccione **Aplicar** para confirmar sus selecciones.</span><span class="sxs-lookup"><span data-stu-id="125be-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="125be-123">Seleccione la clave principal y el tipo semántico para los atributos</span><span class="sxs-lookup"><span data-stu-id="125be-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="125be-124">Después de seleccionar sus entidades, la página **Mapa** enumera las entidades seleccionadas para su revisión.</span><span class="sxs-lookup"><span data-stu-id="125be-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="125be-125">Defina la clave principal de una entidad e identifique el tipo semántico de un atributo en la entidad.</span><span class="sxs-lookup"><span data-stu-id="125be-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="125be-126">**Clave principal**: seleccione un atributo como clave principal para cada una de las entidades.</span><span class="sxs-lookup"><span data-stu-id="125be-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="125be-127">Para que un atributo pueda ser una clave principal válida, no debe incluir valores duplicados, no deben faltar valores ni debe haber valores nulos.</span><span class="sxs-lookup"><span data-stu-id="125be-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="125be-128">Los atributos de tipo de datos de cadena, entero y GUID se admiten como claves principales y se mostrarán en un campo para que usted seleccione.</span><span class="sxs-lookup"><span data-stu-id="125be-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="125be-129">**Tipo semántico de atributo**: Categorías de los atributos, como dirección de correo electrónico o nombre.</span><span class="sxs-lookup"><span data-stu-id="125be-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="125be-130">Para usar modelos de IA para predicción inteligente de semántica, ahorrar tiempo y mejorar la precisión, configure **Asignación inteligente** a **Activada**.</span><span class="sxs-lookup"><span data-stu-id="125be-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="125be-131">La asignación inteligente destaca la recomendación de semántica basada en IA en el campo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="125be-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="125be-132">Si lo configura en **Desactivado**, verá nuestras recomendaciones de asignación regular.</span><span class="sxs-lookup"><span data-stu-id="125be-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="125be-133">Puede seleccionar cualquier tipo semántico de la lista de opciones disponibles y anular la selección sugerida.</span><span class="sxs-lookup"><span data-stu-id="125be-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="125be-134">![Tipo de atributo y predicción de semántica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo y predicción de semántica")</span><span class="sxs-lookup"><span data-stu-id="125be-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="125be-135">También es posible agregar un tipo semántico personalizado.</span><span class="sxs-lookup"><span data-stu-id="125be-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="125be-136">Seleccione el campo de tipo para un atributo y escriba el nombre de tipo semántico personalizado.</span><span class="sxs-lookup"><span data-stu-id="125be-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="125be-137">De esta forma, también puede cambiar los tipos de atributos que el sistema identificó.</span><span class="sxs-lookup"><span data-stu-id="125be-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="125be-138">Todos los atributos para los que se identifica automáticamente un tipo semántico se agrupan en la sección **Revisar campos asignados**.</span><span class="sxs-lookup"><span data-stu-id="125be-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="125be-139">Revise estos atributos y sus tipos semánticos porque se utilizarán para combinar sus entidades en el paso de combinación de la unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="125be-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="125be-140">Los atributos que no se asignan automáticamente a un tipo semántico se agrupan en la sección **Definir los datos en los campos sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="125be-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="125be-141">Seleccione el campo de tipo semántico para los atributos sin asignar, o introduzca su nombre de tipo de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="125be-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="125be-142">![Clave principal y tipo de atributo](media/data-manager-configure-map-add-attributes.png "Clave principal y tipo de atributo")</span><span class="sxs-lookup"><span data-stu-id="125be-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="125be-143">Un campo se debe asignar al tipo semántico Person.FullName para completar el nombre del cliente en la tarjeta del cliente.</span><span class="sxs-lookup"><span data-stu-id="125be-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="125be-144">De lo contrario, las tarjetas de cliente aparecerán sin nombre.</span><span class="sxs-lookup"><span data-stu-id="125be-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="125be-145">Agregar y quitar atributos y entidades</span><span class="sxs-lookup"><span data-stu-id="125be-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="125be-146">En **Unificar** > **Asignar**, seleccione **Editar campos**.</span><span class="sxs-lookup"><span data-stu-id="125be-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="125be-147">En el panel **Editar campos**, agregue o quite atributos y entidades.</span><span class="sxs-lookup"><span data-stu-id="125be-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="125be-148">Utilice la búsqueda o desplácese para buscar y seleccionar sus atributos y entidades de interés.</span><span class="sxs-lookup"><span data-stu-id="125be-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="125be-149">No puede eliminar un atributo o una entidad si ya se han asociado.</span><span class="sxs-lookup"><span data-stu-id="125be-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="125be-150">![Agregar o quitar atributos](media/configure-data-map-edit.png "Agregar o quitar atributos")</span><span class="sxs-lookup"><span data-stu-id="125be-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="125be-151">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="125be-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="125be-152">Agregar imágenes a perfiles</span><span class="sxs-lookup"><span data-stu-id="125be-152">Add images to profiles</span></span>

<span data-ttu-id="125be-153">Si una entidad contiene URL para imágenes de perfil o logotipos disponibles públicamente, puede agregarlas al perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="125be-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="125be-154">Seleccione la entidad y busque el campo que contiene la URL de la imagen de perfil.</span><span class="sxs-lookup"><span data-stu-id="125be-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="125be-155">En el campo de entrada **Tipo**, escriba manualmente el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="125be-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="125be-156">Para una persona: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="125be-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="125be-157">Para una organización: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="125be-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="125be-158">Continúe con los pasos de unificación y asegúrese de que el atributo que contiene la URL de la imagen también se agregue en el paso [Combinación](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="125be-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="125be-159">Establecer atributos para organizaciones</span><span class="sxs-lookup"><span data-stu-id="125be-159">Set attributes for organizations</span></span>

<span data-ttu-id="125be-160">Para las organizaciones (versión preliminar), el tipo de atributo debe asignarse a "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="125be-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="125be-161">![Clave principal y tipo de atributo B2B](media/configure-data-map-edit-b2b.png "Clave principal y tipo de atributo B2B")</span><span class="sxs-lookup"><span data-stu-id="125be-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="125be-162">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="125be-162">Next step</span></span>

<span data-ttu-id="125be-163">Como parte del proceso de unificación de datos, vaya a la página **Coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="125be-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="125be-164">Visite [**Coincidencia**](match-entities.md) para obtener información sobre esta fase.</span><span class="sxs-lookup"><span data-stu-id="125be-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="125be-165">Mira el siguiente video: [Primeros pasos: crear un perfil de cliente unificado](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="125be-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]