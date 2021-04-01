---
title: Buscar clientes similares con IA
description: Busque segmentos de clientes similares con inteligencia artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596796"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="499d9-103">Clientes similares (vista previa)</span><span class="sxs-lookup"><span data-stu-id="499d9-103">Similar Customers (preview)</span></span>

<span data-ttu-id="499d9-104">Esta característica le permite buscar clientes similares en su base de clientes utilizando inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="499d9-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="499d9-105">Debe tener al menos un segmento creado para usar esta función.</span><span class="sxs-lookup"><span data-stu-id="499d9-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="499d9-106">Ampliar los criterios de un segmento existente ayuda a encontrar clientes que sean similares a ese segmento.</span><span class="sxs-lookup"><span data-stu-id="499d9-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="499d9-107">*Buscar clientes similares* utiliza medios automatizados para evaluar datos y hacer predicciones basadas en esos datos y, por lo tanto, tiene la capacidad de usarse como método de creación de perfiles, tal como lo define el Reglamento General de Protección de Datos ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="499d9-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="499d9-108">El uso de esta función por parte del cliente para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones.</span><span class="sxs-lookup"><span data-stu-id="499d9-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="499d9-109">Usted es responsable de garantizar que el uso de Dynamics 365 Customer Insights, incluidas las predicciones, cumple con todas las leyes y regulaciones aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="499d9-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="499d9-110">Buscar clientes similares</span><span class="sxs-lookup"><span data-stu-id="499d9-110">Finding similar customers</span></span>

1. <span data-ttu-id="499d9-111">En las informaciones de público, vaya a **Segmentos** y seleccione el segmento en el que desea basar su nuevo segmento.</span><span class="sxs-lookup"><span data-stu-id="499d9-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="499d9-112">Ese es su *segmento de origen*.</span><span class="sxs-lookup"><span data-stu-id="499d9-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="499d9-113">En la barra de acción, seleccione **Buscar clientes similares**.</span><span class="sxs-lookup"><span data-stu-id="499d9-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="499d9-114">Revise el nombre sugerido para su nuevo segmento y cámbielo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="499d9-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="499d9-115">Revise los campos que definen su nuevo segmento.</span><span class="sxs-lookup"><span data-stu-id="499d9-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="499d9-116">Estos campos definen la base sobre la cual el sistema intentará encontrar clientes similares a su segmento de origen.</span><span class="sxs-lookup"><span data-stu-id="499d9-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="499d9-117">El sistema seleccionará los campos recomendados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="499d9-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="499d9-118">Los campos que pueden reducir significativamente el rendimiento del modelo se excluyen automáticamente:</span><span class="sxs-lookup"><span data-stu-id="499d9-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="499d9-119">Campos con los siguientes tipos de datos: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="499d9-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="499d9-120">Campos con una cardinalidad (el número de elementos en un campo) de menos de 2 o más de 30</span><span class="sxs-lookup"><span data-stu-id="499d9-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="499d9-121">Elija si quiere incluir **Todos los clientes** o solo clientes de un **Segmento existente específico** en su nuevo segmento.</span><span class="sxs-lookup"><span data-stu-id="499d9-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="499d9-122">Excluya a los clientes en su segmento de origen seleccionando la casilla **Excluir a todos del segmento de origen**.</span><span class="sxs-lookup"><span data-stu-id="499d9-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="499d9-123">Por defecto, el sistema sugiere incluir solo el 20% del tamaño audiencia objetivo en su salida.</span><span class="sxs-lookup"><span data-stu-id="499d9-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="499d9-124">Edite este umbral según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="499d9-124">Edit this threshold as needed.</span></span> <span data-ttu-id="499d9-125">Aumentar el umbral reducirá la precisión.</span><span class="sxs-lookup"><span data-stu-id="499d9-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="499d9-126">Seleccione **Ejecutar** en la parte inferior de la página para iniciar una tarea de clasificación binaria (un método de aprendizaje automático) que analice el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="499d9-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="499d9-127">Ver el segmento similar</span><span class="sxs-lookup"><span data-stu-id="499d9-127">View the similar segment</span></span>

