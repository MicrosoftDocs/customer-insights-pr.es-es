---
title: 'Conector LiveRamp '
description: Aprenda a configurar la conexión y a exportar a LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760348"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="76d34-103">Exportar segmentos a LiveRamp&reg; (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76d34-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="76d34-104">Active sus datos en LiveRamp para conectarse con más de 500 plataformas en ecosistemas digitales, sociales y de televisión.</span><span class="sxs-lookup"><span data-stu-id="76d34-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="76d34-105">Trabaje con sus datos en LiveRamp para orientar, suprimir y personalizar las campañas publicitarias.</span><span class="sxs-lookup"><span data-stu-id="76d34-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="76d34-106">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="76d34-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="76d34-107">Necesita una suscripción a LiveRamp para usar este conector.</span><span class="sxs-lookup"><span data-stu-id="76d34-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="76d34-108">Para obtener una suscripción, puede ponerse en [contacto con LiveRamp](https://liveramp.com/contact/) directamente.</span><span class="sxs-lookup"><span data-stu-id="76d34-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="76d34-109">[Más información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="76d34-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="76d34-110">Configurar conexión a LiveRamp</span><span class="sxs-lookup"><span data-stu-id="76d34-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="76d34-111">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="76d34-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="76d34-112">Seleccione **Agregar conexión** y elija **LiveRamp** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="76d34-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="76d34-113">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="76d34-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="76d34-114">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="76d34-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="76d34-115">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="76d34-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="76d34-116">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="76d34-116">Choose who can use this connection.</span></span> <span data-ttu-id="76d34-117">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="76d34-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="76d34-118">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="76d34-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="76d34-119">Especifique un **Nombre de usuario** y la **Contraseña** para su cuenta de FTP seguro (SFTP) de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="76d34-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="76d34-120">Estas credenciales pueden ser distintas de las credenciales de LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="76d34-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="76d34-121">Seleccione **Comprobar** para probar la conexión a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="76d34-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="76d34-122">Después de una comprobación correcta, proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="76d34-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="76d34-123">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="76d34-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="76d34-124">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="76d34-124">Configure an export</span></span>

<span data-ttu-id="76d34-125">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="76d34-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="76d34-126">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="76d34-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="76d34-127">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="76d34-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76d34-128">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="76d34-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="76d34-129">En el campo **Conexión para exportación**, elija una conexión de la sección LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="76d34-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="76d34-130">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="76d34-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="76d34-131">En el campo **Elegir su identificador clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar estos datos a LiveRamp para la resolución de identidad.</span><span class="sxs-lookup"><span data-stu-id="76d34-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="76d34-132">![Conector para LiveRamp con asignación de atributos](media/export-liveramp-segments.png "Conector para LiveRamp con asignación de atributos")</span><span class="sxs-lookup"><span data-stu-id="76d34-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="76d34-133">Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="76d34-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="76d34-134">Seleccione **Agregar atributo** para asignar más atributos para enviar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="76d34-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="76d34-135">Es probable que el envío de más atributos de identificador clave a LiveRamp le proporcione una tasa de coincidencia más alta.</span><span class="sxs-lookup"><span data-stu-id="76d34-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="76d34-136">Seleccione los segmentos que desea exportar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="76d34-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="76d34-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="76d34-137">Select **Save**.</span></span>

<span data-ttu-id="76d34-138">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="76d34-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="76d34-139">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="76d34-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="76d34-140">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="76d34-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="76d34-141">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="76d34-141">Data privacy and compliance</span></span>

<span data-ttu-id="76d34-142">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Liveramp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="76d34-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="76d34-143">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Liveramp cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="76d34-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="76d34-144">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="76d34-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="76d34-145">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="76d34-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
