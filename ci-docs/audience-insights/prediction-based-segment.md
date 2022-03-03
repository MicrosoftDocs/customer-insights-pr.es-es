---
title: Segmentos basados en los resultados de predicción
description: Cree segmentos basados en la entidad de salida de un modelo predicción.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226684"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Cree un segmento basado en un modelo de predicción (versión preliminar)

Los resultados de las predicciones a veces solo se aplican a un subconjunto de sus clientes. Aumente la personalización de las recomendaciones creando segmentos a partir de los resultados de los modelos de predicción. Por ejemplo, es posible que desee dar recomendaciones específicas a los clientes que prefieren un determinado tipo de servicio. 

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.

- Un modelo de recomendación de productos, abandono de transacciones, abandono de suscripciones o valor de duración del cliente configurado en Customer Insights. Revise los requisitos para configurar los diferentes modelos:

  - [Modelo de recomendación de producto](predict-product-recommendation.md)
  - [Modelo de abandono de suscripción](predict-subscription-churn.md)
  - [Modelo de abandono transaccional](predict-transactional-churn.md)
  - [Modelo del valor de duración del cliente](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Crear un segmento de clientes basado en predicciones

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.

1. Seleccione los puntos suspensivos verticales junto al modelo que desea revisar y seleccione **Ver**.

1. En la página de resultados, seleccione **Crear segmento**. Para obtener más información sobre la página de resultados, revise el artículo sobre el modelo.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla de la página de resultados predicción con la acción Crear segmento resaltada.":::

1. Cree un nuevo segmento basado en la entidad del modelo seleccionado. Para obtener más información, vea [Crear y administrar segmentos](segments.md).