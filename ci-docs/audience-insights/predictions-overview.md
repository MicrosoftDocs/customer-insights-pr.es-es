---
title: Descripción general de los escenarios predicción admitidos
description: Predicción escenarios y opciones cubiertos por la aplicación Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095753"
---
# <a name="predictions-overview"></a><span data-ttu-id="02b1a-103">Vista preliminar de predicciones</span><span class="sxs-lookup"><span data-stu-id="02b1a-103">Predictions overview</span></span>

<span data-ttu-id="02b1a-104">Dynamics 365 Customer Insights viene con una variedad de opciones que aprovechan la inteligencia artificial y Aprendizaje automático para predecir datos.</span><span class="sxs-lookup"><span data-stu-id="02b1a-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="02b1a-105">Modelos listos para usar</span><span class="sxs-lookup"><span data-stu-id="02b1a-105">Out-of-box models</span></span>

<span data-ttu-id="02b1a-106">La forma más fácil de comenzar a predecir datos son los modelos predefinidos, a menudo denominados modelos listos para usar.</span><span class="sxs-lookup"><span data-stu-id="02b1a-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="02b1a-107">Solo requieren ciertos datos y estructura para generar información rápidamente.</span><span class="sxs-lookup"><span data-stu-id="02b1a-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="02b1a-108">Actualmente, están disponibles los siguientes modelos:</span><span class="sxs-lookup"><span data-stu-id="02b1a-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="02b1a-109">[Valor de por vida del cliente](predict-customer-lifetime-value.md): predice los ingresos potenciales de un cliente durante toda la interacción con una empresa.</span><span class="sxs-lookup"><span data-stu-id="02b1a-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="02b1a-110">[Recomendación de producto](predict-product-recommendation.md): sugiere conjuntos de recomendaciones de productos predictivas basadas en el comportamiento de compra y los clientes con patrones de compra similares.</span><span class="sxs-lookup"><span data-stu-id="02b1a-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="02b1a-111">[Abandono de suscripción](predict-subscription-churn.md): predice si un cliente está en peligro por dejar de usar los productos o servicios de suscripción de su compañía.</span><span class="sxs-lookup"><span data-stu-id="02b1a-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="02b1a-112">[Abandono transaccional](predict-transactional-churn.md): predice si un cliente ya no comprará sus productos o servicios en un determinado período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="02b1a-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="02b1a-113">Integración con Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="02b1a-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="02b1a-114">Si una organización ya usa escenarios Aprendizaje automático basados en experimentos Azure Machine Learning, la característica de modelos personalizados en Customer Insights ayuda a conectar los puntos.</span><span class="sxs-lookup"><span data-stu-id="02b1a-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="02b1a-115">Cree flujos de trabajo que le ayudan a elegir los datos de los que desea generar información y asignar los resultados a sus perfiles de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="02b1a-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="02b1a-116">Para más información, ver [Modelos personalizados de aprendizaje automático](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="02b1a-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="02b1a-117">Predicción AI Builder</span><span class="sxs-lookup"><span data-stu-id="02b1a-117">AI Builder prediction</span></span>

<span data-ttu-id="02b1a-118">A veces, los conjuntos de datos están incompletos y faltan algunos valores.</span><span class="sxs-lookup"><span data-stu-id="02b1a-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="02b1a-119">Customer Insights puede ayudar a predecir los valores perdidos para la entidad y los segmentos del Cliente.</span><span class="sxs-lookup"><span data-stu-id="02b1a-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="02b1a-120">Para obtener más información, consulte [Complete sus datos parciales con predicciones](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="02b1a-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
