---
title: Enriquecimiento con el enriquecimiento de terceros HERE Technologies
description: Información general sobre el enriquecimiento de terceros HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896072"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="f7cfe-103">Enriquecimiento de perfiles de clientes con HERE Technologies (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="f7cfe-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="f7cfe-104">HERE Technologies es una empresa de plataformas de ubicación que proporciona datos y servicios centrados en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="f7cfe-105">Con los servicios de enriquecimiento de datos de HERE Technologies, puede construir una comprensión más precisa de la ubicación de sus clientes con normalización de direcciones, extracción de latitud y longitud, etc.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7cfe-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f7cfe-106">Prerequisites</span></span>

<span data-ttu-id="f7cfe-107">Para configurar los enriquecimientos de HERE Technologies, se deben cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="f7cfe-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f7cfe-108">Debe disponer de una suscripción activa de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="f7cfe-109">Para obtener una suscripción, puede [registrarse aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [ponerse en contacto con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="f7cfe-110">Obtenga más información sobre el enriquecimiento de ubicación de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="f7cfe-111">Hay una [conexión](connections.md) a HERE disponible *o* tiene permisos de [administrador](permissions.md#administrator) y la clave API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f7cfe-112">Configurar el enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="f7cfe-112">Configure the enrichment</span></span>

1. <span data-ttu-id="f7cfe-113">Vaya a **Datos** > **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="f7cfe-114">Seleccione **Enriquecer mis datos** en la ventana de HERE Technologies y seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7cfe-115">![Mosaico de HERE Technologies](media/HERE-tile.png "Mosaico de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="f7cfe-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="f7cfe-116">Seleccione una [conexión](connections.md) en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="f7cfe-117">Contacte con un administrador si no hay conexión disponible.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="f7cfe-118">Si es un administrador, puede crear una conexión seleccionando **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="f7cfe-119">Elija **HERE Technologies** desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="f7cfe-120">Seleccione **Conectarse a HERE Technologies** para confirmar la selección.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="f7cfe-121">Seleccione **Siguiente** y elija el **Conjunto de datos del cliente** que desea enriquecer con datos de ubicación de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="f7cfe-122">Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. <span data-ttu-id="f7cfe-124">Elija si desea asignar campos a la dirección principal y/o secundaria.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="f7cfe-125">Puede especificar una asignación de campo para ambas direcciones y enriquecer los perfiles para ambas direcciones por separado.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="f7cfe-126">Por ejemplo, si hay una casa y una dirección comercial.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="f7cfe-127">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-127">Select **Next**.</span></span>

1. <span data-ttu-id="f7cfe-128">Defina qué campos de sus perfiles unificados se deben utilizar para buscar datos de ubicación coincidentes en HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="f7cfe-129">Los campos **Calle 1** y **Código postal** son obligatorios para la dirección primaria y/o secundaria seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="f7cfe-130">Para una mayor precisión de coincidencia, se pueden agregar más campos.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7cfe-131">![Página de configuración de enriquecimiento de HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuración de enriquecimiento de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="f7cfe-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="f7cfe-132">Seleccione **Siguiente** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="f7cfe-133">Escriba un nombre para el enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="f7cfe-134">1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="f7cfe-135">Configurar la conexión para HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="f7cfe-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="f7cfe-136">Debe ser un administrador para configurar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f7cfe-137">Seleccione **Agregar conexión** cuando configure un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="f7cfe-138">Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f7cfe-139">Proporcione una clave API de HERE Technologies válida.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="f7cfe-140">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="f7cfe-141">Seleccione **Verificar** para validar la configuración.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f7cfe-142">Después de completar la verificación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7cfe-143">![Página de configuración de la conexión de HERE Technologies](media/enrichment-HERE-connection.png "Página de configuración de la conexión de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="f7cfe-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f7cfe-144">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="f7cfe-144">Enrichment results</span></span>

<span data-ttu-id="f7cfe-145">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f7cfe-146">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7cfe-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f7cfe-147">El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y los tiempos de respuesta de la API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="f7cfe-148">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f7cfe-149">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f7cfe-150">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7cfe-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f7cfe-151">Next steps</span></span>

<span data-ttu-id="f7cfe-152">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f7cfe-153">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7cfe-154">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="f7cfe-154">Data privacy and compliance</span></span>

<span data-ttu-id="f7cfe-155">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7cfe-156">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que HERE Technologies cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7cfe-157">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7cfe-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f7cfe-158">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="f7cfe-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
