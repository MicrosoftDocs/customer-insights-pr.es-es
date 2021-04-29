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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896026"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="2b933-103">Enriquecimiento para perfiles de clientes (vista previa)</span><span class="sxs-lookup"><span data-stu-id="2b933-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="2b933-104">Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="2b933-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página del centro de enriquecimiento":::

<span data-ttu-id="2b933-106">En la información de audiencia, vaya a **Datos** > **Enriquecimiento** para trabajar con opciones de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="2b933-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="2b933-107">Debe tener permisos de Colaborador o Administrador para crear o editar enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="2b933-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="2b933-108">Para obtener más información, vea [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2b933-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="2b933-109">En la pestaña **Descubrir** encontrará los siguientes enriquecimientos:</span><span class="sxs-lookup"><span data-stu-id="2b933-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="2b933-110">[Marcas](enrichment-microsoft.md) proporcionadas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b933-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="2b933-111">[Intereses](enrichment-microsoft.md) proporcionados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b933-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="2b933-112">[Datos de empresa](enrichment-leadspace.md) proporcionados por Leadspace</span><span class="sxs-lookup"><span data-stu-id="2b933-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="2b933-113">[Datos demográficos](enrichment-experian.md) proporcionados por Experian</span><span class="sxs-lookup"><span data-stu-id="2b933-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="2b933-114">[Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="2b933-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="2b933-115">[Datos de cliente](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)</span><span class="sxs-lookup"><span data-stu-id="2b933-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="2b933-116">En la pestaña **Mis enriquecimientos** puede ver los enriquecimientos que ha configurado y editar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="2b933-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="2b933-117">Administrar enriquecimientos existentes</span><span class="sxs-lookup"><span data-stu-id="2b933-117">Manage existing enrichments</span></span>

<span data-ttu-id="2b933-118">Vaya a **Mis enriquecimientos** para ver todos los enriquecimientos configurados.</span><span class="sxs-lookup"><span data-stu-id="2b933-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="2b933-119">Cada enriquecimiento se representa como una fila que incluye información adicional sobre el enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="2b933-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="2b933-120">Seleccione un enriquecimiento para ver las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="2b933-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="2b933-121">También puede seleccionar los puntos suspensivos (...) en un elemento de la lista para ver las opciones.</span><span class="sxs-lookup"><span data-stu-id="2b933-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opciones para administrar enriquecimientos en la lista de enriquecimientos":::

- <span data-ttu-id="2b933-123">**Vea** los detalles de enriquecimiento con el número de perfiles de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="2b933-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="2b933-124">**Edite** la configuración de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="2b933-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="2b933-125">**Ejecutar** el enriquecimiento para actualizar los perfiles de los clientes con los últimos datos.</span><span class="sxs-lookup"><span data-stu-id="2b933-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="2b933-126">**Desactive** un enriquecimiento existente para evitar que se actualice automáticamente con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="2b933-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="2b933-127">Los datos de la última actualización exitosa seguirán estando disponibles.</span><span class="sxs-lookup"><span data-stu-id="2b933-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="2b933-128">**Active** un enriquecimiento inactivo para reiniciar la actualización automática con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="2b933-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="2b933-129">**Eliminar** un enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="2b933-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="2b933-130">Puede ejecutar o desactivar varios enriquecimientos a la vez seleccionándolos en la lista.</span><span class="sxs-lookup"><span data-stu-id="2b933-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="2b933-131">Las opciones de visualización y edición no están disponibles como acción masiva y solo funcionan para un enriquecimiento a la vez.</span><span class="sxs-lookup"><span data-stu-id="2b933-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="2b933-132">Enriquecimientos y conexiones</span><span class="sxs-lookup"><span data-stu-id="2b933-132">Enrichments and connections</span></span>

<span data-ttu-id="2b933-133">Los enriquecimientos de terceros se configuran mediante [conexiones](connections.md), que un administrador configura con credenciales y proporciona consentimiento para transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="2b933-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="2b933-134">La conexión puede ser utilizadas por parte de administradores y colaboradores para configurar enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="2b933-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="2b933-135">Múltiples enriquecimientos del mismo tipo</span><span class="sxs-lookup"><span data-stu-id="2b933-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="2b933-136">La entidad que se va a enriquecer se especifica durante la configuración del enriquecimiento, lo que le permite enriquecer solo un subconjunto de sus perfiles.</span><span class="sxs-lookup"><span data-stu-id="2b933-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="2b933-137">Por ejemplo, enriquezca los datos solo para un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="2b933-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="2b933-138">Puede configurar varios enriquecimientos del mismo tipo y reutilizar la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="2b933-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="2b933-139">Algunos enriquecimientos tendrán límites en el número de enriquecimientos del mismo tipo que se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="2b933-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="2b933-140">Los límites y el uso actual se pueden ver en la página **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="2b933-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
