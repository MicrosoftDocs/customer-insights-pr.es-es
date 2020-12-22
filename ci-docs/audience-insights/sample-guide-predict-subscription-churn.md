---
title: Guía de ejemplo de predicción de abandono de suscripción
description: Utilice esta guía de muestra para probar el modelo de predicción de cancelación de suscripción de uso inmediato.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654001"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="160e5-103">Guía de ejemplo de predicción de abandono de suscripción (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="160e5-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="160e5-104">Le explicaremos un ejemplo completo de predicción de cancelación de suscripción utilizando los datos de muestra que se proporcionan a continuación.</span><span class="sxs-lookup"><span data-stu-id="160e5-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="160e5-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="160e5-105">Scenario</span></span>

<span data-ttu-id="160e5-106">Contoso es una empresa que produce café y máquinas de café de alta calidad, que venden a través de su sitio web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="160e5-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="160e5-107">Recientemente, comenzaron un negocio de suscripción para que sus clientes obtengan café de forma regular.</span><span class="sxs-lookup"><span data-stu-id="160e5-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="160e5-108">Su objetivo es conocer qué clientes suscritos podrían cancelar su suscripción en los próximos meses.</span><span class="sxs-lookup"><span data-stu-id="160e5-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="160e5-109">Saber cuál de sus clientes es **probable que cancele**, puede ayudarle a ahorrar esfuerzos de marketing, centrándose en mantenerlos.</span><span class="sxs-lookup"><span data-stu-id="160e5-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="160e5-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="160e5-110">Prerequisites</span></span>

- <span data-ttu-id="160e5-111">Al menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="160e5-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="160e5-112">Le recomendamos que implemente los siguientes pasos [en un nuevo entorno](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="160e5-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="160e5-113">Tarea 1: ingerir datos</span><span class="sxs-lookup"><span data-stu-id="160e5-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="160e5-114">Revise los articulos [sobre la ingesta de datos](data-sources.md) y la [importación de orígenes de datos usando conectores de Power Query](connect-power-query.md) específicamente.</span><span class="sxs-lookup"><span data-stu-id="160e5-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="160e5-115">La siguiente información asume que está familiarizado con la ingesta de datos en general.</span><span class="sxs-lookup"><span data-stu-id="160e5-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="160e5-116">Ingerir datos de clientes de una plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="160e5-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="160e5-117">Cree un origen de datos llamado **Comercio electrónico**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="160e5-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="160e5-118">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="160e5-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="160e5-119">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="160e5-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="160e5-120">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="160e5-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="160e5-121">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="160e5-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="160e5-122">**CreatedOn**: fecha/hora/zona</span><span class="sxs-lookup"><span data-stu-id="160e5-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="160e5-123">![Transformar DoB en Fecha](media/ecommerce-dob-date.PNG "transformar fecha de nacimiento a fecha")</span><span class="sxs-lookup"><span data-stu-id="160e5-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="160e5-124">En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="160e5-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="160e5-125">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="160e5-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="160e5-126">Ingerir datos de clientes del esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="160e5-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="160e5-127">Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="160e5-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="160e5-128">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="160e5-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="160e5-129">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="160e5-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="160e5-130">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="160e5-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="160e5-131">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="160e5-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="160e5-132">**RewardsPoints**: número entero</span><span class="sxs-lookup"><span data-stu-id="160e5-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="160e5-133">**CreatedOn**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="160e5-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="160e5-134">En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="160e5-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="160e5-135">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="160e5-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="160e5-136">Ingerir información de suscripción</span><span class="sxs-lookup"><span data-stu-id="160e5-136">Ingest subscription information</span></span>

1. <span data-ttu-id="160e5-137">Cree un origen de datos llamado **SubscriptionHistory**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="160e5-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="160e5-138">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="160e5-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="160e5-139">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="160e5-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="160e5-140">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="160e5-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="160e5-141">**SubscriptioID**: número entero</span><span class="sxs-lookup"><span data-stu-id="160e5-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="160e5-142">**SubscriptionAmount** : moneda</span><span class="sxs-lookup"><span data-stu-id="160e5-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="160e5-143">**SubscriptionEndDate**: Fecha/hora</span><span class="sxs-lookup"><span data-stu-id="160e5-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="160e5-144">**SubscriptionStartDate**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="160e5-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="160e5-145">**TransactionDate** : fecha/hora</span><span class="sxs-lookup"><span data-stu-id="160e5-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="160e5-146">**IsRecurring**: verdadero/falso</span><span class="sxs-lookup"><span data-stu-id="160e5-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="160e5-147">**Is_auto_renew**: verdadero/falso</span><span class="sxs-lookup"><span data-stu-id="160e5-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="160e5-148">**RecurringFrequencyInMonths**: número entero</span><span class="sxs-lookup"><span data-stu-id="160e5-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="160e5-149">En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="160e5-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="160e5-150">Guarde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="160e5-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="160e5-151">Ingerir datos de clientes de revisiones del sitio web</span><span class="sxs-lookup"><span data-stu-id="160e5-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="160e5-152">Cree un origen de datos llamado **Sitio web**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="160e5-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="160e5-153">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="160e5-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="160e5-154">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="160e5-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="160e5-155">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="160e5-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="160e5-156">**ReviewRating**: número entero</span><span class="sxs-lookup"><span data-stu-id="160e5-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="160e5-157">**ReviewDate**: fecha</span><span class="sxs-lookup"><span data-stu-id="160e5-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="160e5-158">En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="160e5-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="160e5-159">Tarea 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="160e5-159">Task 2 - Data unification</span></span>

