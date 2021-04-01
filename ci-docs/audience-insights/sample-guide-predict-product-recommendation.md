---
title: Guía de ejemplo de predicción de recomendaciones de producto
description: Utilice esta guía de ejemplo para probar el modelo de predicción de recomendaciones de producto predefinida.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595294"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="faa02-103">Guía de ejemplo de predicción de recomendaciones de producto (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="faa02-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="faa02-104">Le explicaremos un ejemplo completo de predicción de recomendaciones de producto utilizando los datos de muestra que se proporcionan a continuación.</span><span class="sxs-lookup"><span data-stu-id="faa02-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="faa02-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="faa02-105">Scenario</span></span>

<span data-ttu-id="faa02-106">Contoso es una empresa que produce café y máquinas de café de alta calidad, que venden a través de su sitio web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="faa02-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="faa02-107">Su objetivo es comprender qué productos deben recomendar a sus clientes recurrentes.</span><span class="sxs-lookup"><span data-stu-id="faa02-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="faa02-108">Saber qué clientes son más **proclives a comprar**, puede ayudarles a ahorrar esfuerzos de marketing al centrarse en elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="faa02-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="faa02-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="faa02-109">Prerequisites</span></span>

- <span data-ttu-id="faa02-110">Al menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="faa02-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="faa02-111">Le recomendamos que implemente los siguientes pasos [en un nuevo entorno](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="faa02-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="faa02-112">Tarea 1: ingerir datos</span><span class="sxs-lookup"><span data-stu-id="faa02-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="faa02-113">Revise los articulos [sobre la ingesta de datos](data-sources.md) y la [importación de orígenes de datos usando conectores de Power Query](connect-power-query.md) específicamente.</span><span class="sxs-lookup"><span data-stu-id="faa02-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="faa02-114">La siguiente información asume que está familiarizado con la ingesta de datos en general.</span><span class="sxs-lookup"><span data-stu-id="faa02-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="faa02-115">Ingerir datos de clientes de una plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="faa02-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="faa02-116">Cree un origen de datos llamado **Comercio electrónico**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="faa02-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="faa02-117">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="faa02-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="faa02-118">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="faa02-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="faa02-119">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="faa02-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="faa02-120">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="faa02-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="faa02-121">**CreatedOn**: fecha/hora/zona</span><span class="sxs-lookup"><span data-stu-id="faa02-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar la fecha de nacimiento a fecha.":::

5. <span data-ttu-id="faa02-123">En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="faa02-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="faa02-124">**Guarde** el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="faa02-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="faa02-125">Ingerir datos de compras en línea</span><span class="sxs-lookup"><span data-stu-id="faa02-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="faa02-126">Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="faa02-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="faa02-127">Elija el conector **Texto/CSV** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="faa02-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="faa02-128">Introduzca la URL para datos de **Compras en línea** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="faa02-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="faa02-129">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="faa02-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="faa02-130">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="faa02-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="faa02-131">**PurchasedOn**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="faa02-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="faa02-132">**TotalPrice**: moneda</span><span class="sxs-lookup"><span data-stu-id="faa02-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="faa02-133">En el campo **Nombre** del panel lateral cambie el nombre de su origen de datos de **Consulta** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="faa02-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="faa02-134">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="faa02-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="faa02-135">Ingerir datos de clientes del esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="faa02-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="faa02-136">Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="faa02-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="faa02-137">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="faa02-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="faa02-138">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="faa02-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="faa02-139">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="faa02-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="faa02-140">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="faa02-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="faa02-141">**RewardsPoints**: número entero</span><span class="sxs-lookup"><span data-stu-id="faa02-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="faa02-142">**CreatedOn**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="faa02-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="faa02-143">En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="faa02-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="faa02-144">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="faa02-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="faa02-145">Tarea 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="faa02-145">Task 2 - Data unification</span></span>

<span data-ttu-id="faa02-146">Después de ingerir los datos, ahora comenzamos el proceso **Asignar, Coincidir, Fusionar** para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="faa02-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="faa02-147">Para obtener más información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="faa02-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="faa02-148">Asignar</span><span class="sxs-lookup"><span data-stu-id="faa02-148">Map</span></span>

