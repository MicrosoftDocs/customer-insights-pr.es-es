---
title: Enriquecimiento con el enriquecimiento de terceros Experian
description: Información general sobre el enriquecimiento de terceros de Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896394"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="850cb-103">Enriquezca los perfiles de los clientes con datos demográficos de Experian (vista previa)</span><span class="sxs-lookup"><span data-stu-id="850cb-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="850cb-104">Experian es un líder mundial en informes crediticios y servicios de marketing para consumidores y empresas.</span><span class="sxs-lookup"><span data-stu-id="850cb-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="850cb-105">Con los servicios de enriquecimiento de datos de Experian, puede desarrollar una comprensión más profunda de sus clientes enriqueciendo los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.</span><span class="sxs-lookup"><span data-stu-id="850cb-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="850cb-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="850cb-106">Prerequisites</span></span>

<span data-ttu-id="850cb-107">Para configurar Experian deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="850cb-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="850cb-108">Tener una suscripción de Experian activa.</span><span class="sxs-lookup"><span data-stu-id="850cb-108">You have an active Experian subscription.</span></span> <span data-ttu-id="850cb-109">Para obtener una suscripción, [póngase en contacto con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="850cb-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="850cb-110">[Más información sobre el enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="850cb-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="850cb-111">Una conexión de Experian ya ha sido configurada por un administrador *o* tiene permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="850cb-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="850cb-112">También necesita el identificador de usuario, el identificador de parte y el número de modelo para su cuenta de transporte seguro (ST) habilitada para SSH que haya creado Experian por usted.</span><span class="sxs-lookup"><span data-stu-id="850cb-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="850cb-113">Configurar el enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="850cb-113">Configure the enrichment</span></span>

1. <span data-ttu-id="850cb-114">Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="850cb-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="850cb-115">Seleccione **Enriquecer mis datos** en la ventana de Experian.</span><span class="sxs-lookup"><span data-stu-id="850cb-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="850cb-116">![Ventana de Experian](media/experian-tile.png "Ventana de Experian")</span><span class="sxs-lookup"><span data-stu-id="850cb-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="850cb-117">Seleccione una [conexión](connections.md) en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="850cb-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="850cb-118">Contacte con un administrador si no hay conexión disponible.</span><span class="sxs-lookup"><span data-stu-id="850cb-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="850cb-119">Si es un administrador, puede crear una conexión seleccionando **Agregar conexión** y eligiendo Experian en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="850cb-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="850cb-120">Seleccione **Conectarse a Experian** para confirmar la selección de la conexión.</span><span class="sxs-lookup"><span data-stu-id="850cb-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="850cb-121">Seleccione **Siguiente** y elija el **Conjunto de datos del cliente** que desea enriquecer con datos demográficos de Experian.</span><span class="sxs-lookup"><span data-stu-id="850cb-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="850cb-122">Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="850cb-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. <span data-ttu-id="850cb-124">Seleccione **Siguiente** y defina qué tipo de campos de sus perfiles unificados deben usarse para buscar datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="850cb-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="850cb-125">Es obligatorio al menos uno de los campos **Nombre y dirección**, **Teléfono**, o **Correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="850cb-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="850cb-126">Para una mayor precisión de correspondencia, se pueden agregar hasta otros dos campos.</span><span class="sxs-lookup"><span data-stu-id="850cb-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="850cb-127">Esta selección afectará a los campos de asignación a los que tiene acceso en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="850cb-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="850cb-128">Más atributos de identificadores clave enviados a Experian probablemente produzcan una tasa de coincidencia más alta.</span><span class="sxs-lookup"><span data-stu-id="850cb-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="850cb-129">Seleccione **Siguiente** para iniciar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="850cb-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="850cb-130">Defina qué campos de sus perfiles unificados deben usarse para buscar datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="850cb-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="850cb-131">Los campos obligatorios están marcados.</span><span class="sxs-lookup"><span data-stu-id="850cb-131">Required fields are marked.</span></span>

1. <span data-ttu-id="850cb-132">Proporcione un nombre para el enriquecimiento y un nombre para la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="850cb-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="850cb-133">Seleccione **Guardar enriquecimiento** después de revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="850cb-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="850cb-134">Configurar la conexión para Experian</span><span class="sxs-lookup"><span data-stu-id="850cb-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="850cb-135">Debe ser un administrador para configurar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="850cb-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="850cb-136">Seleccione **Agregar conexión** cuando configure un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Experian.</span><span class="sxs-lookup"><span data-stu-id="850cb-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="850cb-137">Seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="850cb-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="850cb-138">Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.</span><span class="sxs-lookup"><span data-stu-id="850cb-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="850cb-139">Ingrese un identificador de usuario válido, un identificador de parte y un número de modelo para su cuenta de transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="850cb-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="850cb-140">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="850cb-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="850cb-141">Seleccione **Verificar** para validar la configuración.</span><span class="sxs-lookup"><span data-stu-id="850cb-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="850cb-142">Después de completar la verificación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="850cb-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel de configuración de conexión de Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="850cb-144">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="850cb-144">Enrichment results</span></span>

<span data-ttu-id="850cb-145">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="850cb-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="850cb-146">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="850cb-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="850cb-147">El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y de los procesos de enriquecimiento configurados para su cuenta por Experian.</span><span class="sxs-lookup"><span data-stu-id="850cb-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="850cb-148">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="850cb-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="850cb-149">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="850cb-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="850cb-150">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="850cb-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="850cb-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="850cb-151">Next steps</span></span>

<span data-ttu-id="850cb-152">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="850cb-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="850cb-153">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="850cb-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="850cb-154">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="850cb-154">Data privacy and compliance</span></span>

<span data-ttu-id="850cb-155">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="850cb-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="850cb-156">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Experian cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="850cb-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="850cb-157">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="850cb-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="850cb-158">Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="850cb-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