<span data-ttu-id="499d9-128">Después de procesar el segmento similar, encontrará el nuevo segmento en la lista de la página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="499d9-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="499d9-129">![Segmento de clientes similares](media/expanded-segment.png "Segmento de clientes similares")</span><span class="sxs-lookup"><span data-stu-id="499d9-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="499d9-130">Seleccione **Ver** en la barra de acción para abrir el detalle del segmento.</span><span class="sxs-lookup"><span data-stu-id="499d9-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="499d9-131">Esta vista contiene información sobre la distribución de resultados en [puntuaciones de similitud](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="499d9-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="499d9-132">También encontrará los valores de puntuación de similitud en la **Vista previa de miembros del segmento**.</span><span class="sxs-lookup"><span data-stu-id="499d9-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="499d9-133">Use la salida de un segmento similar</span><span class="sxs-lookup"><span data-stu-id="499d9-133">Use the output of a similar segment</span></span>

<span data-ttu-id="499d9-134">Puede [trabajar con la salida de un segmento similar](segments.md) igual que con otros segmentos.</span><span class="sxs-lookup"><span data-stu-id="499d9-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="499d9-135">Por ejemplo, exporte el segmento o cree una medida.</span><span class="sxs-lookup"><span data-stu-id="499d9-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="499d9-136">Actualizar y editar un segmento similar</span><span class="sxs-lookup"><span data-stu-id="499d9-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="499d9-137">Para actualizar un segmento similar, selecciónelo en la página **Segmentos** y seleccione **Actualizar** en la barra de acción.</span><span class="sxs-lookup"><span data-stu-id="499d9-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="499d9-138">Editar un segmento similar volverá a procesar sus datos.</span><span class="sxs-lookup"><span data-stu-id="499d9-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="499d9-139">El segmento creado anteriormente se actualiza con datos actualizados.</span><span class="sxs-lookup"><span data-stu-id="499d9-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="499d9-140">Para editar un segmento similar, selecciónelo en la página **Segmentos** y seleccione **Editar** en la barra de acción.</span><span class="sxs-lookup"><span data-stu-id="499d9-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="499d9-141">Aplique los cambios y seleccione **Ejecutar** para comenzar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="499d9-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="499d9-142">Eliminar un segmento similar</span><span class="sxs-lookup"><span data-stu-id="499d9-142">Delete a similar segment</span></span>

<span data-ttu-id="499d9-143">Seleccione el segmento en la página **Segmentos** y seleccione **Eliminar** en la barra de acción.</span><span class="sxs-lookup"><span data-stu-id="499d9-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="499d9-144">A continuación, confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="499d9-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="499d9-145">Acerca de puntuaciones de similitud</span><span class="sxs-lookup"><span data-stu-id="499d9-145">About similarity scores</span></span>

<span data-ttu-id="499d9-146">El modelo de aprendizaje automático de clasificación binaria asigna una puntuación a los clientes del segmento similar.</span><span class="sxs-lookup"><span data-stu-id="499d9-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="499d9-147">La puntuación se basa en la similitud con los clientes del segmento de origen.</span><span class="sxs-lookup"><span data-stu-id="499d9-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="499d9-148">Las puntuaciones de similitud por debajo de 0,55 son clientes que el sistema clasificó como *no similares* a clientes del segmento de origen</span><span class="sxs-lookup"><span data-stu-id="499d9-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="499d9-149">Las puntuaciones de similitud entre 0,55 - 0,7 se clasifican como *algo similares*</span><span class="sxs-lookup"><span data-stu-id="499d9-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="499d9-150">Las puntuaciones de similitud entre 0,7 - 0,85 se clasifican como *similares*</span><span class="sxs-lookup"><span data-stu-id="499d9-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="499d9-151">Las puntuaciones de similitud entre 0,85 - 1 son clientes que el sistema clasificó como *muy similares*</span><span class="sxs-lookup"><span data-stu-id="499d9-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="499d9-152">Los clientes con puntuaciones de similitud inferiores a 0,4 no se incluyen en el resultado del modelo.</span><span class="sxs-lookup"><span data-stu-id="499d9-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="499d9-153">El sistema no los considera lo suficientemente similares al segmento de origen.</span><span class="sxs-lookup"><span data-stu-id="499d9-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]