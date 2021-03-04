---
title: Conectarse a entidades en el lago gestionado de Common Data Service
description: Importar datos de un data lake administrado por Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267835"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="1bb20-103">Conéctese a los datos en un data lake administrado de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="1bb20-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1bb20-104">Este artículo proporciona información sobre cómo los clientes existentes de Dynamics 365 pueden conectarse rápidamente a sus entidades analíticas en el lago gestionado de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1bb20-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="1bb20-105">Debe ser administrador en la organización de Common Data Service para continuar y ver la lista de entidades disponibles en el lago administrado.</span><span class="sxs-lookup"><span data-stu-id="1bb20-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="1bb20-106">Consideraciones importantes</span><span class="sxs-lookup"><span data-stu-id="1bb20-106">Important considerations</span></span>

<span data-ttu-id="1bb20-107">Los datos almacenados en servicios en línea como Azure Data Lake Storage pueden almacenarse en una ubicación diferente de dónde se procesan o almacenan los datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1bb20-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="1bb20-108"> Al importar o conectarse a datos almacenados en servicios en línea, acepta que los datos pueden transferirse y almacenarse con Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="1bb20-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="1bb20-109">Conectarse a un lago gestionado por Common Data Service</span><span class="sxs-lookup"><span data-stu-id="1bb20-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="1bb20-110">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1bb20-111">Seleccione **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="1bb20-112">Seleccione **Conectar con Common Data Service** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="1bb20-113">Escriba un **Nombre** para el origen de datos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="1bb20-114">Directrices de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="1bb20-114">Name guidelines:</span></span> 
   - <span data-ttu-id="1bb20-115">Empiece con una letra.</span><span class="sxs-lookup"><span data-stu-id="1bb20-115">Start with a letter.</span></span>
   - <span data-ttu-id="1bb20-116">Utilice solo letras y números.</span><span class="sxs-lookup"><span data-stu-id="1bb20-116">Use letters and numbers only.</span></span> <span data-ttu-id="1bb20-117">No se permiten caracteres especiales ni espacios.</span><span class="sxs-lookup"><span data-stu-id="1bb20-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="1bb20-118">Utilice entre 3 y 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1bb20-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="1bb20-119">Especifique la **Dirección del servidor** de su organización de Common Data Service y seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1bb20-120">![Cuadro de diálogo para introducir la dirección del servidor de Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="1bb20-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="1bb20-121">En la lista disponible, seleccione el conjunto de entidades que desea ingerir.</span><span class="sxs-lookup"><span data-stu-id="1bb20-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="1bb20-122">Si algunas entidades ya están seleccionadas, puede que se utilicen en otras aplicaciones de Dynamics 365 (como Dynamics 365 Sales Insights o Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="1bb20-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="1bb20-123">No se puede cambiar esta selección.</span><span class="sxs-lookup"><span data-stu-id="1bb20-123">You can't change the selection.</span></span> <span data-ttu-id="1bb20-124">Estas entidades estarán disponibles una vez que se cree el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb20-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1bb20-125">![Cuadro de diálogo que muestra una lista de entidades en la organización de Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="1bb20-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="1bb20-126">Guarde la selección para comenzar a sincronizar las entidades seleccionadas con el lago gestionado por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1bb20-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="1bb20-127">Encontrará la conexión recién agregada en la página **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="1bb20-128">Se pondrá en cola para actualizarse y mostrará un recuento de entidades igual a 0 hasta que se hayan sincronizado todas las entidades.</span><span class="sxs-lookup"><span data-stu-id="1bb20-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="1bb20-129">Solo un origen de datos de un entorno puede usar simultáneamente el mismo lago gestionado Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1bb20-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="1bb20-130">Editar un origen de datos de lago gestionado por Common Data Service</span><span class="sxs-lookup"><span data-stu-id="1bb20-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="1bb20-131">Solo se edita la selección de entidad después de crear el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb20-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="1bb20-132">Por ejemplo, si se agregaron entidades adicionales a Common Data Service y desea importarlas también.</span><span class="sxs-lookup"><span data-stu-id="1bb20-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="1bb20-133">Para conectarse a una instancia de Common Data Service distinta, puede [crear un origen de datos nuevo](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="1bb20-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="1bb20-134">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1bb20-135">Junto al origen de datos que desea actualizar, seleccione los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="1bb20-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="1bb20-136">Seleccione la opción **Editar** de la lista.</span><span class="sxs-lookup"><span data-stu-id="1bb20-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="1bb20-137">Seleccione entidades adicionales de la lista de entidades disponibles y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1bb20-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]