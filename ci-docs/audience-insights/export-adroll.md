---
title: Exportar datos de Customer Insights a AdRoll
description: Aprenda a configurar la conexión a AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697095"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="fb1e3-103">Conector para AdRoll (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="fb1e3-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="fb1e3-104">Exporte segmentos de perfiles de clientes unificados a AdRoll y utilícelos para publicidad.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="fb1e3-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fb1e3-105">Prerequisites</span></span>

-   <span data-ttu-id="fb1e3-106">Tiene una [cuenta de AdRoll](https://www.adroll.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fb1e3-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fb1e3-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="fb1e3-109">Conectarse a AdRoll</span><span class="sxs-lookup"><span data-stu-id="fb1e3-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="fb1e3-110">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fb1e3-111">En **AdRoll**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="fb1e3-112">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panel de configuración para la conexión de AdRoll.":::

1. <span data-ttu-id="fb1e3-114">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fb1e3-115">Seleccione **Conectar** para inicializar la conexión a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="fb1e3-116">Seleccione **Autenticarse con AdRoll** y proporcione sus credenciales de administrador para AdRoll.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="fb1e3-117">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fb1e3-118">Introduzca su **Identificador de anunciante de AdRoll** [AdRoll anunciable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="fb1e3-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="fb1e3-119">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="fb1e3-120">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="fb1e3-120">Configure the connector</span></span>

1. <span data-ttu-id="fb1e3-121">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fb1e3-122">Es obligatorio para exportar segmentos a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="fb1e3-123">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-123">Select the segments you want to export.</span></span> <span data-ttu-id="fb1e3-124">Seleccione un segmento con al menos 100 miembros.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="fb1e3-125">No puede exportar segmentos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-125">You can't export smaller segments.</span></span> <span data-ttu-id="fb1e3-126">Además, el tamaño máximo de un segmento para exportar es de 250 000 miembros por exportación.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="fb1e3-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fb1e3-128">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="fb1e3-128">Export the data</span></span>

<span data-ttu-id="fb1e3-129">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fb1e3-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fb1e3-130">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fb1e3-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fb1e3-131">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="fb1e3-131">Known limitations</span></span>

- <span data-ttu-id="fb1e3-132">Puede exportar hasta 250 000 perfiles de clientes a AdRoll por exportación.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="fb1e3-133">No puede exportar segmentos con menos de 100 perfiles a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="fb1e3-134">La exportación a AdRoll está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="fb1e3-135">La exportación de hasta 250 000 perfiles a AdRoll puede tardar hasta 10 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="fb1e3-136">La cantidad de perfiles que puede exportar a AdRoll depende y está limitada a su contrato con AdRoll.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fb1e3-137">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="fb1e3-137">Data privacy and compliance</span></span>

<span data-ttu-id="fb1e3-138">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a AdRoll, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fb1e3-139">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que AdRoll cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fb1e3-140">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fb1e3-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="fb1e3-141">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="fb1e3-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
