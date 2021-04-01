---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar la conexión a Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598130"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="e33bb-103">Conector para Dynamics 365 Sales (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="e33bb-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e33bb-104">Use sus datos de clientes para crear listas de marketing, realizar un seguimiento de los flujos de trabajo y enviar promociones con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e33bb-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="e33bb-105">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="e33bb-105">Prerequisite</span></span>

1. <span data-ttu-id="e33bb-106">Los registros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales.</span><span class="sxs-lookup"><span data-stu-id="e33bb-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="e33bb-107">Más información sobre cómo ingerir contactos en [Dynamics 365 Sales usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e33bb-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e33bb-108">La exportación de segmentos de las informaciones de público a Sales no creará nuevos registros de contactos en las instancias de Sales.</span><span class="sxs-lookup"><span data-stu-id="e33bb-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="e33bb-109">Los registros de contacto de Sales deben ingerirse en las informaciones de público y usarse como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e33bb-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e33bb-110">También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.</span><span class="sxs-lookup"><span data-stu-id="e33bb-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="e33bb-111">Configurar el conector para Sales</span><span class="sxs-lookup"><span data-stu-id="e33bb-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="e33bb-112">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="e33bb-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e33bb-113">En **Dynamics 365 Sales**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e33bb-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="e33bb-114">Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="e33bb-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e33bb-115">Introduzca la dirección URL de Sales de su organización en el campo **Dirección del servidor**.</span><span class="sxs-lookup"><span data-stu-id="e33bb-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e33bb-116">En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e33bb-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="e33bb-117">Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e33bb-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e33bb-118">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e33bb-118">Select **Next**.</span></span>

1. <span data-ttu-id="e33bb-119">Elija uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="e33bb-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="e33bb-120">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e33bb-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e33bb-121">Exportar los datos</span><span class="sxs-lookup"><span data-stu-id="e33bb-121">Export the data</span></span>

<span data-ttu-id="e33bb-122">Puede [exportar datos a petición](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e33bb-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e33bb-123">La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e33bb-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]