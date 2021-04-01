---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar la conexión a Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597624"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="cabe7-103">Conector para Dynamics 365 Marketing (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="cabe7-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cabe7-104">Use los [segmentos](segments.md) creados para generar campañas y contactar con grupos específicos de clientes con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="cabe7-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="cabe7-105">Para obtener más información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="cabe7-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="cabe7-106">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="cabe7-106">Prerequisite</span></span>

- <span data-ttu-id="cabe7-107">Los registros de contacto deben estar presentes en Dynamics 365 Marketing antes de poder exportar un segmento de Customer Insights a Marketing.</span><span class="sxs-lookup"><span data-stu-id="cabe7-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="cabe7-108">Más información sobre cómo ingerir contactos en [Dynamics 365 Marketing usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cabe7-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cabe7-109">La exportación de segmentos de las informaciones de público a Marketing no creará nuevos registros de contactos en las instancias de Marketing.</span><span class="sxs-lookup"><span data-stu-id="cabe7-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="cabe7-110">Los registros de contacto de Marketing deben ingerirse en las informaciones de público y usarse como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cabe7-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="cabe7-111">También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.</span><span class="sxs-lookup"><span data-stu-id="cabe7-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="cabe7-112">Configurar el conector para Marketing</span><span class="sxs-lookup"><span data-stu-id="cabe7-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="cabe7-113">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="cabe7-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cabe7-114">En **Dynamics 365 Marketing**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="cabe7-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="cabe7-115">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="cabe7-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cabe7-116">Introduzca la dirección URL de Marketing de su organización en el campo **Dirección del servidor**.</span><span class="sxs-lookup"><span data-stu-id="cabe7-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="cabe7-117">En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="cabe7-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="cabe7-118">Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cabe7-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="cabe7-119">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cabe7-119">Select **Next**.</span></span>

1. <span data-ttu-id="cabe7-120">Elija uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="cabe7-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="cabe7-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cabe7-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cabe7-122">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="cabe7-122">Export the data</span></span>

<span data-ttu-id="cabe7-123">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cabe7-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cabe7-124">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cabe7-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]