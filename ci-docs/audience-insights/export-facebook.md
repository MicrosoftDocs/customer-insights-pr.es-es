---
title: Exportar datos de Customer Insights al Administrador de anuncios de Facebook
description: Aprenda a configurar la conexión al Administrador de anuncios de Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596704"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="5a614-103">Conector para Administrador de anuncios de Facebook (vista previa)</span><span class="sxs-lookup"><span data-stu-id="5a614-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="5a614-104">Exportar segmentos de perfiles de clientes unificados a Administrador de anuncios de Facebook para crear campañas en Facebook e Instagram.</span><span class="sxs-lookup"><span data-stu-id="5a614-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a614-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5a614-105">Prerequisites</span></span>

- <span data-ttu-id="5a614-106">Necesita tener una [**cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que incluya una [**cuenta de negocios de Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="5a614-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="5a614-107">Debe ser administrador en la [**Cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="5a614-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="5a614-108">Conectar a Administrador de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="5a614-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="5a614-109">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="5a614-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5a614-110">En **Administrador de anuncios de Facebook**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="5a614-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="5a614-111">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="5a614-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5a614-112">Seleccione **Continuar con Facebook** para iniciar sesión en su Cuenta de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="5a614-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="5a614-113">Autorizar el permiso **ads_management** después de autenticarse con Facebook.</span><span class="sxs-lookup"><span data-stu-id="5a614-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="5a614-114">Seleccione la **Cuenta de anuncios de Facebook** con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="5a614-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="5a614-115">Seleccione un **Audiencia personalizado existente** de la lista desplegable o cree una **Nueva audiencia personalizada**.</span><span class="sxs-lookup"><span data-stu-id="5a614-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="5a614-116">Para más información, vea [**Audiencias en Administrador de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="5a614-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="5a614-117">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="5a614-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5a614-118">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="5a614-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5a614-119">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="5a614-119">Configure the connector</span></span>

1. <span data-ttu-id="5a614-120">En **Elija su campo de identificador de clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar a Administrador de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="5a614-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="5a614-121">Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5a614-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="5a614-122">[SUGERENCIA] Las mejores posibilidades para que se produzca una coincidencia es seleccionar **Correo electrónico** como identificador clave</span><span class="sxs-lookup"><span data-stu-id="5a614-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="5a614-123">Agregar identificadores adicionales puede mejorar la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="5a614-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="5a614-124">Seleccione **Agregar atributo** para asignar atributos adicionales para enviar a Administrador de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="5a614-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="5a614-125">Los atributos de Administrador de anuncios de Facebook se asignan a los siguientes nombres descriptivos: **FN** = **Nombre**, **LN** = **Apellidos**, **FI** = **Primera inicial**, **PHONE** = **Teléfono**, **GEN** = **Género**, **DOB** = **Fecha de nacimiento**, **ST** = **Estado**, **CT** = **Ciudad**, **ZIP** = **Código postal**, **COUNTRY** = **País / Región**</span><span class="sxs-lookup"><span data-stu-id="5a614-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="5a614-126">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="5a614-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="5a614-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5a614-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5a614-128">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="5a614-128">Export the data</span></span>

<span data-ttu-id="5a614-129">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a614-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5a614-130">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a614-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5a614-131">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="5a614-131">Known limitations</span></span>

- <span data-ttu-id="5a614-132">Hasta 10 millones de perfiles de cliente por exportación al administrador de Facebook Ads</span><span class="sxs-lookup"><span data-stu-id="5a614-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="5a614-133">La exportación al administrador de Facebook Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="5a614-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="5a614-134">La exportación de segmentos con un total de 10 millón de perfiles puede tardar hasta 90 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="5a614-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a614-135">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="5a614-135">Data privacy and compliance</span></span>

<span data-ttu-id="5a614-136">Cuando habilita Dynamics 365 Customer Insights para transmitir datos al Administrador de anuncios de Facebook, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="5a614-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a614-137">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Facebook cumplan con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="5a614-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a614-138">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a614-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5a614-139">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="5a614-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]