---
title: Exportar datos de Customer Insights a Microsoft Advertising
description: Aprenda a configurar la conexión y a exportar a Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124555"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="bb782-103">Exportar segmentos a Microsoft Advertising (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="bb782-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="bb782-104">Exporte segmentos de Customer Insights a Microsoft Advertising para crear audiencias de Customer Match.</span><span class="sxs-lookup"><span data-stu-id="bb782-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="bb782-105">Utilice estas audiencias para sus campañas publicitarias.</span><span class="sxs-lookup"><span data-stu-id="bb782-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb782-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bb782-106">Prerequisites</span></span>

-   <span data-ttu-id="bb782-107">Una [cuenta de Microsoft Advertising](https://ads.microsoft.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="bb782-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bb782-108">Ha aceptado las condiciones de uso de Customer Match.</span><span class="sxs-lookup"><span data-stu-id="bb782-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="bb782-109">[Segmentos configurados](segments.md) en información de público.</span><span class="sxs-lookup"><span data-stu-id="bb782-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bb782-110">Los perfiles de clientes unificados en los segmentos exportados contienen un campo con una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bb782-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bb782-111">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="bb782-111">Known limitations</span></span>

- <span data-ttu-id="bb782-112">Puede exportar hasta 500 000 perfiles por exportación a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="bb782-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="bb782-113">La exportación a Microsoft Advertising está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="bb782-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="bb782-114">La exportación de hasta 500 000 de perfiles a Microsoft Advertising puede tardar hasta 10 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="bb782-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="bb782-115">Configurar la conexión a Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="bb782-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="bb782-116">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="bb782-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bb782-117">Seleccione **Agregar conexión** y elija **Microsoft Advertising** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="bb782-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="bb782-118">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="bb782-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bb782-119">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="bb782-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bb782-120">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="bb782-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bb782-121">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="bb782-121">Choose who can use this connection.</span></span> <span data-ttu-id="bb782-122">El valor predeterminado es administradores.</span><span class="sxs-lookup"><span data-stu-id="bb782-122">The default is administrators.</span></span> <span data-ttu-id="bb782-123">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bb782-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bb782-124">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="bb782-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bb782-125">Seleccione **Conectar** para inicializar la conexión a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="bb782-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="bb782-126">Seleccione **Autenticar con Microsoft Advertising** y proporcione sus credenciales de administrador para Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="bb782-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="bb782-127">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bb782-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bb782-128">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="bb782-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bb782-129">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="bb782-129">Configure an export</span></span>

<span data-ttu-id="bb782-130">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="bb782-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bb782-131">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bb782-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bb782-132">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="bb782-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bb782-133">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="bb782-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bb782-134">En el campo **Conexión para exportación**, elija una conexión de la sección Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="bb782-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="bb782-135">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="bb782-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bb782-136">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="bb782-136">Select the segments to export.</span></span> <span data-ttu-id="bb782-137">Las audiencias de Customer Match en Microsoft Advertising se crean automáticamente con el nombre de los segmentos seleccionados para exportar.</span><span class="sxs-lookup"><span data-stu-id="bb782-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="bb782-138">Cada segmento dará como resultado una audiencia diferente de Customer Match.</span><span class="sxs-lookup"><span data-stu-id="bb782-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="bb782-139">Introduzca su **Id. de cliente e Id. de cuenta de Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="bb782-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="bb782-140">Puede encontrar el Id. de cliente (`cid`) e Id. de cuenta (`aid`) en los parámetros de la URL cuando inicie sesión en Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="bb782-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="bb782-141">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado con la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="bb782-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="bb782-142">Es obligatorio exportar segmentos a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="bb782-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="bb782-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb782-143">Select **Save**.</span></span>

<span data-ttu-id="bb782-144">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="bb782-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bb782-145">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb782-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bb782-146">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bb782-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bb782-147">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="bb782-147">Data privacy and compliance</span></span>

<span data-ttu-id="bb782-148">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Microsoft Advertising, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="bb782-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bb782-149">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Microsoft Advertising cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="bb782-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bb782-150">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bb782-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bb782-151">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para detener esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="bb782-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
