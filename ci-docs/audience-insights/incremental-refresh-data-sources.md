---
title: Actualización incremental para fuentes de datos basadas en Power Query
description: Actualice los datos nuevos y actualizados para grandes fuentes de datos basados en Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407039"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="470c9-103">Actualización incremental para fuentes de datos basadas en Power Query</span><span class="sxs-lookup"><span data-stu-id="470c9-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="470c9-104">La actualización incremental de las fuentes de datos ofrece las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="470c9-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="470c9-105">**Actualizaciones más rápidas** - Solo se actualizan los datos que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="470c9-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="470c9-106">Por ejemplo, puede actualizar solo los últimos cinco días de un conjunto de datos histórico.</span><span class="sxs-lookup"><span data-stu-id="470c9-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="470c9-107">**Mayor fiabilidad** - Con actualizaciones más pequeñas, no necesita mantener conexiones a sistemas de origen volátiles durante tanto tiempo, lo que reduce el riesgo de problemas de conexión.</span><span class="sxs-lookup"><span data-stu-id="470c9-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="470c9-108">**Reducción del consumo de recursos** - Actualizar solo un subconjunto de sus datos totales brinda un uso más eficiente de los recursos informáticos y disminuye la huella ambiental.</span><span class="sxs-lookup"><span data-stu-id="470c9-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="470c9-109">Configurar actualización incremental</span><span class="sxs-lookup"><span data-stu-id="470c9-109">Configure incremental refresh</span></span>

<span data-ttu-id="470c9-110">Las informaciones de público permiten la actualización incremental de las fuentes de datos importadas a través de Power Query que admiten la ingestión incremental.</span><span class="sxs-lookup"><span data-stu-id="470c9-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="470c9-111">Por ejemplo, las bases de datos Azure SQL con campos de fecha y hora que indican cuándo se actualizaron por última vez los registros de datos.</span><span class="sxs-lookup"><span data-stu-id="470c9-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="470c9-112">[Crea un nuevo origen de datos basado en Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="470c9-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="470c9-113">Proporcione un nombre para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="470c9-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="470c9-114">Seleccione un origen de datos que admita la actualización incremental, como la base de datos de Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="470c9-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="470c9-115">Seleccione las entidades o tablas para ingerir.</span><span class="sxs-lookup"><span data-stu-id="470c9-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="470c9-116">Complete los pasos de transformación y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="470c9-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="470c9-117">En el cuadro de diálogo **Configurar actualización incremental**, seleccione **Configurar** para abrir la **Configuración de actualización incremental**.</span><span class="sxs-lookup"><span data-stu-id="470c9-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="470c9-118">Si selecciona **Omitir**, el origen de datos actualizará todo el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="470c9-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="470c9-119">También puede aplicar una actualización incremental más tarde editando un origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="470c9-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="470c9-120">En **Configuración de actualización incremental**, configurará la actualización incremental para todas las entidades que seleccionó al crear el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="470c9-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="470c9-121">![Configurar entidades en un origen de datos para actualización incremental](media/incremental-refresh-settings.png "Configurar entidades en un origen de datos para actualización incremental")</span><span class="sxs-lookup"><span data-stu-id="470c9-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="470c9-122">Seleccione una entidad y proporcione los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="470c9-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="470c9-123">**Definir la clave principal**: Seleccione una clave principal para la entidad o tabla.</span><span class="sxs-lookup"><span data-stu-id="470c9-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="470c9-124">**Definir el campo "última actualización"**: Este campo solo mostrará atributos de tipo fecha u hora.</span><span class="sxs-lookup"><span data-stu-id="470c9-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="470c9-125">Seleccione un atributo que indique cuándo se actualizaron por última vez los registros.</span><span class="sxs-lookup"><span data-stu-id="470c9-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="470c9-126">Se utilizará para identificar los registros que se encuentran dentro del periodo de tiempo de actualización incremental.</span><span class="sxs-lookup"><span data-stu-id="470c9-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="470c9-127">**Buscar actualizaciones cada**: Especifique cuánto durará el periodo de tiempo de la actualización incremental.</span><span class="sxs-lookup"><span data-stu-id="470c9-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="470c9-128">Seleccione **Guardar** para completar la creación del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="470c9-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="470c9-129">La actualización de datos inicial será una actualización completa.</span><span class="sxs-lookup"><span data-stu-id="470c9-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="470c9-130">Posteriormente, la actualización incremental de datos se producirá como se configuró en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="470c9-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
