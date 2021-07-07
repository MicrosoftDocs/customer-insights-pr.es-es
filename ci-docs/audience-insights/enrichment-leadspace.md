---
title: Enriquecimiento de los perfiles de la empresa con el enriquecimiento de terceros de Leadspace
description: Información general sobre el enriquecimiento de terceros de Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305223"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0f195-103">Enriquecimiento de perfiles de empresa con Leadspace (vista previa)</span><span class="sxs-lookup"><span data-stu-id="0f195-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0f195-104">Leadspace es una empresa de ciencia de datos que proporciona una plataforma de datos de clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="0f195-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0f195-105">Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa.</span><span class="sxs-lookup"><span data-stu-id="0f195-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0f195-106">Los enriquecimientos incluyen más atributos como el tamaño de la empresa, su ubicación, su sector y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0f195-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f195-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f195-107">Prerequisites</span></span>

<span data-ttu-id="0f195-108">Para configurar Leadspace deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="0f195-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0f195-109">Debe tener una licencia activa de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0f195-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="0f195-110">Usted tiene [perfiles de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="0f195-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="0f195-111">Una conexión de Leadspace ya ha sido configurada por un administrador o tiene permisos de [administrador](permissions.md#administrator) y la "clave perpetua" (denominada **Token de Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="0f195-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0f195-112">Póngase en contacto directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obtener detalles sobre su producto.</span><span class="sxs-lookup"><span data-stu-id="0f195-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0f195-113">Configurar el enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="0f195-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0f195-114">En las informaciones de público, vaya a **Datos** > **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="0f195-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0f195-115">Seleccione **Enriquecer mis datos** en la ventana de Leadspace y seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="0f195-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla del mosaico de Leadspace.":::

1. <span data-ttu-id="0f195-117">Seleccione una [conexión](connections.md) en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0f195-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="0f195-118">Contacte con un administrador si no hay conexión disponible.</span><span class="sxs-lookup"><span data-stu-id="0f195-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0f195-119">Si es un administrador, puede crear una conexión seleccionando **Agregar conexión** y elija **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="0f195-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="0f195-120">Seleccione **Conectarse a Leadspace** para confirmar la selección de la conexión.</span><span class="sxs-lookup"><span data-stu-id="0f195-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="0f195-121">Seleccione **Siguiente** y elija el **Conjunto de datos del cliente** que desea enriquecer con datos empresariales de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0f195-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="0f195-122">Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="0f195-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. <span data-ttu-id="0f195-124">Seleccione **Siguiente** y defina qué campos de sus perfiles unificados se usan para buscar datos empresariales coincidentes de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0f195-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0f195-125">Se requiere el campo **Nombre de la compañía**.</span><span class="sxs-lookup"><span data-stu-id="0f195-125">The **Name of company** field is required.</span></span> <span data-ttu-id="0f195-126">Para una mayor precisión de coincidencia, pueden añadirse hasta otros dos campos, **Sitio web de la compañía** y **Ubicación de la compañía**.</span><span class="sxs-lookup"><span data-stu-id="0f195-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::

1. <span data-ttu-id="0f195-128">Seleccione **Siguiente** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="0f195-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0f195-129">Proporcione un nombre para el enriquecimiento y seleccione **Guardar enriquecimiento** después de revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="0f195-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="0f195-130">Configurar la conexión para Leadspace</span><span class="sxs-lookup"><span data-stu-id="0f195-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="0f195-131">Debe ser un administrador para configurar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="0f195-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0f195-132">Seleccione **Agregar conexión** cuando configure un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0f195-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="0f195-133">Seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="0f195-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="0f195-134">Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.</span><span class="sxs-lookup"><span data-stu-id="0f195-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0f195-135">Proporcionar su token de Leadspace válido.</span><span class="sxs-lookup"><span data-stu-id="0f195-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="0f195-136">Revise y proporcione su consentimiento para **Privacidad y cumplimiento de datos** seleccionando **Estoy de acuerdo**.</span><span class="sxs-lookup"><span data-stu-id="0f195-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="0f195-137">Seleccione **Verificar** para validar la configuración.</span><span class="sxs-lookup"><span data-stu-id="0f195-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0f195-138">Después de completar la verificación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0f195-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuración de la conexión de Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="0f195-140">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="0f195-140">Enrichment results</span></span>

<span data-ttu-id="0f195-141">Después de actualizar el enriquecimiento, puede revisar los datos de la empresa recién enriquecidos en [Mis enriquecimientos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0f195-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0f195-142">Puede encontrar la hora de la última actualización y la cantidad de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="0f195-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0f195-143">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="0f195-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0f195-144">Para obtener más información, vea [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="0f195-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f195-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0f195-145">Next steps</span></span>

<span data-ttu-id="0f195-146">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="0f195-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0f195-147">Crear [segmentos](segments.md) y [medidas](measures.md) e incluso [exportar los datos](export-destinations.md) para brindar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="0f195-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0f195-148">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="0f195-148">Data privacy and compliance</span></span>

<span data-ttu-id="0f195-149">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="0f195-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0f195-150">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Leadspace cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="0f195-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0f195-151">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0f195-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0f195-152">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="0f195-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
