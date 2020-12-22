---
title: Enriquecimiento con el enriquecimiento de terceros HERE Technologies
description: Información general sobre el enriquecimiento de terceros HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668699"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="bc07b-103">Enriquecimiento de perfiles de clientes con HERE Technologies (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="bc07b-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="bc07b-104">HERE Technologies es una empresa de plataformas de ubicación que proporciona datos y servicios centrados en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="bc07b-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="bc07b-105">Con los servicios de enriquecimiento de datos de HERE Technologies, puede construir una comprensión más precisa de la ubicación de sus clientes con normalización de direcciones, extracción de latitud y longitud, etc.</span><span class="sxs-lookup"><span data-stu-id="bc07b-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc07b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bc07b-106">Prerequisites</span></span>

<span data-ttu-id="bc07b-107">Para configurar los enriquecimientos de HERE Technologies, se deben cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="bc07b-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bc07b-108">Debe disponer de una suscripción activa de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bc07b-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="bc07b-109">Para obtener una suscripción, puede [registrarse aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [ponerse en contacto con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente.</span><span class="sxs-lookup"><span data-stu-id="bc07b-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="bc07b-110">Obtenga más información sobre el enriquecimiento de ubicación de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bc07b-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="bc07b-111">Tiene la clave de API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bc07b-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="bc07b-112">Tiene permisos de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="bc07b-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="bc07b-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="bc07b-113">Configuration</span></span>

1. <span data-ttu-id="bc07b-114">Vaya a **Datos** > **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="bc07b-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="bc07b-115">Seleccione **Enriquecer mis datos** en el mosaico de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bc07b-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc07b-116">![Mosaico de HERE Technologies](media/HERE-tile.png "Mosaico de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bc07b-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="bc07b-117">Inroduzca una **Clave de API de HERE Technologies** activa.</span><span class="sxs-lookup"><span data-stu-id="bc07b-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="bc07b-118">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="bc07b-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="bc07b-119">Confirme ambas entradas seleccionando **Conéctese AQUÍ**.</span><span class="sxs-lookup"><span data-stu-id="bc07b-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="bc07b-120">Seleccione **Agregar datos** y elija si desea asignar campos a la dirección principal y/o secundaria.</span><span class="sxs-lookup"><span data-stu-id="bc07b-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="bc07b-121">Puede especificar una asignación de campo para ambas direcciones (por ejemplo, una dirección particular y una comercial) y enriquecer los perfiles para ambas direcciones por separado.</span><span class="sxs-lookup"><span data-stu-id="bc07b-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="bc07b-122">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bc07b-122">Select **Next**.</span></span>

1. <span data-ttu-id="bc07b-123">Defina qué campos de sus perfiles unificados se deben utilizar para buscar datos de ubicación coincidentes en HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bc07b-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="bc07b-124">Los campos **Calle 1** y **Código postal** son obligatorios para la dirección primaria y/o secundaria seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="bc07b-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="bc07b-125">Para una mayor precisión de coincidencia, se pueden agregar más campos.</span><span class="sxs-lookup"><span data-stu-id="bc07b-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc07b-126">![Página de configuración de enriquecimiento de HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuración de enriquecimiento de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bc07b-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="bc07b-127">Seleccione **Aplicar** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="bc07b-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bc07b-128">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="bc07b-128">Enrichment results</span></span>

<span data-ttu-id="bc07b-129">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="bc07b-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bc07b-130">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bc07b-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bc07b-131">El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y los tiempos de respuesta de la API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bc07b-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="bc07b-132">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="bc07b-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="bc07b-133">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="bc07b-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bc07b-134">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="bc07b-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc07b-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bc07b-135">Next steps</span></span>

<span data-ttu-id="bc07b-136">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="bc07b-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bc07b-137">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="bc07b-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bc07b-138">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="bc07b-138">Data privacy and compliance</span></span>

<span data-ttu-id="bc07b-139">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="bc07b-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bc07b-140">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que HERE Technologies cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="bc07b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bc07b-141">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bc07b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bc07b-142">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="bc07b-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
