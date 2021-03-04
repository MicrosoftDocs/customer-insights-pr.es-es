---
title: Enriquecimiento con el enriquecimiento de terceros Experian
description: Información general sobre el enriquecimiento de terceros de Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269581"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="e3da0-103">Enriquezca los perfiles de los clientes con datos demográficos de Experian (vista previa)</span><span class="sxs-lookup"><span data-stu-id="e3da0-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="e3da0-104">Experian es un líder mundial en informes crediticios y servicios de marketing para consumidores y empresas.</span><span class="sxs-lookup"><span data-stu-id="e3da0-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="e3da0-105">Con los servicios de enriquecimiento de datos de Experian, puede desarrollar una comprensión más profunda de sus clientes enriqueciendo los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.</span><span class="sxs-lookup"><span data-stu-id="e3da0-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3da0-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e3da0-106">Prerequisites</span></span>

<span data-ttu-id="e3da0-107">Para configurar Experian deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="e3da0-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e3da0-108">Tener una suscripción de Experian activa.</span><span class="sxs-lookup"><span data-stu-id="e3da0-108">You have an active Experian subscription.</span></span> <span data-ttu-id="e3da0-109">Para obtener una suscripción, [póngase en contacto con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="e3da0-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="e3da0-110">[Más información sobre el enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="e3da0-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="e3da0-111">Uste tiene el ID. de usuario, el ID. de parte y el número de modelo para su cuenta de transporte seguro (ST) habilitada por SSH que Experian creó para usted.</span><span class="sxs-lookup"><span data-stu-id="e3da0-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="e3da0-112">Tiene permisos de [Administrador](permissions.md#administrator) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="e3da0-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="e3da0-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="e3da0-113">Configuration</span></span>

1. <span data-ttu-id="e3da0-114">Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="e3da0-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e3da0-115">Seleccione **Enriquecer mis datos** en la ventana de Experian.</span><span class="sxs-lookup"><span data-stu-id="e3da0-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3da0-116">![Ventana de Experian](media/experian-tile.png "Ventana de Experian")</span><span class="sxs-lookup"><span data-stu-id="e3da0-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="e3da0-117">Seleccione **Comenzar** e ingrese el ID. de usuario, ID. de parte y número de modelo para su cuenta de transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="e3da0-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="e3da0-118">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="e3da0-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="e3da0-119">Confirme todas las entradas seleccionando **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e3da0-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="e3da0-120">Asignar sus campos</span><span class="sxs-lookup"><span data-stu-id="e3da0-120">Map your fields</span></span>

1.  <span data-ttu-id="e3da0-121">Seleccione **Agregar datos** y elija el **Conjunto de datos de cliente** que desee enriquecer con datos demográficos de Experian.</span><span class="sxs-lookup"><span data-stu-id="e3da0-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="e3da0-122">Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="e3da0-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="e3da0-123">Seleccione sus identificadores clave en **Nombre y dirección**, **Correo electrónico**, o **Teléfono** para enviar a Experian para la resolución de identidad.</span><span class="sxs-lookup"><span data-stu-id="e3da0-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="e3da0-124">Más atributos de identificadores clave enviados a Experian probablemente produzcan una tasa de coincidencia más alta.</span><span class="sxs-lookup"><span data-stu-id="e3da0-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="e3da0-125">Seleccione **Siguiente** y asigne los atributos correspondientes desde su entidad de cliente unificada para los campos de identificador de clave seleccionados.</span><span class="sxs-lookup"><span data-stu-id="e3da0-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="e3da0-126">Seleccione **Agregar atributo** para asignar atributos adicionales que le gustaría enviar a Experian.</span><span class="sxs-lookup"><span data-stu-id="e3da0-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="e3da0-127">Seleccione **Guardar** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="e3da0-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e3da0-128">![Asignación de campos de Experian](media/experian-field-mapping.png "Asignación de campos de Experian")</span><span class="sxs-lookup"><span data-stu-id="e3da0-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e3da0-129">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="e3da0-129">Enrichment results</span></span>

<span data-ttu-id="e3da0-130">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="e3da0-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e3da0-131">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e3da0-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3da0-132">El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y de los procesos de enriquecimiento configurados para su cuenta por Experian.</span><span class="sxs-lookup"><span data-stu-id="e3da0-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="e3da0-133">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="e3da0-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e3da0-134">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="e3da0-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e3da0-135">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="e3da0-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3da0-136">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e3da0-136">Next steps</span></span>

<span data-ttu-id="e3da0-137">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="e3da0-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e3da0-138">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="e3da0-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3da0-139">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="e3da0-139">Data privacy and compliance</span></span>

<span data-ttu-id="e3da0-140">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="e3da0-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3da0-141">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Experian cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="e3da0-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3da0-142">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3da0-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e3da0-143">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="e3da0-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]