---
title: Vista preliminar de predicciones
description: Predicción escenarios y opciones cubiertos por la aplicación Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610211"
---
# <a name="predictions-overview"></a>Vista preliminar de predicciones

Dynamics 365 Customer Insights viene con una variedad de opciones que aprovechan la inteligencia artificial y Aprendizaje automático para predecir datos.

## <a name="out-of-box-models"></a>Modelos listos para usar

La forma más fácil de comenzar a predecir datos son los modelos predefinidos, a menudo denominados modelos listos para usar. Solo requieren ciertos datos y estructura para generar información rápidamente. Están disponibles los siguientes modelos:

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

- [Valor de por vida del cliente](predict-customer-lifetime-value.md): predice los ingresos potenciales de un cliente durante toda la interacción con una empresa.
- [Recomendación de producto](predict-product-recommendation.md): sugiere conjuntos de recomendaciones de productos predictivas basadas en el comportamiento de compra y los clientes con patrones de compra similares.
- [Abandono de suscripción](predict-subscription-churn.md): predice si un cliente está en peligro por dejar de usar los productos o servicios de suscripción de su compañía.
- [Abandono transaccional](predict-transactional-churn.md): predice si un cliente individual ya no comprará sus productos o servicios en un determinado período de tiempo.
- [Análisis de sentimiento](sentiment-analysis.md): analiza el sentimiento de los comentarios de los clientes e identifica los aspectos comerciales que se mencionan con frecuencia.

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

- [Abandono transaccional](predict-transactional-churn.md): predice si una cuenta de cliente ya no comprará sus productos o servicios en un determinado período de tiempo.

---

> [!TIP]
> Le recomendamos que actualice regularmente los modelos listos para usar con datos actualizados para asegurarse de que informen con precisión su caso de uso empresarial. Los datos se actualizan ad-hoc cuando el sistema ingiere orígenes de datos nuevos o actualizados. Sin embargo, los modelos solo volverán a puntuar en este caso y seguirán utilizando los datos de entrenamiento existentes.
>
> Configure un **Horario de actualización** estableciendo el programa de reentrenamiento del modelo durante la configuración. El modelo se volverá a entrenar y puntuar en este horario, que puede cambiar en cualquier momento.

## <a name="azure-machine-learning-integration"></a>Integración con Azure Machine Learning

Si una organización ya usa escenarios Aprendizaje automático basados en experimentos Azure Machine Learning, la característica de modelos personalizados en Customer Insights ayuda a conectar los puntos. Cree flujos de trabajo que le ayudan a elegir los datos de los que desea generar información y asignar los resultados a sus perfiles de cliente unificado. Para más información, ver [Modelos personalizados de aprendizaje automático](custom-models.md).

## <a name="manage-existing-predictions"></a>Administrar predicciones existentes

Vaya a la página **Inteligencia** > **Predicciones**. Sobre la pestaña **Mis predicciones**, vea las predicciones que creó, su tipo predicción, el nombre de la entidad de salida, el estado, la última vez que se editó predicción y la última vez que se actualizaron los datos. Puede ordenar la lista de predicciones por cualquier columna.

Seleccione una predicción para ver las acciones disponibles.

:::image type="content" source="media/predictions.png" alt-text="Página Mis predicciones.":::

- **Edite** la predicción para cambiar sus propiedades.
- [**Actualice**](#refresh-a-prediction) la predicción para incluir los últimos datos.
- **Vea** los detalles de predicción.
- [**Informe de usabilidad de datos de entrada**](#view-the-input-data-usability-report) para ver errores, advertencias y recomendaciones.
- **Elimine** la predicción.

### <a name="refresh-a-prediction"></a>Actualizar una predicción

Las predicciones se pueden actualizar de forma automática o manualmente, a petición. Para actualizar manualmente todas las predicciones, seleccione **Refrescar todo**. Para actualizar manualmente una predicción, selecciónela y elija **Actualizar**. A [programar una actualización automática](schedule-refresh.md), vaya a **Administración** > **Sistema** > **Programar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Ver informe de facilidad de uso de datos de entrada

El informe de usabilidad de datos de entrada proporciona una vista consolidada de los errores y advertencias que pueden estar generando sus predicciones listas para usar. También ofrece recomendaciones sobre cómo mejorar el rendimiento del modelo.

El informe está disponible después de que un modelo haya completado su proceso de formación. Se crea para cada modelo por separado, independientemente de si se completó el entrenamiento correctamente o no.

Sobre la pestaña **Mis predicciones**, seleccione la predicción y elija **Informe de usabilidad de datos de entrada**. O desde la vista de detalles de predicción, seleccione **Informe de usabilidad de datos de entrada**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ejemplo de un informe de usabilidad de datos de entrada que muestra una tabla con errores, advertencias y recomendaciones.":::

El informe incluye:

- **Nombre**: nombre descriptivo del error, advertencia o recomendación.
- **Paso**: Fase de modelo, formación o puntuación, a la que se refiere la información.
- **Estado**: Gravedad de la información (error, advertencia, recomendación).
- **Nombre de la columna**: columna de una entidad que debe modificarse para mejorar el rendimiento del modelo.
- **Nombre de la entidad**: nombre de la entidad que debe modificarse para mejorar el rendimiento del modelo.
- **Detalles**: detalles sobre el error, la advertencia o la recomendación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