1. <span data-ttu-id="faa02-149">Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes.</span><span class="sxs-lookup"><span data-stu-id="faa02-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="faa02-150">Vaya a **Datos** > **Unificar** > **Mapa**.</span><span class="sxs-lookup"><span data-stu-id="faa02-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="faa02-151">Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="faa02-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unificar las fuentes de datos de comercio electrónico y fidelización.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="faa02-153">Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="faa02-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifique LoyaltyId como clave principal.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="faa02-155">Coincidir</span><span class="sxs-lookup"><span data-stu-id="faa02-155">Match</span></span>

1. <span data-ttu-id="faa02-156">Vaya a la pestaña **Coincidir** y seleccione **Establecer orden**.</span><span class="sxs-lookup"><span data-stu-id="faa02-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="faa02-157">En la lista desplegable **Principal**, elija **eCommerceContacts : eCommerce** como el origen principal e incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="faa02-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="faa02-158">En la lista desplegable **Entidad 2**, elija **loyCustomers : LoyaltyScheme** e incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="faa02-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unifique la coincidencia de comercio electrónico y fidelización.](media/unify-match-order.png)

4. <span data-ttu-id="faa02-160">Seleccione **Crear nueva regla**</span><span class="sxs-lookup"><span data-stu-id="faa02-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="faa02-161">Agregue su primera condición con FullName.</span><span class="sxs-lookup"><span data-stu-id="faa02-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="faa02-162">Para eCommerceContacts seleccione **FullName** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="faa02-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="faa02-163">Para loyCustomers, seleccione **FullName** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="faa02-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="faa02-164">Seleccione el desplegable **Normalizar** y elija **Tipo (teléfono, nombre, dirección...)**.</span><span class="sxs-lookup"><span data-stu-id="faa02-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="faa02-165">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="faa02-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="faa02-166">Introduzca el nombre **FullName, Email** para la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="faa02-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="faa02-167">Agregar una segunda condición para la dirección de correo electrónico seleccionando **Agregar condición**</span><span class="sxs-lookup"><span data-stu-id="faa02-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="faa02-168">Para la entidad eCommerceContacts, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="faa02-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="faa02-169">Para la entidad loyCustomers, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="faa02-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="faa02-170">Deje Normalizar en blanco.</span><span class="sxs-lookup"><span data-stu-id="faa02-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="faa02-171">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="faa02-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unifique la regla de coincidencia para el nombre y el correo electrónico.](media/unify-match-rule.png)

7. <span data-ttu-id="faa02-173">Seleccione **Guardar** y **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="faa02-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="faa02-174">Fusionar mediante combinación</span><span class="sxs-lookup"><span data-stu-id="faa02-174">Merge</span></span>

1. <span data-ttu-id="faa02-175">Vaya a la pestaña **Fusionar**.</span><span class="sxs-lookup"><span data-stu-id="faa02-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="faa02-176">En **ContactId** de la entidad **loyCustomers**, cambie el nombre para mostrar a **ContactIdLOYALTY** para diferenciarlo de los otros id. ingeridos.</span><span class="sxs-lookup"><span data-stu-id="faa02-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![cambie el nombre de contactid a partir del id. de fidelidad.](media/unify-merge-contactid.png)

1. <span data-ttu-id="faa02-178">Seleccione **Guardar** y **Ejecutar** para iniciar el proceso de fusión.</span><span class="sxs-lookup"><span data-stu-id="faa02-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="faa02-179">Tarea 3: Configurar la predicción de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="faa02-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="faa02-180">Con los perfiles de clientes unificados en su lugar, ahora podemos ejecutar la predicción de cancelación de suscripción.</span><span class="sxs-lookup"><span data-stu-id="faa02-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="faa02-181">Vaya a **Inteligencia** > **Predicción** y elija **Recomendación de producto**.</span><span class="sxs-lookup"><span data-stu-id="faa02-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="faa02-182">Seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="faa02-182">Select **Get started**.</span></span>

