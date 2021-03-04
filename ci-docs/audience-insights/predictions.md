---
title: Completar datos parciales usando predicciones
description: Utilice predicciones para completar datos incompletos del cliente.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268293"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="6a186-103">Complete sus datos parciales con predicciones</span><span class="sxs-lookup"><span data-stu-id="6a186-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6a186-104">Las predicciones le permiten crear fácilmente valores de predicción que pueden mejorar su comprensión de un cliente.</span><span class="sxs-lookup"><span data-stu-id="6a186-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="6a186-105">En la página **Inteligencia** > **Predicciones**, puede seleccionar **Mis predicciones** para ver las predicciones que ha configurado en otras partes de las informaciones de público y poder personalizarlas aún más.</span><span class="sxs-lookup"><span data-stu-id="6a186-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="6a186-106">No puede usar esta característica si su entorno usa almacenamiento de Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="6a186-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="6a186-107">La característica de predicciones utiliza medios automatizados para evaluar datos y realizar predicciones basadas en esos datos, y por lo tanto, tiene capacidad de ser utilizada como método de generación de perfiles, de acuerdo con la definición de ese término en el Reglamento General de Protección de Datos ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="6a186-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="6a186-108">El uso de esta función por parte del cliente para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones.</span><span class="sxs-lookup"><span data-stu-id="6a186-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="6a186-109">Usted es responsable de garantizar que el uso de Dynamics 365 Customer Insights, incluidas las predicciones, cumple con todas las leyes y regulaciones aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="6a186-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a186-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6a186-110">Prerequisites</span></span>

<span data-ttu-id="6a186-111">Antes de que su organización pueda usar la característica de predicciones, se deben cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="6a186-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="6a186-112">Tu organización tiene una instancia [establecida en Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) y está en la misma organización que Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6a186-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="6a186-113">Tu entorno está unido a tu instancia de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6a186-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="6a186-114">Si está [creando un nuevo entorno](manage-environments.md), configúrelo en el cuadro de diálogo **Crear un entorno** y seleccione **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="6a186-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="6a186-115">Si ya ha creado un entorno, vaya a su configuración y seleccione **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="6a186-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="6a186-116">De cualquier manera, en la sección **Usar predicciones**, introduzca la URL de instancia de Common Data Service a la que desea adjuntar su entorno.</span><span class="sxs-lookup"><span data-stu-id="6a186-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="6a186-117">Crear una predicción en la entidad de cliente</span><span class="sxs-lookup"><span data-stu-id="6a186-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="6a186-118">En las informaciones de público, vaya a **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="6a186-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="6a186-119">Seleccione la entidad **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="6a186-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="6a186-120">En la entidad **Customer: CustomerInsights**, seleccione la pestaña **Campos**.</span><span class="sxs-lookup"><span data-stu-id="6a186-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="6a186-121">Busque el nombre del atributo para el que desea predecir valores y, a continuación, seleccione el icono **Información general** en la columna **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="6a186-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a186-122">![Icono de visión general](media/intelligence-overviewicon.png "Icono de visión general")</span><span class="sxs-lookup"><span data-stu-id="6a186-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="6a186-123">Si hay una alta tasa de valores que faltan para el atributo, seleccione **Predecir valores que faltan** para continuar con la predicción.</span><span class="sxs-lookup"><span data-stu-id="6a186-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a186-124">![Estado de resumen con el botón predecir valores que faltan](media/intelligence-overviewpredictmissingvalues.png "Estado de resumen con el botón predecir valores que faltan")</span><span class="sxs-lookup"><span data-stu-id="6a186-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="6a186-125">Proporcione un **Nombre para mostrar** y un **Nombre de entidad de salida** para los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="6a186-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="6a186-126">Una lista de opciones rellenada previamente mostrará dónde puede asignar los valores a una categoría de predicción.</span><span class="sxs-lookup"><span data-stu-id="6a186-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="6a186-127">En este caso, las únicas opciones de categoría serán 0 o 1, ya que se asignan a la naturaleza verdadera/falsa o binaria de la predicción.</span><span class="sxs-lookup"><span data-stu-id="6a186-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="6a186-128">En la columna Categoría, asigne los valores de campo que desea clasificar como "0" en la predicción final a "0" y los elementos que desea clasificar como "1" en la predicción final a "1".</span><span class="sxs-lookup"><span data-stu-id="6a186-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a186-129">![Ejemplo que muestra valores de campo asignados a categorías](media/intelligence-categorymapping.png "Ejemplo que muestra valores de campo asignados a categorías")</span><span class="sxs-lookup"><span data-stu-id="6a186-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="6a186-130">Seleccione **Listo** y se procesará la predicción.</span><span class="sxs-lookup"><span data-stu-id="6a186-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="6a186-131">El procesamiento llevará algún tiempo, dependiendo del tamaño y la complejidad de los datos.</span><span class="sxs-lookup"><span data-stu-id="6a186-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="6a186-132">Los resultados estarán disponibles en una nueva entidad basada en el **Nombre de entidad de salida** de la predicción que ha creado.</span><span class="sxs-lookup"><span data-stu-id="6a186-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="6a186-133">Crear una predicción al crear un segmento</span><span class="sxs-lookup"><span data-stu-id="6a186-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="6a186-134">Predecir los valores que faltan para un atributo elegido específico también es posible al crear un segmento.</span><span class="sxs-lookup"><span data-stu-id="6a186-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="6a186-135">En concreto, cuando crea rápidamente un segmento basado en la entidad de cliente unificada o en la entidad Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="6a186-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="6a186-136">Como parte de este flujo, elegirá un atributo específico en el que basar el segmento, como Satisfacción del cliente o Importe de la compra.</span><span class="sxs-lookup"><span data-stu-id="6a186-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="6a186-137">Al crear el segmento, el sistema sugerirá un método para predecir los valores que faltan para este atributo.</span><span class="sxs-lookup"><span data-stu-id="6a186-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="6a186-138">En las informaciones de público, vaya a **Segmentos** y seleccione el mosaico **Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="6a186-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="6a186-139">Elija un **Campo** para crear un segmento y seleccione un **Operador** y, a continuación, seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="6a186-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="6a186-140">Proporcione un **Nombre** y un **Nombre para mostrar** para el segmento.</span><span class="sxs-lookup"><span data-stu-id="6a186-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="6a186-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a186-141">Select **Save**.</span></span>

