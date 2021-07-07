---
title: Guía de muestra de la predicción del valor de por vida del cliente
description: Utilice esta guía de muestra para probar el modelo de valor de vida útil del cliente predicción.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306370"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="06c8f-103">Guía de muestra de la predicción (CLV) del valor de por vida del cliente</span><span class="sxs-lookup"><span data-stu-id="06c8f-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="06c8f-104">Esta guía le explicará un ejemplo de extremo a extremo de la predicción del valor de vida útil del cliente (CLV) en Customer Insights utilizando datos de muestra.</span><span class="sxs-lookup"><span data-stu-id="06c8f-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="06c8f-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="06c8f-105">Scenario</span></span>

<span data-ttu-id="06c8f-106">Contoso es una empresa que produce café y cafeteras de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="06c8f-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="06c8f-107">Venden los productos a través de su Sitio web de café Contoso.</span><span class="sxs-lookup"><span data-stu-id="06c8f-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="06c8f-108">La empresa quiere comprender el valor (ingresos) que sus clientes pueden generar en los próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="06c8f-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="06c8f-109">Conocer el valor esperado de sus clientes en los próximos 12 meses les ayudará a dirigir sus esfuerzos de marketing hacia clientes de alto valor.</span><span class="sxs-lookup"><span data-stu-id="06c8f-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="06c8f-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="06c8f-110">Prerequisites</span></span>

- <span data-ttu-id="06c8f-111">Por lo menos [permisos de colaborador](permissions.md) en información de público.</span><span class="sxs-lookup"><span data-stu-id="06c8f-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="06c8f-112">Le recomendamos que implemente los siguientes pasos [en un nuevo entorno](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="06c8f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="06c8f-113">Tarea 1: ingerir datos</span><span class="sxs-lookup"><span data-stu-id="06c8f-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="06c8f-114">Revisa los artículos [sobre la ingesta de datos](data-sources.md) e [importar fuentes de datos usando conectores Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="06c8f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="06c8f-115">La siguiente información asume que está familiarizado con la ingesta de datos en general.</span><span class="sxs-lookup"><span data-stu-id="06c8f-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="06c8f-116">Ingerir datos de clientes de una plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="06c8f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="06c8f-117">Cree un origen de datos llamado **Comercio electrónico**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="06c8f-118">Introduzca la URL de los contactos de comercio electrónico [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="06c8f-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="06c8f-119">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="06c8f-120">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="06c8f-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="06c8f-121">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="06c8f-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="06c8f-122">**CreatedOn**: fecha/hora/zona</span><span class="sxs-lookup"><span data-stu-id="06c8f-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar la fecha de nacimiento a fecha.":::

1. <span data-ttu-id="06c8f-124">En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="06c8f-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="06c8f-125">**Guarde** el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="06c8f-126">Ingerir datos de compras en línea</span><span class="sxs-lookup"><span data-stu-id="06c8f-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="06c8f-127">Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="06c8f-128">Elija el conector **Texto/CSV** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="06c8f-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="06c8f-129">Introduzca la URL para datos de **Compras en línea** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="06c8f-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="06c8f-130">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="06c8f-131">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="06c8f-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="06c8f-132">**PurchasedOn**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="06c8f-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="06c8f-133">**TotalPrice**: moneda</span><span class="sxs-lookup"><span data-stu-id="06c8f-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="06c8f-134">En el campo **Nombre** del panel lateral cambie el nombre de su origen de datos de **Consulta** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="06c8f-135">**Guarde** el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="06c8f-136">Ingerir datos de clientes del esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="06c8f-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="06c8f-137">Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="06c8f-138">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="06c8f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="06c8f-139">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="06c8f-140">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="06c8f-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="06c8f-141">**DateOfBirth**: fecha</span><span class="sxs-lookup"><span data-stu-id="06c8f-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="06c8f-142">**RewardsPoints**: número entero</span><span class="sxs-lookup"><span data-stu-id="06c8f-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="06c8f-143">**CreatedOn**: fecha/hora</span><span class="sxs-lookup"><span data-stu-id="06c8f-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="06c8f-144">En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="06c8f-145">**Guarde** el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="06c8f-146">Ingerir datos de clientes de revisiones del sitio web</span><span class="sxs-lookup"><span data-stu-id="06c8f-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="06c8f-147">Cree un origen de datos llamado **Sitio web**, elija la opción de importación y seleccione el conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="06c8f-148">Introduzca la URL de los contactos de comercio electrónico https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="06c8f-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="06c8f-149">Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="06c8f-150">Actualice el tipo de datos para las columnas que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="06c8f-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="06c8f-151">**ReviewRating**: Número decimal</span><span class="sxs-lookup"><span data-stu-id="06c8f-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="06c8f-152">**ReviewDate**: fecha</span><span class="sxs-lookup"><span data-stu-id="06c8f-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="06c8f-153">En el campo "Nombre" del panel derecho, cambie el nombre de su origen de datos de **Consulta** a **Reseñas**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="06c8f-154">**Guarde** el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="06c8f-155">Tarea 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="06c8f-155">Task 2 - Data unification</span></span>

<span data-ttu-id="06c8f-156">Después de ingerir los datos, ahora comenzamos el proceso de unificación de datos para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="06c8f-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="06c8f-157">Para obtener más información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="06c8f-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="06c8f-158">Asignar</span><span class="sxs-lookup"><span data-stu-id="06c8f-158">Map</span></span>

1. <span data-ttu-id="06c8f-159">Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes.</span><span class="sxs-lookup"><span data-stu-id="06c8f-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="06c8f-160">Vaya a **Datos** > **Unificar** > **Mapa**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="06c8f-161">Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="06c8f-162">Después, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-162">Then, select **Apply**.</span></span>

   ![unificar las fuentes de datos de comercio electrónico y fidelización.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="06c8f-164">Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifique LoyaltyId como clave principal.](media/unify-loyaltyid.png)

1. <span data-ttu-id="06c8f-166">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="06c8f-167">Coincidir</span><span class="sxs-lookup"><span data-stu-id="06c8f-167">Match</span></span>

1. <span data-ttu-id="06c8f-168">Vaya a la pestaña **Coincidir** y seleccione **Establecer orden**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="06c8f-169">En la lista desplegable **Principal**, seleccione **eCommerceContacts: eCommerce** como el origen principal en incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="06c8f-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="06c8f-170">En la lista desplegable **Entidad 2**, seleccione **loyCustomers: LoyaltyScheme** e incluya todos los registros.</span><span class="sxs-lookup"><span data-stu-id="06c8f-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unifique la coincidencia de comercio electrónico y fidelización.](media/unify-match-order.png)

