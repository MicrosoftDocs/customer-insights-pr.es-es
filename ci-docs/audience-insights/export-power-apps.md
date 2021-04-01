---
title: Conector de Power Apps
description: Conectar con Power Apps y Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598176"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="dcd5a-103">Conector de Microsoft Power Apps (vista previa)</span><span class="sxs-lookup"><span data-stu-id="dcd5a-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="dcd5a-104">Lleve perfiles de clientes unificados a sus aplicaciones personalizadas con Power Apps.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="dcd5a-105">Conectar Power Apps y Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="dcd5a-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="dcd5a-106">Customer Insights es una de las muchas [fuentes disponibles para datos en Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="dcd5a-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="dcd5a-107">Consulte la documentación de Power Apps para aprender a [agregar una conexión de datos a una aplicación](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="dcd5a-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="dcd5a-108">Le recomendamos que también revise [cómo Power Apps usa la delegación para manejar grandes conjuntos de datos en aplicaciones de lienzo](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="dcd5a-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="dcd5a-109">Entidades disponibles</span><span class="sxs-lookup"><span data-stu-id="dcd5a-109">Available entities</span></span>

<span data-ttu-id="dcd5a-110">Después de agregar Customer Insights como una conexión de datos, puede elegir las siguientes entidades en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="dcd5a-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="dcd5a-111">Cliente: para utilizar datos del [perfil de cliente unificado](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dcd5a-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="dcd5a-112">UnifiedActivity: para mostrar la [escala de tiempo de la actividad](activities.md) en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="dcd5a-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="dcd5a-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="dcd5a-114">Entidades recuperables</span><span class="sxs-lookup"><span data-stu-id="dcd5a-114">Retrievable entities</span></span>

<span data-ttu-id="dcd5a-115">Solo puede recuperar las entidades **Cliente**, **UnifiedActivity** y **Segmentos** a través del conector de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="dcd5a-116">Se muestran otras entidades porque el conector subyacente las admite mediante desencadenadores en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="dcd5a-117">Delegación</span><span class="sxs-lookup"><span data-stu-id="dcd5a-117">Delegation</span></span>

<span data-ttu-id="dcd5a-118">La delegación funciona para la entidad Cliente y la entidad UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="dcd5a-119">Delegación para la entidad **Cliente**: para usar la delegación para esta entidad, los campos deben estar indexados en [Índice de búsqueda y filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="dcd5a-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="dcd5a-120">Delegación para **UnifiedActivity**: La delegación de esta entidad solo funciona para los campos **ActivityId** y **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="dcd5a-121">Para obtener más información sobre la delegación, consulte [Funciones y operaciones delegables de Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="dcd5a-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="dcd5a-122">Ejemplo de control de galería</span><span class="sxs-lookup"><span data-stu-id="dcd5a-122">Example gallery control</span></span>

<span data-ttu-id="dcd5a-123">Por ejemplo, agregue perfiles de cliente a un [control de galería](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="dcd5a-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="dcd5a-124">Agregue un control de **Galería** a una aplicación que esté creando.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dcd5a-125">![Agregar un elemento de galería](media/connector-powerapps9.png "Agregar un elemento de galería")</span><span class="sxs-lookup"><span data-stu-id="dcd5a-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="dcd5a-126">Seleccione **Cliente** como origen de datos para elementos.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dcd5a-127">![Seleccionar un origen de datos](media/choose-datasource-powerapps.png "Seleccionar un origen de datos")</span><span class="sxs-lookup"><span data-stu-id="dcd5a-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="dcd5a-128">Puede cambiar el panel de datos a la derecha para seleccionar qué campo mostrará la entidad de Cliente en la galería.</span><span class="sxs-lookup"><span data-stu-id="dcd5a-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="dcd5a-129">Si desea mostrar cualquier campo del cliente seleccionado en la galería, complete la propiedad Texto de una etiqueta:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="dcd5a-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="dcd5a-130">Ejemplo: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="dcd5a-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="dcd5a-131">Para mostrar la escala de tiempo unificada para un cliente, agregue un elemento Galería y agregue la propiedad Items: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="dcd5a-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="dcd5a-132">Ejemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="dcd5a-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]