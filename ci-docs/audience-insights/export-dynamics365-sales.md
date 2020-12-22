---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar la conexión a Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643839"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="498b2-103">Conector para Dynamics 365 Sales (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="498b2-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="498b2-104">Use sus datos de clientes para crear listas de marketing, realizar un seguimiento de los flujos de trabajo y enviar promociones con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="498b2-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="498b2-105">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="498b2-105">Prerequisite</span></span>

<span data-ttu-id="498b2-106">Registros de contactos [de Common Data Service ingeridos en Dynamics 365 Sales](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="498b2-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="498b2-107">Configurar el conector para Sales</span><span class="sxs-lookup"><span data-stu-id="498b2-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="498b2-108">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="498b2-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="498b2-109">En **Dynamics 365 Sales**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="498b2-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="498b2-110">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="498b2-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="498b2-111">Introduzca la dirección URL de Sales de su organización en el campo **Dirección del servidor**.</span><span class="sxs-lookup"><span data-stu-id="498b2-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="498b2-112">En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="498b2-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="498b2-113">Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="498b2-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="498b2-114">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="498b2-114">Select **Next**.</span></span>

1. <span data-ttu-id="498b2-115">Elija uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="498b2-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="498b2-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="498b2-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="498b2-117">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="498b2-117">Export the data</span></span>

<span data-ttu-id="498b2-118">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="498b2-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="498b2-119">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="498b2-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