<span data-ttu-id="160e5-160">Después de ingerir los datos, ahora comenzamos el proceso **Asignar, Coincidir, Fusionar** para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="160e5-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="160e5-161">Para obtener más información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="160e5-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="160e5-162">Asignar</span><span class="sxs-lookup"><span data-stu-id="160e5-162">Map</span></span>

1. <span data-ttu-id="160e5-163">Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes.</span><span class="sxs-lookup"><span data-stu-id="160e5-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="160e5-164">Vaya a **Datos** > **Unificar** > **Mapa**.</span><span class="sxs-lookup"><span data-stu-id="160e5-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="160e5-165">Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="160e5-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar las fuentes de datos de comercio electrónico y fidelización.":::

1. <span data-ttu-id="160e5-167">Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="160e5-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifique LoyaltyId como clave principal.":::

### <a name="match"></a><span data-ttu-id="160e5-169">Coincidir</span><span class="sxs-lookup"><span data-stu-id="160e5-169">Match</span></span>

1. <span data-ttu-id="160e5-170">Vaya a la pestaña **Coincidir** y seleccione **Establecer orden**.</span><span class="sxs-lookup"><span data-stu-id="160e5-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="160e5-171">En la lista desplegable **Principal**, elija **eCommerceContacts : eCommerce** como el origen principal e incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="160e5-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="160e5-172">En la lista desplegable **Entidad 2**, elija **loyCustomers : LoyaltyScheme** e incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="160e5-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifique la coincidencia de comercio electrónico y fidelización.":::

1. <span data-ttu-id="160e5-174">Seleccione **Crear nueva regla**</span><span class="sxs-lookup"><span data-stu-id="160e5-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="160e5-175">Agregue su primera condición con FullName.</span><span class="sxs-lookup"><span data-stu-id="160e5-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="160e5-176">Para eCommerceContacts seleccione **FullName** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="160e5-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="160e5-177">Para loyCustomers, seleccione **FullName** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="160e5-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="160e5-178">Seleccione el desplegable **Normalizar** y elija **Tipo (teléfono, nombre, dirección...)**.</span><span class="sxs-lookup"><span data-stu-id="160e5-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="160e5-179">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="160e5-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="160e5-180">Introduzca el nombre **FullName, Email** para la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="160e5-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="160e5-181">Agregar una segunda condición para la dirección de correo electrónico seleccionando **Agregar condición**</span><span class="sxs-lookup"><span data-stu-id="160e5-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="160e5-182">Para la entidad eCommerceContacts, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="160e5-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="160e5-183">Para la entidad loyCustomers, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="160e5-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="160e5-184">Deje Normalizar en blanco.</span><span class="sxs-lookup"><span data-stu-id="160e5-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="160e5-185">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="160e5-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifique la regla de coincidencia para el nombre y el correo electrónico.":::

7. <span data-ttu-id="160e5-187">Seleccione **Guardar** y **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="160e5-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="160e5-188">Fusionar mediante combinación</span><span class="sxs-lookup"><span data-stu-id="160e5-188">Merge</span></span>

1. <span data-ttu-id="160e5-189">Vaya a la pestaña **Fusionar**.</span><span class="sxs-lookup"><span data-stu-id="160e5-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="160e5-190">En **ContactId** de la entidad **loyCustomers**, cambie el nombre para mostrar a **ContactIdLOYALTY** para diferenciarlo de los otros id. ingeridos.</span><span class="sxs-lookup"><span data-stu-id="160e5-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="cambie el nombre de contactid a partir del id. de fidelidad.":::

