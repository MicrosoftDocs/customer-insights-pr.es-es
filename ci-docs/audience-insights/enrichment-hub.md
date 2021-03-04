---
title: Enriquecer perfiles de cliente unificados
description: Utilice las capacidades para enriquecer los datos de sus clientes.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269489"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="3327d-103">Enriquecimiento para perfiles de clientes (vista previa)</span><span class="sxs-lookup"><span data-stu-id="3327d-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="3327d-104">Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="3327d-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página del centro de enriquecimiento":::

<span data-ttu-id="3327d-106">En la información de audiencia, vaya a **Datos** > **Enriquecimiento** para trabajar con opciones de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="3327d-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="3327d-107">Debe tener permisos de Colaborador o Administrador para crear o editar enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="3327d-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="3327d-108">Para obtener más información, vea [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3327d-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="3327d-109">En la pestaña **Descubrir** encontrará los siguientes enriquecimientos:</span><span class="sxs-lookup"><span data-stu-id="3327d-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="3327d-110">[Marcas](enrichment-microsoft-graph.md) proporcionadas por Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="3327d-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="3327d-111">[Intereses](enrichment-microsoft-graph.md) proporcionados por Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="3327d-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="3327d-112">[Datos de empresa](enrichment-leadspace.md) proporcionados por Leadspace</span><span class="sxs-lookup"><span data-stu-id="3327d-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="3327d-113">[Datos demográficos](enrichment-experian.md) proporcionados por Experian</span><span class="sxs-lookup"><span data-stu-id="3327d-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="3327d-114">[Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="3327d-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="3327d-115">[Datos de cliente](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)</span><span class="sxs-lookup"><span data-stu-id="3327d-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="3327d-116">En la pestaña **Mis enriquecimientos** puede ver los enriquecimientos que ha configurado y editar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="3327d-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="3327d-117">Administrar enriquecimientos existentes</span><span class="sxs-lookup"><span data-stu-id="3327d-117">Manage existing enrichments</span></span>

<span data-ttu-id="3327d-118">Vaya a **Mis enriquecimientos** para ver todos los enriquecimientos configurados.</span><span class="sxs-lookup"><span data-stu-id="3327d-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="3327d-119">Cada enriquecimiento se representa como una fila que incluye información adicional sobre el enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="3327d-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="3327d-120">Seleccione un enriquecimiento para ver las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="3327d-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="3327d-121">Alternativamente, puede seleccionar los puntos suspensivos (...) en un elemento de la lista para ver las opciones.</span><span class="sxs-lookup"><span data-stu-id="3327d-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opciones para administrar enriquecimientos en la lista de enriquecimientos":::

- <span data-ttu-id="3327d-123">**Vea** los detalles de enriquecimiento con el número de perfiles de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="3327d-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="3327d-124">**Edite** la configuración de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="3327d-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="3327d-125">**Ejecutar** el enriquecimiento para actualizar los perfiles de los clientes con los últimos datos.</span><span class="sxs-lookup"><span data-stu-id="3327d-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="3327d-126">**Desactive** un enriquecimiento existente para evitar que se actualice automáticamente con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="3327d-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="3327d-127">Los datos de la última actualización exitosa seguirán estando disponibles.</span><span class="sxs-lookup"><span data-stu-id="3327d-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="3327d-128">**Active** un enriquecimiento inactivo para reiniciar la actualización automática con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="3327d-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="3327d-129">**Eliminar** un enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="3327d-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="3327d-130">Puede ejecutar o desactivar varios enriquecimientos a la vez seleccionándolos en la lista.</span><span class="sxs-lookup"><span data-stu-id="3327d-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="3327d-131">Las opciones de visualización y edición no están disponibles como acción masiva y solo funcionan para un enriquecimiento a la vez.</span><span class="sxs-lookup"><span data-stu-id="3327d-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]