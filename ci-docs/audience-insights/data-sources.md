---
title: Usar orígenes de datos para ingerir datos
description: Aprenda a importar datos desde distintos orígenes.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887915"
---
# <a name="data-sources-overview"></a><span data-ttu-id="a3637-103">Información general de los orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="a3637-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a3637-104">La capacidad de información de público de Dynamics 365 Customer Insights se conecta a datos de un amplio conjunto de orígenes.</span><span class="sxs-lookup"><span data-stu-id="a3637-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="a3637-105">Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*.</span><span class="sxs-lookup"><span data-stu-id="a3637-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="a3637-106">Después de ingerir los datos, puede [unificar](data-unification.md) y actuar sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="a3637-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="a3637-107">Agregar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="a3637-107">Add a data source</span></span>

<span data-ttu-id="a3637-108">Consulte los artículos detallados sobre cómo agregar un origen de datos, según la opción que elija.</span><span class="sxs-lookup"><span data-stu-id="a3637-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="a3637-109">Puede agregar un origen de datos de tres formas principales:</span><span class="sxs-lookup"><span data-stu-id="a3637-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="a3637-110">A través de decenas de conectores de Power Query</span><span class="sxs-lookup"><span data-stu-id="a3637-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="a3637-111">Desde una carpeta de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="a3637-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="a3637-112">Desde su propio lago de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a3637-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="a3637-113">Agregar datos de orígenes de datos locales</span><span class="sxs-lookup"><span data-stu-id="a3637-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="a3637-114">La ingesta de datos de orígenes de datos locales en Audience Insights se admite según los flujos de datos de Power Platform.</span><span class="sxs-lookup"><span data-stu-id="a3637-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="a3637-115">Los flujos de datos se pueden habilitar en Customer Insights [proporcionando la dirección URL del entorno de Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) al configurar el entorno.</span><span class="sxs-lookup"><span data-stu-id="a3637-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="a3637-116">Los orígenes de datos que se crean después de asociar un entorno de Dataverse con Customer Insights utilizarán [flujos de datos de Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto.</span><span class="sxs-lookup"><span data-stu-id="a3637-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="a3637-117">Los flujos de datos admiten la conectividad local mediante las puertas de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="a3637-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="a3637-118">Quite y vuelva a crear los orígenes de datos que existían antes de que un entorno de Dataverse se asociara para utilizar las puertas de enlace de datos locales.</span><span class="sxs-lookup"><span data-stu-id="a3637-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="a3637-119">Las puertas de enlace de datos de un entorno de Power BI o Power Apps existente serán visibles y podrá reutilizarlas en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3637-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="a3637-120">La página de orígenes de datos muestra enlaces para ir al entorno de Power Platform donde puede ver y configurar puertas de enlace de datos locales.</span><span class="sxs-lookup"><span data-stu-id="a3637-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Captura de pantalla de la página de orígenes de datos que muestra enlaces que apuntan al entorno de Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="a3637-122">Revisar datos ingeridos</span><span class="sxs-lookup"><span data-stu-id="a3637-122">Review ingested data</span></span>

