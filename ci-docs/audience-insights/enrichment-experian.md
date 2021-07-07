---
title: Enriquecimiento con el enriquecimiento de terceros de Experian
description: Información general sobre el enriquecimiento de Experian de terceros.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309841"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="8ea44-103">Enriquezca los perfiles de los clientes con datos demográficos de Experian (vista previa)</span><span class="sxs-lookup"><span data-stu-id="8ea44-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="8ea44-104">Experian es líder mundial en informes crediticios y servicios de marketing para consumidores y empresas.</span><span class="sxs-lookup"><span data-stu-id="8ea44-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="8ea44-105">Con los servicios de enriquecimiento de datos de Experian, puede desarrollar una comprensión más a fondo de sus clientes al enriquecer los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.</span><span class="sxs-lookup"><span data-stu-id="8ea44-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ea44-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8ea44-106">Prerequisites</span></span>

<span data-ttu-id="8ea44-107">Para configurar Experian, deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8ea44-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8ea44-108">Tiene una suscripción de Experian activa.</span><span class="sxs-lookup"><span data-stu-id="8ea44-108">You have an active Experian subscription.</span></span> <span data-ttu-id="8ea44-109">Para obtener una suscripción, [póngase en contacto con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="8ea44-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="8ea44-110">[Más información sobre el enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="8ea44-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="8ea44-111">Una conexión Experian ya ha sido configurada por un administrador *o* tiene permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="8ea44-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="8ea44-112">También necesita la identificación de usuario, la identificación de parte y el número de modelo para su cuenta de transporte seguro (ST) habilitada para SSH que haya creado Experian por usted.</span><span class="sxs-lookup"><span data-stu-id="8ea44-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="8ea44-113">Países/regiones admitidos</span><span class="sxs-lookup"><span data-stu-id="8ea44-113">Supported countries/regions</span></span>

<span data-ttu-id="8ea44-114">Actualmente, solo admitimos el enriquecimiento de perfiles de clientes en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8ea44-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="8ea44-115">Configurar el enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="8ea44-115">Configure the enrichment</span></span>

1. <span data-ttu-id="8ea44-116">Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="8ea44-117">Seleccione **Enriquecer mis datos** en la ventana de Experian.</span><span class="sxs-lookup"><span data-stu-id="8ea44-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8ea44-118">![Experian mosaico](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="8ea44-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="8ea44-119">Seleccione una [conexión](connections.md) en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8ea44-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="8ea44-120">Contacte con un administrador si no hay conexión disponible.</span><span class="sxs-lookup"><span data-stu-id="8ea44-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="8ea44-121">Si es un administrador, puede crear una conexión seleccionando **Agregar conexión** y eligiendo Experian en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8ea44-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="8ea44-122">Seleccione **Conectar a Experian** para confirmar la selección de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ea44-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="8ea44-123">Seleccione **próximo** y elija el **conjunto de datos Cliente** que desee enriquecer con datos demográficos de Experian.</span><span class="sxs-lookup"><span data-stu-id="8ea44-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="8ea44-124">Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="8ea44-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. <span data-ttu-id="8ea44-126">Seleccione **Siguiente** y defina qué tipo de campos de sus perfiles unificados deben usarse para buscar datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="8ea44-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8ea44-127">Es obligatorio al menos uno de los campos **Nombre y dirección**, **Teléfono**, o **Correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="8ea44-128">Para una mayor precisión de correspondencia, se pueden agregar hasta otros dos campos.</span><span class="sxs-lookup"><span data-stu-id="8ea44-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="8ea44-129">Esta selección afectará a los campos de asignación a los que tiene acceso en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="8ea44-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="8ea44-130">Si se envían más atributos de identificadores de claves enviados a Experian, probablemente se genere un índice de coincidencia más alto.</span><span class="sxs-lookup"><span data-stu-id="8ea44-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="8ea44-131">Seleccione **Siguiente** para iniciar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="8ea44-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="8ea44-132">Definir qué tipo de campos de sus perfiles unificados deben usarse para buscar datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="8ea44-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8ea44-133">Los campos obligatorios están marcados.</span><span class="sxs-lookup"><span data-stu-id="8ea44-133">Required fields are marked.</span></span>

1. <span data-ttu-id="8ea44-134">Proporcione un nombre para el enriquecimiento y un nombre para la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="8ea44-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="8ea44-135">Seleccione **Guardar enriquecimiento** después de revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="8ea44-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="8ea44-136">Configurar la conexión para Experian</span><span class="sxs-lookup"><span data-stu-id="8ea44-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="8ea44-137">Debe ser un administrador para configurar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="8ea44-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="8ea44-138">Seleccione **Agregar conexión** al configurar un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Experian.</span><span class="sxs-lookup"><span data-stu-id="8ea44-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="8ea44-139">Seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="8ea44-140">Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="8ea44-141">Identifique un identificador de usuario, un identificador de parte de grupo y un número de modelo válidos para su cuenta de transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="8ea44-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="8ea44-142">Revise y proporcione su consentimiento para **Privacidad y cumplimiento de datos** seleccionando **Estoy de acuerdo**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="8ea44-143">Seleccione **Verificar** para validar la configuración.</span><span class="sxs-lookup"><span data-stu-id="8ea44-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="8ea44-144">Después de completar la verificación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel de configuración de conexión de Experian":::.

## <a name="enrichment-results"></a><span data-ttu-id="8ea44-146">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="8ea44-146">Enrichment results</span></span>

<span data-ttu-id="8ea44-147">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="8ea44-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8ea44-148">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8ea44-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8ea44-149">El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y de los procesos de enriquecimiento configurados para su cuenta por Experian.</span><span class="sxs-lookup"><span data-stu-id="8ea44-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="8ea44-150">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8ea44-151">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="8ea44-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8ea44-152">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="8ea44-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ea44-153">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ea44-153">Next steps</span></span>

<span data-ttu-id="8ea44-154">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="8ea44-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8ea44-155">Crear [segmentos](segments.md) y [medidas](measures.md) e incluso [exportar los datos](export-destinations.md) para brindar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="8ea44-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8ea44-156">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="8ea44-156">Data privacy and compliance</span></span>

<span data-ttu-id="8ea44-157">Cuando habilite Dynamics 365 Customer Insights para transmitir datos a Experian, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="8ea44-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8ea44-158">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Experian cumple las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="8ea44-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8ea44-159">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8ea44-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8ea44-160">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="8ea44-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