5. <span data-ttu-id="6a186-142">Si el segmento que ha creado tiene datos incompletos en el campo de origen, puede elegir predecir los valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="6a186-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a186-143">![Botón Predicción](media/segments-predictoption.png "Botón Predicción")</span><span class="sxs-lookup"><span data-stu-id="6a186-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="6a186-144">Proporcione un **Nombre para mostrar** y un **Nombre de entidad de salida** para los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="6a186-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="6a186-145">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="6a186-145">Select **Done**.</span></span> <span data-ttu-id="6a186-146">La predicción se generará en breve en una nueva entidad con el nombre que proporcionó para el **Nombre de entidad de salida**.</span><span class="sxs-lookup"><span data-stu-id="6a186-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="6a186-147">Ver una predicción</span><span class="sxs-lookup"><span data-stu-id="6a186-147">View a prediction</span></span>

1. <span data-ttu-id="6a186-148">En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="6a186-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6a186-149">Seleccione la predicción que desea revisar.</span><span class="sxs-lookup"><span data-stu-id="6a186-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="6a186-150">Seleccione los puntos suspensivos en la columna **Acciones** y elija **Ver**.</span><span class="sxs-lookup"><span data-stu-id="6a186-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="6a186-151">Verá una serie de puntos de datos en la vista de la predicción.</span><span class="sxs-lookup"><span data-stu-id="6a186-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a186-152">![Página de predicciones](media/intelligence-predictionsviewpage.png "Página de predicciones")</span><span class="sxs-lookup"><span data-stu-id="6a186-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="6a186-153">**Valores de predicción** muestra la asignación que creó durante la fase de asignación de valor de campo a categoría.</span><span class="sxs-lookup"><span data-stu-id="6a186-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="6a186-154">Estos son los valores del conjunto de datos que se han asignado a una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="6a186-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="6a186-155">-**Principales influencias** son los factores del conjunto de datos que probablemente influyeron en la confianza de la predicción de que el valor de campo se asignara a una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="6a186-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="6a186-156">**Rendimiento** indica el acierto de las predicciones.</span><span class="sxs-lookup"><span data-stu-id="6a186-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="6a186-157">Seleccione el vínculo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6a186-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="6a186-158">**Vista previa** muestra ejemplos del conjunto de datos de salida desde la predicción y la probabilidad, o nuestra confianza, del valor de predicción, donde 0 es incierto, y 1 es cierto.</span><span class="sxs-lookup"><span data-stu-id="6a186-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="6a186-159">Actualizar una predicción</span><span class="sxs-lookup"><span data-stu-id="6a186-159">Update a prediction</span></span>