1. <span data-ttu-id="faa02-183">Asigne al modelo el nombre **OOB Product Recommendation Model Prediction** y a la entidad de salida **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="faa02-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="faa02-184">Defina tres condiciones para el modelo:</span><span class="sxs-lookup"><span data-stu-id="faa02-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="faa02-185">**Número de productos**: establezca este valor en **5**.</span><span class="sxs-lookup"><span data-stu-id="faa02-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="faa02-186">Esta configuración define cuántos productos desea recomendar a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="faa02-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="faa02-187">**¿Sugerir productos que los clientes hayan comprado recientemente?**: seleccione **sí** para indicar que desea incluir productos en la recomendación que sus clientes hayan comprado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="faa02-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="faa02-188">**Ventana para mirar atrás**: seleccione al menos **365 días**.</span><span class="sxs-lookup"><span data-stu-id="faa02-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="faa02-189">Este valor define el período hacia el pasado de la actividad del cliente que va a contemplar el modelo para usarlo como entrada para sus recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="faa02-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias del modelo para el modelo de recomendación de producto.":::

1. <span data-ttu-id="faa02-191">Seleccione **Datos requeridos** y seleccione **Agregar datos** para el historial de compras.</span><span class="sxs-lookup"><span data-stu-id="faa02-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="faa02-192">Añada la entidad **eCommercePurchases : eCommerce** y asigne los campos de comercio electrónico a los campos correspondientes requeridos por el modelo.</span><span class="sxs-lookup"><span data-stu-id="faa02-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="faa02-193">Únase a la entidad **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="faa02-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Únase a entidades de comercio electrónico.](media/model-purchase-join.png)

1. <span data-ttu-id="faa02-195">Seleccione **Siguiente** para establecer la programación del modelo.</span><span class="sxs-lookup"><span data-stu-id="faa02-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="faa02-196">El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se ingieren nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="faa02-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="faa02-197">En este ejemplo, seleccione **Mensualmente**.</span><span class="sxs-lookup"><span data-stu-id="faa02-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="faa02-198">Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="faa02-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="faa02-199">Tarea 4: revisar los resultados y las explicaciones del modelo</span><span class="sxs-lookup"><span data-stu-id="faa02-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="faa02-200">Deje que el modelo complete el entrenamiento y la puntuación de los datos.</span><span class="sxs-lookup"><span data-stu-id="faa02-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="faa02-201">Ahora puede revisar las explicaciones del modelo de recomendación de productos.</span><span class="sxs-lookup"><span data-stu-id="faa02-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="faa02-202">Para más información, consulte [Revisar un estado de predicción y los resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="faa02-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="faa02-203">Tarea 5: Crear un segmento de productos muy comprados</span><span class="sxs-lookup"><span data-stu-id="faa02-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="faa02-204">La ejecución del modelo de producción crea una nueva entidad que puede ver en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="faa02-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="faa02-205">Puede crear un nuevo segmento basado en la entidad creada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="faa02-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="faa02-206">Vaya a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="faa02-206">Go to **Segments**.</span></span> <span data-ttu-id="faa02-207">Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**.</span><span class="sxs-lookup"><span data-stu-id="faa02-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creación de un segmento con la salida del modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="faa02-209">Seleccione el punto de conexión **OOBProductRecommendationModelPrediction** y defina el segmento:</span><span class="sxs-lookup"><span data-stu-id="faa02-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="faa02-210">Campo: ProductID</span><span class="sxs-lookup"><span data-stu-id="faa02-210">Field: ProductID</span></span>
   - <span data-ttu-id="faa02-211">Operador: Valor</span><span class="sxs-lookup"><span data-stu-id="faa02-211">Operator: Value</span></span>
   - <span data-ttu-id="faa02-212">Valor: seleccione los tres identificadores de producto principales</span><span class="sxs-lookup"><span data-stu-id="faa02-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cree un segmento a partir de los resultados del modelo.":::

<span data-ttu-id="faa02-214">Ahora tiene un segmento que se actualiza dinámicamente, que identifica a los clientes que están más dispuestos a comprar los tres productos más recomendados.</span><span class="sxs-lookup"><span data-stu-id="faa02-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="faa02-215">Para obtener más información, vea [Crear y administrar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="faa02-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]