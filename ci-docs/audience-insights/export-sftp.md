---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar la conexión a un host SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643524"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="2d132-103">Conector para SFTP (vista previa)</span><span class="sxs-lookup"><span data-stu-id="2d132-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="2d132-104">Use sus datos de clientes en aplicaciones de terceros exportándolos de forma segura a un servidor a través del protocolo seguro de transferencia de archivos (SFTP).</span><span class="sxs-lookup"><span data-stu-id="2d132-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d132-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2d132-105">Prerequisites</span></span>

- <span data-ttu-id="2d132-106">Disponibilidad de un host SFTP y credenciales correspondientes.</span><span class="sxs-lookup"><span data-stu-id="2d132-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="2d132-107">Conectarse a SFTP</span><span class="sxs-lookup"><span data-stu-id="2d132-107">Connect to SFTP</span></span>

1. <span data-ttu-id="2d132-108">Vaya a **Administración** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="2d132-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2d132-109">En **SFTP**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2d132-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="2d132-110">Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="2d132-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2d132-111">Proporcione un **Nombre de usuario**, una **Contraseña** y un **Nombre de host** para su cuenta SFTP.</span><span class="sxs-lookup"><span data-stu-id="2d132-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="2d132-112">Ejemplo: si la carpeta raíz de su servidor SFTP es /root/folder y desea que los datos se exporten a /root/folder/ci_export_destination_folder, el servidor debe ser sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="2d132-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="2d132-113">Seleccione **Verificar** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="2d132-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="2d132-114">Después de una verificación correcta, elija si desea exportar sus datos **Comprimidos** o **Descomprimidos** y seleccione el **delimitador de campo** para los archivos exportados.</span><span class="sxs-lookup"><span data-stu-id="2d132-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="2d132-115">Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.</span><span class="sxs-lookup"><span data-stu-id="2d132-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2d132-116">Seleccione **Siguiente** para comenzar a configurar la exportación.</span><span class="sxs-lookup"><span data-stu-id="2d132-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="2d132-117">Configurar la conexión</span><span class="sxs-lookup"><span data-stu-id="2d132-117">Configure the connection</span></span>

1. <span data-ttu-id="2d132-118">Seleccionar los **atributos de clientes** que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="2d132-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="2d132-119">Puede exportar uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="2d132-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="2d132-120">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2d132-120">Select **Next**.</span></span>

1. <span data-ttu-id="2d132-121">Seleccione los segmentos que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="2d132-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="2d132-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2d132-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2d132-123">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="2d132-123">Export the data</span></span>

<span data-ttu-id="2d132-124">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2d132-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2d132-125">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2d132-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2d132-126">Privacidad y cumplimiento de datos</span><span class="sxs-lookup"><span data-stu-id="2d132-126">Data privacy and compliance</span></span>

<span data-ttu-id="2d132-127">Cuando habilita Dynamics 365 Customer Insights para transmitir datos a través de SFTP, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales.</span><span class="sxs-lookup"><span data-stu-id="2d132-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2d132-128">Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que el destino de exportación cumpla con las obligaciones de privacidad o seguridad que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="2d132-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2d132-129">Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2d132-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2d132-130">Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="2d132-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
