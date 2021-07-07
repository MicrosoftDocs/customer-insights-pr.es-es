---
title: Guía de ejemplo de predicción de abandono de transacción
description: Utilice esta guía de ejemplo para probar el modelo de predicción de cancelación de transacción de uso inmediato.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306141"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="191cb-103">Guía de ejemplo de predicción de abandono de transacción (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="191cb-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="191cb-104">Esta guía le llevará por un ejemplo completo de predicción de cancelación de transacción en Customer Insights, utilizando los datos de ejemplo que se proporcionan a continuación.</span><span class="sxs-lookup"><span data-stu-id="191cb-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="191cb-105">Todos los datos utilizados en esta guía no son datos reales del cliente y forman parte del conjunto de datos Contoso encontrado en el entorno *Demostración* de la suscripción a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="191cb-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="191cb-106">Escenario</span><span class="sxs-lookup"><span data-stu-id="191cb-106">Scenario</span></span>

<span data-ttu-id="191cb-107">Contoso es una empresa que produce café y máquinas de café de alta calidad, que venden a través de su sitio web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="191cb-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="191cb-108">Su objetivo es saber qué clientes que normalmente compran sus productos de forma regular, dejarán de ser clientes activos en los próximos 60 días.</span><span class="sxs-lookup"><span data-stu-id="191cb-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="191cb-109">Saber cuál de sus clientes es **probable que cancele**, puede ayudarle a ahorrar esfuerzos de marketing, centrándose en mantenerlos.</span><span class="sxs-lookup"><span data-stu-id="191cb-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="191cb-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="191cb-110">Prerequisites</span></span>

- <span data-ttu-id="191cb-111">Al menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="191cb-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="191cb-112">Le recomendamos que implemente los siguientes pasos [en un nuevo entorno](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="191cb-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="191cb-113">Tarea 1: ingerir datos</span><span class="sxs-lookup"><span data-stu-id="191cb-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="191cb-114">Revise los articulos [sobre la ingesta de datos](data-sources.md) y la [importación de orígenes de datos usando conectores de Power Query](connect-power-query.md) específicamente.</span><span class="sxs-lookup"><span data-stu-id="191cb-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="191cb-115">La siguiente información asume que está familiarizado con la ingesta de datos en general.</span><span class="sxs-lookup"><span data-stu-id="191cb-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="191cb-116">Ingerir datos de clientes de una plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="191cb-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="191cb-117">Cree un origen de datos llamado **Comercio electrónico**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="191cb-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="191cb-118">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="191cb-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="191cb-119">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="191cb-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="191cb-120">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="191cb-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="191cb-121">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="191cb-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="191cb-122">**CreatedOn**: fecha/hora/zona</span><span class="sxs-lookup"><span data-stu-id="191cb-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="191cb-123">![Transformar DoB en Fecha](media/ecommerce-dob-date.PNG "transformar fecha de nacimiento a fecha")</span><span class="sxs-lookup"><span data-stu-id="191cb-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="191cb-124">En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="191cb-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="191cb-125">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="191cb-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="191cb-126">Ingerir datos de compras en línea</span><span class="sxs-lookup"><span data-stu-id="191cb-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="191cb-127">Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="191cb-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="191cb-128">Elija el conector **Texto/CSV** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="191cb-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="191cb-129">Introduzca la URL para datos de **Compras en línea** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="191cb-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="191cb-130">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="191cb-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="191cb-131">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="191cb-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="191cb-132">**PurchasedOn**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="191cb-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="191cb-133">**TotalPrice**: moneda</span><span class="sxs-lookup"><span data-stu-id="191cb-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="191cb-134">En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="191cb-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="191cb-135">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="191cb-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="191cb-136">Ingerir datos de clientes del esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="191cb-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="191cb-137">Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="191cb-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="191cb-138">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="191cb-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="191cb-139">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="191cb-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="191cb-140">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="191cb-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="191cb-141">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="191cb-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="191cb-142">**RewardsPoints**: número entero</span><span class="sxs-lookup"><span data-stu-id="191cb-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="191cb-143">**CreatedOn**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="191cb-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="191cb-144">En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="191cb-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="191cb-145">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="191cb-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="191cb-146">Tarea 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="191cb-146">Task 2 - Data unification</span></span>

