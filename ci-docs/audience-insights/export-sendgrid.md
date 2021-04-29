---
title: Exportar datos de Customer Insights a SendGrid
description: Aprenda a configurar la conexión y a exportar a SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759786"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="7e11a-103">Exportar segmentos a SendGrid (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="7e11a-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="7e11a-104">Exporte segmentos de perfiles de clientes unificados a las listas de contactos de SendGrid y utilícelos para campañas y marketing por correo electrónico en SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7e11a-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7e11a-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="7e11a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7e11a-106">Tiene una [cuenta de SendGrid](https://sendgrid.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7e11a-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7e11a-107">Hay listas de contactos existentes en SendGrid y los identificadores correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7e11a-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="7e11a-108">Para más información, consulte [SendGrid: Administrar contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="7e11a-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="7e11a-109">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="7e11a-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7e11a-110">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e11a-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7e11a-111">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="7e11a-111">Known limitations</span></span>

- <span data-ttu-id="7e11a-112">Hasta 100 000 perfiles en total para SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7e11a-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="7e11a-113">La exportación a SendGrid está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="7e11a-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="7e11a-114">La exportación de hasta 100 000 perfiles a SendGrid puede tardar unas pocas horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="7e11a-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="7e11a-115">La cantidad de perfiles que puede exportar a SendGrid depende y está limitada a su contrato con SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7e11a-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="7e11a-116">Configurar conexión a SendGrid</span><span class="sxs-lookup"><span data-stu-id="7e11a-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="7e11a-117">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7e11a-118">Seleccione **Agregar conexión** y elija **SendGrid** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="7e11a-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="7e11a-119">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7e11a-120">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="7e11a-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7e11a-121">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="7e11a-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7e11a-122">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="7e11a-122">Choose who can use this connection.</span></span> <span data-ttu-id="7e11a-123">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="7e11a-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7e11a-124">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7e11a-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7e11a-125">Especifique su **Clave API de SendGrid** [Clave API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="7e11a-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="7e11a-126">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7e11a-127">Seleccione **Conectar** para inicializar la conexión a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7e11a-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="7e11a-128">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7e11a-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7e11a-129">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="7e11a-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7e11a-130">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="7e11a-130">Configure an export</span></span>

<span data-ttu-id="7e11a-131">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="7e11a-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7e11a-132">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7e11a-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7e11a-133">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7e11a-134">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7e11a-135">En el campo **Conexión para exportación**, elija una conexión de la sección SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7e11a-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="7e11a-136">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="7e11a-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7e11a-137">Especifique su **[identificador de lista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="7e11a-138">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="7e11a-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7e11a-139">Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **País o región**, **Provincia**, **Ciudad** y **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="7e11a-140">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="7e11a-140">Select the segments you want to export.</span></span> <span data-ttu-id="7e11a-141">Recomendamos encarecidamente **no exportar más de 100 000 perfiles de clientes en total** a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7e11a-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="7e11a-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e11a-142">Select **Save**.</span></span>

<span data-ttu-id="7e11a-143">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="7e11a-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7e11a-144">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7e11a-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7e11a-145">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7e11a-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7e11a-146">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="7e11a-146">Data privacy and compliance</span></span>

<span data-ttu-id="7e11a-147">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a SendGrid, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="7e11a-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7e11a-148">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que SendGrid cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="7e11a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7e11a-149">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7e11a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7e11a-150">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="7e11a-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]