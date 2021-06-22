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
# <a name="manage-predictions"></a>Administrar predicciones

Este artículo analiza algunas de las tareas que comparten la mayoría de los escenarios predicción.

## <a name="troubleshoot-a-failed-prediction"></a>Solucionar problemas de una predicción con errores

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.

1. Seleccione los puntos suspensivos verticales junto a la predicción para la que desea ver los registros de errores.

1. Seleccione **Registros**.

1. Revisar todos los errores. Hay varios tipos de errores que pueden producirse, y describen qué condición causó el error. Por ejemplo, un error de que no hay suficientes datos para predecir con precisión generalmente se resuelve cargando datos adicionales en Customer Insights.

## <a name="input-data-usability-report"></a>Informe de facilidad de uso de datos de entrada

El informe de usabilidad de datos de entrada proporciona una vista consolidada de los errores y advertencias que pueden estar generando sus predicciones listas para usar. También ofrece recomendaciones sobre cómo mejorar el rendimiento del modelo.

El informe está disponible después de que un modelo haya completado su proceso de formación. Se crea para cada modelo por separado, independientemente de si se completó correctamente o no.

> [!NOTE]
> Actualmente, esta función solo funciona para el modelo Transaction Churn.

### <a name="view-the-input-data-usability-report"></a>Ver informe de facilidad de uso de datos de entrada

Una vez que un modelo listo para usar haya completado su paso de capacitación, vea el informe:
- Seleccione las elipses junto al nombre del modelo y elija **Informe de usabilidad de datos de entrada**.
- Seleccione el estado de un modelo seleccionando **Ver informe de usabilidad de datos de entrada** en el panel lateral.
- Seleccione uno de los modelos de la lista y seleccione **Informe de usabilidad de datos de entrada** en la barra de comandos.
- Abra la página de resultados del modelo y seleccione **Informe de usabilidad de datos de entrada** en la barra de comandos.

### <a name="information-in-the-input-data-usability-report"></a>Información en el informe de usabilidad de datos de entrada

Las siguientes columnas del informe contienen información útil para mejorar los datos del modelo.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ejemplo de un informe de usabilidad de datos de entrada que muestra una tabla con errores, advertencias y recomendaciones.":::

- Nombre: nombre descriptivo del error, advertencia o recomendación.
- Paso: Fase de modelo, formación o puntuación, a la que se refiere la información.
- Estado: Gravedad de la información (error, advertencia, recomendación).
- Nombre de la columna: columna de una entidad que debe modificarse para mejorar el rendimiento del modelo.
- Nombre de la entidad: nombre de la entidad que debe modificarse para mejorar el rendimiento del modelo.
- Detalles: detalles sobre el error, la advertencia o la recomendación.

## <a name="refresh-a-prediction"></a>Actualizar una predicción

Las predicciones se actualizarán automáticamente en la misma [programación que actualizan sus datos](system.md#schedule-tab) definida en la configuración. También puede actualizarlas manualmente.

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.

1. Seleccione los puntos suspensivos verticales junto a la predicción que desea actualizar.

1. Seleccione **Actualizar**.

## <a name="delete-a-prediction"></a>Eliminar una predicción

Eliminar un predicción también elimina su entidad de salida.

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.

1. Seleccione los puntos suspensivos verticales junto a la predicción que desea eliminar.

1. Seleccione **Eliminar**.
