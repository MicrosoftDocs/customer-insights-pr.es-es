---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar la conexión a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598222"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="98294-103">Conector para Mailchimp (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="98294-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="98294-104">Exporte segmentos de perfiles de clientes unificados a Mailchimp para crear boletines y campañas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98294-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98294-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="98294-105">Prerequisites</span></span>

-   <span data-ttu-id="98294-106">Tiene una [cuenta de Mailchimp](https://mailchimp.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="98294-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="98294-107">Hay públicos existentes en Mailchimp y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="98294-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="98294-108">Para más información, consulte [Audiencias de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="98294-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="98294-109">Ha [configurado los segmentos](segments.md)</span><span class="sxs-lookup"><span data-stu-id="98294-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="98294-110">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="98294-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="98294-111">Conectarse a Mailchimp</span><span class="sxs-lookup"><span data-stu-id="98294-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="98294-112">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="98294-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="98294-113">En **Mailchimp**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="98294-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="98294-114">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="98294-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="98294-115">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="98294-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="98294-116">Introduzca su **[Id. de público de Mailchimp](https://mailchimp.com/help/find-audience-id/)** y seleccione **Conectar** para inicializar la conexión a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="98294-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="98294-117">Seleccione **Autenticarse con Mailchimp** y proporcione sus credenciales de Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="98294-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="98294-118">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98294-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportar la captura de pantalla para conexión de Mailchimp":::

1. <span data-ttu-id="98294-120">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="98294-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="98294-121">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="98294-121">Configure the connector</span></span>

1. <span data-ttu-id="98294-122">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="98294-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="98294-123">Opcionalmente, puede exporta **Nombre de pila** y **Apellido** como campos adicionales para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="98294-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="98294-124">Seleccione **Agregar atributo** para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="98294-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="98294-125">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="98294-125">Select the segments you want to export.</span></span> <span data-ttu-id="98294-126">Puede exportar hasta 1 millón de perfiles de clientes en total a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="98294-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Seleccionar campos y segmentos para exportar a Mailchimp":::

1. <span data-ttu-id="98294-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98294-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="98294-129">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="98294-129">Export the data</span></span>

<span data-ttu-id="98294-130">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="98294-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="98294-131">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="98294-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="98294-132">En Mailchimp, ahora puede encontrar sus segmentos en [Públicos de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="98294-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="98294-133">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="98294-133">Known limitations</span></span>

- <span data-ttu-id="98294-134">Hasta 1 millón de perfiles por exportación a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="98294-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="98294-135">La exportación a Mailchimp está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="98294-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="98294-136">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta tres horas, debido a las limitaciones del proveedor.</span><span class="sxs-lookup"><span data-stu-id="98294-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="98294-137">La cantidad de perfiles que puede exportar a Mailchimp depende y está limitada a su contrato con Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="98294-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="98294-138">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="98294-138">Data privacy and compliance</span></span>

<span data-ttu-id="98294-139">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="98294-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="98294-140">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Mailchimp cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="98294-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="98294-141">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="98294-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="98294-142">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="98294-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]