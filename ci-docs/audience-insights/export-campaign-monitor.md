---
title: Exportar datos de Customer Insights a Campaign Monitor
description: Aprenda a configurar la conexión y a exportar a Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124202"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="eba9f-103">Exportar segmentos a Campaign Monitor (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="eba9f-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="eba9f-104">Exporte segmentos de perfiles de clientes unificados a Campaign Monitor y utilícelos para actividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="eba9f-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eba9f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="eba9f-105">Prerequisites</span></span>

-   <span data-ttu-id="eba9f-106">Tiene una [cuenta de Campaign Monitor](https://www.campaignmonitor.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="eba9f-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="eba9f-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="eba9f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="eba9f-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="eba9f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="eba9f-109">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="eba9f-109">Known limitations</span></span>

- <span data-ttu-id="eba9f-110">Puede exportar hasta 1 millón de perfiles por exportación a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="eba9f-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="eba9f-111">La exportación a Campaign Monitor está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="eba9f-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="eba9f-112">La exportación de hasta 1 millón de perfiles a Campaign Monitor puede tardar hasta 20 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="eba9f-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="eba9f-113">La cantidad de perfiles que puede exportar a Campaign Monitor depende y está limitada en su contrato con Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="eba9f-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="eba9f-114">Configurar una conexión a Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="eba9f-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="eba9f-115">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="eba9f-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="eba9f-116">Seleccione **Agregar conexión** y elija **Campaign Monitor** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="eba9f-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="eba9f-117">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="eba9f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="eba9f-118">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="eba9f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="eba9f-119">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="eba9f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="eba9f-120">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="eba9f-120">Choose who can use this connection.</span></span> <span data-ttu-id="eba9f-121">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="eba9f-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="eba9f-122">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="eba9f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="eba9f-123">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="eba9f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="eba9f-124">Seleccione **Conectar** para inicializar la conexión a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="eba9f-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="eba9f-125">Seleccione **Autenticar con Campaign Monitor** y proporcione sus credenciales de administrador para Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="eba9f-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="eba9f-126">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eba9f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="eba9f-127">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="eba9f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="eba9f-128">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="eba9f-128">Configure an export</span></span>

<span data-ttu-id="eba9f-129">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="eba9f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="eba9f-130">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="eba9f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="eba9f-131">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="eba9f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eba9f-132">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="eba9f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="eba9f-133">En el campo **Conexión para exportación**, elija una conexión en la sección Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="eba9f-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="eba9f-134">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="eba9f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="eba9f-135">Escriba su [**Identificador de Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="eba9f-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="eba9f-136">[Genere la clave API](https://www.campaignmonitor.com/api/getting-started/) en **Configuraciones de la cuenta** de Campaign Monitor primero para ver el identificador de la lista de API.</span><span class="sxs-lookup"><span data-stu-id="eba9f-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="eba9f-137">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="eba9f-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="eba9f-138">Es obligatorio exportar segmentos a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="eba9f-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="eba9f-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="eba9f-139">Select **Save**.</span></span>

<span data-ttu-id="eba9f-140">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="eba9f-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="eba9f-141">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eba9f-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="eba9f-142">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="eba9f-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eba9f-143">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="eba9f-143">Data privacy and compliance</span></span>

<span data-ttu-id="eba9f-144">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Campaign Monitor, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="eba9f-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eba9f-145">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Campaign Monitor cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="eba9f-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="eba9f-146">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="eba9f-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="eba9f-147">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="eba9f-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