1. <span data-ttu-id="6a186-160">En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="6a186-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6a186-161">Seleccione la predicción que desea actualizar y seleccione el icono **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="6a186-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="6a186-162">La predicción se programará para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="6a186-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="6a186-163">Puede ver la hora en que se actualizó por última vez en la columna **Actualizado** de la página **Predicciones**.</span><span class="sxs-lookup"><span data-stu-id="6a186-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="6a186-164">Editar una predicción</span><span class="sxs-lookup"><span data-stu-id="6a186-164">Edit a prediction</span></span>

<span data-ttu-id="6a186-165">Después de crear una predicción, puede personalizar el modelo en el AI Builder para aumentar la eficacia del modelo.</span><span class="sxs-lookup"><span data-stu-id="6a186-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="6a186-166">En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="6a186-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6a186-167">Seleccione la predicción que desea editar.</span><span class="sxs-lookup"><span data-stu-id="6a186-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="6a186-168">Seleccione los puntos suspensivos en la columna **Acciones** y elija **Ver**.</span><span class="sxs-lookup"><span data-stu-id="6a186-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="6a186-169">Seleccione **Personalizar en AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="6a186-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="6a186-170">Actualice el modelo en AI Builder.</span><span class="sxs-lookup"><span data-stu-id="6a186-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="6a186-171">[Obtener más información sobre cómo administrar modelos en AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="6a186-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="6a186-172">La siguiente ejecución de la predicción usará el modelo actualizado que ha creado.</span><span class="sxs-lookup"><span data-stu-id="6a186-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="6a186-173">Los nuevos modelos creados en AI Builder no se mostrarán en las informaciones de público a menos que el modelo se haya creado a partir de las experiencias enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6a186-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="6a186-174">Quitar una predicción</span><span class="sxs-lookup"><span data-stu-id="6a186-174">Remove a prediction</span></span>

1. <span data-ttu-id="6a186-175">En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.</span><span class="sxs-lookup"><span data-stu-id="6a186-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6a186-176">Seleccione la predicción que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="6a186-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="6a186-177">Seleccione los puntos suspensivos en la columna **Acciones** y elija **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6a186-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="6a186-178">Confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="6a186-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6a186-179">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="6a186-179">Troubleshooting</span></span>

<span data-ttu-id="6a186-180">Si no puede completar el proceso de Common Data Service de conexión debido a un error, puede intentar completar el proceso manualmente.</span><span class="sxs-lookup"><span data-stu-id="6a186-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="6a186-181">Hay dos problemas conocidos que pueden producirse en el proceso de conexión:</span><span class="sxs-lookup"><span data-stu-id="6a186-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="6a186-182">La solución de complemento de tarjeta de cliente no está instalada.</span><span class="sxs-lookup"><span data-stu-id="6a186-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="6a186-183">Complete las instrucciones para [instalar y configurar la solución](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="6a186-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="6a186-184">No se otorgan permisos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6a186-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="6a186-185">Vaya a [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6a186-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="6a186-186">Seleccione **Entornos**.</span><span class="sxs-lookup"><span data-stu-id="6a186-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="6a186-187">Seleccione los puntos suspensivos junto al entorno al que desea agregar el permiso y seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="6a186-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="6a186-188">Expanda **Usuarios + permisos** y seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="6a186-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="6a186-189">Seleccione sucesivamente **+ Nuevo** y **Usuario**.</span><span class="sxs-lookup"><span data-stu-id="6a186-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="6a186-190">Seleccione **Usuario de la aplicación** si aún no está seleccionado e introduzca la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="6a186-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="6a186-191">**Nombre de usuario:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6a186-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="6a186-192">**Id. de aplicación:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="6a186-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="6a186-193">**Nombre de pila:** Cliente</span><span class="sxs-lookup"><span data-stu-id="6a186-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="6a186-194">**Apellidos:** Insights</span><span class="sxs-lookup"><span data-stu-id="6a186-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="6a186-195">**Correo electrónico principal:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6a186-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="6a186-196">Seleccione **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6a186-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="6a186-197">Seleccione el usuario que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="6a186-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="6a186-198">Seleccione **Administrar roles** en la barra de menús superior.</span><span class="sxs-lookup"><span data-stu-id="6a186-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="6a186-199">Seleccione **Administrador del sistema** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a186-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]