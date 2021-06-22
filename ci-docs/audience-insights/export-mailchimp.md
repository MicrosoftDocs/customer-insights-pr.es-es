---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar la conexión y a exportar a Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124248"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="04270-103">Exportar segmentos a Mailchimp (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="04270-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="04270-104">Exporte segmentos de perfiles de clientes unificados a Mailchimp para crear boletines y campañas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04270-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="04270-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="04270-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="04270-106">Tiene una [cuenta de Mailchimp](https://mailchimp.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="04270-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="04270-107">Hay públicos existentes en Mailchimp y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="04270-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="04270-108">Para más información, consulte [Audiencias de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="04270-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="04270-109">Ha [configurado los segmentos](segments.md)</span><span class="sxs-lookup"><span data-stu-id="04270-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="04270-110">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="04270-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="04270-111">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="04270-111">Known limitations</span></span>

- <span data-ttu-id="04270-112">Hasta 1 millón de perfiles por exportación a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04270-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="04270-113">La exportación a Mailchimp está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="04270-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="04270-114">La exportación de segmentos con un millón de perfiles puede tardar hasta tres horas.</span><span class="sxs-lookup"><span data-stu-id="04270-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="04270-115">La cantidad de perfiles que puede exportar a Mailchimp depende y está limitada a su contrato con Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04270-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="04270-116">Configurar conexión a Mailchimp</span><span class="sxs-lookup"><span data-stu-id="04270-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="04270-117">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="04270-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="04270-118">Seleccione **Agregar conexión** y elija **Autopilot** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="04270-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="04270-119">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="04270-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="04270-120">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="04270-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="04270-121">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="04270-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="04270-122">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="04270-122">Choose who can use this connection.</span></span> <span data-ttu-id="04270-123">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="04270-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="04270-124">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="04270-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="04270-125">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="04270-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="04270-126">Seleccione **Conectar** para inicializar la conexión a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04270-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="04270-127">Seleccione **Autenticarse con Mailchimp** y proporcione sus credenciales de Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04270-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="04270-128">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="04270-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="04270-129">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="04270-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="04270-130">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="04270-130">Configure the connector</span></span>

<span data-ttu-id="04270-131">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="04270-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="04270-132">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="04270-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="04270-133">Vaya a **Datos**> **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="04270-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="04270-134">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="04270-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="04270-135">En el campo **Conexión para exportación**, elija una conexión de la sección Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04270-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="04270-136">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="04270-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="04270-137">Escriba su **[identificador de audiencia de Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="04270-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="04270-138">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="04270-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="04270-139">Opcionalmente, puede exportar el **Nombre de pila** y el **Apellido** para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="04270-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="04270-140">Seleccione **Agregar atributo** para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="04270-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="04270-141">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="04270-141">Select the segments you want to export.</span></span> <span data-ttu-id="04270-142">Puede exportar hasta 1 millón de perfiles de clientes en total a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="04270-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="04270-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="04270-143">Select **Save**.</span></span>

<span data-ttu-id="04270-144">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="04270-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="04270-145">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="04270-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="04270-146">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="04270-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="04270-147">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="04270-147">Data privacy and compliance</span></span>

<span data-ttu-id="04270-148">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="04270-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="04270-149">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Mailchimp cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="04270-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="04270-150">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="04270-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="04270-151">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="04270-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
