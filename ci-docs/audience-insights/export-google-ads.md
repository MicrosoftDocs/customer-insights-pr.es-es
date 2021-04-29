---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar la conexión y a exportar a Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759796"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="d6925-103">Exportar segmentos a Google Ads (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d6925-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="d6925-104">Exporte segmentos de perfiles de clientes unificados a la lista de público de Google Ads y utilícelos para anunciar en Búsqueda de Google, Gmail, YouTube y la Red de visualización de Google.</span><span class="sxs-lookup"><span data-stu-id="d6925-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d6925-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="d6925-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="d6925-106">Tiene una [cuenta de Google Ads](https://ads.google.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d6925-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d6925-107">Tiene un [símbolo (token) de desarrollador de Google Ads aprobado](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="d6925-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="d6925-108">Cumple los requisitos de la [Directiva de asignación de clientes](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="d6925-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="d6925-109">Cumple los requisitos de los [tamaños de listas de marketing](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="d6925-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="d6925-110">Hay públicos existentes en Google Ads y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d6925-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="d6925-111">Para más información, consulte [Audiencias de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="d6925-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="d6925-112">Ha [configurado los segmentos](segments.md)</span><span class="sxs-lookup"><span data-stu-id="d6925-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="d6925-113">Los perfiles de clientes unificados en los segmentos exportados contienen campos que representan una dirección de correo electrónico, un nombre de pila y los apellidos</span><span class="sxs-lookup"><span data-stu-id="d6925-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d6925-114">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="d6925-114">Known limitations</span></span>

- <span data-ttu-id="d6925-115">Hasta 1 millón de perfiles por exportación a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d6925-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="d6925-116">La exportación a Google Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="d6925-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="d6925-117">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 5 minutos debido a las limitaciones del lado del proveedor.</span><span class="sxs-lookup"><span data-stu-id="d6925-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="d6925-118">La coincidencia en Google Ads puede tardar hasta 48 horas.</span><span class="sxs-lookup"><span data-stu-id="d6925-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="d6925-119">Configurar conexión a Google Ads</span><span class="sxs-lookup"><span data-stu-id="d6925-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="d6925-120">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="d6925-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d6925-121">Seleccione **Agregar conexión** y elija **Google Ads** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="d6925-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="d6925-122">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="d6925-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d6925-123">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="d6925-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d6925-124">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="d6925-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d6925-125">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="d6925-125">Choose who can use this connection.</span></span> <span data-ttu-id="d6925-126">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="d6925-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d6925-127">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d6925-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d6925-128">Introduzca su **[Id. de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="d6925-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="d6925-129">Introduzca su **[Token de desarrollador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="d6925-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="d6925-130">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="d6925-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d6925-131">Seleccione **Autenticarse con Google Ads** y proporcione sus credenciales de Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d6925-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="d6925-132">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d6925-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d6925-133">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="d6925-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="d6925-134">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="d6925-134">Configure an export</span></span>

<span data-ttu-id="d6925-135">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="d6925-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d6925-136">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d6925-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d6925-137">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="d6925-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6925-138">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="d6925-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d6925-139">En el campo **Conexión para exportación**, elija una conexión de la sección Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d6925-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="d6925-140">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="d6925-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d6925-141">Introduzca su **[Id. de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** y seleccione **Conectar** para inicializar la conexión a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d6925-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="d6925-142">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="d6925-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d6925-143">Repita los mismos pasos para los campos **Nombre de pila** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="d6925-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="d6925-144">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="d6925-144">Select the segments you want to export.</span></span> <span data-ttu-id="d6925-145">Puede exportar hasta 1 millón de perfiles de clientes en total a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="d6925-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="d6925-146">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="d6925-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d6925-147">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d6925-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d6925-148">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d6925-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d6925-149">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="d6925-149">Data privacy and compliance</span></span>

<span data-ttu-id="d6925-150">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="d6925-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d6925-151">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Google Ads cumplan con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="d6925-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d6925-152">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d6925-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d6925-153">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="d6925-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
