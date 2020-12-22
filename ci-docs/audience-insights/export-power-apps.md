---
title: Conector de Power Apps
description: Conectar con Power Apps y Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407006"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="8dd0e-103">Conector de Microsoft Power Apps (vista previa)</span><span class="sxs-lookup"><span data-stu-id="8dd0e-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="8dd0e-104">Lleve perfiles de clientes unificados a sus aplicaciones personalizadas con Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="8dd0e-105">Conectar Power Apps y Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8dd0e-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="8dd0e-106">Customer Insights es una de las muchas [fuentes disponibles para datos en Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="8dd0e-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="8dd0e-107">Consulte la documentación de Power Apps para aprender a [agregar una conexión de datos a una aplicación](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="8dd0e-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="8dd0e-108">Le recomendamos que también revise [cómo Power Apps usa la delegación para manejar grandes conjuntos de datos en aplicaciones de lienzo](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="8dd0e-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="8dd0e-109">Entidades disponibles</span><span class="sxs-lookup"><span data-stu-id="8dd0e-109">Available entities</span></span>

<span data-ttu-id="8dd0e-110">Después de agregar Customer Insights como una conexión de datos, puede elegir las siguientes entidades en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="8dd0e-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="8dd0e-111">Cliente: para utilizar datos del [perfil de cliente unificado](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8dd0e-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="8dd0e-112">Actividad unificada del cliente: para mostrar la [escala de tiempo](activities.md) en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="8dd0e-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="8dd0e-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="8dd0e-114">Entidades recuperables</span><span class="sxs-lookup"><span data-stu-id="8dd0e-114">Retrievable entities</span></span>

<span data-ttu-id="8dd0e-115">Solo puede recuperar las entidades **Cliente**, **UnifiedActivity** y **Segmentos** a través del conector de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="8dd0e-116">Se muestran otras entidades porque el conector subyacente las admite mediante desencadenadores en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="8dd0e-117">Delegación</span><span class="sxs-lookup"><span data-stu-id="8dd0e-117">Delegation</span></span>

<span data-ttu-id="8dd0e-118">La delegación funciona para la entidad Cliente y la entidad UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="8dd0e-119">Delegación para la entidad **Cliente**: para usar la delegación para esta entidad, los campos deben estar indexados en [Índice de búsqueda y filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="8dd0e-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="8dd0e-120">Delegación para **UnifiedActivity**: La delegación de esta entidad solo funciona para los campos **ActivityId** y **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="8dd0e-121">Para obtener más información sobre la delegación, consulte [Funciones y operaciones delegables de Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="8dd0e-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="8dd0e-122">Ejemplo de control de galería</span><span class="sxs-lookup"><span data-stu-id="8dd0e-122">Example gallery control</span></span>

<span data-ttu-id="8dd0e-123">Por ejemplo, agregue perfiles de cliente a un [control de galería](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="8dd0e-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="8dd0e-124">Agregue un control de **Galería** a una aplicación que esté creando.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8dd0e-125">![Agregar un elemento de galería](media/connector-powerapps9.png "Agregar un elemento de galería")</span><span class="sxs-lookup"><span data-stu-id="8dd0e-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="8dd0e-126">Seleccione **Cliente** como origen de datos para elementos.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8dd0e-127">![Seleccionar un origen de datos](media/choose-datasource-powerapps.png "Seleccionar un origen de datos")</span><span class="sxs-lookup"><span data-stu-id="8dd0e-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="8dd0e-128">Puede cambiar el panel de datos a la derecha para seleccionar qué campo mostrará la entidad de Cliente en la galería.</span><span class="sxs-lookup"><span data-stu-id="8dd0e-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="8dd0e-129">Si desea mostrar cualquier campo del cliente seleccionado en la galería, complete la propiedad Texto de una etiqueta:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="8dd0e-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="8dd0e-130">Ejemplo: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="8dd0e-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="8dd0e-131">Para mostrar la escala de tiempo unificada para un cliente, agregue un elemento Galería y agregue la propiedad Items: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="8dd0e-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="8dd0e-132">Ejemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="8dd0e-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