<span data-ttu-id="191cb-147">Después de ingerir los datos, ahora comenzamos el proceso **Asignar, Coincidir, Fusionar** para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="191cb-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="191cb-148">Para obtener más información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="191cb-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="191cb-149">Asignar</span><span class="sxs-lookup"><span data-stu-id="191cb-149">Map</span></span>

1. <span data-ttu-id="191cb-150">Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes.</span><span class="sxs-lookup"><span data-stu-id="191cb-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="191cb-151">Vaya a **Datos** > **Unificar** > **Mapa**.</span><span class="sxs-lookup"><span data-stu-id="191cb-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="191cb-152">Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="191cb-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar las fuentes de datos de comercio electrónico y fidelización.":::

1. <span data-ttu-id="191cb-154">Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="191cb-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifique LoyaltyId como clave principal.":::

### <a name="match"></a><span data-ttu-id="191cb-156">Coincidir</span><span class="sxs-lookup"><span data-stu-id="191cb-156">Match</span></span>

1. <span data-ttu-id="191cb-157">Vaya a la pestaña **Coincidir** y seleccione **Establecer orden**.</span><span class="sxs-lookup"><span data-stu-id="191cb-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="191cb-158">En la lista desplegable **Principal**, seleccione **eCommerceContacts: eCommerce** como el origen principal en incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="191cb-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="191cb-159">En la lista desplegable **Entidad 2**, seleccione **loyCustomers: LoyaltyScheme** e incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="191cb-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifique la coincidencia de comercio electrónico y fidelización.":::

1. <span data-ttu-id="191cb-161">Seleccione **Crear nueva regla**</span><span class="sxs-lookup"><span data-stu-id="191cb-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="191cb-162">Agregue su primera condición con FullName.</span><span class="sxs-lookup"><span data-stu-id="191cb-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="191cb-163">Para eCommerceContacts, seleccione **FullName** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="191cb-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="191cb-164">Para loyCustomers, seleccione **FullName** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="191cb-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="191cb-165">Seleccione el desplegable **Normalizar** y elija **Tipo (teléfono, nombre, dirección...)**.</span><span class="sxs-lookup"><span data-stu-id="191cb-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="191cb-166">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="191cb-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="191cb-167">Introduzca el nombre **FullName, Email** para la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="191cb-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="191cb-168">Agregar una segunda condición para la dirección de correo electrónico seleccionando **Agregar condición**</span><span class="sxs-lookup"><span data-stu-id="191cb-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="191cb-169">Para la entidad eCommerceContacts, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="191cb-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="191cb-170">Para la entidad loyCustomers, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="191cb-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="191cb-171">Deje Normalizar en blanco.</span><span class="sxs-lookup"><span data-stu-id="191cb-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="191cb-172">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="191cb-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifique la regla de coincidencia para el nombre y el correo electrónico.":::

7. <span data-ttu-id="191cb-174">Seleccione **Guardar** y **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="191cb-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="191cb-175">Fusionar mediante combinación</span><span class="sxs-lookup"><span data-stu-id="191cb-175">Merge</span></span>

1. <span data-ttu-id="191cb-176">Vaya a la pestaña **Fusionar**.</span><span class="sxs-lookup"><span data-stu-id="191cb-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="191cb-177">En **ContactId** de la entidad **loyCustomers**, cambie el nombre para mostrar a **ContactIdLOYALTY** para diferenciarlo de los otros id. ingeridos.</span><span class="sxs-lookup"><span data-stu-id="191cb-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="cambie el nombre de contactid a partir del id. de fidelidad.":::

