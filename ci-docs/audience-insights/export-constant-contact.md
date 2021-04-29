---
title: Exportar datos de Customer Insights a Constant Contact
description: Aprenda a configurar la conexión y a exportar a Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760641"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="c02e4-103">Exportar listas de segmentos a Constant Contact (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c02e4-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="c02e4-104">Exporte segmentos de perfiles de clientes unificados a Constant Contact y utilícelos para actividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="c02e4-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c02e4-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="c02e4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="c02e4-106">Tiene una [cuenta de Constant Contact](https://www.constantcontact.com/account-home) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c02e4-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c02e4-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="c02e4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c02e4-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c02e4-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c02e4-109">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="c02e4-109">Known limitations</span></span>

- <span data-ttu-id="c02e4-110">Puede exportar hasta 1 millón de perfiles por exportación a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c02e4-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="c02e4-111">La exportación a Constant Contact está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="c02e4-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="c02e4-112">La exportación de hasta 1 millón de perfiles a Constant Contact puede tardar hasta 1 hora en completarse.</span><span class="sxs-lookup"><span data-stu-id="c02e4-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="c02e4-113">La cantidad de perfiles que puede exportar a Constant Contact depende y está limitada en su contrato con Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c02e4-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="c02e4-114">Configurar la conexión a Constant Contact</span><span class="sxs-lookup"><span data-stu-id="c02e4-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="c02e4-115">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="c02e4-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c02e4-116">Seleccione **Agregar conexión** y elija **Constant Contact** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="c02e4-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="c02e4-117">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="c02e4-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c02e4-118">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c02e4-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c02e4-119">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="c02e4-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c02e4-120">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c02e4-120">Choose who can use this connection.</span></span> <span data-ttu-id="c02e4-121">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="c02e4-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c02e4-122">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c02e4-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c02e4-123">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="c02e4-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c02e4-124">Seleccione **Conectar** para inicializar la conexión a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c02e4-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="c02e4-125">Seleccione **Autenticar con AdRoll** y proporcione sus credenciales de administrador para Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c02e4-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="c02e4-126">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c02e4-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c02e4-127">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="c02e4-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c02e4-128">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="c02e4-128">Configure an export</span></span>

<span data-ttu-id="c02e4-129">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="c02e4-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c02e4-130">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c02e4-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c02e4-131">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="c02e4-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c02e4-132">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="c02e4-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c02e4-133">En el campo **Conexión para exportación**, elija una conexión en la sección Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c02e4-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="c02e4-134">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="c02e4-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c02e4-135">Escriba su [**identificador de la lista de Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="c02e4-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="c02e4-136">Abra una lista en Constant Contact para encontrar el identificador de la lista en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c02e4-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="c02e4-137">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="c02e4-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c02e4-138">Es obligatorio exportar segmentos a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c02e4-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="c02e4-139">Opcionalmente, puede exporta Nombre de pila y Apellido como campos adicionales para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="c02e4-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="c02e4-140">Seleccione **Agregar atributo** para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="c02e4-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c02e4-141">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="c02e4-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="c02e4-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c02e4-142">Select **Save**.</span></span>

<span data-ttu-id="c02e4-143">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c02e4-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c02e4-144">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c02e4-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c02e4-145">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c02e4-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c02e4-146">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="c02e4-146">Data privacy and compliance</span></span>

<span data-ttu-id="c02e4-147">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Constant Contact, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="c02e4-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c02e4-148">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Constant Contact cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="c02e4-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c02e4-149">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c02e4-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c02e4-150">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="c02e4-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
