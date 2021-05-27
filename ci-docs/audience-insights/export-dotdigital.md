---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar la conexión y a exportar a DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976867"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="45a9a-103">Exportar listas de segmentos a DotDigital (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="45a9a-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="45a9a-104">Exporte segmentos de perfiles de clientes unificados a las libretas de direcciones de DotDigital y utilícelos para campañas, marketing por correo electrónico y para crear segmentos de clientes con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="45a9a-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="45a9a-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="45a9a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="45a9a-106">Tiene una [Cuenta de DotDigital](https://dotdigital.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="45a9a-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="45a9a-107">Hay libretas de direcciones existentes en DotDigital y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="45a9a-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="45a9a-108">El id. se puede encontrar en la URL cuando selecciona y abre una libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="45a9a-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="45a9a-109">Para más información, consulte [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="45a9a-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="45a9a-110">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="45a9a-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="45a9a-111">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="45a9a-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="45a9a-112">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="45a9a-112">Known limitations</span></span>

- <span data-ttu-id="45a9a-113">Hasta 1 millón de perfiles por exportación a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="45a9a-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="45a9a-114">La exportación a DotDigital está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="45a9a-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="45a9a-115">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas, debido a las limitaciones del proveedor.</span><span class="sxs-lookup"><span data-stu-id="45a9a-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="45a9a-116">La cantidad de perfiles que puede exportar a DotDigital depende y está limitada a su contrato con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="45a9a-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="45a9a-117">Configurar conexión a DotDigital</span><span class="sxs-lookup"><span data-stu-id="45a9a-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="45a9a-118">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="45a9a-119">Seleccione **Agregar conexión** y elija **DotDigital** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="45a9a-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="45a9a-120">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="45a9a-121">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="45a9a-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="45a9a-122">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="45a9a-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="45a9a-123">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="45a9a-123">Choose who can use this connection.</span></span> <span data-ttu-id="45a9a-124">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="45a9a-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="45a9a-125">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="45a9a-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="45a9a-126">Introduzca su **nombre de usuario y contraseña de DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="45a9a-127">Introduzca su **[Id. de la libreta de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="45a9a-128">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="45a9a-129">Seleccione **Conectar** para inicializar la conexión a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="45a9a-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="45a9a-130">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="45a9a-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="45a9a-131">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="45a9a-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="45a9a-132">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="45a9a-132">Configure an export</span></span>

<span data-ttu-id="45a9a-133">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="45a9a-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="45a9a-134">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="45a9a-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="45a9a-135">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="45a9a-136">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="45a9a-137">En el campo **Conexión para exportación**, elija una conexión de la sección DotDigital.</span><span class="sxs-lookup"><span data-stu-id="45a9a-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="45a9a-138">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="45a9a-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="45a9a-139">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="45a9a-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="45a9a-140">Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **Nombre completo**, **Género** y **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="45a9a-141">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="45a9a-141">Select the segments you want to export.</span></span> <span data-ttu-id="45a9a-142">Puede exportar hasta 1 millón de perfiles de clientes en total a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="45a9a-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="45a9a-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="45a9a-143">Select **Save**.</span></span>

<span data-ttu-id="45a9a-144">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="45a9a-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="45a9a-145">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="45a9a-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="45a9a-146">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="45a9a-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="45a9a-147">En DotDigital, ahora puede encontrar sus segmentos en [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="45a9a-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="45a9a-148">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="45a9a-148">Data privacy and compliance</span></span>

<span data-ttu-id="45a9a-149">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="45a9a-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="45a9a-150">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que DotDigital cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="45a9a-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="45a9a-151">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="45a9a-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="45a9a-152">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="45a9a-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
