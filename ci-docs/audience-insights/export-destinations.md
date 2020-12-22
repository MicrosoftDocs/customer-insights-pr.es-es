---
title: Destinos de exportación
description: Exporte datos y administre destinos de exportación.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643884"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="88a9d-103">Destinos de exportación (vista previa)</span><span class="sxs-lookup"><span data-stu-id="88a9d-103">Export destinations (preview)</span></span>

<span data-ttu-id="88a9d-104">La página **Destinos de exportación** muestra todas las ubicaciones que ha configurado como destino de exportación de datos.</span><span class="sxs-lookup"><span data-stu-id="88a9d-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="88a9d-105">También puede agregar nuevos destinos para exportación.</span><span class="sxs-lookup"><span data-stu-id="88a9d-105">You can also add new destinations for export.</span></span> <span data-ttu-id="88a9d-106">Además, muestra las opciones de exportación disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="88a9d-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="88a9d-107">Obtenga información general rápida, una descripción y descubra lo que puede hacer con cada opción de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="88a9d-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="88a9d-108">Exporte perfiles, medidas y segmentos unificados a aplicaciones compatibles relevantes para su negocio.</span><span class="sxs-lookup"><span data-stu-id="88a9d-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="88a9d-109">Vaya a **Administración** > **Exportar destinos** para encontrar las siguientes opciones de extensibilidad:</span><span class="sxs-lookup"><span data-stu-id="88a9d-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="88a9d-110">Complemento de tarjeta de cliente de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="88a9d-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="88a9d-111">Conector de administrador de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="88a9d-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="88a9d-112">Power Automateconector</span><span class="sxs-lookup"><span data-stu-id="88a9d-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="88a9d-113">Power Appsconector</span><span class="sxs-lookup"><span data-stu-id="88a9d-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="88a9d-114">Power BIconector</span><span class="sxs-lookup"><span data-stu-id="88a9d-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="88a9d-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="88a9d-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="88a9d-116">Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="88a9d-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="88a9d-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="88a9d-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="88a9d-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="88a9d-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="88a9d-119">Conector LiveRamp &reg;</span><span class="sxs-lookup"><span data-stu-id="88a9d-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="88a9d-120">Bot para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88a9d-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="88a9d-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="88a9d-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="88a9d-122">API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="88a9d-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="88a9d-123">Agregar un nuevo destino de exportación</span><span class="sxs-lookup"><span data-stu-id="88a9d-123">Add a new export destination</span></span>

<span data-ttu-id="88a9d-124">Para agregar destinos de exportación, tiene [permisos de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="88a9d-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="88a9d-125">Si exporta a servicios de Microsoft, suponemos que ambos servicios están en la misma organización.</span><span class="sxs-lookup"><span data-stu-id="88a9d-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="88a9d-126">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="88a9d-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="88a9d-127">Pase a la pestaña **Mis destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="88a9d-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="88a9d-128">Seleccione **Agregar destino** para crear un nuevo destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="88a9d-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="88a9d-129">En el panel **Agregar destino**, seleccione el **Tipo** de destino de exportación en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="88a9d-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="88a9d-130">Proporcione los detalles necesarios y seleccione **Siguiente** para crear el destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="88a9d-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="88a9d-131">También puede seleccionar **Configurar** en un icono de la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="88a9d-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="88a9d-132">Ver destinos de exportación</span><span class="sxs-lookup"><span data-stu-id="88a9d-132">View Export destinations</span></span>

<span data-ttu-id="88a9d-133">Una vez creados los destinos de exportación, los verá en una tabla de la pestaña **Mis destinos de exportación**. Esta tabla tiene tres columnas:</span><span class="sxs-lookup"><span data-stu-id="88a9d-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="88a9d-134">**Nombre para mostrar**: el nombre que ha introducido al crear el destino.</span><span class="sxs-lookup"><span data-stu-id="88a9d-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="88a9d-135">**Tipo**: el tipo de destino de exportación que estableció al crear el destino.</span><span class="sxs-lookup"><span data-stu-id="88a9d-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="88a9d-136">**Creado**: la fecha en la que creó el destino.</span><span class="sxs-lookup"><span data-stu-id="88a9d-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="88a9d-137">Editar un destino de exportación</span><span class="sxs-lookup"><span data-stu-id="88a9d-137">Edit an export destination</span></span>

1. <span data-ttu-id="88a9d-138">Seleccione los puntos suspensivos verticales del destino de exportación que desea editar.</span><span class="sxs-lookup"><span data-stu-id="88a9d-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88a9d-139">![Puntos suspensivos verticales](media/export-destinations-page-ellipsis.png "Puntos suspensivos verticales")</span><span class="sxs-lookup"><span data-stu-id="88a9d-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="88a9d-140">Seleccione **Editar** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="88a9d-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="88a9d-141">Cambie los valores que requieren actualización y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="88a9d-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="88a9d-142">Exportar datos a petición</span><span class="sxs-lookup"><span data-stu-id="88a9d-142">Export data on demand</span></span>

<span data-ttu-id="88a9d-143">Tras configurar un conector para un destino de exportación, las exportaciones se ejecutarán en cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="88a9d-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="88a9d-144">Para exportar datos sin esperar una actualización programada, vaya a la pestaña **Mis destinos de exportación** en **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="88a9d-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="88a9d-145">![Puntos suspensivos verticales](media/export-destinations-page-ellipsis.png "Puntos suspensivos verticales")</span><span class="sxs-lookup"><span data-stu-id="88a9d-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="88a9d-146">Seleccione **Exportar** encima de la lista para ejecutar simultáneamente la exportación a todos los destinos de exportación.</span><span class="sxs-lookup"><span data-stu-id="88a9d-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="88a9d-147">Seleccione los puntos suspensivos (...) que se muestran a continuación de un elemento de la lista y después elija la opción **Exportar** para ejecutar la exportación para un solo destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="88a9d-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="88a9d-148">Quitar un destino de exportación</span><span class="sxs-lookup"><span data-stu-id="88a9d-148">Remove an Export destination</span></span>

<span data-ttu-id="88a9d-149">Para quitar un destino de exportación, empiece desde la página principal **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="88a9d-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="88a9d-150">Seleccione los puntos suspensivos verticales para el destino de exportación que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="88a9d-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88a9d-151">![Puntos suspensivos verticales](media/export-destinations-page-ellipsis.png "Puntos suspensivos verticales")</span><span class="sxs-lookup"><span data-stu-id="88a9d-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="88a9d-152">Seleccione **Quitar** del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="88a9d-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="88a9d-153">Confirme la eliminación seleccionando **Quitar** en la pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="88a9d-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
