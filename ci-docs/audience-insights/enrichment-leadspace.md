---
title: Enriquecimiento de los perfiles de la empresa con el enriquecimiento de terceros de Leadspace
description: Información general sobre el enriquecimiento de terceros de Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597670"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="9d752-103">Enriquecimiento de perfiles de empresa con Leadspace (vista previa)</span><span class="sxs-lookup"><span data-stu-id="9d752-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="9d752-104">Leadspace es una empresa de ciencia de datos que proporciona una plataforma de datos de clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="9d752-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="9d752-105">Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa.</span><span class="sxs-lookup"><span data-stu-id="9d752-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="9d752-106">Los enriquecimientos incluyen atributos adicionales, como el tamaño de la compañía, la ubicación, el sector y mucho más.</span><span class="sxs-lookup"><span data-stu-id="9d752-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d752-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9d752-107">Prerequisites</span></span>

<span data-ttu-id="9d752-108">Para configurar Leadspace deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="9d752-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9d752-109">Tiene una licencia Leadspace activa y la “clave perpetua” (denominada **Token de Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="9d752-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="9d752-110">Contacte directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para detalles sobre su producto.</span><span class="sxs-lookup"><span data-stu-id="9d752-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="9d752-111">Tiene permisos de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="9d752-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="9d752-112">Usted tiene [perfiles de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="9d752-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="9d752-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="9d752-113">Configuration</span></span>

1. <span data-ttu-id="9d752-114">En las informaciones de público, vaya a **Datos** > **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="9d752-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="9d752-115">Seleccione **Enriquecer mis datos** en la ventana Leadspace.</span><span class="sxs-lookup"><span data-stu-id="9d752-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla del mosaico de Leadspace.":::

1. <span data-ttu-id="9d752-117">Seleccione **Comenzar** y luego introduzca un **Token de Leadspace** activo (clave perpetua).</span><span class="sxs-lookup"><span data-stu-id="9d752-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="9d752-118">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="9d752-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="9d752-119">Confirme ambas entradas seleccionando **Conectarse a Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="9d752-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="9d752-120">Seleccione **Agregar datos** y elija el conjunto de datos de cliente que desee enriquecer con datos empresariales de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="9d752-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="9d752-121">Puede seleccionar la entidad *Cliente* para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="9d752-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Elija entre el perfil del cliente y el enriquecimiento del segmento.":::

1. <span data-ttu-id="9d752-123">Haga clic en **Siguiente** y defina qué campos de sus perfiles unificados se deben utilizar para buscar datos de empresa coincidentes en Leadspace.</span><span class="sxs-lookup"><span data-stu-id="9d752-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="9d752-124">Se requiere el campo **Nombre de la compañía**.</span><span class="sxs-lookup"><span data-stu-id="9d752-124">The **Name of company** field is required.</span></span> <span data-ttu-id="9d752-125">Para una mayor precisión de coincidencia, pueden añadirse hasta otros dos campos, **Sitio web de la compañía** y **Ubicación de la compañía**.</span><span class="sxs-lookup"><span data-stu-id="9d752-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::
   
1. <span data-ttu-id="9d752-127">Seleccione **Aplicar** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="9d752-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="9d752-128">Seleccione **Ejecutar** para enriquecer los perfiles de la empresa.</span><span class="sxs-lookup"><span data-stu-id="9d752-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="9d752-129">La duración de un enriquecimiento depende de la cantidad de perfiles de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="9d752-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="9d752-130">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="9d752-130">Enrichment results</span></span>

<span data-ttu-id="9d752-131">Después de actualizar el enriquecimiento, puede revisar los datos de la empresa recién enriquecidos en [Mis enriquecimientos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="9d752-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="9d752-132">Puede encontrar la hora de la última actualización y la cantidad de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="9d752-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9d752-133">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="9d752-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="9d752-134">Para obtener más información, vea [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="9d752-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d752-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9d752-135">Next steps</span></span>

<span data-ttu-id="9d752-136">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="9d752-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9d752-137">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="9d752-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9d752-138">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="9d752-138">Data privacy and compliance</span></span>

<span data-ttu-id="9d752-139">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="9d752-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9d752-140">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Leadspace cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="9d752-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9d752-141">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9d752-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9d752-142">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="9d752-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]