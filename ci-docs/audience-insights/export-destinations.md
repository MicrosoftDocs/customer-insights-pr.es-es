---
title: Exportar datos de Customer Insights
description: Administrar exportaciones para compartir datos.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016657"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="56e7d-103">Información general del exportaciones (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="56e7d-103">Exports (preview) overview</span></span>

<span data-ttu-id="56e7d-104">La página **Exportaciones** muestra todas las exportaciones configuradas.</span><span class="sxs-lookup"><span data-stu-id="56e7d-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="56e7d-105">Las exportaciones comparten datos específicos con varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="56e7d-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="56e7d-106">Pueden incluir perfiles de clientes o entidades, esquemas y detalles de mapeo.</span><span class="sxs-lookup"><span data-stu-id="56e7d-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="56e7d-107">Cada exportación requiere una [conexión, configurada por un administrador, para administrar la autenticación y el acceso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="56e7d-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="56e7d-108">Vaya a **Datos** > **Exportaciones** para ver la página de exportaciones.</span><span class="sxs-lookup"><span data-stu-id="56e7d-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="56e7d-109">Todos los roles de usuario tienen acceso para ver las exportaciones configuradas.</span><span class="sxs-lookup"><span data-stu-id="56e7d-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="56e7d-110">Uso del campo de búsqueda en la barra de comandos para buscar exportaciones por su nombre, nombre de conexión o tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="56e7d-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="56e7d-111">Configurar una nueva exportación</span><span class="sxs-lookup"><span data-stu-id="56e7d-111">Set up a new export</span></span>

<span data-ttu-id="56e7d-112">Para configurar o editar una exportación, debe tener conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="56e7d-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="56e7d-113">Las conexiones dependen de su [rol del usuario](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="56e7d-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="56e7d-114">Los administradores tienen acceso a todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="56e7d-114">Administrators have access to all connections.</span></span> <span data-ttu-id="56e7d-115">También pueden crear nuevas conexiones al configurar una exportación.</span><span class="sxs-lookup"><span data-stu-id="56e7d-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="56e7d-116">Los colaboradores pueden tener acceso a conexiones específicas.</span><span class="sxs-lookup"><span data-stu-id="56e7d-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="56e7d-117">Dependen de los administradores para configurar y compartir conexiones.</span><span class="sxs-lookup"><span data-stu-id="56e7d-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="56e7d-118">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="56e7d-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="56e7d-119">Los visores solo pueden ver las exportaciones existentes, pero no crearlas.</span><span class="sxs-lookup"><span data-stu-id="56e7d-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="56e7d-120">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="56e7d-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="56e7d-121">Seleccione **Agregar exportación** para crear un nuevo destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="56e7d-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="56e7d-122">En el panel **Configurar exportación**, seleccione qué conexión usar.</span><span class="sxs-lookup"><span data-stu-id="56e7d-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="56e7d-123">Las [conexiones](connections.md) son administradas por administradores.</span><span class="sxs-lookup"><span data-stu-id="56e7d-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="56e7d-124">Proporcione los detalles requeridos y seleccione **Guardar** para crear la exportación.</span><span class="sxs-lookup"><span data-stu-id="56e7d-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="56e7d-125">Editar una exportación</span><span class="sxs-lookup"><span data-stu-id="56e7d-125">Edit an export</span></span>

1. <span data-ttu-id="56e7d-126">Seleccione los puntos suspensivos verticales del destino de exportación que desea editar.</span><span class="sxs-lookup"><span data-stu-id="56e7d-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="56e7d-127">Seleccione **Editar** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="56e7d-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="56e7d-128">Cambie los valores que desea actualizar y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="56e7d-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="56e7d-129">Ver exportaciones y detalles de exportación</span><span class="sxs-lookup"><span data-stu-id="56e7d-129">View Exports and export details</span></span>

<span data-ttu-id="56e7d-130">Después de crear los destinos de la exportación, se enumeran en **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="56e7d-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="56e7d-131">Todos los usuarios pueden ver qué datos se comparten y su estado más reciente.</span><span class="sxs-lookup"><span data-stu-id="56e7d-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="56e7d-132">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="56e7d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="56e7d-133">Los usuarios sin permisos de edición seleccionan **Vista** en vez de **Editar** para ver los detalles de la exportación.</span><span class="sxs-lookup"><span data-stu-id="56e7d-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="56e7d-134">Este panel lateral muestra la configuración de esta exportación.</span><span class="sxs-lookup"><span data-stu-id="56e7d-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="56e7d-135">Sin permisos de edición, no puede cambiar valores.</span><span class="sxs-lookup"><span data-stu-id="56e7d-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="56e7d-136">Seleccione **Cerrar** para volver a la página de exportaciones.</span><span class="sxs-lookup"><span data-stu-id="56e7d-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="56e7d-137">Ejecutar exportaciones según las necesidades</span><span class="sxs-lookup"><span data-stu-id="56e7d-137">Run exports on demand</span></span>

<span data-ttu-id="56e7d-138">Después de configurar una exportación, se ejecutará con cada [actualización programada](system.md#schedule-tab) siempre que tenga una conexión que funcione.</span><span class="sxs-lookup"><span data-stu-id="56e7d-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="56e7d-139">Para exportar datos sin esperar una actualización programada, vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="56e7d-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="56e7d-140">Tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="56e7d-140">You have two options:</span></span>

- <span data-ttu-id="56e7d-141">Para ejecutar todas las exportaciones, seleccione **Ejecutar todo** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="56e7d-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="56e7d-142">Para ejecutar una sola exportación, seleccione los puntos suspensivos (...) en un elemento de la lista y luego elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="56e7d-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="56e7d-143">Quitar una exportación</span><span class="sxs-lookup"><span data-stu-id="56e7d-143">Remove an Export</span></span>

1. <span data-ttu-id="56e7d-144">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="56e7d-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="56e7d-145">Seleccione los puntos suspensivos verticales para la exportación que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="56e7d-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="56e7d-146">Seleccione **Quitar** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="56e7d-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="56e7d-147">Confirme la eliminación seleccionando **Quitar** en la pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="56e7d-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