1. <span data-ttu-id="06c8f-172">Seleccione **Agregar regla**</span><span class="sxs-lookup"><span data-stu-id="06c8f-172">Select **Add rule**</span></span>

1. <span data-ttu-id="06c8f-173">Agregue su primera condición con FullName.</span><span class="sxs-lookup"><span data-stu-id="06c8f-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="06c8f-174">Para eCommerceContacts, seleccione **FullName** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="06c8f-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="06c8f-175">Para loyCustomers, seleccione **FullName** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="06c8f-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="06c8f-176">Seleccione el menú desplegable **Normalizar** y elija **Tipo (teléfono, nombre, dirección, ...)**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="06c8f-177">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="06c8f-178">Introduzca el nombre **FullName, Email** para la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="06c8f-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="06c8f-179">Agregar una segunda condición para la dirección de correo electrónico seleccionando **Agregar condición**</span><span class="sxs-lookup"><span data-stu-id="06c8f-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="06c8f-180">Para la entidad eCommerceContacts, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="06c8f-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="06c8f-181">Para la entidad loyCustomers, elija **Correo electrónico** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="06c8f-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="06c8f-182">Deje Normalizar en blanco.</span><span class="sxs-lookup"><span data-stu-id="06c8f-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="06c8f-183">Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unifique la regla de coincidencia para el nombre y el correo electrónico.](media/unify-match-rule.png)

1. <span data-ttu-id="06c8f-185">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-185">Select **Done**.</span></span>

1. <span data-ttu-id="06c8f-186">Seleccione **Guardar** y **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="06c8f-187">Combinar</span><span class="sxs-lookup"><span data-stu-id="06c8f-187">Merge</span></span>

1. <span data-ttu-id="06c8f-188">Vaya a la pestaña **Fusionar**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="06c8f-189">En **ContactId** de la entidad **loyCustomers**, cambie el nombre para mostrar a **ContactIdLOYALTY** para diferenciarlo de los otros id. ingeridos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![cambie el nombre de contactid a partir del id. de fidelidad.](media/unify-merge-contactid.png)

