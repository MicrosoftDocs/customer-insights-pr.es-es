---
title: Entidades y conjuntos de datos
description: Ver los datos en la página Entidades.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407015"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="57746-103">Entidades en la información de público</span><span class="sxs-lookup"><span data-stu-id="57746-103">Entities in audience insights</span></span>

<span data-ttu-id="57746-104">Después de [configurar los orígenes de datos](data-sources.md), vaya a la página **Entidades** para evaluar la calidad de los datos procesados.</span><span class="sxs-lookup"><span data-stu-id="57746-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="57746-105">Las entidades se consideran conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="57746-105">Entities are considered datasets.</span></span> <span data-ttu-id="57746-106">Múltiples capacidades de Dynamics 365 Customer Insights se construyen alrededor de estas entidades.</span><span class="sxs-lookup"><span data-stu-id="57746-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="57746-107">Revisarlas de cerca puede ayudarle a validar la salida de esas capacidades.</span><span class="sxs-lookup"><span data-stu-id="57746-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="57746-108">La página **Entidades** enumera entidades e incluye varias columnas:</span><span class="sxs-lookup"><span data-stu-id="57746-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="57746-109">**Nombre**: el nombre de la entidad de datos.</span><span class="sxs-lookup"><span data-stu-id="57746-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="57746-110">Si ve un símbolo de advertencia junto a un nombre de entidad, significa que los datos de esa entidad no se cargaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="57746-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="57746-111">**Origen**: El tipo de origen de datos que procesó la entidad</span><span class="sxs-lookup"><span data-stu-id="57746-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="57746-112">**Creada por**: Nombre de la persona que creó la entidad.</span><span class="sxs-lookup"><span data-stu-id="57746-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="57746-113">**Creado**: Fecha y hora de creación de la entidad</span><span class="sxs-lookup"><span data-stu-id="57746-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="57746-114">**Actualizada por**: Nombre de la persona que actualizó la entidad.</span><span class="sxs-lookup"><span data-stu-id="57746-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="57746-115">**Última actualización**: Fecha y hora de la última actualización de la entidad</span><span class="sxs-lookup"><span data-stu-id="57746-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="57746-116">**Última actualización**: fecha y hora de la última actualización de datos</span><span class="sxs-lookup"><span data-stu-id="57746-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="57746-117">Explorar los datos de una entidad específica</span><span class="sxs-lookup"><span data-stu-id="57746-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="57746-118">Seleccione una entidad para explorar los diferentes campos y registros incluidos en esa entidad.</span><span class="sxs-lookup"><span data-stu-id="57746-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="57746-119">![Seleccionar una entidad](media/data-manager-entities-data.png "Seleccionar una entidad")</span><span class="sxs-lookup"><span data-stu-id="57746-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="57746-120">La pestaña **Datos** está seleccionada de forma predeterminada y muestra una tabla con detalles sobre registros individuales de la entidad.</span><span class="sxs-lookup"><span data-stu-id="57746-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="57746-121">![Tabla de campos](media/data-manager-entities-fields.PNG "Tabla de campos")</span><span class="sxs-lookup"><span data-stu-id="57746-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="57746-122">La pestaña **Campos** muestra una tabla para revisar los detalles de la entidad seleccionada, como nombres de campo, tipos de datos y tipos.</span><span class="sxs-lookup"><span data-stu-id="57746-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="57746-123">La columna **Tipo** muestra los tipos asociados a Common Data Model, que son definidos automáticamente por el sistema o [asignados manualmente](map-entities.md) por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="57746-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="57746-124">Se trata de tipos semánticos que pueden diferir de los tipos de datos de los atributos: por ejemplo, el campo *Correo electrónico* siguiente tiene un tipo de datos *Texto*, pero su tipo de Common Data Model (semántico) puede ser *Email* o *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="57746-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="57746-125">Ambas tablas muestran solo un ejemplo de los datos de la entidad.</span><span class="sxs-lookup"><span data-stu-id="57746-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="57746-126">Para ver el conjunto de datos completo, vaya a la página **Orígenes de datos**, seleccione una entidad, seleccione **Editar** y, a continuación, vea los datos de esta entidad con el editor de Power Query como se explica en [Orígenes de datos](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="57746-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="57746-127">Para obtener más información sobre los datos procesados en la entidad, la columna **Resumen** proporciona algunas características importantes de los datos, como nulos, valores que faltan, valores únicos, recuentos y distribuciones, según corresponda a los datos.</span><span class="sxs-lookup"><span data-stu-id="57746-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="57746-128">Seleccione el icono de gráfico para ver el resumen de los datos.</span><span class="sxs-lookup"><span data-stu-id="57746-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="57746-129">![Símbolo de resumen](media/data-manager-entities-summary.png "Tabla de resumen de datos")</span><span class="sxs-lookup"><span data-stu-id="57746-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="57746-130">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="57746-130">Next step</span></span>

<span data-ttu-id="57746-131">Consulte el tema [Unificar](data-unification.md) para obtener información sobre cómo *asignar*, *emparejar* y *combinar* los datos procesados.</span><span class="sxs-lookup"><span data-stu-id="57746-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
