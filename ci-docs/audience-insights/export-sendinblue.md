---
title: Exportar datos de Customer Insights a Sendinblue
description: Aprenda a configurar la conexión y exportar a Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314679"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="78a21-103">Exportar segmentos a Sendinblue (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="78a21-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="78a21-104">Exportar segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y aprovechar grupos específicos de clientes con Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="78a21-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="78a21-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="78a21-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="78a21-106">Tiene una [cuenta de Sendinblue](https://www.sendinblue.com/) y las credenciales de administrador correspondientes.</span><span class="sxs-lookup"><span data-stu-id="78a21-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="78a21-107">Hay listas existentes en Sendinblue y los identificadores correspondientes.</span><span class="sxs-lookup"><span data-stu-id="78a21-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="78a21-108">Ha [configurado los segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="78a21-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="78a21-109">Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="78a21-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="78a21-110">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="78a21-110">Known limitations</span></span>

- <span data-ttu-id="78a21-111">Hasta 1 millón de perfiles por exportación a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="78a21-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="78a21-112">La exportación a Sendinblue está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="78a21-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="78a21-113">La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="78a21-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="78a21-114">La cantidad de perfiles que puede exportar a Sendinblue depende de su contrato con Sendinblue y queda limitada a lo que en se especifique en dicho contrato.</span><span class="sxs-lookup"><span data-stu-id="78a21-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="78a21-115">Configurar la conexión a Sendinblue</span><span class="sxs-lookup"><span data-stu-id="78a21-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="78a21-116">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="78a21-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="78a21-117">Seleccione **Agregar conexión** y elija **Sendinblue** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="78a21-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="78a21-118">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="78a21-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="78a21-119">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="78a21-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="78a21-120">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="78a21-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="78a21-121">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="78a21-121">Choose who can use this connection.</span></span> <span data-ttu-id="78a21-122">De forma predeterminada, solo son administradores.</span><span class="sxs-lookup"><span data-stu-id="78a21-122">By default it's only administrators.</span></span> <span data-ttu-id="78a21-123">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="78a21-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="78a21-124">Especifique su **[clave de API de Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**</span><span class="sxs-lookup"><span data-stu-id="78a21-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="78a21-125">Seleccione **Acepto** para confirmar la **Privacidad y cumplimiento de los datos** y seleccione **Conectar** para inicializar la conexión a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="78a21-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="78a21-126">Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="78a21-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="78a21-127">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="78a21-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="78a21-128">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="78a21-128">Configure an export</span></span>

<span data-ttu-id="78a21-129">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="78a21-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="78a21-130">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="78a21-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="78a21-131">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="78a21-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="78a21-132">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="78a21-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="78a21-133">En el campo **Conexión para exportación**, elija una conexión de la sección Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="78a21-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="78a21-134">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="78a21-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="78a21-135">Indique su **Id. de lista de Sendinblue**.</span><span class="sxs-lookup"><span data-stu-id="78a21-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="78a21-136">En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.</span><span class="sxs-lookup"><span data-stu-id="78a21-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="78a21-137">Opcionalmente, puede exportar **Nombre de pila**, **Apellido**, y **Teléfono** para crear correos electrónicos más personalizados.</span><span class="sxs-lookup"><span data-stu-id="78a21-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="78a21-138">Seleccione **Agregar atributo** para asignar estos campos.</span><span class="sxs-lookup"><span data-stu-id="78a21-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="78a21-139">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="78a21-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="78a21-140">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78a21-140">Select **Save**.</span></span>

<span data-ttu-id="78a21-141">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="78a21-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="78a21-142">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="78a21-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="78a21-143">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="78a21-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="78a21-144">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="78a21-144">Data privacy and compliance</span></span>

<span data-ttu-id="78a21-145">Cuando habilite Dynamics 365 Customer Insights para transmitir datos a Sendinblue, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="78a21-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="78a21-146">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Sendinblue cumple las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="78a21-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="78a21-147">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="78a21-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="78a21-148">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="78a21-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
