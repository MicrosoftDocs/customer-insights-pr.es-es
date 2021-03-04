---
title: Usar orígenes de datos para ingerir datos
description: Aprenda a importar datos desde distintos orígenes.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269719"
---
# <a name="data-sources-overview"></a><span data-ttu-id="6d1ea-103">Información general de los orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="6d1ea-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6d1ea-104">La capacidad de información de público de Dynamics 365 Customer Insights se conecta a datos de un amplio conjunto de orígenes.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="6d1ea-105">Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="6d1ea-106">Después de ingerir los datos, puede [unificar](data-unification.md) y actuar sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="6d1ea-107">Agregar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="6d1ea-107">Add a data source</span></span>

<span data-ttu-id="6d1ea-108">Consulte los artículos detallados sobre cómo agregar un origen de datos, según la opción que elija.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="6d1ea-109">Puede agregar un origen de datos de tres formas principales:</span><span class="sxs-lookup"><span data-stu-id="6d1ea-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="6d1ea-110">A través de decenas de conectores de Power Query</span><span class="sxs-lookup"><span data-stu-id="6d1ea-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="6d1ea-111">Desde una carpeta de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="6d1ea-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="6d1ea-112">Desde su propio lago de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6d1ea-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="6d1ea-113">Todavía no puede agregar datos de orígenes de datos locales.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="6d1ea-114">Revisar datos ingeridos</span><span class="sxs-lookup"><span data-stu-id="6d1ea-114">Review ingested data</span></span>

<span data-ttu-id="6d1ea-115">Podrá ver el nombre de cada origen de datos ingeridos, su estado y la última vez que se actualizaron los datos para ese origen.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="6d1ea-116">Puede ordenar la lista de orígenes de datos por cada columna.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6d1ea-117">![Origen de datos agregado](media/configure-data-datasource-added.png "Origen de datos agregado")</span><span class="sxs-lookup"><span data-stu-id="6d1ea-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="6d1ea-118">Estado</span><span class="sxs-lookup"><span data-stu-id="6d1ea-118">Status</span></span>  |<span data-ttu-id="6d1ea-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d1ea-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6d1ea-120">Operación correcta</span><span class="sxs-lookup"><span data-stu-id="6d1ea-120">Successful</span></span>   |<span data-ttu-id="6d1ea-121">El origen de datos se ingirió correctamente si se menciona una hora en la columna **Actualizado**.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="6d1ea-122">Sin iniciar</span><span class="sxs-lookup"><span data-stu-id="6d1ea-122">Not started</span></span>   |<span data-ttu-id="6d1ea-123">El origen de datos aún no tiene datos ingeridos o sigue en modo de borrador.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="6d1ea-124">Actualizando</span><span class="sxs-lookup"><span data-stu-id="6d1ea-124">Refreshing</span></span>    |<span data-ttu-id="6d1ea-125">La ingesta de datos está en curso.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-125">Data ingestion is in progress.</span></span> <span data-ttu-id="6d1ea-126">Para cancelar esta operación, seleccione **Detener la actualización** en la columna **Acciones**.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="6d1ea-127">Al detener la actualización de un origen de datos se revertirá a su último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="6d1ea-128">Con errores</span><span class="sxs-lookup"><span data-stu-id="6d1ea-128">Failed</span></span>     |<span data-ttu-id="6d1ea-129">Se han producido errores al ingerir datos.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="6d1ea-130">Seleccione el valor en la columna **Estado** de cualquier origen de datos para revisar más detalles.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="6d1ea-131">En el panel **Detalles del progreso**, expanda **Fuentes de datos**.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="6d1ea-132">Seleccione **Ver detalles** para obtener más información sobre el estado de actualización, incluidos los detalles del error y las actualizaciones del proceso posterior.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="6d1ea-133">La carga de datos puede tardar bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-133">Loading data can take some time.</span></span> <span data-ttu-id="6d1ea-134">Una vez completada una actualización, se pueden revisar los datos ingeridos en la página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="6d1ea-135">Para obtener más información, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="6d1ea-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="6d1ea-136">Actualizar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="6d1ea-136">Refresh a data source</span></span>

<span data-ttu-id="6d1ea-137">Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="6d1ea-138">Vaya a **Administrador** > **Sistema** > [**Programación**](system.md#schedule-tab) para configurar actualizaciones programadas de todos sus orígenes de datos ingeridos.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="6d1ea-139">Para actualizar un origen de datos a petición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6d1ea-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="6d1ea-140">En informaciones de público, vaya a **Datos** > **Orígenes de datos**</span><span class="sxs-lookup"><span data-stu-id="6d1ea-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="6d1ea-141">Seleccione los puntos suspensivos verticales junto al origen de datos que desea actualizar y seleccione **Actualizar** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="6d1ea-142">El origen de datos ahora se desencadena para una actualización manual.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="6d1ea-143">Actualizar un origen de datos actualizará tanto el esquema de entidad como los datos de todas las entidades especificadas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="6d1ea-144">Seleccione **Dejar de actualizar** si desea cancelar una actualización existente y el origen de datos volverá a su último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="6d1ea-145">Eliminar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="6d1ea-145">Delete a data source</span></span>

1. <span data-ttu-id="6d1ea-146">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6d1ea-147">Seleccione los puntos suspensivos verticales junto al origen de datos que desea quitar y seleccione **Eliminar** desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="6d1ea-148">Confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="6d1ea-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]