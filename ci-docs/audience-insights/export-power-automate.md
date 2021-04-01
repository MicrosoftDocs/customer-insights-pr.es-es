---
title: Conector para Power Automate | Microsoft Docs
description: Crear flujos en Microsoft Power Automate desde Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597946"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="23391-103">Conector de Power Automate (vista previa)</span><span class="sxs-lookup"><span data-stu-id="23391-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="23391-104">Desencadene eventos específicos para que se produzcan automáticamente cuando cambien los datos y administre flujos más complejos directamente en [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="23391-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="23391-105">Desencadenadores de Power Automate</span><span class="sxs-lookup"><span data-stu-id="23391-105">Power Automate triggers</span></span>

<span data-ttu-id="23391-106">Utilice desencadenadores para crear flujos de nube y automatizar tareas repetitivas, como notificaciones o acciones más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="23391-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="23391-107">Desencadenador cuando falla una actualización de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="23391-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="23391-108">Desencadenador cuando una actualización de origen de datos se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="23391-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="23391-109">Desencadenador cuando se cruza un umbral en un segmento.</span><span class="sxs-lookup"><span data-stu-id="23391-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="23391-110">El desencadenador se limita a cruzar por encima del umbral.</span><span class="sxs-lookup"><span data-stu-id="23391-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="23391-111">Desencadenador cuando se cruza un umbral en una medida empresarial.</span><span class="sxs-lookup"><span data-stu-id="23391-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="23391-112">El desencadenador se limita a cruzar por encima del umbral.</span><span class="sxs-lookup"><span data-stu-id="23391-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="23391-113">Desencadene cuando se completa una actualización (fuentes de datos, segmentos, medidas, ...).</span><span class="sxs-lookup"><span data-stu-id="23391-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="23391-114">Se desencadena cuando se completa una actualización del proceso de unificación (mapa, coincidencia, fusión).</span><span class="sxs-lookup"><span data-stu-id="23391-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="23391-115">[Configurar los desencadenadores en Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="23391-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="23391-116">Acciones de Power Automate</span><span class="sxs-lookup"><span data-stu-id="23391-116">Power Automate actions</span></span>
<span data-ttu-id="23391-117">El conector Power Automate proporciona otras acciones además de los desencadenantes disponibles.</span><span class="sxs-lookup"><span data-stu-id="23391-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="23391-118">Para obtener más información, vea el [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="23391-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="23391-119">Crea un flujo de Power Automate</span><span class="sxs-lookup"><span data-stu-id="23391-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="23391-120">En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="23391-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="23391-121">En el icono de **Power Automate**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="23391-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="23391-122">Se abre el conector de Customer Insights (versión preliminar) en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="23391-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="23391-123">**Iniciar sesión** en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="23391-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="23391-124">Elija uno de los desencadenadores disponibles y agregue más pasos a su nuevo flujo.</span><span class="sxs-lookup"><span data-stu-id="23391-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="23391-125">Para obtener más información, consulte [Crear un flujo de nube en Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="23391-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="23391-126">Ejemplos de cómo utilizar los flujos:</span><span class="sxs-lookup"><span data-stu-id="23391-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="23391-127">Publique un mensaje en un canal de Microsoft Teams si falla una actualización origen de datos.</span><span class="sxs-lookup"><span data-stu-id="23391-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="23391-128">Envíe un correo electrónico a los propietarios de los datos cuando se cruce un umbral en un segmento.</span><span class="sxs-lookup"><span data-stu-id="23391-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]