---
title: Descripción general de los escenarios predicción admitidos
description: Predicción escenarios y opciones cubiertos por la aplicación Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647999"
---
# <a name="predictions-overview"></a>Vista preliminar de predicciones

Dynamics 365 Customer Insights viene con una variedad de opciones que aprovechan la inteligencia artificial y Aprendizaje automático para predecir datos. 

## <a name="out-of-box-models"></a>Modelos listos para usar

La forma más fácil de comenzar a predecir datos son los modelos predefinidos, a menudo denominados modelos listos para usar. Solo requieren ciertos datos y estructura para generar información rápidamente. Actualmente, están disponibles los siguientes modelos: 

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

- [Valor de por vida del cliente](predict-customer-lifetime-value.md): predice los ingresos potenciales de un cliente durante toda la interacción con una empresa.
- [Recomendación de producto](predict-product-recommendation.md): sugiere conjuntos de recomendaciones de productos predictivas basadas en el comportamiento de compra y los clientes con patrones de compra similares.
- [Abandono de suscripción](predict-subscription-churn.md): predice si un cliente está en peligro por dejar de usar los productos o servicios de suscripción de su compañía.
- [Abandono transaccional](predict-transactional-churn.md): predice si un cliente ya no comprará sus productos o servicios en un determinado período de tiempo.
- [Análisis de sentimiento](sentiment-analysis.md): analice el sentimiento de los comentarios de los clientes e identifique los aspectos comerciales que se mencionan con frecuencia.

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

- [Abandono transaccional](predict-transactional-churn.md): predice si un cliente ya no comprará sus productos o servicios en un determinado período de tiempo.

---

> [!TIP]
> Le recomendamos que actualice regularmente los modelos listos para usar con datos actualizados para asegurarse de que informen con precisión su caso de uso empresarial. Los datos se actualizan ad-hoc cuando el sistema ingiere orígenes de datos nuevos o actualizados. Sin embargo, los modelos solo volverán a puntuar en este caso y seguirán utilizando los datos de entrenamiento existentes.
> 
> Puede configurar un **Horario de actualización** estableciendo el programa de reentrenamiento del modelo en la experiencia de configuración. El modelo se volverá a entrenar y puntuar en este horario, que puede cambiar en cualquier momento.


## <a name="azure-machine-learning-integration"></a>Integración con Azure Machine Learning

Si una organización ya usa escenarios Aprendizaje automático basados en experimentos Azure Machine Learning, la característica de modelos personalizados en Customer Insights ayuda a conectar los puntos. Cree flujos de trabajo que le ayudan a elegir los datos de los que desea generar información y asignar los resultados a sus perfiles de cliente unificado. Para más información, ver [Modelos personalizados de aprendizaje automático](custom-models.md).

## <a name="ai-builder-prediction"></a>Predicción de AI Builder

A veces, los conjuntos de datos están incompletos y faltan algunos valores. Customer Insights puede ayudar a predecir los valores perdidos para la entidad y los segmentos del Cliente. Para obtener más información, consulte [Complete sus datos parciales con predicciones](predictions.md).
