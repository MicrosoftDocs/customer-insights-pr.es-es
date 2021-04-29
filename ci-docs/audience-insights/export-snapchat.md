---
title: Exportar datos de Customer Insights a Snapchat
description: Aprenda a configurar la conexión y a exportar a Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760640"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="58014-103">Exportar listas de segmentos a Snapchat (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="58014-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="58014-104">Exporte segmentos de perfiles de clientes unificados a Snapchat y utilícelos para actividades de publicidad.</span><span class="sxs-lookup"><span data-stu-id="58014-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="58014-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="58014-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="58014-106">Usted tiene una [cuenta comercial de Snapchat](https://business.snapchat.com/), una [cuenta de anuncios de Snapchat](https://ads.snapchat.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="58014-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="58014-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="58014-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="58014-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="58014-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="58014-109">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="58014-109">Known limitations</span></span>

- <span data-ttu-id="58014-110">La exportación a Snapchat está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="58014-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="58014-111">La exportación de hasta 1 millón de perfiles a Snapchat puede tardar hasta 15 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="58014-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="58014-112">Configurar conexión a Snapchat</span><span class="sxs-lookup"><span data-stu-id="58014-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="58014-113">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="58014-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="58014-114">Seleccione **Agregar conexión** y elija **Snapchat** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="58014-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="58014-115">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="58014-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="58014-116">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="58014-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="58014-117">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="58014-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="58014-118">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="58014-118">Choose who can use this connection.</span></span> <span data-ttu-id="58014-119">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="58014-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="58014-120">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="58014-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="58014-121">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="58014-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="58014-122">Seleccione **Conectar** para inicializar la conexión a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="58014-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="58014-123">Seleccione **Autenticar con Snapchat** y proporcione sus credenciales de administrador para Snapchat.</span><span class="sxs-lookup"><span data-stu-id="58014-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="58014-124">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="58014-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="58014-125">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="58014-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="58014-126">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="58014-126">Configure an export</span></span>

<span data-ttu-id="58014-127">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="58014-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="58014-128">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="58014-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="58014-129">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="58014-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="58014-130">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="58014-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="58014-131">En el campo **Conexión para exportación**, elija una conexión de la sección Snapchat.</span><span class="sxs-lookup"><span data-stu-id="58014-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="58014-132">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="58014-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="58014-133">Indique el [**identificador de audiencia de Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="58014-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="58014-134">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="58014-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="58014-135">Es obligatorio exportar segmentos a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="58014-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="58014-136">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="58014-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="58014-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="58014-137">Select **Save**.</span></span>

<span data-ttu-id="58014-138">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="58014-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="58014-139">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="58014-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="58014-140">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="58014-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="58014-141">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="58014-141">Data privacy and compliance</span></span>

<span data-ttu-id="58014-142">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Snapchat, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="58014-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="58014-143">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Snapchat cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="58014-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="58014-144">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="58014-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="58014-145">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="58014-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
