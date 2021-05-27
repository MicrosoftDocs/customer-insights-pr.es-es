---
title: Enriquecer perfiles de cliente unificados
description: Utilice las capacidades para enriquecer los datos de sus clientes.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954508"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="17316-103">Enriquecimiento para perfiles de clientes (vista previa)</span><span class="sxs-lookup"><span data-stu-id="17316-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="17316-104">Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="17316-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página del centro de enriquecimiento":::

<span data-ttu-id="17316-106">En la información de audiencia, vaya a **Datos** > **Enriquecimiento** para trabajar con opciones de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="17316-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="17316-107">Debe tener permisos de Colaborador o Administrador para crear o editar enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="17316-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="17316-108">Para obtener más información, vea [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="17316-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="17316-109">En la pestaña **Descubrir** encontrará los siguientes enriquecimientos:</span><span class="sxs-lookup"><span data-stu-id="17316-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="17316-110">[Marcas](enrichment-microsoft.md) proporcionadas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="17316-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="17316-111">[Intereses](enrichment-microsoft.md) proporcionados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="17316-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="17316-112">[Direcciones mejoradas](enrichment-enhanced-addresses.md) proporcionadas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="17316-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="17316-113">[Datos de empresa](enrichment-leadspace.md) proporcionados por Leadspace</span><span class="sxs-lookup"><span data-stu-id="17316-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="17316-114">[Datos demográficos](enrichment-experian.md) proporcionados por Experian</span><span class="sxs-lookup"><span data-stu-id="17316-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="17316-115">[Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="17316-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="17316-116">[Datos de cliente](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)</span><span class="sxs-lookup"><span data-stu-id="17316-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="17316-117">En la pestaña **Mis enriquecimientos** puede ver los enriquecimientos que ha configurado y editar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="17316-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="17316-118">Administrar enriquecimientos existentes</span><span class="sxs-lookup"><span data-stu-id="17316-118">Manage existing enrichments</span></span>

<span data-ttu-id="17316-119">Vaya a **Mis enriquecimientos** para ver todos los enriquecimientos configurados.</span><span class="sxs-lookup"><span data-stu-id="17316-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="17316-120">Cada enriquecimiento se representa como una fila que incluye información adicional sobre el enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="17316-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="17316-121">Seleccione un enriquecimiento para ver las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="17316-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="17316-122">También puede seleccionar los puntos suspensivos (...) en un elemento de la lista para ver las opciones.</span><span class="sxs-lookup"><span data-stu-id="17316-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opciones para administrar enriquecimientos en la lista de enriquecimientos":::

- <span data-ttu-id="17316-124">**Vea** los detalles de enriquecimiento con el número de perfiles de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="17316-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="17316-125">**Edite** la configuración de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="17316-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="17316-126">**Ejecutar** el enriquecimiento para actualizar los perfiles de los clientes con los últimos datos.</span><span class="sxs-lookup"><span data-stu-id="17316-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="17316-127">**Desactive** un enriquecimiento existente para evitar que se actualice automáticamente con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="17316-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="17316-128">Los datos de la última actualización exitosa seguirán estando disponibles.</span><span class="sxs-lookup"><span data-stu-id="17316-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="17316-129">**Active** un enriquecimiento inactivo para reiniciar la actualización automática con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="17316-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="17316-130">**Eliminar** un enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="17316-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="17316-131">Puede ejecutar o desactivar varios enriquecimientos a la vez seleccionándolos en la lista.</span><span class="sxs-lookup"><span data-stu-id="17316-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="17316-132">Las opciones de visualización y edición no están disponibles como acción masiva y solo funcionan para un enriquecimiento a la vez.</span><span class="sxs-lookup"><span data-stu-id="17316-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="17316-133">Enriquecimientos y conexiones</span><span class="sxs-lookup"><span data-stu-id="17316-133">Enrichments and connections</span></span>

<span data-ttu-id="17316-134">Los enriquecimientos de terceros se configuran mediante [conexiones](connections.md), que un administrador configura con credenciales y proporciona consentimiento para transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="17316-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="17316-135">La conexión puede ser utilizadas por parte de administradores y colaboradores para configurar enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="17316-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="17316-136">Múltiples enriquecimientos del mismo tipo</span><span class="sxs-lookup"><span data-stu-id="17316-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="17316-137">La entidad que se va a enriquecer se especifica durante la configuración del enriquecimiento, lo que le permite enriquecer solo un subconjunto de sus perfiles.</span><span class="sxs-lookup"><span data-stu-id="17316-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="17316-138">Por ejemplo, enriquezca los datos solo para un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="17316-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="17316-139">Puede configurar varios enriquecimientos del mismo tipo y reutilizar la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="17316-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="17316-140">Algunos enriquecimientos tendrán límites en el número de enriquecimientos del mismo tipo que se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="17316-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="17316-141">Los límites y el uso actual se pueden ver en la página **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="17316-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
