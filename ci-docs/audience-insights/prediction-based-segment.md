---
title: Segmentos basados en los resultados de predicción
description: Cree segmentos basados en la entidad de salida de un modelo predicción.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036440"
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