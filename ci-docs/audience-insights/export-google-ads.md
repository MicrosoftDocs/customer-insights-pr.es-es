---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar la conexión a Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268983"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="28ef9-103">Conector para Google Ads (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="28ef9-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="28ef9-104">Exporte segmentos de perfiles de clientes unificados a la lista de público de Google Ads y utilícelos para anunciar en Búsqueda de Google, Gmail, YouTube y la Red de visualización de Google.</span><span class="sxs-lookup"><span data-stu-id="28ef9-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="28ef9-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="28ef9-105">Prerequisites</span></span>

-   <span data-ttu-id="28ef9-106">Tiene una [cuenta de Google Ads](https://ads.google.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="28ef9-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="28ef9-107">Hay públicos existentes en Google Ads y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="28ef9-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="28ef9-108">Para más información, consulte [Audiencias de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="28ef9-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="28ef9-109">Ha [configurado los segmentos](segments.md)</span><span class="sxs-lookup"><span data-stu-id="28ef9-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="28ef9-110">Los perfiles de clientes unificados en los segmentos exportados contienen campos que representan una dirección de correo electrónico, un nombre de pila y los apellidos</span><span class="sxs-lookup"><span data-stu-id="28ef9-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="28ef9-111">Conectar a Google Ads</span><span class="sxs-lookup"><span data-stu-id="28ef9-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="28ef9-112">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="28ef9-113">En **Google Ads**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="28ef9-114">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="28ef9-115">Introduzca su **[Id. de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="28ef9-116">Introduzca su **[Token de desarrollador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="28ef9-117">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="28ef9-118">Introduzca su **[Id. de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** y seleccione **Conectar** para inicializar la conexión a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="28ef9-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="28ef9-119">Seleccione **Autenticarse con Google Ads** y proporcione sus credenciales de Google Ads.</span><span class="sxs-lookup"><span data-stu-id="28ef9-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="28ef9-120">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="28ef9-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportar captura de pantalla para conexión de Google Ads":::

1. <span data-ttu-id="28ef9-122">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="28ef9-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="28ef9-123">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="28ef9-123">Configure the connector</span></span>

1. <span data-ttu-id="28ef9-124">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="28ef9-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="28ef9-125">Repita los mismos pasos para los campos **Nombre de pila** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="28ef9-126">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="28ef9-126">Select the segments you want to export.</span></span> <span data-ttu-id="28ef9-127">Puede exportar hasta 1 millón de perfiles de clientes en total a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="28ef9-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="28ef9-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28ef9-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="28ef9-129">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="28ef9-129">Export the data</span></span>

<span data-ttu-id="28ef9-130">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="28ef9-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="28ef9-131">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="28ef9-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="28ef9-132">En Google Ads, ahora puede encontrar sus segmentos en [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="28ef9-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="28ef9-133">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="28ef9-133">Known limitations</span></span>

- <span data-ttu-id="28ef9-134">Hasta 1 millón de perfiles por exportación a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="28ef9-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="28ef9-135">La exportación a Google Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="28ef9-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="28ef9-136">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 5 minutos debido a las limitaciones del lado del proveedor.</span><span class="sxs-lookup"><span data-stu-id="28ef9-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="28ef9-137">La coincidencia en Google Ads puede tardar hasta 48 horas.</span><span class="sxs-lookup"><span data-stu-id="28ef9-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="28ef9-138">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="28ef9-138">Data privacy and compliance</span></span>

<span data-ttu-id="28ef9-139">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="28ef9-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="28ef9-140">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Google Ads cumplan con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="28ef9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="28ef9-141">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="28ef9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="28ef9-142">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="28ef9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]