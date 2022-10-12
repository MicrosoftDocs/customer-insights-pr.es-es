---
title: Crear un segmento basado en un modelo de predicción
description: Cree segmentos basados en la entidad de salida de un modelo predicción.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610448"
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

1. Seleccione el modelo que desea revisar y seleccione **Ver**.

1. En la página de resultados, seleccione **Crear segmento**. Para obtener más información sobre la página de resultados, revise el artículo sobre el modelo.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla de la página de resultados predicción con la acción Crear segmento resaltada.":::

1. Cree un nuevo segmento usanod atributos de la entidad de salida del modelo seleccionado. Para obtener más información, vea [Crear y administrar segmentos](segments.md).

> [!TIP]
> También puede crear un segmento para un modelo predicción desde la página **Segmentos** seleccionando **Nuevo** y eligiendo **Crear desde** > **Inteligencia**. Para obtener más información, consulte [Crear un nuevo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
