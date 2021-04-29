---
title: Administrar permisos de usuario
description: Más información sobre permisos y roles de usuario.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760394"
---
# <a name="user-permissions"></a><span data-ttu-id="e255c-103">Permisos de usuario</span><span class="sxs-lookup"><span data-stu-id="e255c-103">User permissions</span></span>

<span data-ttu-id="e255c-104">La página **Permisos** es donde configurará los roles y permisos para usar las informaciones de público.</span><span class="sxs-lookup"><span data-stu-id="e255c-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="e255c-105">Debe tener permisos de administrador para ver la página.</span><span class="sxs-lookup"><span data-stu-id="e255c-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="e255c-106">Para acceder a la página de permisos en las informaciones de público, vaya a **Administración** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="e255c-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="e255c-107">Hay tres tipos de roles:</span><span class="sxs-lookup"><span data-stu-id="e255c-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="e255c-108">Espectador</span><span class="sxs-lookup"><span data-stu-id="e255c-108">Viewer</span></span>

- <span data-ttu-id="e255c-109">Explore la información y los segmentos en las páginas **Inicio** y **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e255c-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="e255c-110">Busque y filtre perfiles de clientes mediante la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="e255c-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="e255c-111">Los campos deben ser de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e255c-111">Fields must be searchable.</span></span>
- <span data-ttu-id="e255c-112">Ver y explorar página **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="e255c-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="e255c-113">Explore y exporte entidades mediante la página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="e255c-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="e255c-114">Vea el estado de los procesos del sistema mediante la página **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="e255c-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="e255c-115">Vea las exportaciones en la página **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="e255c-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="e255c-116">Instale y use el panel **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="e255c-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="e255c-117">Colaborador</span><span class="sxs-lookup"><span data-stu-id="e255c-117">Contributor</span></span>

- <span data-ttu-id="e255c-118">Todos los permisos disponibles para el visor.</span><span class="sxs-lookup"><span data-stu-id="e255c-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="e255c-119">Cargue y transforme datos mediante la página **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="e255c-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="e255c-120">Complete las secciones *Unificación de datos* (**Asignar**, **Coincidir** y **Combinar**) que dan como resultado la entidad de perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="e255c-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="e255c-121">Defina **Relaciones** y **Actividades**.</span><span class="sxs-lookup"><span data-stu-id="e255c-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="e255c-122">Cree segmentos mediante la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="e255c-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="e255c-123">Cree medidas mediante la página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="e255c-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="e255c-124">Administre la configuración y enriquezca los perfiles de clientes desde la página **Enriquecimiento** (solo para enriquecimientos de primera parte).</span><span class="sxs-lookup"><span data-stu-id="e255c-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="e255c-125">Administre y cree exportaciones basadas en conexiones compartidas con colaboradores.</span><span class="sxs-lookup"><span data-stu-id="e255c-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="e255c-126">[Obtenga más información sobre cómo los administradores permiten que los colaboradores utilicen una conexión para las exportaciones.](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e255c-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="e255c-127">Administrador</span><span class="sxs-lookup"><span data-stu-id="e255c-127">Administrator</span></span>

- <span data-ttu-id="e255c-128">Todos los permisos disponibles para el colaborador.</span><span class="sxs-lookup"><span data-stu-id="e255c-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="e255c-129">Cambie la configuración de la página **Sistema**, incluido el idioma de trabajo y las programaciones de actualización de los procesos del sistema.</span><span class="sxs-lookup"><span data-stu-id="e255c-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="e255c-130">Vea y agregue permisos mediante la página **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="e255c-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="e255c-131">Establezca definiciones de buscar y filtrar para la página Clientes mediante la página **Índice de búsqueda y filtros** (accesible a través de la página **Clientes**).</span><span class="sxs-lookup"><span data-stu-id="e255c-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="e255c-132">Administre las conexiones y permítalas para otros roles de usuario en la página **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="e255c-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="e255c-133">Administre la configuración y enriquezca los perfiles de clientes desde la página **Enriquecimiento** (para todos los enriquecimientos).</span><span class="sxs-lookup"><span data-stu-id="e255c-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="e255c-134">Gestione y cree exportaciones en la página **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="e255c-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="e255c-135">Instale y utilice el **Complemento de tarjeta de cliente**.</span><span class="sxs-lookup"><span data-stu-id="e255c-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="e255c-136">Agregue y use el conector de **Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="e255c-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="e255c-137">Habilitar el uso de las [API de Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="e255c-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="e255c-138">Asignar roles y permisos</span><span class="sxs-lookup"><span data-stu-id="e255c-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="e255c-139">En informaciones de público, vaya a **Administración** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="e255c-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="e255c-140">Seleccione **Agregar usuarios** para abrir el panel **Agregar/editar permisos**.</span><span class="sxs-lookup"><span data-stu-id="e255c-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="e255c-141">Utilice el campo **Buscar** para encontrar el usuario o grupo de Azure Active Directory cuyos permisos desea ajustar.</span><span class="sxs-lookup"><span data-stu-id="e255c-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="e255c-142">Seleccione un **Rol** para asignar a ese usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="e255c-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="e255c-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e255c-143">Select **Save**.</span></span> <span data-ttu-id="e255c-144">El entorno actual se compartirá automáticamente con el usuario o los miembros del grupo cuyos permisos ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="e255c-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="e255c-145">Los usuarios pueden acceder a la aplicación Customer Insights y trabajar de acuerdo con su rol específico.</span><span class="sxs-lookup"><span data-stu-id="e255c-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="e255c-146">Ver permisos actuales</span><span class="sxs-lookup"><span data-stu-id="e255c-146">View current permissions</span></span>

<span data-ttu-id="e255c-147">En las informaciones de públicos, vaya a **Administrador** > **Permisos** para ver qué asignaciones de roles están activas actualmente.</span><span class="sxs-lookup"><span data-stu-id="e255c-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="e255c-148">La columna **Tipo** especifica un único usuario, grupo o aplicación.</span><span class="sxs-lookup"><span data-stu-id="e255c-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="e255c-149">El sistema admite usuarios individuales y grupos.</span><span class="sxs-lookup"><span data-stu-id="e255c-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="e255c-150">Los roles se especifican en la columna **Rol**.</span><span class="sxs-lookup"><span data-stu-id="e255c-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="e255c-151">Seleccione cualquier título de columna para ordenar los resultados por el valor de esa columna.</span><span class="sxs-lookup"><span data-stu-id="e255c-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="e255c-152">Utilice el campo **Buscar** en la parte superior de la página para localizar usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="e255c-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
