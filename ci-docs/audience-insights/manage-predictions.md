---
title: Tareas compartidas para escenarios predicción
description: Aprenda a administrar, solucionar problemas y perfeccionar las predicciones.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095754"
---
# <a name="manage-predictions"></a><span data-ttu-id="d2822-103">Administrar predicciones</span><span class="sxs-lookup"><span data-stu-id="d2822-103">Manage predictions</span></span>

<span data-ttu-id="d2822-104">Este artículo analiza algunas de las tareas que comparten la mayoría de los escenarios predicción.</span><span class="sxs-lookup"><span data-stu-id="d2822-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="d2822-105">Solucionar problemas de una predicción con errores</span><span class="sxs-lookup"><span data-stu-id="d2822-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="d2822-106">Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="d2822-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d2822-107">Seleccione los puntos suspensivos verticales junto a la predicción para la que desea ver los registros de errores.</span><span class="sxs-lookup"><span data-stu-id="d2822-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="d2822-108">Seleccione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="d2822-108">Select **Logs**.</span></span>

1. <span data-ttu-id="d2822-109">Revisar todos los errores.</span><span class="sxs-lookup"><span data-stu-id="d2822-109">Review all the errors.</span></span> <span data-ttu-id="d2822-110">Hay varios tipos de errores que pueden producirse, y describen qué condición causó el error.</span><span class="sxs-lookup"><span data-stu-id="d2822-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="d2822-111">Por ejemplo, un error de que no hay suficientes datos para predecir con precisión generalmente se resuelve cargando datos adicionales en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d2822-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="d2822-112">Informe de facilidad de uso de datos de entrada</span><span class="sxs-lookup"><span data-stu-id="d2822-112">Input data usability report</span></span>

<span data-ttu-id="d2822-113">El informe de usabilidad de datos de entrada proporciona una vista consolidada de los errores y advertencias que pueden estar generando sus predicciones listas para usar.</span><span class="sxs-lookup"><span data-stu-id="d2822-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="d2822-114">También ofrece recomendaciones sobre cómo mejorar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d2822-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="d2822-115">El informe está disponible después de que un modelo haya completado su proceso de formación.</span><span class="sxs-lookup"><span data-stu-id="d2822-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="d2822-116">Se crea para cada modelo por separado, independientemente de si se completó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="d2822-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="d2822-117">Actualmente, esta función solo funciona para el modelo Transaction Churn.</span><span class="sxs-lookup"><span data-stu-id="d2822-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="d2822-118">Ver informe de facilidad de uso de datos de entrada</span><span class="sxs-lookup"><span data-stu-id="d2822-118">View the input data usability report</span></span>

<span data-ttu-id="d2822-119">Una vez que un modelo listo para usar haya completado su paso de capacitación, vea el informe:</span><span class="sxs-lookup"><span data-stu-id="d2822-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="d2822-120">Seleccione las elipses junto al nombre del modelo y elija **Informe de usabilidad de datos de entrada**.</span><span class="sxs-lookup"><span data-stu-id="d2822-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="d2822-121">Seleccione el estado de un modelo seleccionando **Ver informe de usabilidad de datos de entrada** en el panel lateral.</span><span class="sxs-lookup"><span data-stu-id="d2822-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="d2822-122">Seleccione uno de los modelos de la lista y seleccione **Informe de usabilidad de datos de entrada** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="d2822-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="d2822-123">Abra la página de resultados del modelo y seleccione **Informe de usabilidad de datos de entrada** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="d2822-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="d2822-124">Información en el informe de usabilidad de datos de entrada</span><span class="sxs-lookup"><span data-stu-id="d2822-124">Information in the input data usability report</span></span>

<span data-ttu-id="d2822-125">Las siguientes columnas del informe contienen información útil para mejorar los datos del modelo.</span><span class="sxs-lookup"><span data-stu-id="d2822-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ejemplo de un informe de usabilidad de datos de entrada que muestra una tabla con errores, advertencias y recomendaciones.":::

- <span data-ttu-id="d2822-127">Nombre: nombre descriptivo del error, advertencia o recomendación.</span><span class="sxs-lookup"><span data-stu-id="d2822-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="d2822-128">Paso: Fase de modelo, formación o puntuación, a la que se refiere la información.</span><span class="sxs-lookup"><span data-stu-id="d2822-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="d2822-129">Estado: Gravedad de la información (error, advertencia, recomendación).</span><span class="sxs-lookup"><span data-stu-id="d2822-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="d2822-130">Nombre de la columna: columna de una entidad que debe modificarse para mejorar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d2822-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d2822-131">Nombre de la entidad: nombre de la entidad que debe modificarse para mejorar el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="d2822-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d2822-132">Detalles: detalles sobre el error, la advertencia o la recomendación.</span><span class="sxs-lookup"><span data-stu-id="d2822-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="d2822-133">Actualizar una predicción</span><span class="sxs-lookup"><span data-stu-id="d2822-133">Refresh a prediction</span></span>

<span data-ttu-id="d2822-134">Las predicciones se actualizarán automáticamente en la misma [programación que actualizan sus datos](system.md#schedule-tab) definida en la configuración.</span><span class="sxs-lookup"><span data-stu-id="d2822-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="d2822-135">También puede actualizarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="d2822-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="d2822-136">Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="d2822-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d2822-137">Seleccione los puntos suspensivos verticales junto a la predicción que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="d2822-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="d2822-138">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="d2822-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="d2822-139">Eliminar una predicción</span><span class="sxs-lookup"><span data-stu-id="d2822-139">Delete a prediction</span></span>

<span data-ttu-id="d2822-140">Eliminar un predicción también elimina su entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="d2822-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="d2822-141">Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="d2822-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d2822-142">Seleccione los puntos suspensivos verticales junto a la predicción que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="d2822-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="d2822-143">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d2822-143">Select **Delete**.</span></span>
