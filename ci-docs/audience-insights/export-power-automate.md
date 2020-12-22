---
title: Conector para Power Automate | Microsoft Docs
description: Cree flujos en Power Automate desde Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407004"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="293f3-103">Conector de Power Automate (vista previa)</span><span class="sxs-lookup"><span data-stu-id="293f3-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="293f3-104">Desencadene eventos específicos para que se produzcan automáticamente cuando cambien los datos y administre flujos más complejos directamente en [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="293f3-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="293f3-105">Desencadenadores de Power Automate</span><span class="sxs-lookup"><span data-stu-id="293f3-105">Power Automate triggers</span></span>

<span data-ttu-id="293f3-106">Puede usar una variedad de desencadenadores que le permiten crear flujos para automatizar tareas repetitivas, como notificaciones o acciones más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="293f3-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="293f3-107">Desencadenador cuando falla una actualización de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="293f3-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="293f3-108">Desencadenador cuando una actualización de origen de datos se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="293f3-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="293f3-109">Desencadenador cuando se cruza un umbral en un segmento.</span><span class="sxs-lookup"><span data-stu-id="293f3-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="293f3-110">El desencadenador se limita a cruzar por encima del umbral.</span><span class="sxs-lookup"><span data-stu-id="293f3-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="293f3-111">Desencadenador cuando se cruza un umbral en una medida empresarial.</span><span class="sxs-lookup"><span data-stu-id="293f3-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="293f3-112">El desencadenador se limita a cruzar por encima del umbral.</span><span class="sxs-lookup"><span data-stu-id="293f3-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="293f3-113">Desencadene cuando se completa una actualización (fuentes de datos, segmentos, medidas, ...).</span><span class="sxs-lookup"><span data-stu-id="293f3-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="293f3-114">Se desencadena cuando se completa una actualización del proceso de unificación (mapa, coincidencia, fusión).</span><span class="sxs-lookup"><span data-stu-id="293f3-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="293f3-115">[Configurar los desencadenadores en Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="293f3-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="293f3-116">Acciones de Power Automate</span><span class="sxs-lookup"><span data-stu-id="293f3-116">Power Automate actions</span></span>
<span data-ttu-id="293f3-117">El conector Power Automate proporciona otras acciones además de los desencadenantes disponibles.</span><span class="sxs-lookup"><span data-stu-id="293f3-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="293f3-118">Para obtener más información, vea el [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="293f3-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="293f3-119">Crear un flujo de Power Automate en informaciones de público</span><span class="sxs-lookup"><span data-stu-id="293f3-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="293f3-120">En las informaciones de público, vaya a **Administrador** > **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="293f3-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="293f3-121">En la página **Sistema**, seleccione la pestaña **Estado**.</span><span class="sxs-lookup"><span data-stu-id="293f3-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="293f3-122">En la sección **Orígenes de datos**, seleccione **Flujos** y **Crear un flujo** de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="293f3-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="293f3-123">![Conector de Power Automate que muestra la acción Crear un flujo](media/power-automate-connector-create-flow.png "Conector de Power Automate que muestra la acción Crear un flujo")</span><span class="sxs-lookup"><span data-stu-id="293f3-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="293f3-124">En Power Automate, seleccione uno de los desencadenadores disponibles para crear su flujo preferido.</span><span class="sxs-lookup"><span data-stu-id="293f3-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="293f3-125">Si está creando su primer flujo, primero deberá autenticarse con el conector de Power Automate.</span><span class="sxs-lookup"><span data-stu-id="293f3-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
