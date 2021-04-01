---
title: Ingestión y limitaciones de datos en tiempo real
description: Información general sobre las capacidades en tiempo real en las informaciones de público.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598590"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="cc51a-103">Ingesta de datos en tiempo real (vista previa)</span><span class="sxs-lookup"><span data-stu-id="cc51a-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="cc51a-104">La funcionalidad casi en tiempo real le permite ver, en segundos, las últimas interacciones que sus clientes han realizado con sus productos o servicios.</span><span class="sxs-lookup"><span data-stu-id="cc51a-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="cc51a-105">Las [actualizaciones programadas](system.md#schedule-tab) incluyen una gran cantidad de registros y varias operaciones complejas.</span><span class="sxs-lookup"><span data-stu-id="cc51a-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="cc51a-106">Primero, los datos se extraen del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cc51a-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="cc51a-107">A continuación, los datos se unifican y luego se enriquecen con información adicional.</span><span class="sxs-lookup"><span data-stu-id="cc51a-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="cc51a-108">Cada ejecución de este proceso puede llevar de minutos a horas.</span><span class="sxs-lookup"><span data-stu-id="cc51a-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="cc51a-109">La funcionalidad en tiempo real proporciona datos inmediatamente para su empleo, hasta que la actualización programada posterior extrae estos datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cc51a-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="cc51a-110">Las actualizaciones en tiempo real tienen un tiempo de caducidad después del cual ya no anulan el valor de origen de datos:</span><span class="sxs-lookup"><span data-stu-id="cc51a-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="cc51a-111">Las actualizaciones de perfil se mantendrán durante 4 horas.</span><span class="sxs-lookup"><span data-stu-id="cc51a-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="cc51a-112">Las actividades se mantendrán durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="cc51a-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="cc51a-113">Estos valores son parámetros de llamada de API que puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="cc51a-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="cc51a-114">Su objetivo es garantizar que sus datos de origen sigan siendo su fuente de verdad.</span><span class="sxs-lookup"><span data-stu-id="cc51a-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="cc51a-115">Si desea que las actualizaciones en tiempo real se incluyan durante más tiempo, debe agregarlas a un origen de datos para que se extraigan durante la próxima actualización programada.</span><span class="sxs-lookup"><span data-stu-id="cc51a-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="cc51a-116">Actualización en tiempo real de los campos unificados del perfil del cliente</span><span class="sxs-lookup"><span data-stu-id="cc51a-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="cc51a-117">Los perfiles actualizados se mostrarán en la vista de la tarjeta del cliente, o en cualquier otra visualización, en unos segundos.</span><span class="sxs-lookup"><span data-stu-id="cc51a-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="cc51a-118">Debido a que las operaciones en tiempo real tienen lugar después de la unificación de datos, solo se aplican a los perfiles de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="cc51a-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="cc51a-119">En consecuencia, los cambios de perfil en tiempo real no actualizarán medidas, la pertenencia de segmentos o los enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="cc51a-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="cc51a-120">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="cc51a-120">Limitations</span></span>

- <span data-ttu-id="cc51a-121">Los perfiles de clientes pueden actualizarse, pero no crearse ni eliminarse.</span><span class="sxs-lookup"><span data-stu-id="cc51a-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="cc51a-122">Exportar actualizaciones en tiempo real a sistemas externos, como Power BI, no es posible por el momento.</span><span class="sxs-lookup"><span data-stu-id="cc51a-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="cc51a-123">Creación de actividades en tiempo real</span><span class="sxs-lookup"><span data-stu-id="cc51a-123">Real-time creation of activities</span></span>

