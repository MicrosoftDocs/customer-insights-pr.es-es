---
title: Exportar datos de Customer Insights a SendGrid
description: Aprenda a configurar la conexión a SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268753"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="a16d1-103">Conector para SendGrid (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a16d1-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="a16d1-104">Exporte segmentos de perfiles de clientes unificados a las listas de contactos de SendGrid y utilícelos para campañas y marketing por correo electrónico en SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a16d1-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a16d1-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a16d1-105">Prerequisites</span></span>

-   <span data-ttu-id="a16d1-106">Tiene una [cuenta de SendGrid](https://sendgrid.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a16d1-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a16d1-107">Hay listas de contactos existentes en SendGrid y los identificadores correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a16d1-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="a16d1-108">Para más información, consulte [SendGrid: Administrar contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="a16d1-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="a16d1-109">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="a16d1-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a16d1-110">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a16d1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="a16d1-111">Conectarse a SendGrid</span><span class="sxs-lookup"><span data-stu-id="a16d1-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="a16d1-112">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="a16d1-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a16d1-113">En **SendGrid**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="a16d1-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="a16d1-114">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="a16d1-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Panel de configuración de exportación de SendGrid.":::

1. <span data-ttu-id="a16d1-116">Especifique su **Clave API de SendGrid** [Clave API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="a16d1-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="a16d1-117">Especifique su **[identificador de lista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="a16d1-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="a16d1-118">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="a16d1-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a16d1-119">Seleccione **Conectar** para inicializar la conexión a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a16d1-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="a16d1-120">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a16d1-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a16d1-121">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="a16d1-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a16d1-122">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="a16d1-122">Configure the connector</span></span>

1. <span data-ttu-id="a16d1-123">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="a16d1-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a16d1-124">Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **País o región**, **Provincia**, **Ciudad** y **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="a16d1-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="a16d1-125">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="a16d1-125">Select the segments you want to export.</span></span> <span data-ttu-id="a16d1-126">Recomendamos encarecidamente **no exportar más de 100 000 perfiles de clientes en total** a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a16d1-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="a16d1-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a16d1-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a16d1-128">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="a16d1-128">Export the data</span></span>

<span data-ttu-id="a16d1-129">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a16d1-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a16d1-130">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a16d1-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a16d1-131">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="a16d1-131">Known limitations</span></span>

- <span data-ttu-id="a16d1-132">Hasta 100 000 perfiles en total para SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a16d1-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="a16d1-133">La exportación a SendGrid está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="a16d1-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="a16d1-134">La exportación de hasta 100 000 perfiles a SendGrid puede tardar unas pocas horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="a16d1-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="a16d1-135">La cantidad de perfiles que puede exportar a SendGrid depende y está limitada a su contrato con SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a16d1-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a16d1-136">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="a16d1-136">Data privacy and compliance</span></span>

<span data-ttu-id="a16d1-137">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a SendGrid, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="a16d1-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a16d1-138">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que SendGrid cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="a16d1-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a16d1-139">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a16d1-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a16d1-140">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a16d1-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]