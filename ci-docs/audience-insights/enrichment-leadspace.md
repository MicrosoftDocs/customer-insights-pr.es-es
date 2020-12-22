---
title: Enriquecimiento de los perfiles de la empresa con el enriquecimiento de terceros de Leadspace
description: Información general sobre el enriquecimiento de terceros de Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668744"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="79696-103">Enriquecimiento de perfiles de empresa con Leadspace (vista previa)</span><span class="sxs-lookup"><span data-stu-id="79696-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="79696-104">Leadspace es una empresa de ciencia de datos que proporciona una plataforma de datos de clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="79696-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="79696-105">Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa.</span><span class="sxs-lookup"><span data-stu-id="79696-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="79696-106">Los enriquecimientos incluyen atributos adicionales, como el tamaño de la compañía, la ubicación, el sector y mucho más.</span><span class="sxs-lookup"><span data-stu-id="79696-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79696-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="79696-107">Prerequisites</span></span>

<span data-ttu-id="79696-108">Para configurar Leadspace deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="79696-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="79696-109">Tiene una licencia Leadspace activa y la “clave perpetua” (denominada **Token de Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="79696-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="79696-110">Contacte directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para detalles sobre su producto.</span><span class="sxs-lookup"><span data-stu-id="79696-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="79696-111">Tiene permisos de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="79696-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="79696-112">Usted tiene [perfiles de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="79696-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="79696-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="79696-113">Configuration</span></span>

1. <span data-ttu-id="79696-114">En las informaciones de público, vaya a **Datos** > **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="79696-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="79696-115">Seleccione **Enriquecer mis datos** en la ventana Leadspace.</span><span class="sxs-lookup"><span data-stu-id="79696-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla del mosaico de Leadspace.":::

1. <span data-ttu-id="79696-117">Seleccione **Comenzar** y luego introduzca un **Token de Leadspace** activo (clave perpetua).</span><span class="sxs-lookup"><span data-stu-id="79696-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="79696-118">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="79696-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="79696-119">Confirme ambas entradas seleccionando **Conectarse a Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="79696-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="79696-120">Seleccione **Datos del mapa** y defina qué campos de sus perfiles unificados se deben utilizar para buscar datos de empresa coincidentes en Leadspace.</span><span class="sxs-lookup"><span data-stu-id="79696-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="79696-121">Se requiere el campo **Nombre de la compañía**.</span><span class="sxs-lookup"><span data-stu-id="79696-121">The **Name of company** field is required.</span></span> <span data-ttu-id="79696-122">Para una mayor precisión de coincidencia, pueden añadirse hasta otros dos campos, **Sitio web de la compañía** y **Ubicación de la compañía**.</span><span class="sxs-lookup"><span data-stu-id="79696-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::
   
1. <span data-ttu-id="79696-124">Seleccione **Aplicar** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="79696-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="79696-125">Seleccione **Ejecutar** para enriquecer los perfiles de la empresa.</span><span class="sxs-lookup"><span data-stu-id="79696-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="79696-126">La duración de un enriquecimiento depende de la cantidad de perfiles de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="79696-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="79696-127">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="79696-127">Enrichment results</span></span>

<span data-ttu-id="79696-128">Después de actualizar el enriquecimiento, puede revisar los datos de la empresa recién enriquecidos en [Mis enriquecimientos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="79696-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="79696-129">Puede encontrar la hora de la última actualización y la cantidad de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="79696-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="79696-130">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="79696-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="79696-131">Para obtener más información, vea [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="79696-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="79696-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="79696-132">Next steps</span></span>

<span data-ttu-id="79696-133">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="79696-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="79696-134">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="79696-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79696-135">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="79696-135">Data privacy and compliance</span></span>

<span data-ttu-id="79696-136">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="79696-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79696-137">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Leadspace cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="79696-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="79696-138">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="79696-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="79696-139">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="79696-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>