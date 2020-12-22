---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar la conexión a Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643794"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="3b6c6-103">Conector para Dynamics 365 Marketing (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="3b6c6-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3b6c6-104">Use los [segmentos](segments.md) creados para generar campañas y contactar con grupos específicos de clientes con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="3b6c6-105">Para obtener más información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="3b6c6-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="3b6c6-106">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="3b6c6-106">Prerequisite</span></span>

<span data-ttu-id="3b6c6-107">Registros de contactos [de Common Data Service ingeridos en Dynamics 365 Marketing](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3b6c6-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="3b6c6-108">Configurar el conector para Marketing</span><span class="sxs-lookup"><span data-stu-id="3b6c6-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="3b6c6-109">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3b6c6-110">En **Dynamics 365 Marketing**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="3b6c6-111">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3b6c6-112">Introduzca la dirección URL de Marketing de su organización en el campo **Dirección del servidor**.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="3b6c6-113">En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="3b6c6-114">Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="3b6c6-115">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-115">Select **Next**.</span></span>

1. <span data-ttu-id="3b6c6-116">Elija uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="3b6c6-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3b6c6-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3b6c6-118">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="3b6c6-118">Export the data</span></span>

<span data-ttu-id="3b6c6-119">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3b6c6-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3b6c6-120">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3b6c6-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