<span data-ttu-id="a3637-123">Podrá ver el nombre de cada origen de datos ingeridos, su estado y la última vez que se actualizaron los datos para ese origen.</span><span class="sxs-lookup"><span data-stu-id="a3637-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="a3637-124">Puede ordenar la lista de orígenes de datos por cada columna.</span><span class="sxs-lookup"><span data-stu-id="a3637-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3637-125">![Origen de datos agregado](media/configure-data-datasource-added.png "Origen de datos agregado")</span><span class="sxs-lookup"><span data-stu-id="a3637-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="a3637-126">Estado</span><span class="sxs-lookup"><span data-stu-id="a3637-126">Status</span></span>  |<span data-ttu-id="a3637-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3637-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="a3637-128">Operación correcta</span><span class="sxs-lookup"><span data-stu-id="a3637-128">Successful</span></span>   |<span data-ttu-id="a3637-129">El origen de datos se ingirió correctamente si se menciona una hora en la columna **Actualizado**.</span><span class="sxs-lookup"><span data-stu-id="a3637-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="a3637-130">Sin iniciar</span><span class="sxs-lookup"><span data-stu-id="a3637-130">Not started</span></span>   |<span data-ttu-id="a3637-131">El origen de datos aún no tiene datos ingeridos o sigue en modo de borrador.</span><span class="sxs-lookup"><span data-stu-id="a3637-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="a3637-132">Actualizando</span><span class="sxs-lookup"><span data-stu-id="a3637-132">Refreshing</span></span>    |<span data-ttu-id="a3637-133">La ingesta de datos está en curso.</span><span class="sxs-lookup"><span data-stu-id="a3637-133">Data ingestion is in progress.</span></span> <span data-ttu-id="a3637-134">Para cancelar esta operación, seleccione **Detener la actualización** en la columna **Acciones**.</span><span class="sxs-lookup"><span data-stu-id="a3637-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="a3637-135">Al detener la actualización de un origen de datos se revertirá a su último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="a3637-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="a3637-136">Con errores</span><span class="sxs-lookup"><span data-stu-id="a3637-136">Failed</span></span>     |<span data-ttu-id="a3637-137">Se han producido errores al ingerir datos.</span><span class="sxs-lookup"><span data-stu-id="a3637-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="a3637-138">Seleccione el valor en la columna **Estado** de cualquier origen de datos para revisar más detalles.</span><span class="sxs-lookup"><span data-stu-id="a3637-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="a3637-139">En el panel **Detalles del progreso**, expanda **Fuentes de datos**.</span><span class="sxs-lookup"><span data-stu-id="a3637-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="a3637-140">Seleccione **Ver detalles** para obtener más información sobre el estado de actualización, incluidos los detalles del error y las actualizaciones del proceso posterior.</span><span class="sxs-lookup"><span data-stu-id="a3637-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="a3637-141">La carga de datos puede tardar bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="a3637-141">Loading data can take some time.</span></span> <span data-ttu-id="a3637-142">Una vez completada una actualización, se pueden revisar los datos ingeridos en la página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="a3637-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="a3637-143">Para obtener más información, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="a3637-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="a3637-144">Actualizar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="a3637-144">Refresh a data source</span></span>

<span data-ttu-id="a3637-145">Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición.</span><span class="sxs-lookup"><span data-stu-id="a3637-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="a3637-146">Vaya a **Administrador** > **Sistema** > [**Programación**](system.md#schedule-tab) para configurar actualizaciones programadas de todos sus orígenes de datos ingeridos.</span><span class="sxs-lookup"><span data-stu-id="a3637-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="a3637-147">Para actualizar un origen de datos a petición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a3637-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="a3637-148">En informaciones de público, vaya a **Datos** > **Orígenes de datos**</span><span class="sxs-lookup"><span data-stu-id="a3637-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="a3637-149">Seleccione los puntos suspensivos verticales junto al origen de datos que desea actualizar y seleccione **Actualizar** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a3637-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="a3637-150">El origen de datos ahora se desencadena para una actualización manual.</span><span class="sxs-lookup"><span data-stu-id="a3637-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="a3637-151">Al actualizar un origen de datos, se actualizará tanto el esquema de la entidad como los datos para todas las entidades especificadas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a3637-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="a3637-152">Seleccione **Dejar de actualizar** si desea cancelar una actualización existente y el origen de datos volverá a su último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="a3637-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="a3637-153">Eliminar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="a3637-153">Delete a data source</span></span>

1. <span data-ttu-id="a3637-154">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="a3637-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a3637-155">Seleccione los puntos suspensivos verticales junto al origen de datos que desea quitar y seleccione **Eliminar** desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="a3637-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="a3637-156">Confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="a3637-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
