---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar la conexión y a exportar a Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759842"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="6bfca-103">Exportar segmentos a Marketo (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6bfca-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="6bfca-104">Exporte segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y usar grupos específicos de clientes con Marketo.</span><span class="sxs-lookup"><span data-stu-id="6bfca-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="6bfca-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="6bfca-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="6bfca-106">Tiene una [cuenta de Marketo](https://login.marketo.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6bfca-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6bfca-107">Hay listas existentes en Marketo y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6bfca-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="6bfca-108">Para obtener más información, consulte las [listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="6bfca-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="6bfca-109">Ha [configurado los segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6bfca-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="6bfca-110">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6bfca-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6bfca-111">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="6bfca-111">Known limitations</span></span>

- <span data-ttu-id="6bfca-112">Hasta 1 millón de perfiles por exportación a Marketo.</span><span class="sxs-lookup"><span data-stu-id="6bfca-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="6bfca-113">La exportación a Marketo está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="6bfca-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="6bfca-114">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas.</span><span class="sxs-lookup"><span data-stu-id="6bfca-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="6bfca-115">La cantidad de perfiles que puede exportar a Marketo depende y está limitada a su contrato con Marketo.</span><span class="sxs-lookup"><span data-stu-id="6bfca-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="6bfca-116">Configurar conexión a Marketo</span><span class="sxs-lookup"><span data-stu-id="6bfca-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="6bfca-117">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="6bfca-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6bfca-118">Seleccione **Agregar conexión** y elija **Marketo** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="6bfca-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="6bfca-119">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="6bfca-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6bfca-120">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="6bfca-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6bfca-121">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="6bfca-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6bfca-122">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="6bfca-122">Choose who can use this connection.</span></span> <span data-ttu-id="6bfca-123">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="6bfca-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6bfca-124">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6bfca-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6bfca-125">Introduzca su **[Id. de cliente de Marketo, secreto de cliente y nombre de host de punto de conexión REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="6bfca-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="6bfca-126">Seleccione **Estoy de acuerdo** para confirmar la **Privacidad y cumplimiento de datos** y seleccione **Conectar** para inicializar la conexión a Marketo.</span><span class="sxs-lookup"><span data-stu-id="6bfca-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="6bfca-127">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6bfca-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6bfca-128">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="6bfca-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6bfca-129">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="6bfca-129">Configure an export</span></span>

<span data-ttu-id="6bfca-130">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="6bfca-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6bfca-131">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6bfca-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6bfca-132">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="6bfca-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6bfca-133">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="6bfca-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6bfca-134">En el campo **Conexión para exportación**, elija una conexión de la sección Marketo.</span><span class="sxs-lookup"><span data-stu-id="6bfca-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="6bfca-135">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="6bfca-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6bfca-136">introduzca su **[ID de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="6bfca-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="6bfca-137">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="6bfca-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="6bfca-138">Opcionalmente, puede exportar el **Nombre de pila**, el **Apellido**, la **Ciudad**, el **Estado** y el **País** para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="6bfca-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="6bfca-139">Seleccione **Agregar atributo** para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="6bfca-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="6bfca-140">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="6bfca-140">Select the segments you want to export.</span></span> <span data-ttu-id="6bfca-141">Puede exportar hasta 1 millón de perfiles de clientes en total a Marketo.</span><span class="sxs-lookup"><span data-stu-id="6bfca-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="6bfca-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6bfca-142">Select **Save**.</span></span>

<span data-ttu-id="6bfca-143">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6bfca-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6bfca-144">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6bfca-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6bfca-145">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6bfca-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="6bfca-146">En Marketo, ahora puede encontrar sus segmentos en [Listas de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="6bfca-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6bfca-147">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="6bfca-147">Data privacy and compliance</span></span>

<span data-ttu-id="6bfca-148">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="6bfca-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6bfca-149">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Marketo cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="6bfca-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6bfca-150">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6bfca-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6bfca-151">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6bfca-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]