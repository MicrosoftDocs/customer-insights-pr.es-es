---
title: Exportar datos de Customer Insights a AdRoll
description: Aprenda a configurar la conexión y a exportar a AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895980"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="2a7bc-103">Exportar listas de segmentos a AdRoll (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="2a7bc-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="2a7bc-104">Exporte segmentos de perfiles de clientes unificados a AdRoll y utilícelos para publicidad.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2a7bc-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="2a7bc-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2a7bc-106">Tiene una [cuenta de AdRoll](https://www.adroll.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2a7bc-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2a7bc-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2a7bc-109">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="2a7bc-109">Known limitations</span></span>

- <span data-ttu-id="2a7bc-110">Puede exportar hasta 250 000 perfiles de clientes a AdRoll por exportación.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="2a7bc-111">No puede exportar segmentos con menos de 100 perfiles a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="2a7bc-112">La exportación a AdRoll está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="2a7bc-113">La exportación de hasta 250 000 perfiles a AdRoll puede tardar hasta 10 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="2a7bc-114">La cantidad de perfiles que puede exportar a AdRoll depende y está limitada a su contrato con AdRoll.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="2a7bc-115">Configurar la conexión a AdRoll</span><span class="sxs-lookup"><span data-stu-id="2a7bc-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="2a7bc-116">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2a7bc-117">Seleccione **Agregar conexión** y elija **AdRoll** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="2a7bc-118">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2a7bc-119">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2a7bc-120">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2a7bc-121">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-121">Choose who can use this connection.</span></span> <span data-ttu-id="2a7bc-122">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2a7bc-123">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2a7bc-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2a7bc-124">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2a7bc-125">Seleccione **Conectar** para inicializar la conexión a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="2a7bc-126">Seleccione **Autenticarse con AdRoll** y proporcione sus credenciales de administrador para AdRoll.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="2a7bc-127">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2a7bc-128">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2a7bc-129">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="2a7bc-129">Configure an export</span></span>

<span data-ttu-id="2a7bc-130">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2a7bc-131">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2a7bc-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2a7bc-132">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2a7bc-133">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2a7bc-134">En el campo **Conexión para exportación**, elija una conexión de la sección AdRoll.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="2a7bc-135">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2a7bc-136">Indique su **identificador de anunciante de AdRoll**. Para más información, vea [Perfiles de anunciantes de AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="2a7bc-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="2a7bc-137">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2a7bc-138">Es obligatorio para exportar segmentos a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="2a7bc-139">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-139">Select the segments you want to export.</span></span> <span data-ttu-id="2a7bc-140">Seleccione un segmento con al menos 100 miembros.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="2a7bc-141">No puede exportar segmentos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-141">You can't export smaller segments.</span></span> <span data-ttu-id="2a7bc-142">Además, el tamaño máximo de un segmento para exportar es de 250 000 miembros por exportación.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="2a7bc-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-143">Select **Save**.</span></span>

<span data-ttu-id="2a7bc-144">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2a7bc-145">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2a7bc-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2a7bc-146">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2a7bc-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2a7bc-147">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="2a7bc-147">Data privacy and compliance</span></span>

<span data-ttu-id="2a7bc-148">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a AdRoll, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2a7bc-149">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que AdRoll cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2a7bc-150">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2a7bc-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2a7bc-151">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="2a7bc-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
