---
title: Exportar datos de Customer Insights a Omnisend
description: Aprenda a configurar la conexión y a exportar a Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124556"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="68f0f-103">Exportar segmentos a Omnisend (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="68f0f-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="68f0f-104">Exporte segmentos de perfiles de clientes unificados a Omnisend y utilícelos para actividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="68f0f-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68f0f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="68f0f-105">Prerequisites</span></span>

-   <span data-ttu-id="68f0f-106">Tiene una [cuenta de Omnisend](https://www.omnisend.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="68f0f-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="68f0f-107">Tiene [segmentos configurados](segments.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="68f0f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="68f0f-108">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="68f0f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="68f0f-109">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="68f0f-109">Known limitations</span></span>

- <span data-ttu-id="68f0f-110">Puede exportar hasta 1 millón de perfiles por exportación a Omnisend y puede tardar hasta 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="68f0f-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="68f0f-111">La exportación a Omnisend está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="68f0f-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="68f0f-112">La cantidad de perfiles que puede exportar a Omnisend depende de su contrato con Omnisend.</span><span class="sxs-lookup"><span data-stu-id="68f0f-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="68f0f-113">Configurar conexión a Omnisend</span><span class="sxs-lookup"><span data-stu-id="68f0f-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="68f0f-114">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="68f0f-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="68f0f-115">Seleccione **Agregar conexión** y elija **Omnisend** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="68f0f-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="68f0f-116">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="68f0f-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="68f0f-117">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="68f0f-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="68f0f-118">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="68f0f-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="68f0f-119">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="68f0f-119">Choose who can use this connection.</span></span> <span data-ttu-id="68f0f-120">De forma predeterminada, solo son administradores.</span><span class="sxs-lookup"><span data-stu-id="68f0f-120">By default it's only administrators.</span></span> <span data-ttu-id="68f0f-121">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="68f0f-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="68f0f-122">Introzuca su [Clave de API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="68f0f-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="68f0f-123">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="68f0f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68f0f-124">Seleccione **Conectar** para inicializar la conexión a Omnisend.</span><span class="sxs-lookup"><span data-stu-id="68f0f-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="68f0f-125">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="68f0f-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="68f0f-126">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="68f0f-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="68f0f-127">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="68f0f-127">Configure an export</span></span>

<span data-ttu-id="68f0f-128">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="68f0f-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="68f0f-129">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="68f0f-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="68f0f-130">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="68f0f-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="68f0f-131">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="68f0f-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="68f0f-132">En el campo **Conexión para exportación**, elija una conexión de la sección Omnisend.</span><span class="sxs-lookup"><span data-stu-id="68f0f-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="68f0f-133">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="68f0f-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="68f0f-134">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="68f0f-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="68f0f-135">Es obligatorio exportar segmentos a Omnisend.</span><span class="sxs-lookup"><span data-stu-id="68f0f-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="68f0f-136">Opcionalmente, puede exportar el Nombre de pila, el Apellido, Dirección la Ciudad, el Estado, Código postal y el País para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="68f0f-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="68f0f-137">Seleccione **Agregar atributo** para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="68f0f-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="68f0f-138">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="68f0f-138">Select **Save**.</span></span>

<span data-ttu-id="68f0f-139">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="68f0f-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="68f0f-140">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68f0f-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68f0f-141">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="68f0f-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68f0f-142">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="68f0f-142">Data privacy and compliance</span></span>

<span data-ttu-id="68f0f-143">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Omnisend, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="68f0f-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68f0f-144">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Omnisend cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="68f0f-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="68f0f-145">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="68f0f-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="68f0f-146">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="68f0f-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
