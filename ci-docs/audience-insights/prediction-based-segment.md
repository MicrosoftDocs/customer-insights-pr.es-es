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
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741450"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="75612-103">Cree un segmento basado en un modelo de predicción (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="75612-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="75612-104">Los resultados de las predicciones a veces solo se aplican a un subconjunto de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="75612-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="75612-105">Aumente la personalización de las recomendaciones creando segmentos a partir de los resultados de los modelos de predicción.</span><span class="sxs-lookup"><span data-stu-id="75612-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="75612-106">Por ejemplo, es posible que desee dar recomendaciones específicas a los clientes que prefieren un determinado tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="75612-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="75612-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="75612-107">Prerequisites</span></span>

- <span data-ttu-id="75612-108">Al menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75612-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="75612-109">Un modelo de recomendación de productos, abandono de transacciones, abandono de suscripciones o valor de duración del cliente configurado en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75612-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="75612-110">Revise los requisitos para configurar los diferentes modelos:</span><span class="sxs-lookup"><span data-stu-id="75612-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="75612-111">Modelo de recomendación de producto</span><span class="sxs-lookup"><span data-stu-id="75612-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="75612-112">Modelo de abandono de suscripción</span><span class="sxs-lookup"><span data-stu-id="75612-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="75612-113">Modelo de abandono transaccional</span><span class="sxs-lookup"><span data-stu-id="75612-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="75612-114">Modelo del valor de duración del cliente</span><span class="sxs-lookup"><span data-stu-id="75612-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="75612-115">Crear un segmento de clientes basado en predicciones</span><span class="sxs-lookup"><span data-stu-id="75612-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="75612-116">Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="75612-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="75612-117">Seleccione los puntos suspensivos verticales junto al modelo que desea revisar y seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="75612-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="75612-118">En la página de resultados, seleccione **Crear segmento**.</span><span class="sxs-lookup"><span data-stu-id="75612-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="75612-119">Para obtener más información sobre la página de resultados, revise el artículo sobre el modelo.</span><span class="sxs-lookup"><span data-stu-id="75612-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla de la página de resultados predicción con la acción Crear segmento resaltada.":::

1. <span data-ttu-id="75612-121">Cree un nuevo segmento basado en la entidad del modelo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="75612-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="75612-122">Para obtener más información, vea [Crear y administrar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="75612-122">For more information, see [Create and manage segments](segments.md).</span></span>