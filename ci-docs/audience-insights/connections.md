---
title: Conexiones a otros servicios de Customer Insights.
description: Comparta datos con otros servicios.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896118"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="5a9f2-103">Información general sobre conexiones (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5a9f2-103">Connections (preview) overview</span></span>

<span data-ttu-id="5a9f2-104">Las conexiones son la clave para permitir el intercambio de datos desde y hacia Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="5a9f2-105">Cada conexión establece el intercambio de datos con un servicio específico.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="5a9f2-106">Las conexiones son la base para [configurar enriquecimientos de terceros](enrichment-hub.md) y [configurar exportaciones](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a9f2-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="5a9f2-107">La misma conexión se puede utilizar varias veces.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="5a9f2-108">Por ejemplo, una conexión para Dynamics 365 Marketing funciona para varias exportaciones y una conexión Leadspace se puede usar para varios enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="5a9f2-109">Vaya a **Administración** > **Conexiones** para crear y ver conexiones.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="5a9f2-110">La pestaña **Conexiones** muestra todas las conexiones activas.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="5a9f2-111">La lista muestra una fila para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="5a9f2-112">Obtenga una descripción general rápida y descubra lo que puede hacer con cada opción de extensibilidad en la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="5a9f2-113">Exportaciones</span><span class="sxs-lookup"><span data-stu-id="5a9f2-113">Exports</span></span>

<span data-ttu-id="5a9f2-114">Solo los administradores pueden configurar nuevas conexiones, pero pueden otorgar acceso a los colaboradores para que usen las conexiones existentes.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="5a9f2-115">Los administradores controlan dónde pueden ir los datos, los colaboradores definen la carga útil y la frecuencia según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="5a9f2-116">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5a9f2-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="5a9f2-117">Enriquecimientos</span><span class="sxs-lookup"><span data-stu-id="5a9f2-117">Enrichments</span></span>

<span data-ttu-id="5a9f2-118">Solo los administradores pueden configurar nuevas conexiones, pero las conexiones creadas siempre están disponibles tanto para administradores como para colaboradores.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="5a9f2-119">Los administradores gestionan las credenciales y dan su consentimiento para las transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="5a9f2-120">Las conexiones pueden ser utilizadas para enriquecimiento tanto por parte de administradores como por parte de colaboradores.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="5a9f2-121">Agregar una nueva conexión</span><span class="sxs-lookup"><span data-stu-id="5a9f2-121">Add a new connection</span></span>

<span data-ttu-id="5a9f2-122">Para agregar conexiones, debe tener [permisos de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5a9f2-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="5a9f2-123">Si se conecta a otros servicios de Microsoft, damos por hecho que ambos servicios están en la misma organización.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="5a9f2-124">Vaya a **Administrador** > **Conexiones (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5a9f2-125">Vaya a la pestaña **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5a9f2-126">Seleccione **Agregar conexión** para crear una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="5a9f2-127">Elija en el menú desplegable qué tipo de conexión desea crear.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="5a9f2-128">En el panel **Configurar conexión**, proporcione los detalles requeridos.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="5a9f2-129">El **Nombre para mostrar** y el tipo de conexión describe una conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="5a9f2-130">Recomendamos elegir un nombre que explique el propósito y el objetivo de esta conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="5a9f2-131">Los campos exactos dependen del servicio al que se esté conectando.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="5a9f2-132">Puede obtener información sobre los detalles de un tipo de conexión específico en el artículo sobre el servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="5a9f2-133">Para crear la conexión, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="5a9f2-134">También puede seleccionar **Configurar** en un icono de la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="5a9f2-135">Permitir que los contribuyentes utilicen una conexión para las exportaciones</span><span class="sxs-lookup"><span data-stu-id="5a9f2-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="5a9f2-136">Al configurar o editar una conexión de exportación, usted elige qué usuarios pueden usar esta conexión específica para definir [exportaciones](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a9f2-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="5a9f2-137">De forma predeterminada, una conexión está disponible para los usuarios con un rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="5a9f2-138">Puede cambiar esta configuración en **Elegir quién puede usar esta conexión** y permitir que los usuarios con el rol colaborador utilicen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="5a9f2-139">Los colaboradores no podrán ver ni editar la conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="5a9f2-140">Solo verán el nombre para mostrar y su tipo al crear una exportación.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="5a9f2-141">Al compartir una conexión, permite que los colaboradores usen una conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="5a9f2-142">Los colaboradores verán conexiones compartidas cuando configuren exportaciones.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="5a9f2-143">Pueden gestionar todas las exportaciones que utilizan esta conexión específica.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="5a9f2-144">Puede cambiar esta configuración manteniendo las exportaciones que ya han sido definidas por los colaboradores.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="5a9f2-145">Editar una conexión</span><span class="sxs-lookup"><span data-stu-id="5a9f2-145">Edit a connection</span></span>

1. <span data-ttu-id="5a9f2-146">Vaya a **Administrador** > **Conexiones (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5a9f2-147">Vaya a la pestaña **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5a9f2-148">Seleccione los puntos suspensivos verticales para la conexión que desea editar.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="5a9f2-149">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-149">Select **Edit**.</span></span>

1. <span data-ttu-id="5a9f2-150">Cambie los valores que desea actualizar y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="5a9f2-151">Quitar una conexión</span><span class="sxs-lookup"><span data-stu-id="5a9f2-151">Remove a connection</span></span>

<span data-ttu-id="5a9f2-152">Si los enriquecimientos o exportaciones utilizan la conexión que está quitando, primero debe desconectarlos o quitarlos.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="5a9f2-153">El cuadro de diálogo para quitar le llevará a los enriquecimientos o exportaciones relevantes.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="5a9f2-154">Los enriquecimientos y exportaciones que se han desconectado se vuelven inactivos.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="5a9f2-155">Se reactivan agregándoles otra conexión en la página [Enriquecimientos](enrichment-hub.md) o [Exportaciones](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a9f2-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="5a9f2-156">Vaya a **Administrador** > **Conexiones (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="5a9f2-157">Vaya a la pestaña **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="5a9f2-158">Seleccione los puntos suspensivos verticales para la conexión que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="5a9f2-159">Seleccione **Quitar** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="5a9f2-160">Aparece un cuadro de diálogo de confirmación.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="5a9f2-161">Si hay enriquecimientos o exportaciones usando esta conexión, seleccione el botón para ver qué está usando la conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="5a9f2-162">**Exportaciones**: puede optar por quitar o desconectar las exportaciones para poder quitar la conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="5a9f2-163">Para desconectar una exportación, los administradores pueden utilizar la acción **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="5a9f2-164">Esta acción está disponible para exportaciones seleccionadas individuales y múltiples.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="5a9f2-165">Al desconectarse, conserva la configuración de exportación, pero no se ejecutará hasta que se le agregue otra conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="5a9f2-166">**Enriquecimientos**: puede optar por quitar o desactivar los enriquecimientos para poder quitar la conexión.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="5a9f2-167">Cuando la conexión no tenga más dependencias, vuelva a **Administrador** > **Conexiones** e intente quitar la conexión nuevamente.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="5a9f2-168">Para confirmar la eliminación, seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5a9f2-168">To confirm the deletion select **Remove**.</span></span>

