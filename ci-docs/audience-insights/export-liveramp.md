---
title: 'Conector LiveRamp '
description: Aprenda a exportar datos a LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597578"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="5b1ec-103">Conector para LiveRamp&reg; (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="5b1ec-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="5b1ec-104">Active sus datos en LiveRamp para conectarse a más de 500 plataformas en ecosistemas digitales, sociales y de televisión.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="5b1ec-105">Trabaje con sus datos en LiveRamp para orientar, suprimir y personalizar las campañas publicitarias.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b1ec-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5b1ec-106">Prerequisites</span></span>

- <span data-ttu-id="5b1ec-107">Necesita una suscripción a LiveRamp para usar este conector.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="5b1ec-108">Para obtener una suscripción, puede ponerse en [contacto con LiveRamp](https://liveramp.com/contact/) directamente.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="5b1ec-109">[Más información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="5b1ec-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="5b1ec-110">Conectarse a LiveRamp</span><span class="sxs-lookup"><span data-stu-id="5b1ec-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="5b1ec-111">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5b1ec-112">En el mosaico de **LiveRamp**, seleccione **Preparar**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="5b1ec-113">Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5b1ec-114">Especifique un **Nombre de usuario** y la **Contraseña** para su cuenta de FTP seguro (SFTP) de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="5b1ec-115">Estas credenciales pueden ser distintas de las credenciales de LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="5b1ec-116">Seleccione **Comprobar** para probar la conexión a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="5b1ec-117">Después de una comprobación correcta, proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="5b1ec-118">Seleccione **Siguiente** para configurar el conector de LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5b1ec-119">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="5b1ec-119">Configure the connector</span></span>

1. <span data-ttu-id="5b1ec-120">En el campo **Elegir su identificador clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar estos datos a LiveRamp para la resolución de identidad.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="5b1ec-121">Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="5b1ec-122">Seleccione **Agregar atributo** para asignar atributos adicionales que se enviarán a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="5b1ec-123">Es probable que el envío de más atributos de identificador clave a LiveRamp le proporcione una tasa de coincidencia más alta.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="5b1ec-124">Seleccione los segmentos que desea exportar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="5b1ec-125">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5b1ec-126">![Conector para LiveRamp con asignación de atributos](media/export-liveramp-segments.png "Conector para LiveRamp con asignación de atributos")</span><span class="sxs-lookup"><span data-stu-id="5b1ec-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5b1ec-127">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="5b1ec-127">Export the data</span></span>

<span data-ttu-id="5b1ec-128">Si se han completado todos los requisitos previos para la exportación, esta comenzará en breve.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="5b1ec-129">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5b1ec-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="5b1ec-130">Una vez que la exportación se ha completado correctamente, puede iniciar sesión en LiveRamp Onboarding para activar y distribuir sus datos.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5b1ec-131">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="5b1ec-131">Data privacy and compliance</span></span>

<span data-ttu-id="5b1ec-132">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Liveramp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5b1ec-133">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Liveramp cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5b1ec-134">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5b1ec-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5b1ec-135">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]