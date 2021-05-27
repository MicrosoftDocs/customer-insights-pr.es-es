---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar la conexión y a exportar a una ubicación de SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976960"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="4ad53-103">Exportar listas de segmentos y otros datos a SFTP (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4ad53-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="4ad53-104">Utilice los datos de sus clientes en aplicaciones de terceros exportándolos a una ubicación del protocolo seguro de transferencia de archivos (SFTP).</span><span class="sxs-lookup"><span data-stu-id="4ad53-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="4ad53-105">Requisitos previos para una conexión</span><span class="sxs-lookup"><span data-stu-id="4ad53-105">Prerequisites for connection</span></span>

- <span data-ttu-id="4ad53-106">Disponibilidad de un host SFTP y las credenciales correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4ad53-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4ad53-107">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="4ad53-107">Known limitations</span></span>

- <span data-ttu-id="4ad53-108">El tiempo de ejecución de una exportación depende del rendimiento de su sistema.</span><span class="sxs-lookup"><span data-stu-id="4ad53-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="4ad53-109">Recomendamos dos núcleos de CPU y 1 Gb de memoria como configuración mínima de su servidor.</span><span class="sxs-lookup"><span data-stu-id="4ad53-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="4ad53-110">Exportar entidades con hasta 100 millones de perfiles de clientes puede prolongarse durante 90 minutos cuando se utiliza la configuración mínima recomendada de dos núcleos de CPU y 1 Gb de memoria.</span><span class="sxs-lookup"><span data-stu-id="4ad53-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="4ad53-111">Configurar conexiones para SFTP</span><span class="sxs-lookup"><span data-stu-id="4ad53-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="4ad53-112">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="4ad53-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4ad53-113">Seleccione **Agregar conexión** y elija **SFTP** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="4ad53-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="4ad53-114">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="4ad53-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4ad53-115">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="4ad53-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4ad53-116">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="4ad53-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4ad53-117">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="4ad53-117">Choose who can use this connection.</span></span> <span data-ttu-id="4ad53-118">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="4ad53-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4ad53-119">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4ad53-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4ad53-120">Proporcione un **Nombre de usuario**, una **Contraseña**,un **Nombre de host** y una **Carpeta de exportación** para su cuenta SFTP.</span><span class="sxs-lookup"><span data-stu-id="4ad53-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="4ad53-121">Seleccione **Verificar** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="4ad53-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="4ad53-122">Elija si desea exportar sus datos **comprimidos** o **descomprimidos** y el **delimitador de campo** para los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="4ad53-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="4ad53-123">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="4ad53-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4ad53-124">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="4ad53-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4ad53-125">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="4ad53-125">Configure an export</span></span>

<span data-ttu-id="4ad53-126">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4ad53-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4ad53-127">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4ad53-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4ad53-128">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="4ad53-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4ad53-129">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="4ad53-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4ad53-130">En el campo **Conexión para exportación**, elija una conexión de la sección SFTP.</span><span class="sxs-lookup"><span data-stu-id="4ad53-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="4ad53-131">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="4ad53-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4ad53-132">Seleccione las entidades, por ejemplo segmentos, que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="4ad53-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4ad53-133">Cada entidad seleccionada se dividirá en hasta cinco archivos de salida cuando se exporten.</span><span class="sxs-lookup"><span data-stu-id="4ad53-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="4ad53-134">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4ad53-134">Select **Save**.</span></span>

<span data-ttu-id="4ad53-135">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4ad53-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4ad53-136">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4ad53-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4ad53-137">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4ad53-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4ad53-138">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="4ad53-138">Data privacy and compliance</span></span>

<span data-ttu-id="4ad53-139">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a través de SFTP, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="4ad53-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4ad53-140">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que el destino de exportación cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="4ad53-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4ad53-141">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4ad53-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4ad53-142">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="4ad53-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
