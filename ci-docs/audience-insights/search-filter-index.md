---
title: Buscar y filtrar perfiles de clientes
description: Encuentre rápidamente información sobre perfiles de clientes unificados y filtre los atributos especificados.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270087"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="ff1f2-103">Perfiles de clientes: índice de búsqueda y filtro</span><span class="sxs-lookup"><span data-stu-id="ff1f2-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="ff1f2-104">El resultado de unificar los datos de sus clientes es una entidad Perfil del Cliente que proporciona una vista unificada de su base total de clientes.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="ff1f2-105">Para [encontrar rápidamente información sobre un cliente específico o un grupo de clientes](customer-profiles.md), puede configurar las funciones **Buscar** y **Filtrar** en la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="ff1f2-106">Siga leyendo para aprender cómo los administradores pueden editar los atributos en la página **Índice de Buscar y filtrar**, que están disponibles para que los usuarios puedan buscarlos y filtrarlos.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ff1f2-107">![Filtro de búsqueda](media/search-filter.png "Filtro de búsqueda")</span><span class="sxs-lookup"><span data-stu-id="ff1f2-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="ff1f2-108">Agregar campos y especificar atributos</span><span class="sxs-lookup"><span data-stu-id="ff1f2-108">Add fields and specify attributes</span></span>

<span data-ttu-id="ff1f2-109">Si es la primera vez que define atributos de búsqueda como administrador, primero debe definir los campos indexados.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="ff1f2-110">Le sugerimos que elija todos los atributos por los cuales los usuarios pueden buscar y filtrar clientes en la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="ff1f2-111">Solo puede especificar atributos que existan en la entidad Perfil del cliente que creó durante el proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="ff1f2-112">Abra la página **Clientes** y seleccione **Índice de Buscar y filtrar**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="ff1f2-113">Seleccione **+Agregar** para especificar los campos indexados.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="ff1f2-114">Seleccione en la lista los atributos que desea agregar como campos indexados.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="ff1f2-115">Siempre puede agregar más atributos seleccionando **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="ff1f2-116">También puede quitar los atributos seleccionados seleccionando el símbolo **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="ff1f2-117">Explore la tabla de campos de clientes indexados</span><span class="sxs-lookup"><span data-stu-id="ff1f2-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="ff1f2-118">La siguiente información se proporciona en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="ff1f2-119">**Nombre**: Representa el nombre del atributo tal como aparece en la entidad Perfil del cliente.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="ff1f2-120">**Tipo de datos**: Especifica si el tipo de datos es una cadena, un número o una fecha.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="ff1f2-121">**Incluidos en la búsqueda**: Especifica si este atributo se puede utilizar para buscar clientes en la página **Clientes** usando el campo **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="ff1f2-122">**Agregar filtro**: Control para definir cómo se puede utilizar este atributo para filtrar en la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="ff1f2-123">Edición de opciones de filtrado para un atributo dado</span><span class="sxs-lookup"><span data-stu-id="ff1f2-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="ff1f2-124">El menú **Filtrar** de la página **Clientes** puede incluir un número variable de niveles de atributo (por ejemplo, diferentes grupos de edad para filtrar clientes).</span><span class="sxs-lookup"><span data-stu-id="ff1f2-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="ff1f2-125">Seleccione **Agregar filtro** para un atributo dado en la página **Índice de Buscar y filtrar**.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="ff1f2-126">Puede definir el número de resultados y el orden en que se organizarán.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="ff1f2-127">Dependiendo del tipo de datos del atributo, aparece uno de los siguientes paneles.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="ff1f2-128">Atributos de tipo cadena: Especifique el número de resultados deseados en el panel **Opciones de filtro de cadena** y la directiva de orden mediante la cual se organizarán.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ff1f2-129">Atributos de tipo numérico: Especifique los intervalos incluidos en el panel **Opciones de filtro de número** y la directiva de orden mediante la cual se organizarán.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ff1f2-130">Atributos de tipo fecha: Especifique los intervalos incluidos en el panel **Opciones de filtro de fecha** y la directiva de orden mediante la cual se organizarán.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="ff1f2-131">Seleccione **Guardar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="ff1f2-132">Seleccione **Ejecutar** una vez que esté listo para aplicar su configuración.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ff1f2-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ff1f2-133">Next steps</span></span>

<span data-ttu-id="ff1f2-134">Vaya a la página **Clientes** para buscar perfiles de clientes o utilice los campos indexados para ver un subconjunto de todos los perfiles de clientes.</span><span class="sxs-lookup"><span data-stu-id="ff1f2-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]