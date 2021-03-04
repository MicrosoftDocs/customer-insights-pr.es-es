---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar la conexión a un host SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268019"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="9e3c7-103">Conector para SFTP (vista previa)</span><span class="sxs-lookup"><span data-stu-id="9e3c7-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="9e3c7-104">Use sus datos de clientes en aplicaciones de terceros exportándolos de forma segura a un servidor a través del protocolo seguro de transferencia de archivos (SFTP).</span><span class="sxs-lookup"><span data-stu-id="9e3c7-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e3c7-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e3c7-105">Prerequisites</span></span>

- <span data-ttu-id="9e3c7-106">Disponibilidad de un host SFTP y las credenciales correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="9e3c7-107">Conectarse a SFTP</span><span class="sxs-lookup"><span data-stu-id="9e3c7-107">Connect to SFTP</span></span>

1. <span data-ttu-id="9e3c7-108">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9e3c7-109">En **SFTP**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="9e3c7-110">Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9e3c7-111">Proporcione un **Nombre de usuario**, una **Contraseña**,un **Nombre de host** y una **Carpeta de exportación** para su cuenta SFTP.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="9e3c7-112">Seleccione **Verificar** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="9e3c7-113">Después de una verificación exitosa, elija si desea exportar sus datos **comprimidos** o **descomprimidos** y seleccione el **delimitador de campo** para los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="9e3c7-114">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9e3c7-115">Seleccione **Siguiente** para comenzar a configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="9e3c7-116">Configurar la exportación</span><span class="sxs-lookup"><span data-stu-id="9e3c7-116">Configure the export</span></span>

1. <span data-ttu-id="9e3c7-117">Seleccione las entidades, por ejemplo segmentos, que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9e3c7-118">Cada entidad seleccionada generará hasta cinco archivos de salida cuando se exporta.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="9e3c7-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9e3c7-120">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="9e3c7-120">Export the data</span></span>

<span data-ttu-id="9e3c7-121">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c7-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9e3c7-122">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9e3c7-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9e3c7-123">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="9e3c7-123">Known limitations</span></span>

- <span data-ttu-id="9e3c7-124">El tiempo de ejecución de una exportación depende del rendimiento de su sistema.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="9e3c7-125">Recomendamos dos núcleos de CPU y 1 Gb de memoria como configuración mínima de su servidor.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="9e3c7-126">Exportar entidades con hasta 100 millones de perfiles de clientes puede prolongarse durante 90 minutos cuando se utiliza la configuración mínima recomendada de dos núcleos de CPU y 1 Gb de memoria.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9e3c7-127">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="9e3c7-127">Data privacy and compliance</span></span>

<span data-ttu-id="9e3c7-128">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a través de SFTP, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9e3c7-129">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que el destino de exportación cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9e3c7-130">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9e3c7-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9e3c7-131">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="9e3c7-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]