1. <span data-ttu-id="160e5-192">Seleccione **Guardar** y **Ejecutar** para iniciar el proceso de fusión.</span><span class="sxs-lookup"><span data-stu-id="160e5-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="160e5-193">Tarea 3: configurar la predicción de abandono de suscripciones</span><span class="sxs-lookup"><span data-stu-id="160e5-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="160e5-194">Con los perfiles de clientes unificados en su lugar, ahora podemos ejecutar la predicción de cancelación de suscripción.</span><span class="sxs-lookup"><span data-stu-id="160e5-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="160e5-195">Para conocer los pasos detallados, consulte el artículo [Predicción de cancelación de suscripción (versión preliminar)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="160e5-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="160e5-196">Vaya a **Inteligencia** > **Descubrir** y seleccione usar el **Modelo de abandono de clientes**.</span><span class="sxs-lookup"><span data-stu-id="160e5-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="160e5-197">Seleccione la opción **Suscripción** y elija **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="160e5-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="160e5-198">Nombre el modelo como **Predicción de cancelación de suscripción OOB** y la entidad de salida como **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="160e5-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="160e5-199">Defina dos condiciones para el modelo de abandono:</span><span class="sxs-lookup"><span data-stu-id="160e5-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="160e5-200">**Días desde que finalizó la suscripción**: **al menos 60** días.</span><span class="sxs-lookup"><span data-stu-id="160e5-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="160e5-201">Si un cliente no renueva la suscripción durante este tiempo después de que finalizada su suscripción, se considerará que ha abandonado.</span><span class="sxs-lookup"><span data-stu-id="160e5-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="160e5-202">**Definición de abandono**: **al menos 93** días.</span><span class="sxs-lookup"><span data-stu-id="160e5-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="160e5-203">La duración del modelo predice qué clientes podrían abandonar.</span><span class="sxs-lookup"><span data-stu-id="160e5-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="160e5-204">Cuanto más lejos mire en el futuro, menos precisos serán los resultados.</span><span class="sxs-lookup"><span data-stu-id="160e5-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleccione las palancas de modelo Ventana de predicción y Definición de abandono.":::

1. <span data-ttu-id="160e5-206">Seleccione **Agregar datos requeridos** y seleccione **Agregar datos** para el historial de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="160e5-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="160e5-207">Añada la entidad **Subscription : SubscriptionHistory** y asigne los campos de comercio electrónico a los campos correspondientes requeridos por el modelo.</span><span class="sxs-lookup"><span data-stu-id="160e5-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="160e5-208">Únase a la entidad **Subscription : SubscriptionHistory** con **eCommerceContacts : eCommerce**, y nombre la relación como **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="160e5-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Únase a entidades de comercio electrónico.":::

1. <span data-ttu-id="160e5-210">En Actividades del cliente, agregue la entidad **webReviews : Website** y asigne los campos de webReviews a los campos correspondientes requeridos por el modelo.</span><span class="sxs-lookup"><span data-stu-id="160e5-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="160e5-211">Clave principal: ReviewId</span><span class="sxs-lookup"><span data-stu-id="160e5-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="160e5-212">Marca de tiempo: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="160e5-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="160e5-213">Evento: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="160e5-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="160e5-214">Configure una actividad para revisiones de sitios web.</span><span class="sxs-lookup"><span data-stu-id="160e5-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="160e5-215">Seleccione la actividad **Revisión** y únase a la entidad **webReviews : Website** con **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="160e5-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="160e5-216">Seleccione **Siguiente** para establecer la programación del modelo.</span><span class="sxs-lookup"><span data-stu-id="160e5-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="160e5-217">El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se ingieren nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="160e5-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="160e5-218">En este ejemplo, seleccione **Mensualmente**.</span><span class="sxs-lookup"><span data-stu-id="160e5-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="160e5-219">Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="160e5-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="160e5-220">Tarea 4: revisar los resultados y las explicaciones del modelo</span><span class="sxs-lookup"><span data-stu-id="160e5-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="160e5-221">Deje que el modelo complete el entrenamiento y la puntuación de los datos.</span><span class="sxs-lookup"><span data-stu-id="160e5-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="160e5-222">Ahora puede revisar las explicaciones del modelo de cancelación de suscripción.</span><span class="sxs-lookup"><span data-stu-id="160e5-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="160e5-223">Para más información, consulte [Revisar un estado de predicción y los resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="160e5-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="160e5-224">Tarea 5: crear un segmento de clientes con alto riesgo de abandono</span><span class="sxs-lookup"><span data-stu-id="160e5-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="160e5-225">La ejecución del modelo de producción crea una nueva entidad que puede ver en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="160e5-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="160e5-226">Puede crear un nuevo segmento basado en la entidad creada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="160e5-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="160e5-227">Vaya a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="160e5-227">Go to **Segments**.</span></span> <span data-ttu-id="160e5-228">Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**.</span><span class="sxs-lookup"><span data-stu-id="160e5-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación de un segmento con la salida del modelo.":::

1. <span data-ttu-id="160e5-230">Seleccione el punto de conexión **OOBSubscriptionChurnPrediction** y defina el segmento:</span><span class="sxs-lookup"><span data-stu-id="160e5-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="160e5-231">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="160e5-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="160e5-232">Operador: mayor que</span><span class="sxs-lookup"><span data-stu-id="160e5-232">Operator: greater than</span></span>
   - <span data-ttu-id="160e5-233">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="160e5-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configure el segmento de cancelación de suscripción.":::

<span data-ttu-id="160e5-235">Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes con alto riesgo de abandono para este negocio de suscripción.</span><span class="sxs-lookup"><span data-stu-id="160e5-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="160e5-236">Para obtener más información, vea [Crear y administrar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="160e5-236">For more information, see [Create and manage segments](segments.md).</span></span>
