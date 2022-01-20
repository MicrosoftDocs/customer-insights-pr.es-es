---
title: Descripción general de los escenarios predicción admitidos
description: Predicción escenarios y opciones cubiertos por la aplicación Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978034"
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


## <a name="azure-machine-learning-integration"></a>Integración con Azure Machine Learning

Si una organización ya usa escenarios Aprendizaje automático basados en experimentos Azure Machine Learning, la característica de modelos personalizados en Customer Insights ayuda a conectar los puntos. Cree flujos de trabajo que le ayudan a elegir los datos de los que desea generar información y asignar los resultados a sus perfiles de cliente unificado. Para más información, ver [Modelos personalizados de aprendizaje automático](custom-models.md).

## <a name="ai-builder-prediction"></a>Predicción AI Builder

A veces, los conjuntos de datos están incompletos y faltan algunos valores. Customer Insights puede ayudar a predecir los valores perdidos para la entidad y los segmentos del Cliente. Para obtener más información, consulte [Complete sus datos parciales con predicciones](predictions.md).