<span data-ttu-id="cc51a-124">La API en tiempo real le permite publicar una nueva actividad desde su sistema de origen (un registro de origen individual) en un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="cc51a-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="cc51a-125">La nueva actividad estará disponible como una actividad unificada en la línea de tiempo de ese perfil de cliente unificado en cuestión de segundos.</span><span class="sxs-lookup"><span data-stu-id="cc51a-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="cc51a-126">Puede ver la línea de tiempo en la vista de la tarjeta del cliente o cualquier otra integración de línea de tiempo que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="cc51a-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="cc51a-127">Las actividades son inmutables.</span><span class="sxs-lookup"><span data-stu-id="cc51a-127">Activities are immutable.</span></span> <span data-ttu-id="cc51a-128">No cambian una vez que se crean.</span><span class="sxs-lookup"><span data-stu-id="cc51a-128">They don't change once created.</span></span>
> - <span data-ttu-id="cc51a-129">Actualmente, los segmentos y las medidas no se actualizan en función de la nueva actividad.</span><span class="sxs-lookup"><span data-stu-id="cc51a-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="cc51a-130">Las actividades agregadas solo a través de la API en tiempo real no son parte de las exportaciones y no se mostrarán en PowerBI.</span><span class="sxs-lookup"><span data-stu-id="cc51a-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="cc51a-131">Hay dos formas de conectar con la API de tiempo real:</span><span class="sxs-lookup"><span data-stu-id="cc51a-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="cc51a-132">[indirectamente](#connect-via-the-dynamics-365-customer-insights-connector), utilizando el [conector de Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="cc51a-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="cc51a-133">[directamente](#connect-directly-to-the-real-time-api), con código</span><span class="sxs-lookup"><span data-stu-id="cc51a-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="cc51a-134">Ambas formas comparten los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="cc51a-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="cc51a-135">Un entorno de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="cc51a-135">A Customer Insights environment</span></span>
- <span data-ttu-id="cc51a-136">Perfiles de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="cc51a-136">Unified customer profiles</span></span>
- <span data-ttu-id="cc51a-137">Actividades configuradas y ejecutadas</span><span class="sxs-lookup"><span data-stu-id="cc51a-137">Activities configured and run</span></span>
- <span data-ttu-id="cc51a-138">Permisos de colaborador o administrador para autenticar su cuenta</span><span class="sxs-lookup"><span data-stu-id="cc51a-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="cc51a-139">Conectarse a través del conector de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="cc51a-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="cc51a-140">La API en tiempo real puede ingerir datos de un conector de Power Platform exclusivo, el [conector de Dynamics 365 Customer Insights](/connectors/customerinsights/), sin la necesidad de escribir e implementar ningún código.</span><span class="sxs-lookup"><span data-stu-id="cc51a-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="cc51a-141">El conector puede realizar las mismas acciones en tiempo real que la API.</span><span class="sxs-lookup"><span data-stu-id="cc51a-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="cc51a-142">Necesita una licencia válida para conectores premium.</span><span class="sxs-lookup"><span data-stu-id="cc51a-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="cc51a-143">Para obtener más información, consulte [Preguntas más frecuentes sobre licencias de Power Apps y Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="cc51a-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="cc51a-144">[Power Apps o Power Automate](/connectors/) de Power Platform</span><span class="sxs-lookup"><span data-stu-id="cc51a-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="cc51a-145">[Aplicaciones lógicas](/azure/connectors/apis-list) de Azure</span><span class="sxs-lookup"><span data-stu-id="cc51a-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="cc51a-146">Para obtener detalles sobre la creación de flujos, consulte la [documentación de Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="cc51a-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="cc51a-147">Conectarse directamente a la API en tiempo real</span><span class="sxs-lookup"><span data-stu-id="cc51a-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="cc51a-148">Puede utilizar las capacidades en tiempo real creando su propia canalización y conectándose directamente a la API de tiempo real.</span><span class="sxs-lookup"><span data-stu-id="cc51a-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="cc51a-149">Puede publicar una actividad en el formato de su sistema de origen o en el formato UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="cc51a-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="cc51a-150">Obtenga el formato haciendo una llamada API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="cc51a-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="cc51a-151">Los detalles de esta API, incluidos los parámetros y las respuestas, se pueden encontrar en la sección **EntityData** de la [referencia de las API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="cc51a-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="cc51a-152">Para obtener más información, consulte [Trabajar con la API de Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="cc51a-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="cc51a-153">Comprendar el uso en tiempo real con telemetría</span><span class="sxs-lookup"><span data-stu-id="cc51a-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="cc51a-154">Obtenga una descripción general del volumen de solicitudes a la API de tiempo real e información sobre los problemas que puede encontrar el sistema.</span><span class="sxs-lookup"><span data-stu-id="cc51a-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="cc51a-155">Puede [acceder a la telemetría en tiempo real](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="cc51a-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]