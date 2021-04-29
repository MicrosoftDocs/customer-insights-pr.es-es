---
title: Exportar datos de Customer Insights
description: Administrar exportaciones para compartir datos.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896164"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="1d46a-103">Información general del exportaciones (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="1d46a-103">Exports (preview) overview</span></span>

<span data-ttu-id="1d46a-104">La página **Exportaciones** muestra todas las exportaciones configuradas.</span><span class="sxs-lookup"><span data-stu-id="1d46a-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="1d46a-105">Las exportaciones comparten datos específicos con varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1d46a-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="1d46a-106">Pueden incluir perfiles de clientes o entidades, esquemas y detalles de mapeo.</span><span class="sxs-lookup"><span data-stu-id="1d46a-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="1d46a-107">Cada exportación requiere una [conexión, configurada por un administrador, para administrar la autenticación y el acceso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="1d46a-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1d46a-108">Hasta marzo de 2021, las exportaciones creaban una conexión al servicio correspondiente de forma automática.</span><span class="sxs-lookup"><span data-stu-id="1d46a-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="1d46a-109">Las exportaciones ahora requieren una [conexión, creada y compartida por un administrador](connections.md) antes de poder crearlas.</span><span class="sxs-lookup"><span data-stu-id="1d46a-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="1d46a-110">Vaya a **Datos** > **Exportaciones** para ver la página de exportaciones.</span><span class="sxs-lookup"><span data-stu-id="1d46a-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="1d46a-111">Todos los roles de usuario tienen acceso para ver las exportaciones configuradas.</span><span class="sxs-lookup"><span data-stu-id="1d46a-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="1d46a-112">Uso del campo de búsqueda en la barra de comandos para buscar exportaciones por su nombre, nombre de conexión o tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="1d46a-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="1d46a-113">Configurar una nueva exportación</span><span class="sxs-lookup"><span data-stu-id="1d46a-113">Set up a new export</span></span>

<span data-ttu-id="1d46a-114">Para configurar o editar una exportación, debe tener conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="1d46a-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="1d46a-115">Las conexiones dependen de su [rol del usuario](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="1d46a-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="1d46a-116">Los administradores tienen acceso a todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="1d46a-116">Administrators have access to all connections.</span></span> <span data-ttu-id="1d46a-117">También pueden crear nuevas conexiones al configurar una exportación.</span><span class="sxs-lookup"><span data-stu-id="1d46a-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="1d46a-118">Los colaboradores pueden tener acceso a conexiones específicas.</span><span class="sxs-lookup"><span data-stu-id="1d46a-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="1d46a-119">Dependen de los administradores para configurar y compartir conexiones.</span><span class="sxs-lookup"><span data-stu-id="1d46a-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="1d46a-120">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1d46a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="1d46a-121">Los visores solo pueden ver las exportaciones existentes, pero no crearlas.</span><span class="sxs-lookup"><span data-stu-id="1d46a-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="1d46a-122">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="1d46a-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1d46a-123">Seleccione **Agregar exportación** para crear un nuevo destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="1d46a-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="1d46a-124">En el panel **Configurar exportación**, seleccione qué conexión usar.</span><span class="sxs-lookup"><span data-stu-id="1d46a-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="1d46a-125">Las [conexiones](connections.md) son administradas por administradores.</span><span class="sxs-lookup"><span data-stu-id="1d46a-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="1d46a-126">Proporcione los detalles requeridos y seleccione **Guardar** para crear la exportación.</span><span class="sxs-lookup"><span data-stu-id="1d46a-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="1d46a-127">Editar una exportación</span><span class="sxs-lookup"><span data-stu-id="1d46a-127">Edit an export</span></span>

1. <span data-ttu-id="1d46a-128">Seleccione los puntos suspensivos verticales del destino de exportación que desea editar.</span><span class="sxs-lookup"><span data-stu-id="1d46a-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="1d46a-129">Seleccione **Editar** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1d46a-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="1d46a-130">Cambie los valores que desea actualizar y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1d46a-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="1d46a-131">Ver exportaciones y detalles de exportación</span><span class="sxs-lookup"><span data-stu-id="1d46a-131">View Exports and export details</span></span>

<span data-ttu-id="1d46a-132">Después de crear los destinos de la exportación, se enumeran en **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="1d46a-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="1d46a-133">Todos los usuarios pueden ver qué datos se comparten y su estado más reciente.</span><span class="sxs-lookup"><span data-stu-id="1d46a-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="1d46a-134">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="1d46a-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1d46a-135">Los usuarios sin permisos de edición seleccionan **Vista** en vez de **Editar** para ver los detalles de la exportación.</span><span class="sxs-lookup"><span data-stu-id="1d46a-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="1d46a-136">Este panel lateral muestra la configuración de esta exportación.</span><span class="sxs-lookup"><span data-stu-id="1d46a-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="1d46a-137">Sin permisos de edición, no puede cambiar valores.</span><span class="sxs-lookup"><span data-stu-id="1d46a-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="1d46a-138">Seleccione **Cerrar** para volver a la página de exportaciones.</span><span class="sxs-lookup"><span data-stu-id="1d46a-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="1d46a-139">Ejecutar exportaciones según las necesidades</span><span class="sxs-lookup"><span data-stu-id="1d46a-139">Run exports on demand</span></span>

<span data-ttu-id="1d46a-140">Después de configurar una exportación, se ejecutará con cada [actualización programada](system.md#schedule-tab) siempre que tenga una conexión que funcione.</span><span class="sxs-lookup"><span data-stu-id="1d46a-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="1d46a-141">Para exportar datos sin esperar una actualización programada, vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="1d46a-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="1d46a-142">Tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="1d46a-142">You have two options:</span></span>

- <span data-ttu-id="1d46a-143">Para ejecutar todas las exportaciones, seleccione **Ejecutar todo** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="1d46a-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="1d46a-144">Para ejecutar una sola exportación, seleccione los puntos suspensivos (...) en un elemento de la lista y luego elija **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1d46a-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="1d46a-145">Quitar una exportación</span><span class="sxs-lookup"><span data-stu-id="1d46a-145">Remove an Export</span></span>

1. <span data-ttu-id="1d46a-146">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="1d46a-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1d46a-147">Seleccione los puntos suspensivos verticales para la exportación que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="1d46a-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="1d46a-148">Seleccione **Quitar** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1d46a-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="1d46a-149">Confirme la eliminación seleccionando **Quitar** en la pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="1d46a-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
