---
title: Exportar datos de Customer Insights a Autopilot
description: Aprenda a configurar la conexión a Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596152"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="67289-103">Conector para Autopilot (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="67289-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="67289-104">Exporte segmentos de perfiles de clientes unificados a Autopilot y utilícelos para marketing por correo electrónico en Autopilot.</span><span class="sxs-lookup"><span data-stu-id="67289-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="67289-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="67289-105">Prerequisites</span></span>

-   <span data-ttu-id="67289-106">Tiene una [cuenta de Autopilot](https://www.autopilothq.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="67289-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="67289-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="67289-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="67289-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="67289-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="67289-109">Conectar a Autopilot</span><span class="sxs-lookup"><span data-stu-id="67289-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="67289-110">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="67289-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="67289-111">En **Autopilot**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="67289-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="67289-112">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="67289-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Panel de configuración para la conexión de Autopilot.":::

1. <span data-ttu-id="67289-114">Especifique su **Clave de API de Autopilot** [Clave de API de Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="67289-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="67289-115">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="67289-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="67289-116">Seleccione **Conectar** para inicializar la conexión a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="67289-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="67289-117">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="67289-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="67289-118">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="67289-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="67289-119">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="67289-119">Configure the connector</span></span>

1. <span data-ttu-id="67289-120">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="67289-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="67289-121">Repita los mismos pasos para otros campos opcionales como **Nombre de pila** o **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="67289-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="67289-122">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="67289-122">Select the segments you want to export.</span></span> <span data-ttu-id="67289-123">Recomendamos encarecidamente **no exportar más de 100 000 perfiles de clientes en total** a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="67289-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="67289-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="67289-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="67289-125">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="67289-125">Export the data</span></span>

<span data-ttu-id="67289-126">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="67289-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="67289-127">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="67289-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="67289-128">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="67289-128">Known limitations</span></span>

- <span data-ttu-id="67289-129">Puede exportar hasta 100 000 perfiles de clientes a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="67289-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="67289-130">La exportación a Autopilot está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="67289-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="67289-131">La exportación de hasta 100 000 perfiles a Autopilot puede tardar unas pocas horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="67289-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="67289-132">La cantidad de perfiles que puede exportar a Autopilot depende y está limitada a su contrato con Autopilot.</span><span class="sxs-lookup"><span data-stu-id="67289-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="67289-133">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="67289-133">Data privacy and compliance</span></span>

<span data-ttu-id="67289-134">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Autopilot, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="67289-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="67289-135">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Autopilot cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="67289-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="67289-136">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="67289-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="67289-137">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="67289-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]