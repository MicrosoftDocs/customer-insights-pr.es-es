---
title: Ver perfiles de clientes
description: Obtenga una vista combinada de los datos unificados de sus clientes.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269765"
---
# <a name="customer-profiles"></a><span data-ttu-id="89ef7-103">Perfiles de clientes</span><span class="sxs-lookup"><span data-stu-id="89ef7-103">Customer profiles</span></span>

<span data-ttu-id="89ef7-104">La página **Clientes** muestra una vista combinada de sus clientes, basada en los datos de perfil recopilados de [todos los orígenes de datos](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="89ef7-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="89ef7-105">Los perfiles de cliente están disponibles una vez [creada la entidad Cliente unificado](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="89ef7-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="89ef7-106">Asegúrese de completar el proceso de unificación de datos para obtener vistas más completas de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="89ef7-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="89ef7-107">La página también le permite buscar clientes.</span><span class="sxs-lookup"><span data-stu-id="89ef7-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="89ef7-108">Los clientes pueden ser individuos u organizaciones (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="89ef7-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="89ef7-109">Cada perfil de cliente u organización está representado por una ventana.</span><span class="sxs-lookup"><span data-stu-id="89ef7-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="89ef7-110">Seleccione una ventana para ver información adicional sobre ese cliente u organización específico.</span><span class="sxs-lookup"><span data-stu-id="89ef7-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="89ef7-111">Utilice los controles de paginación en la parte inferior de la lista para ver registros adicionales.</span><span class="sxs-lookup"><span data-stu-id="89ef7-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="89ef7-112">![Perfiles de cliente B2C](media/profiles-customers.png "Perfiles de cliente B2C")</span><span class="sxs-lookup"><span data-stu-id="89ef7-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="89ef7-113">Organizaciones (vista previa)</span><span class="sxs-lookup"><span data-stu-id="89ef7-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="89ef7-114">![Perfiles de cliente B2B](media/profile-customers-b2b.png "Perfiles de cliente B2B")</span><span class="sxs-lookup"><span data-stu-id="89ef7-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="89ef7-115">Si no puede ver los mosaicos cuando selecciona **Clientes** en navegación, su Administrador necesita [definir al menos un atributo de que se pueda buscar](search-filter-index.md) en el **Índice de Buscar y filtrar**.</span><span class="sxs-lookup"><span data-stu-id="89ef7-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="89ef7-116">Buscar clientes</span><span class="sxs-lookup"><span data-stu-id="89ef7-116">Search for customers</span></span>

<span data-ttu-id="89ef7-117">Busque clientes introduciendo un nombre o algún otro atributo en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="89ef7-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="89ef7-118">La búsqueda solo funciona en la entidad Perfil de cliente creada durante el proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="89ef7-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="89ef7-119">Como administrador, puede configurar los atributos que se pueden buscar mediante la página de **Índice de Buscar y filtrar**.</span><span class="sxs-lookup"><span data-stu-id="89ef7-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="89ef7-120">Si desea obtener más información, consulte el tema sobre [Administrar Índice de Buscar y filtrar](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="89ef7-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="89ef7-121">Filtrar clientes</span><span class="sxs-lookup"><span data-stu-id="89ef7-121">Filter customers</span></span>

<span data-ttu-id="89ef7-122">Puede filtrar clientes por los campos de entidad Perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="89ef7-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="89ef7-123">Al igual que en la búsqueda, el administrador primero tendrá que definir los campos como filtrables mediante la página **Índice de Buscar y filtrar**.</span><span class="sxs-lookup"><span data-stu-id="89ef7-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="89ef7-124">Seleccione **Filtro** en la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="89ef7-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="89ef7-125">Active las casillas situadas junto a los atributos por los que desea filtrar clientes.</span><span class="sxs-lookup"><span data-stu-id="89ef7-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="89ef7-126">![Perfiles de clientes](media/profiles-customers3.png "Perfiles de clientes")</span><span class="sxs-lookup"><span data-stu-id="89ef7-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="89ef7-127">Elimine sus filtros seleccionando **Limpiar filtros** en la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="89ef7-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="89ef7-128">Panel de detalles del cliente</span><span class="sxs-lookup"><span data-stu-id="89ef7-128">Customer details page</span></span>

<span data-ttu-id="89ef7-129">Seleccione cualquiera de los mosaicos de clientes para abrir la **Página de detalles del cliente**.</span><span class="sxs-lookup"><span data-stu-id="89ef7-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="89ef7-130">Esta vista contiene información unificada para el cliente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="89ef7-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="89ef7-131">Los detalles del cliente incluyen:</span><span class="sxs-lookup"><span data-stu-id="89ef7-131">Customer details include:</span></span>

-   <span data-ttu-id="89ef7-132">**Mosaico de perfil de cliente:** este mosaico muestra los diferentes valores de la entidad de perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="89ef7-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="89ef7-133">Estos detalles pueden incluir la dirección de correo electrónico, el nombre, la ciudad, etc.</span><span class="sxs-lookup"><span data-stu-id="89ef7-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="89ef7-134">**Intereses potenciales, marcas potenciales:** muestra si configuró un enriquecimiento propio.</span><span class="sxs-lookup"><span data-stu-id="89ef7-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="89ef7-135">Representa intereses y afinidades potenciales para las marcas que podría tener un cliente con un perfil similar al de este cliente.</span><span class="sxs-lookup"><span data-stu-id="89ef7-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="89ef7-136">Para más información, consulte [Enriquecer los perfiles de los clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="89ef7-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="89ef7-137">**Medidas:** muestra si configuró una o más medidas de un tipo específico: medidas de atributos del cliente.</span><span class="sxs-lookup"><span data-stu-id="89ef7-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="89ef7-138">Incluyen KPI calculados en torno a sus clientes a nivel de cliente individual.</span><span class="sxs-lookup"><span data-stu-id="89ef7-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="89ef7-139">Para obtener más información, consulte [Definir y administrar medidas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="89ef7-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="89ef7-140">**Escala de tiempo de actividad:** muestra si ha configurado actividades.</span><span class="sxs-lookup"><span data-stu-id="89ef7-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="89ef7-141">La vista de la línea de tiempo contiene actividades ordenadas cronológicamente de este cliente, comenzando por la actividad más reciente.</span><span class="sxs-lookup"><span data-stu-id="89ef7-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="89ef7-142">Para obtener más información, consulte [Actividades del cliente](activities.md).</span><span class="sxs-lookup"><span data-stu-id="89ef7-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="89ef7-143">Seleccione **Volver a Clientes** para volver a la página de búsqueda de clientes.</span><span class="sxs-lookup"><span data-stu-id="89ef7-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89ef7-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="89ef7-144">Next steps</span></span>

<span data-ttu-id="89ef7-145">[Agregar más orígenes de datos](data-sources.md) o [crear segmentos de clientes](segments.md).</span><span class="sxs-lookup"><span data-stu-id="89ef7-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]