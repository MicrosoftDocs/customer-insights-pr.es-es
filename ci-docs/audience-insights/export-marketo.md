---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar la conexión a Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267102"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="0f0e7-103">Conector para Marketo (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="0f0e7-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="0f0e7-104">Exporte segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y usar grupos específicos de clientes con Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f0e7-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f0e7-105">Prerequisites</span></span>

-   <span data-ttu-id="0f0e7-106">Tiene una [cuenta de Marketo](https://login.marketo.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0f0e7-107">Hay listas existentes en Marketo y los id. correspondientes.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="0f0e7-108">Para obtener más información, consulte las [listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0f0e7-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="0f0e7-109">Ha [configurado los segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0f0e7-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0f0e7-110">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="0f0e7-111">Conectar a Marketo</span><span class="sxs-lookup"><span data-stu-id="0f0e7-111">Connect to Marketo</span></span>

1. <span data-ttu-id="0f0e7-112">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0f0e7-113">En **Marketo**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="0f0e7-114">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0f0e7-115">Introduzca su **[Id. de cliente de Marketo, secreto de cliente y nombre de host de punto de conexión REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="0f0e7-116">introduzca su **[ID de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="0f0e7-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="0f0e7-117">Seleccione **Estoy de acuerdo** para confirmar la **Privacidad y cumplimiento de datos** y seleccione **Conectar** para inicializar la conexión a Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="0f0e7-118">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportar la captura de pantalla para conexión de Marketo":::

1. <span data-ttu-id="0f0e7-120">Seleccione **Siguiente** para configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0f0e7-121">Configurar el conector</span><span class="sxs-lookup"><span data-stu-id="0f0e7-121">Configure the connector</span></span>

1. <span data-ttu-id="0f0e7-122">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0f0e7-123">Opcionalmente, puede exportar **Nombre de pila**, **Apellido**, **Ciudad**, **Estado** y **País/Región** como campos adicionales para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="0f0e7-124">Seleccione **Agregar atributo** para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0f0e7-125">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-125">Select the segments you want to export.</span></span> <span data-ttu-id="0f0e7-126">Puede exportar hasta 1 millón de perfiles de clientes en total a Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Seleccionar campos y segmentos para exportar a Marketo":::

1. <span data-ttu-id="0f0e7-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0f0e7-129">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="0f0e7-129">Export the data</span></span>

<span data-ttu-id="0f0e7-130">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0f0e7-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0f0e7-131">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0f0e7-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0f0e7-132">En Marketo, ahora puede encontrar sus segmentos en [Listas de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0f0e7-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0f0e7-133">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="0f0e7-133">Known limitations</span></span>

- <span data-ttu-id="0f0e7-134">Hasta 1 millón de perfiles por exportación a Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="0f0e7-135">La exportación a Marketo está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="0f0e7-136">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="0f0e7-137">La cantidad de perfiles que puede exportar a Marketo depende y está limitada a su contrato con Marketo.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0f0e7-138">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="0f0e7-138">Data privacy and compliance</span></span>

<span data-ttu-id="0f0e7-139">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0f0e7-140">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Marketo cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0f0e7-141">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0f0e7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0f0e7-142">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="0f0e7-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]