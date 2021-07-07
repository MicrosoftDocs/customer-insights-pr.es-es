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
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304717"
---
# <a name="data-sources-overview"></a><span data-ttu-id="96236-103">Información general de los orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="96236-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="96236-104">La capacidad de información de público de Dynamics 365 Customer Insights se conecta a datos de un amplio conjunto de orígenes.</span><span class="sxs-lookup"><span data-stu-id="96236-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="96236-105">Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*.</span><span class="sxs-lookup"><span data-stu-id="96236-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="96236-106">Después de ingerir los datos, puede [unificar](data-unification.md) y actuar sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="96236-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="96236-107">Agregar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="96236-107">Add a data source</span></span>

<span data-ttu-id="96236-108">Consulte los artículos detallados sobre cómo agregar un origen de datos, según la opción que elija.</span><span class="sxs-lookup"><span data-stu-id="96236-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="96236-109">Puede agregar un origen de datos de tres formas principales:</span><span class="sxs-lookup"><span data-stu-id="96236-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="96236-110">A través de decenas de conectores de Power Query</span><span class="sxs-lookup"><span data-stu-id="96236-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="96236-111">Desde una carpeta de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="96236-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="96236-112">Desde su propio lago de Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="96236-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="96236-113">Agregar datos de orígenes de datos locales</span><span class="sxs-lookup"><span data-stu-id="96236-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="96236-114">La ingesta de datos de orígenes de datos locales en Audience Insights se admite según los flujos de datos de Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="96236-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="96236-115">Los flujos de datos se pueden habilitar en Customer Insights [proporcionando la dirección URL del entorno de Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) al configurar el entorno.</span><span class="sxs-lookup"><span data-stu-id="96236-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="96236-116">Los orígenes de datos que se crean después de asociar un entorno de Dataverse con Customer Insights utilizarán [flujos de datos de Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto.</span><span class="sxs-lookup"><span data-stu-id="96236-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="96236-117">Los flujos de datos admiten conectividad local mediante la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="96236-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="96236-118">Quite y vuelva a crear los orígenes de datos que existían antes de que un entorno de Dataverse se asociara para [utilizar las puertas de enlace de datos locales](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="96236-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="96236-119">Las puertas de enlace de datos de un entorno de Power BI o Power Apps existente serán visibles y podrá reutilizarlas en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="96236-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="96236-120">La página de orígenes de datos muestra enlaces para ir al entorno de Microsoft Power Platform donde puede ver y configurar puertas de enlace de datos locales.</span><span class="sxs-lookup"><span data-stu-id="96236-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="96236-121">Revisar datos ingeridos</span><span class="sxs-lookup"><span data-stu-id="96236-121">Review ingested data</span></span>

<span data-ttu-id="96236-122">Podrá ver el nombre de cada origen de datos ingeridos, su estado y la última vez que se actualizaron los datos para ese origen.</span><span class="sxs-lookup"><span data-stu-id="96236-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="96236-123">Puede ordenar la lista de orígenes de datos por cada columna.</span><span class="sxs-lookup"><span data-stu-id="96236-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96236-124">![Origen de datos agregado](media/configure-data-datasource-added.png "Origen de datos agregado")</span><span class="sxs-lookup"><span data-stu-id="96236-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="96236-125">Estado</span><span class="sxs-lookup"><span data-stu-id="96236-125">Status</span></span>  |<span data-ttu-id="96236-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="96236-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="96236-127">Operación correcta</span><span class="sxs-lookup"><span data-stu-id="96236-127">Successful</span></span>   |<span data-ttu-id="96236-128">El origen de datos se ingirió correctamente si se menciona una hora en la columna **Actualizado**.</span><span class="sxs-lookup"><span data-stu-id="96236-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="96236-129">Sin iniciar</span><span class="sxs-lookup"><span data-stu-id="96236-129">Not started</span></span>   |<span data-ttu-id="96236-130">El origen de datos aún no tiene datos ingeridos o sigue en modo de borrador.</span><span class="sxs-lookup"><span data-stu-id="96236-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="96236-131">Actualizando</span><span class="sxs-lookup"><span data-stu-id="96236-131">Refreshing</span></span>    |<span data-ttu-id="96236-132">La ingesta de datos está en curso.</span><span class="sxs-lookup"><span data-stu-id="96236-132">Data ingestion is in progress.</span></span> <span data-ttu-id="96236-133">Para cancelar esta operación, seleccione **Detener la actualización** en la columna **Acciones**.</span><span class="sxs-lookup"><span data-stu-id="96236-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="96236-134">Al detener la actualización de un origen de datos se revertirá a su último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="96236-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="96236-135">Con errores</span><span class="sxs-lookup"><span data-stu-id="96236-135">Failed</span></span>     |<span data-ttu-id="96236-136">Se han producido errores al ingerir datos.</span><span class="sxs-lookup"><span data-stu-id="96236-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="96236-137">Seleccione el valor en la columna **Estado** de cualquier origen de datos para revisar más detalles.</span><span class="sxs-lookup"><span data-stu-id="96236-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="96236-138">En el panel **Detalles del progreso**, expanda **Fuentes de datos**.</span><span class="sxs-lookup"><span data-stu-id="96236-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="96236-139">Seleccione **Ver detalles** para obtener más información sobre el estado de actualización, incluidos los detalles del error y las actualizaciones del proceso posterior.</span><span class="sxs-lookup"><span data-stu-id="96236-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="96236-140">La carga de datos puede llevar tiempo.</span><span class="sxs-lookup"><span data-stu-id="96236-140">Loading data can take time.</span></span> <span data-ttu-id="96236-141">Una vez completada una actualización, se pueden revisar los datos ingeridos en la página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="96236-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="96236-142">Para obtener más información, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="96236-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="96236-143">Actualizar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="96236-143">Refresh a data source</span></span>

<span data-ttu-id="96236-144">Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición.</span><span class="sxs-lookup"><span data-stu-id="96236-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="96236-145">Vaya a **Administrador** > **Sistema** > [**Programación**](system.md#schedule-tab) para configurar actualizaciones programadas de todos sus orígenes de datos ingeridos.</span><span class="sxs-lookup"><span data-stu-id="96236-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="96236-146">Para actualizar un origen de datos a petición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="96236-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="96236-147">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="96236-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="96236-148">Seleccione los puntos suspensivos verticales junto al origen de datos que desea actualizar y seleccione **Actualizar** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="96236-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="96236-149">El origen de datos ahora se desencadena para una actualización manual.</span><span class="sxs-lookup"><span data-stu-id="96236-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="96236-150">Al actualizar un origen de datos, se actualizará tanto el esquema de la entidad como los datos para todas las entidades especificadas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="96236-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="96236-151">Seleccione **Dejar de actualizar** si desea cancelar una actualización existente y el origen de datos volverá a su último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="96236-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="96236-152">Eliminar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="96236-152">Delete a data source</span></span>

1. <span data-ttu-id="96236-153">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="96236-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="96236-154">Seleccione los puntos suspensivos verticales junto al origen de datos que desea quitar y seleccione **Eliminar** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="96236-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="96236-155">Confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="96236-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
