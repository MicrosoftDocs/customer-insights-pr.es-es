---
title: Exportar datos de Customer Insights a LinkedIn Ads
description: Aprenda a configurar la conexión y a exportar a LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124557"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="30fd5-103">Exportar segmentos a LinkedIn Ads (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="30fd5-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="30fd5-104">Exporte segmentos de perfiles de clientes unificados a LinkedIn Ads para crear Matched Audiences.</span><span class="sxs-lookup"><span data-stu-id="30fd5-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="30fd5-105">Utilice las Matched Audiences para la segmentación de empresas y la segmentación de contactos.</span><span class="sxs-lookup"><span data-stu-id="30fd5-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30fd5-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="30fd5-106">Prerequisites</span></span>

-   <span data-ttu-id="30fd5-107">Tiene una [cuenta de LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="30fd5-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="30fd5-108">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="30fd5-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="30fd5-109">Los perfiles de clientes en los segmentos exportados contienen un campo con una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="30fd5-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="30fd5-110">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="30fd5-110">Known limitations</span></span>

- <span data-ttu-id="30fd5-111">Puede exportar hasta 100 000 perfiles por exportación a LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="30fd5-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="30fd5-112">La exportación a LinkedIn Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="30fd5-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="30fd5-113">La exportación de hasta 100 000 perfiles a LinkedIn Ads puede tardar hasta 10 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="30fd5-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="30fd5-114">Configurar la conexión a LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="30fd5-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="30fd5-115">En Audience Insights, vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="30fd5-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="30fd5-116">Seleccione **Agregar conexión** y elija **LinkedIn Ads** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="30fd5-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="30fd5-117">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="30fd5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="30fd5-118">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="30fd5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="30fd5-119">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="30fd5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="30fd5-120">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="30fd5-120">Choose who can use this connection.</span></span> <span data-ttu-id="30fd5-121">Si no realiza ninguna acción, el valor predeterminado es Administradores.</span><span class="sxs-lookup"><span data-stu-id="30fd5-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="30fd5-122">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="30fd5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="30fd5-123">Proporcione su [Id. de cuenta de LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="30fd5-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="30fd5-124">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="30fd5-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="30fd5-125">Seleccione **Conectar** para inicializar la conexión a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="30fd5-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="30fd5-126">Seleccione **Autenticar con LinkedIn** y proporcione sus credenciales de administrador para LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="30fd5-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="30fd5-127">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="30fd5-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="30fd5-128">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="30fd5-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="30fd5-129">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="30fd5-129">Configure an export</span></span>

<span data-ttu-id="30fd5-130">Puede configurar una exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="30fd5-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="30fd5-131">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="30fd5-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="30fd5-132">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="30fd5-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="30fd5-133">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="30fd5-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="30fd5-134">En el campo **Conexión para exportación**, elija una conexión de la sección LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="30fd5-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="30fd5-135">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="30fd5-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="30fd5-136">Elija si desea exportar datos para hacer [segmentación de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [segmentación de la empresa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en Linkedin.</span><span class="sxs-lookup"><span data-stu-id="30fd5-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="30fd5-137">En la sección **Coincidencia de datos**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="30fd5-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="30fd5-138">Es obligatorio exportar segmentos a LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="30fd5-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="30fd5-139">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="30fd5-139">Select the segments you want to export.</span></span> <span data-ttu-id="30fd5-140">Las Matched Audiences en LinkedIn Campaign Manager se crearán automáticamente con el nombre de los segmentos que seleccionó para exportar.</span><span class="sxs-lookup"><span data-stu-id="30fd5-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="30fd5-141">Cada segmento dará como resultado una Matched Audience diferente.</span><span class="sxs-lookup"><span data-stu-id="30fd5-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="30fd5-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="30fd5-142">Select **Save**.</span></span>

<span data-ttu-id="30fd5-143">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="30fd5-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="30fd5-144">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="30fd5-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="30fd5-145">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="30fd5-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="30fd5-146">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="30fd5-146">Data privacy and compliance</span></span>

<span data-ttu-id="30fd5-147">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a LinkedIn Ads, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="30fd5-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="30fd5-148">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que LinkedIn Ads cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="30fd5-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="30fd5-149">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="30fd5-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="30fd5-150">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para detener el uso de esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="30fd5-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
