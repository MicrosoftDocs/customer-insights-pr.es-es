---
title: Exportar datos de Customer Insights al Administrador de anuncios de Facebook
description: Aprenda a configurar la conexión y a exportar a el administrador de anuncios de Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305131"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="ca5e1-103">Exportar lista de segmentos al administrador de anuncios de Facebook (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ca5e1-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="ca5e1-104">Exportar segmentos de perfiles de clientes unificados a Administrador de anuncios de Facebook para crear campañas en Facebook e Instagram.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ca5e1-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="ca5e1-105">Prerequisites for connection</span></span>

- <span data-ttu-id="ca5e1-106">Debe tener una [**Cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)que incluya una [**Cuenta empresarial de Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="ca5e1-107">Debe ser un administrador en la [**Cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ca5e1-108">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="ca5e1-108">Known limitations</span></span>

- <span data-ttu-id="ca5e1-109">Hasta 10 millones de perfiles de clientes por exportación al administrador de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="ca5e1-110">La exportación al administrador de anuncios de Facebook está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="ca5e1-111">Cree o actualice audiencias personalizadas en Facebook solo de tipo *lista de clientes*.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="ca5e1-112">La exportación de segmentos con un total de 10 millón de perfiles puede tardar hasta 90 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="ca5e1-113">Configurar una conexión al administrador de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="ca5e1-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="ca5e1-114">Antes de que los usuarios puedan crear una exportación, un administrador debe configurar la conexión al servicio y permitir que los colaboradores usen la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="ca5e1-115">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ca5e1-116">Seleccione **Agregar conexión** y elija **Administrador de anuncios de Facebook** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="ca5e1-117">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ca5e1-118">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ca5e1-119">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ca5e1-120">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-120">Choose who can use this connection.</span></span> <span data-ttu-id="ca5e1-121">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ca5e1-122">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ca5e1-123">Autenticación con anuncios de Facebook:</span><span class="sxs-lookup"><span data-stu-id="ca5e1-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="ca5e1-124">Seleccione **Continuar con Facebook** para iniciar sesión en su cuenta de Facebook.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="ca5e1-125">Autorizar el permiso **ads_management** después de autenticarse con Facebook.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="ca5e1-126">Seleccione la **Cuenta de anuncios de Facebook** con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="ca5e1-127">Seleccione una **Público personalizado existente** en la lista desplegable o cree un **Nuevo público personalizado**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="ca5e1-128">Para más información, vea [**Audiencias en Administrador de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="ca5e1-129">Solo puede crear o actualizar audiencias personalizadas en Facebook del tipo *lista de clientes* con esta exportación.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="ca5e1-130">En algunos casos, verá públicos personalizadas de diferentes tipos en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="ca5e1-131">Si selecciona un tipo diferente a la *lista de clientes*, dará como resultado una exportación fallida.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="ca5e1-132">Revise **Privacidad y cumplimiento de datos** y seleccione **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="ca5e1-133">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ca5e1-134">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="ca5e1-134">Configure an export</span></span>

<span data-ttu-id="ca5e1-135">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ca5e1-136">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ca5e1-137">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ca5e1-138">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="ca5e1-139">En el campo **Conexión para exportación**, elija una conexión en la sección **Administrador de anuncios de Facebook**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="ca5e1-140">Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="ca5e1-141">En **Elija su campo de identificador de clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar a Administrador de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="ca5e1-142">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ca5e1-143">Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="ca5e1-144">Las mejores posibilidades para que se produzca una coincidencia es seleccionar **Correo electrónico** como identificador clave</span><span class="sxs-lookup"><span data-stu-id="ca5e1-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="ca5e1-145">Agregar identificadores adicionales puede mejorar la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="ca5e1-146">Seleccione **Agregar atributo** para asignar más atributos para enviar al administrador de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="ca5e1-147">Los atributos de Administrador de anuncios de Facebook se asignan a los siguientes nombres descriptivos: **FN** = **Nombre**, **LN** = **Apellidos**, **FI** = **Primera inicial**, **PHONE** = **Teléfono**, **GEN** = **Género**, **DOB** = **Fecha de nacimiento**, **ST** = **Estado**, **CT** = **Ciudad**, **ZIP** = **Código postal**, **COUNTRY** = **País / Región**</span><span class="sxs-lookup"><span data-stu-id="ca5e1-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="ca5e1-148">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ca5e1-149">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-149">Select **Save**.</span></span>

<span data-ttu-id="ca5e1-150">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ca5e1-151">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="ca5e1-152">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ca5e1-153">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="ca5e1-153">Data privacy and compliance</span></span>

<span data-ttu-id="ca5e1-154">Cuando habilita Dynamics 365 Customer Insights para transmitir datos al Administrador de anuncios de Facebook, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ca5e1-155">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Facebook cumplan con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ca5e1-156">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ca5e1-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ca5e1-157">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="ca5e1-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
