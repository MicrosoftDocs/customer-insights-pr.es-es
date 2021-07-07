---
title: Exportar datos de Customer Insights a Salesforce Marketing Cloud
description: Aprenda a configurar la conexión y exportar a Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314678"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="984ca-103">Exportar segmentos y otros datos a Salesforce Marketing Cloud (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="984ca-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="984ca-104">Utilice los datos de sus clientes en Salesforce Marketing Cloud exportándolos a través de una ubicación de Protocolo seguro de transferencia de archivos (SFTP).</span><span class="sxs-lookup"><span data-stu-id="984ca-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="984ca-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="984ca-105">Prerequisites for connection</span></span>

- <span data-ttu-id="984ca-106">Disponibilidad de un host SFTP y las correspondientes credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="984ca-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="984ca-107">Cómo configurar ubicaciones SFTP para Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="984ca-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="984ca-108">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="984ca-108">Known limitations</span></span>

- <span data-ttu-id="984ca-109">El tiempo de ejecución de una exportación depende del rendimiento de su sistema.</span><span class="sxs-lookup"><span data-stu-id="984ca-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="984ca-110">Recomendamos dos núcleos de CPU y 1 Gb de memoria como configuración mínima de su servidor.</span><span class="sxs-lookup"><span data-stu-id="984ca-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="984ca-111">La exportación de entidades con hasta 100 millones de perfiles de clientes puede tardar 90 minutos cuando se utiliza la configuración mínima recomendada.</span><span class="sxs-lookup"><span data-stu-id="984ca-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="984ca-112">Configurar la conexión a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="984ca-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="984ca-113">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="984ca-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="984ca-114">Seleccione **Agregar conexión** y elija **Salesforce Marketing Cloud** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="984ca-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="984ca-115">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="984ca-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="984ca-116">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="984ca-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="984ca-117">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="984ca-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="984ca-118">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="984ca-118">Choose who can use this connection.</span></span> <span data-ttu-id="984ca-119">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="984ca-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="984ca-120">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="984ca-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="984ca-121">Proporcione un **Nombre de usuario**, una **Contraseña**,un **Nombre de host** y una **Carpeta de exportación** para su cuenta SFTP.</span><span class="sxs-lookup"><span data-stu-id="984ca-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="984ca-122">Seleccione **Verificar** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="984ca-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="984ca-123">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="984ca-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="984ca-124">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="984ca-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="984ca-125">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="984ca-125">Configure an export</span></span>

<span data-ttu-id="984ca-126">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="984ca-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="984ca-127">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="984ca-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="984ca-128">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="984ca-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="984ca-129">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="984ca-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="984ca-130">En el campo **Conexión para exportación**, elija una conexión de la sección SFTP.</span><span class="sxs-lookup"><span data-stu-id="984ca-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="984ca-131">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="984ca-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="984ca-132">Elija si desea exportar sus datos **comprimidos** o **descomprimidos** y el **delimitador de campo** para los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="984ca-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="984ca-133">Seleccione las entidades, por ejemplo segmentos, que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="984ca-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="984ca-134">Cada entidad seleccionada se dividirá en hasta cinco archivos de salida cuando se exporten.</span><span class="sxs-lookup"><span data-stu-id="984ca-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="984ca-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="984ca-135">Select **Save**.</span></span>

<span data-ttu-id="984ca-136">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="984ca-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="984ca-137">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="984ca-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="984ca-138">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="984ca-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="984ca-139">Importar datos de Customer Insights desde una ubicación de SFTP a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="984ca-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="984ca-140">Cree [extensiones de datos en Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar el archivo de datos de Customer Insights desde la ubicación SFTP.</span><span class="sxs-lookup"><span data-stu-id="984ca-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="984ca-141">[Importar los datos de la ubicación SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) a la extensión de datos de Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="984ca-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="984ca-142">Configure la automatización para importar los datos a las extensiones de datos.</span><span class="sxs-lookup"><span data-stu-id="984ca-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="984ca-143">Más información sobre [automatizaciones de colocación de archivos y automatizaciones programadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="984ca-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="984ca-144">Definir una [automatización de colocación de archivos](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o una [automatización programada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="984ca-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="984ca-145">He aquí un ejemplo de [una automatización con SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="984ca-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="984ca-146">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="984ca-146">Data privacy and compliance</span></span>

<span data-ttu-id="984ca-147">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a través de SFTP, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="984ca-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="984ca-148">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que el destino de exportación cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="984ca-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="984ca-149">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="984ca-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="984ca-150">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="984ca-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