1. <span data-ttu-id="191cb-179">Seleccione **Guardar** y **Ejecutar** para iniciar el proceso de fusión.</span><span class="sxs-lookup"><span data-stu-id="191cb-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="191cb-180">Tarea 3: configurar la predicción de abandono de transacciones</span><span class="sxs-lookup"><span data-stu-id="191cb-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="191cb-181">Con los perfiles de clientes unificados en su lugar, ahora podemos ejecutar la predicción de cancelación de suscripción.</span><span class="sxs-lookup"><span data-stu-id="191cb-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="191cb-182">Para conocer los pasos detallados, consulte el artículo [Predicción de cancelación de suscripción (versión preliminar)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="191cb-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="191cb-183">Vaya a **Inteligencia** > **Descubrir** y seleccione usar el **Modelo de abandono de clientes**.</span><span class="sxs-lookup"><span data-stu-id="191cb-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="191cb-184">Seleccione la opción **Transactional** y elija **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="191cb-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="191cb-185">Nombre el modelo como **Predicción de cancelación de transacción de comercio electrónico OOB** y la entidad de salida como **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="191cb-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="191cb-186">Defina dos condiciones para el modelo de abandono:</span><span class="sxs-lookup"><span data-stu-id="191cb-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="191cb-187">**Ventana de predicción**: **al menos 60** dias.</span><span class="sxs-lookup"><span data-stu-id="191cb-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="191cb-188">Esta configuración define en qué medida en el futuro queremos predecir el abandono de clientes.</span><span class="sxs-lookup"><span data-stu-id="191cb-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="191cb-189">**Definición de abandono**: **al menos 60** días.</span><span class="sxs-lookup"><span data-stu-id="191cb-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="191cb-190">La duración sin compra después de la cual un cliente se considera abandonado.</span><span class="sxs-lookup"><span data-stu-id="191cb-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Seleccione las palancas de modelo Ventana de predicción y Definición de abandono.":::

1. <span data-ttu-id="191cb-192">Seleccione **Historial de compras (obligatorio)** y seleccione **Agregar datos** para el historial de compras.</span><span class="sxs-lookup"><span data-stu-id="191cb-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="191cb-193">Añada la entidad **eCommercePurchases : eCommerce** y asigne los campos de comercio electrónico a los campos correspondientes requeridos por el modelo.</span><span class="sxs-lookup"><span data-stu-id="191cb-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="191cb-194">Únase a la entidad **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="191cb-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Únase a entidades de comercio electrónico.":::

1. <span data-ttu-id="191cb-196">Seleccione **Siguiente** para establecer la programación del modelo.</span><span class="sxs-lookup"><span data-stu-id="191cb-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="191cb-197">El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se ingieren nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="191cb-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="191cb-198">En este ejemplo, seleccione **Mensualmente**.</span><span class="sxs-lookup"><span data-stu-id="191cb-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="191cb-199">Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="191cb-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="191cb-200">Tarea 4: revisar los resultados y las explicaciones del modelo</span><span class="sxs-lookup"><span data-stu-id="191cb-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="191cb-201">Deje que el modelo complete el entrenamiento y la puntuación de los datos.</span><span class="sxs-lookup"><span data-stu-id="191cb-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="191cb-202">Ahora puede revisar las explicaciones del modelo de cancelación de suscripción.</span><span class="sxs-lookup"><span data-stu-id="191cb-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="191cb-203">Para más información, consulte [Revisar un estado de predicción y los resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="191cb-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="191cb-204">Tarea 5: crear un segmento de clientes con alto riesgo de abandono</span><span class="sxs-lookup"><span data-stu-id="191cb-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="191cb-205">La ejecución del modelo de producción crea una nueva entidad que puede ver en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="191cb-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="191cb-206">Puede crear un nuevo segmento basado en la entidad creada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="191cb-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="191cb-207">Vaya a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="191cb-207">Go to **Segments**.</span></span> <span data-ttu-id="191cb-208">Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**.</span><span class="sxs-lookup"><span data-stu-id="191cb-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación de un segmento con la salida del modelo.":::

1. <span data-ttu-id="191cb-210">Seleccione el punto de conexión **OOBSubscriptionChurnPrediction** y defina el segmento:</span><span class="sxs-lookup"><span data-stu-id="191cb-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="191cb-211">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="191cb-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="191cb-212">Operador: mayor que</span><span class="sxs-lookup"><span data-stu-id="191cb-212">Operator: greater than</span></span>
   - <span data-ttu-id="191cb-213">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="191cb-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configure el segmento de cancelación de suscripción.":::

<span data-ttu-id="191cb-215">Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes con alto riesgo de abandono para este negocio de suscripción.</span><span class="sxs-lookup"><span data-stu-id="191cb-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="191cb-216">Para obtener más información, vea [Crear y administrar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="191cb-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]