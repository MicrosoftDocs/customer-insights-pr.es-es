---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar la conexión a DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269121"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="05e6f-103">Conector para DotDigital (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="05e6f-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="05e6f-104">Exporte segmentos de perfiles de clientes unificados a las libretas de direcciones de DotDigital y utilícelos para campañas, marketing por correo electrónico y para crear segmentos de clientes con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="05e6f-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="05e6f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="05e6f-105">Prerequisites</span></span>

-   <span data-ttu-id="05e6f-106">Tiene una [Cuenta de DotDigital](https://dotdigital.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="05e6f-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="05e6f-107">Hay libretas de direcciones existentes en DotDigital y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="05e6f-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="05e6f-108">El id. se puede encontrar en la URL cuando selecciona y abre una libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="05e6f-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="05e6f-109">Para más información, consulte [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="05e6f-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="05e6f-110">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="05e6f-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="05e6f-111">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="05e6f-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="05e6f-112">Conectarse a DotDigital</span><span class="sxs-lookup"><span data-stu-id="05e6f-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="05e6f-113">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="05e6f-114">En **DotDigital**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="05e6f-115">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Panel de configuración para la exportación de DotDigital.":::

1. <span data-ttu-id="05e6f-117">Introduzca su **nombre de usuario y contraseña de DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="05e6f-118">Introduzca su **[Id. de la libreta de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="05e6f-119">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="05e6f-120">Seleccione **Conectar** para inicializar la conexión a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="05e6f-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="05e6f-121">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="05e6f-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="05e6f-122">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="05e6f-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="05e6f-123">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="05e6f-123">Configure the connector</span></span>

1. <span data-ttu-id="05e6f-124">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="05e6f-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="05e6f-125">Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **Nombre completo**, **Género** y **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="05e6f-126">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="05e6f-126">Select the segments you want to export.</span></span> <span data-ttu-id="05e6f-127">Puede exportar hasta 1 millón de perfiles de clientes en total a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="05e6f-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="05e6f-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="05e6f-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="05e6f-129">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="05e6f-129">Export the data</span></span>

<span data-ttu-id="05e6f-130">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="05e6f-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="05e6f-131">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="05e6f-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="05e6f-132">En DotDigital, ahora puede encontrar sus segmentos en [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="05e6f-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="05e6f-133">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="05e6f-133">Known limitations</span></span>

- <span data-ttu-id="05e6f-134">Hasta 1 millón de perfiles por exportación a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="05e6f-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="05e6f-135">La exportación a DotDigital está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="05e6f-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="05e6f-136">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas, debido a las limitaciones del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05e6f-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="05e6f-137">La cantidad de perfiles que puede exportar a DotDigital depende y está limitada a su contrato con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="05e6f-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="05e6f-138">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="05e6f-138">Data privacy and compliance</span></span>

<span data-ttu-id="05e6f-139">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="05e6f-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="05e6f-140">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que DotDigital cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="05e6f-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="05e6f-141">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="05e6f-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="05e6f-142">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="05e6f-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]