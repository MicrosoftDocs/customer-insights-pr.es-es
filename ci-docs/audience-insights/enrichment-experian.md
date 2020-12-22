---
title: Enriquecimiento con el enriquecimiento de terceros Experian
description: Información general sobre el enriquecimiento de terceros de Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668834"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="fdd28-103">Enriquezca los perfiles de los clientes con datos demográficos de Experian (vista previa)</span><span class="sxs-lookup"><span data-stu-id="fdd28-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="fdd28-104">Experian es un líder mundial en informes crediticios y servicios de marketing para consumidores y empresas.</span><span class="sxs-lookup"><span data-stu-id="fdd28-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="fdd28-105">Con los servicios de enriquecimiento de datos de Experian, puede desarrollar una comprensión más profunda de sus clientes enriqueciendo los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.</span><span class="sxs-lookup"><span data-stu-id="fdd28-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdd28-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fdd28-106">Prerequisites</span></span>

<span data-ttu-id="fdd28-107">Para configurar Experian deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="fdd28-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fdd28-108">Tener una suscripción de Experian activa.</span><span class="sxs-lookup"><span data-stu-id="fdd28-108">You have an active Experian subscription.</span></span> <span data-ttu-id="fdd28-109">Para obtener una suscripción, [póngase en contacto con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="fdd28-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="fdd28-110">[Más información sobre el enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="fdd28-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="fdd28-111">Uste tiene el ID. de usuario, el ID. de parte y el número de modelo para su cuenta de transporte seguro (ST) habilitada por SSH que Experian creó para usted.</span><span class="sxs-lookup"><span data-stu-id="fdd28-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="fdd28-112">Tiene permisos de [Administrador](permissions.md#administrator) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="fdd28-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="fdd28-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="fdd28-113">Configuration</span></span>

1. <span data-ttu-id="fdd28-114">Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="fdd28-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="fdd28-115">Seleccione **Enriquecer mis datos** en la ventana de Experian.</span><span class="sxs-lookup"><span data-stu-id="fdd28-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fdd28-116">![Ventana de Experian](media/experian-tile.png "Ventana de Experian")</span><span class="sxs-lookup"><span data-stu-id="fdd28-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="fdd28-117">Seleccione **Comenzar** e ingrese el ID. de usuario, ID. de parte y número de modelo para su cuenta de transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="fdd28-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="fdd28-118">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="fdd28-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="fdd28-119">Confirme todas las entradas seleccionando **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="fdd28-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="fdd28-120">Asignar sus campos</span><span class="sxs-lookup"><span data-stu-id="fdd28-120">Map your fields</span></span>

1. <span data-ttu-id="fdd28-121">Seleccione **Agregar datos** y elija sus identificadores clave desde **Nombre y dirección**, **Correo electrónico** o **Teléfono** para enviar a Experian para la resolución de identidad.</span><span class="sxs-lookup"><span data-stu-id="fdd28-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="fdd28-122">Más atributos de identificadores clave enviados a Experian probablemente produzcan una tasa de coincidencia más alta.</span><span class="sxs-lookup"><span data-stu-id="fdd28-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="fdd28-123">Seleccione **Siguiente** y asigne los atributos correspondientes desde su entidad de cliente unificada para los campos de identificador de clave seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fdd28-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="fdd28-124">Seleccione **Agregar atributo** para asignar atributos adicionales que le gustaría enviar a Experian.</span><span class="sxs-lookup"><span data-stu-id="fdd28-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="fdd28-125">Seleccione **Guardar** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="fdd28-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fdd28-126">![Asignación de campos de Experian](media/experian-field-mapping.png "Asignación de campos de Experian")</span><span class="sxs-lookup"><span data-stu-id="fdd28-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fdd28-127">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="fdd28-127">Enrichment results</span></span>

<span data-ttu-id="fdd28-128">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="fdd28-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fdd28-129">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fdd28-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fdd28-130">El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y de los procesos de enriquecimiento configurados para su cuenta por Experian.</span><span class="sxs-lookup"><span data-stu-id="fdd28-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="fdd28-131">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="fdd28-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="fdd28-132">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="fdd28-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fdd28-133">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="fdd28-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fdd28-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fdd28-134">Next steps</span></span>

<span data-ttu-id="fdd28-135">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="fdd28-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fdd28-136">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="fdd28-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fdd28-137">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="fdd28-137">Data privacy and compliance</span></span>

<span data-ttu-id="fdd28-138">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="fdd28-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fdd28-139">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Experian cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="fdd28-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fdd28-140">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fdd28-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fdd28-141">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="fdd28-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