1. <span data-ttu-id="06c8f-191">Seleccione **Guardar** y **Ejecutar fusión y procesos subsiguientes**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="06c8f-192">Tarea 3: configurar el valor de vida útil del cliente predicción</span><span class="sxs-lookup"><span data-stu-id="06c8f-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="06c8f-193">Con los perfiles de cliente unificados en su lugar, ahora podemos ejecutar el valor de vida útil del cliente predicción.</span><span class="sxs-lookup"><span data-stu-id="06c8f-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="06c8f-194">Para conocer los pasos detallados, consulte [Predicción de vida útil del cliente (versión preliminar)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="06c8f-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="06c8f-195">Vaya a **Inteligencia**  > **Predicciones** y seleccione el **Modelo de valor de vida útil**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="06c8f-196">Revise la información en el panel lateral y seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="06c8f-197">Nombre el modelo **OOB eCommerce CLV predicción** y la entidad de salida **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="06c8f-198">Defina las preferencias del modelo para el modelo CLV:</span><span class="sxs-lookup"><span data-stu-id="06c8f-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="06c8f-199">**Predicción período de tiempo**: **12 meses o 1 año**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="06c8f-200">Esta configuración define qué tan lejos en el futuro se predecirá el valor de vida útil del cliente.</span><span class="sxs-lookup"><span data-stu-id="06c8f-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="06c8f-201">**Clientes activos**: especifique qué significan los clientes activos para su empresa.</span><span class="sxs-lookup"><span data-stu-id="06c8f-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="06c8f-202">Establezca el período de tiempo histórico en el que un cliente debe haber tenido al menos una transacción para ser considerado activo.</span><span class="sxs-lookup"><span data-stu-id="06c8f-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="06c8f-203">El modelo solo predecirá CLV para clientes activos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="06c8f-204">Elija entre dejar que el modelo calcule el período de tiempo en función de los datos históricos de transacciones o proporcionar un período de tiempo específico.</span><span class="sxs-lookup"><span data-stu-id="06c8f-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="06c8f-205">En esta guía de muestra, **deje que el modelo calcule el intervalo de compra**, que es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="06c8f-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="06c8f-206">**Clientes de alto valor**: defina los clientes de alto valor como un percentil de los clientes que más pagan.</span><span class="sxs-lookup"><span data-stu-id="06c8f-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="06c8f-207">El modelo utiliza esta entrada para proporcionar resultados que se ajustan a la definición de su negocio de clientes de alto valor.</span><span class="sxs-lookup"><span data-stu-id="06c8f-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="06c8f-208">Puede elegir permitir que el modelo defina qué clientes son de alto valor.</span><span class="sxs-lookup"><span data-stu-id="06c8f-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="06c8f-209">Utiliza una regla heurística que deriva el percentil.</span><span class="sxs-lookup"><span data-stu-id="06c8f-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="06c8f-210">También puede definir clientes de alto valor como un percentil de los clientes futuros que más pagan.</span><span class="sxs-lookup"><span data-stu-id="06c8f-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="06c8f-211">En esta guía de muestra, definimos manualmente a los clientes de alto valor como **30% superior de los clientes activos que pagan** y seleccione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Paso de preferencias en la experiencia guiada para el modelo CLV.":::

1. <span data-ttu-id="06c8f-213">En el paso **Datos necesarios**, seleccione **Agregar datos** para proporcionar los datos del historial de transacciones.</span><span class="sxs-lookup"><span data-stu-id="06c8f-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="06c8f-214">Añada la entidad **eCommercePurchases: eCommerce** y asigne los atributos que requiere el modelo:</span><span class="sxs-lookup"><span data-stu-id="06c8f-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="06c8f-215">ID de transacción: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="06c8f-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="06c8f-216">Fecha de transacción: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="06c8f-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="06c8f-217">Importe de la transacción: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="06c8f-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="06c8f-218">Id. del producto: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="06c8f-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="06c8f-219">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-219">Select **Next**.</span></span>

1. <span data-ttu-id="06c8f-220">Establezca la relación entre la entidad **eCommercePurchases: eCommerce** y **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="06c8f-221">El paso **Datos adicionales (opcional)** le permite agregar más datos de actividad del cliente.</span><span class="sxs-lookup"><span data-stu-id="06c8f-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="06c8f-222">Estos datos pueden ayudar a obtener más información sobre las interacciones de los clientes con su empresa, lo que puede contribuir al CLV.</span><span class="sxs-lookup"><span data-stu-id="06c8f-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="06c8f-223">Agregue interacciones clave con el cliente, como registros web, registros servicio al cliente o el historial del programa de recompensas, puede mejorar la precisión de las predicciones.</span><span class="sxs-lookup"><span data-stu-id="06c8f-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="06c8f-224">Seleccione **Agregar datos** para incluir más datos de actividad del cliente.</span><span class="sxs-lookup"><span data-stu-id="06c8f-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="06c8f-225">Agregue la entidad de actividad del cliente y asigne los nombres de sus campos a los campos correspondientes requeridos por el modelo:</span><span class="sxs-lookup"><span data-stu-id="06c8f-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="06c8f-226">Entidad de actividad del cliente: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="06c8f-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="06c8f-227">Clave principal: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="06c8f-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="06c8f-228">Marca de tiempo: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="06c8f-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="06c8f-229">Evento (nombre de la actividad): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="06c8f-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="06c8f-230">Detalles (cantidad o valor): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="06c8f-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="06c8f-231">Seleccione **Siguiente** y configure la actividad y la relación entre los datos de la transacción y los datos del cliente:</span><span class="sxs-lookup"><span data-stu-id="06c8f-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="06c8f-232">Tipo de actividad: elegir existente</span><span class="sxs-lookup"><span data-stu-id="06c8f-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="06c8f-233">Etiqueta de actividad: Review</span><span class="sxs-lookup"><span data-stu-id="06c8f-233">Activity label: Review</span></span>
   - <span data-ttu-id="06c8f-234">Etiqueta correspondiente: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="06c8f-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="06c8f-235">Entidad del cliente: : eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="06c8f-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="06c8f-236">Relación: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="06c8f-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="06c8f-237">Seleccione **Siguiente** para establecer la programación del modelo.</span><span class="sxs-lookup"><span data-stu-id="06c8f-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="06c8f-238">El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se introducen nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="06c8f-239">Para este ejemplo, elija **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="06c8f-240">Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="06c8f-241">Tarea 4: revisar los resultados y las explicaciones del modelo</span><span class="sxs-lookup"><span data-stu-id="06c8f-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="06c8f-242">Deje que el modelo complete el entrenamiento y la puntuación de los datos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="06c8f-243">A continuación, puede revisar los resultados y las explicaciones del modelo CLV.</span><span class="sxs-lookup"><span data-stu-id="06c8f-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="06c8f-244">Para más información, consulte [Revisar un estado de predicción y los resultados](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="06c8f-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="06c8f-245">Tarea 5: crear un segmento de clientes de alto valor</span><span class="sxs-lookup"><span data-stu-id="06c8f-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="06c8f-246">La ejecución del modelo crea una nueva entidad, que se enumera en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="06c8f-247">Puede crear un nuevo segmento de clientes basado en la entidad creada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="06c8f-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="06c8f-248">Vaya a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="06c8f-249">Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**.</span><span class="sxs-lookup"><span data-stu-id="06c8f-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creación de un segmento con la salida del modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="06c8f-251">Seleccione la entidad **OOBeCommerceCLVPrediction** y defina el segmento:</span><span class="sxs-lookup"><span data-stu-id="06c8f-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="06c8f-252">Campo: CLVScore</span><span class="sxs-lookup"><span data-stu-id="06c8f-252">Field: CLVScore</span></span>
  - <span data-ttu-id="06c8f-253">Operador: mayor que</span><span class="sxs-lookup"><span data-stu-id="06c8f-253">Operator: greater than</span></span>
  - <span data-ttu-id="06c8f-254">Valor: 1500</span><span class="sxs-lookup"><span data-stu-id="06c8f-254">Value: 1500</span></span>

1. <span data-ttu-id="06c8f-255">Seleccione **Revisar** y **Guardar** el segmento.</span><span class="sxs-lookup"><span data-stu-id="06c8f-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="06c8f-256">Ahora tiene un segmento que identifica a los clientes que se prevé que generarán más de 1500 $ de ingresos en los próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="06c8f-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="06c8f-257">Este segmento se actualiza dinámicamente si se ingieren más datos.</span><span class="sxs-lookup"><span data-stu-id="06c8f-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="06c8f-258">Para obtener más información, vea [Crear y administrar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="06c8f-258">For more information, see [Create and manage segments](segments.md).</span></span>
