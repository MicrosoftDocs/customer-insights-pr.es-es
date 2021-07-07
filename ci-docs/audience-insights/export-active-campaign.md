---
title: Exportar datos de Customer Insights a ActiveCampaign
description: Aprenda a configurar la conexión y exportar a ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314680"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="b0ed8-103">Exportar segmentos a ActiveCampaign (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b0ed8-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="b0ed8-104">Exporte segmentos de perfiles de clientes unificados a ActiveCampaign y utilícelos para actividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0ed8-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b0ed8-105">Prerequisites</span></span>

-   <span data-ttu-id="b0ed8-106">Tiene una [cuenta de ActiveCampaign](https://www.activecampaign.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b0ed8-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b0ed8-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo con una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b0ed8-109">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="b0ed8-109">Known limitations</span></span>

- <span data-ttu-id="b0ed8-110">Puede exportar hasta 1 millón de perfiles por exportación a ActiveCampaign y puede tardar hasta 90 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="b0ed8-111">La exportación a ActiveCampaign está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="b0ed8-112">La cantidad de perfiles que puede exportar a ActiveCampaign depende de su contrato con ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="b0ed8-113">Configurar la conexión a ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="b0ed8-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="b0ed8-114">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b0ed8-115">Seleccione **Agregar conexión** y elija **ActiveCampaign** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="b0ed8-116">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b0ed8-117">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b0ed8-118">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b0ed8-119">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-119">Choose who can use this connection.</span></span> <span data-ttu-id="b0ed8-120">De forma predeterminada, solo son administradores.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-120">By default, it's only administrators.</span></span> <span data-ttu-id="b0ed8-121">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b0ed8-122">Especifique su [cave de API ActiveCampaign y nombre de host del punto de conexión de REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="b0ed8-123">El nombre de host del punto de conexión REST es solo el nombre de host, sin https://.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="b0ed8-124">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b0ed8-125">Seleccione **Conectar** para inicializar la conexión a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="b0ed8-126">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b0ed8-127">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b0ed8-128">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="b0ed8-128">Configure an export</span></span>

<span data-ttu-id="b0ed8-129">Puede configurar una exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="b0ed8-130">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b0ed8-131">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b0ed8-132">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b0ed8-133">En el campo **Conexión para exportación**, elija una conexión de la sección ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="b0ed8-134">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b0ed8-135">Indique su [**Id. de lista de ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="b0ed8-136">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b0ed8-137">Es obligatorio exportar segmentos a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="b0ed8-138">Opcionalmente, puede exportar Nombre de pila, Apellido, y Teléfono para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="b0ed8-139">Seleccione Agregar atributo para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="b0ed8-140">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-140">Select **Save**.</span></span>

<span data-ttu-id="b0ed8-141">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b0ed8-142">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b0ed8-143">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b0ed8-144">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="b0ed8-144">Data privacy and compliance</span></span>

<span data-ttu-id="b0ed8-145">Cuando habilite Dynamics 365 Customer Insights para transmitir datos a ActiveCampaign, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b0ed8-146">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que ActiveCampaign cumple las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b0ed8-147">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b0ed8-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b0ed8-148">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b0ed8-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
