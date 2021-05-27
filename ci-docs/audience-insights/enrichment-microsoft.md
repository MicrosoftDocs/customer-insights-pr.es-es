---
title: Enriquecer los perfiles de los clientes con datos de Microsoft
description: Utilice datos propios de Microsoft para enriquecer los datos de sus clientes con afinidades de marca e intereses.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064912"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="42f5b-103">Enriquezca los perfiles de los clientes con afinidades de marca e interés (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="42f5b-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="42f5b-104">Utilice datos propios de Microsoft para enriquecer los datos de sus clientes con afinidades de marca e intereses.</span><span class="sxs-lookup"><span data-stu-id="42f5b-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="42f5b-105">Estas afinidades se determinan en función de los datos de personas con datos demográficos similares a los de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="42f5b-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="42f5b-106">Esta información le ayuda a comprender y segmentar mejor a sus clientes en función de sus afinidades con marcas e intereses específicos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="42f5b-107">En la información de público, vaya a **Datos** > **Enriquecimiento** para [configurar y ver enriquecimientos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="42f5b-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="42f5b-108">Para configurar el enriquecimiento de afinidades de marca, vaya a la pestaña **Descubrir** y seleccione **Enriquecer mis datos** en la ventana **Marcas**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="42f5b-109">Para configurar el enriquecimiento de afinidades de intereses, vaya a la pestaña **Descubrir** y seleccione **Enriquecer mis datos** en la ventana **Intereses**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42f5b-110">![Ventanas Marcas y aficiones](media/BrandsInterest-tile-Hub.png "Ventanas Marcas y aficiones")</span><span class="sxs-lookup"><span data-stu-id="42f5b-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="42f5b-111">Cómo determinamos las afinidades</span><span class="sxs-lookup"><span data-stu-id="42f5b-111">How we determine affinities</span></span>

<span data-ttu-id="42f5b-112">Usamos los datos de búsqueda en línea de Microsoft para encontrar afinidades por marcas e intereses en varios segmentos demográficos (definidos por edad, género o ubicación).</span><span class="sxs-lookup"><span data-stu-id="42f5b-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="42f5b-113">El volumen de búsqueda en línea de una marca o interés determina cuánta afinidad tiene un segmento demográfico, en comparación con otros segmentos, con esa marca o interés.</span><span class="sxs-lookup"><span data-stu-id="42f5b-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="42f5b-114">Nivel de afinidad y puntuación</span><span class="sxs-lookup"><span data-stu-id="42f5b-114">Affinity level and score</span></span>

<span data-ttu-id="42f5b-115">En cada perfil de cliente enriquecido, proporcionamos dos valores relacionados: nivel de afinidad y puntuación de afinidad.</span><span class="sxs-lookup"><span data-stu-id="42f5b-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="42f5b-116">Estos valores le ayudan a determinar el nivel de afinidad para el segmento demográfico de ese perfil, para una marca o interés, en comparación con otros segmentos demográficos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="42f5b-117">El *nivel de afinidad* consta de cuatro niveles y la *puntuación de afinidad* se calcula en una escala de 100 puntos que se asigna a los niveles de afinidad.</span><span class="sxs-lookup"><span data-stu-id="42f5b-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="42f5b-118">Nivel de afinidad</span><span class="sxs-lookup"><span data-stu-id="42f5b-118">Affinity level</span></span> |<span data-ttu-id="42f5b-119">Puntuación de afinidad</span><span class="sxs-lookup"><span data-stu-id="42f5b-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="42f5b-120">Muy alto</span><span class="sxs-lookup"><span data-stu-id="42f5b-120">Very high</span></span>     | <span data-ttu-id="42f5b-121">85-100</span><span class="sxs-lookup"><span data-stu-id="42f5b-121">85-100</span></span>       |
|<span data-ttu-id="42f5b-122">Alto</span><span class="sxs-lookup"><span data-stu-id="42f5b-122">High</span></span>     | <span data-ttu-id="42f5b-123">70-84</span><span class="sxs-lookup"><span data-stu-id="42f5b-123">70-84</span></span>        |
|<span data-ttu-id="42f5b-124">Medio</span><span class="sxs-lookup"><span data-stu-id="42f5b-124">Medium</span></span>     | <span data-ttu-id="42f5b-125">35-69</span><span class="sxs-lookup"><span data-stu-id="42f5b-125">35-69</span></span>        |
|<span data-ttu-id="42f5b-126">Bajo</span><span class="sxs-lookup"><span data-stu-id="42f5b-126">Low</span></span>     | <span data-ttu-id="42f5b-127">1-34</span><span class="sxs-lookup"><span data-stu-id="42f5b-127">1-34</span></span>        |

<span data-ttu-id="42f5b-128">Dependiendo de la granularidad que desee para medir la afinidad, puede utilizar el nivel de afinidad o la puntuación.</span><span class="sxs-lookup"><span data-stu-id="42f5b-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="42f5b-129">La puntuación de afinidad le brinda un control más preciso.</span><span class="sxs-lookup"><span data-stu-id="42f5b-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="42f5b-130">Países/regiones admitidos</span><span class="sxs-lookup"><span data-stu-id="42f5b-130">Supported countries/regions</span></span>

<span data-ttu-id="42f5b-131">Actualmente admitimos las siguientes opciones de país/región: Australia, Canadá (inglés), Francia, Alemania, Reino Unido o Estados Unidos (inglés).</span><span class="sxs-lookup"><span data-stu-id="42f5b-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="42f5b-132">Para seleccionar un país, abra **Enriquecimiento de marcas** o **Enriquecimiento de intereses** y seleccione **Cambiar** junto a **País/Región**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="42f5b-133">En el panel **Configuración de país/región**, elija una opción y seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="42f5b-134">Implicaciones relacionadas con la selección de países</span><span class="sxs-lookup"><span data-stu-id="42f5b-134">Implications related to country selection</span></span>

- <span data-ttu-id="42f5b-135">A la hora de [elegir sus propias marcas](#define-your-brands-or-interests), el sistema proporciona sugerencias basadas en el país o región seleccionados.</span><span class="sxs-lookup"><span data-stu-id="42f5b-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="42f5b-136">Cuando [elige un sector](#define-your-brands-or-interests), obtendrá las marcas o los intereses más relevantes según el país o la región seleccionados.</span><span class="sxs-lookup"><span data-stu-id="42f5b-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="42f5b-137">Cuando [enriquezca perfiles](#refresh-enrichment), enriqueceremos todos los perfiles de cliente para los que obtenemos datos para las marcas e intereses seleccionados.</span><span class="sxs-lookup"><span data-stu-id="42f5b-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="42f5b-138">Incluyendo perfiles que no se encuentran en el país o región seleccionados.</span><span class="sxs-lookup"><span data-stu-id="42f5b-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="42f5b-139">Por ejemplo, si seleccionó Alemania, enriqueceremos los perfiles ubicados en los Estados Unidos si tenemos datos disponibles para las marcas e intereses seleccionados en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="42f5b-140">Configurar enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="42f5b-140">Configure Enrichment</span></span>

<span data-ttu-id="42f5b-141">Una experiencia guiada le ayuda a configurar los enriquecimientos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="42f5b-142">Defina sus marcas o intereses</span><span class="sxs-lookup"><span data-stu-id="42f5b-142">Define your brands or interests</span></span>

<span data-ttu-id="42f5b-143">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="42f5b-143">Select one of the following options:</span></span>

- <span data-ttu-id="42f5b-144">**Sector**: el sistema identifica las principales marcas o intereses relevantes para su sector y enriquece los datos de sus clientes con ellos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="42f5b-145">**Elegir el suyo propio**: seleccione hasta cinco elementos de la lista de marcas o intereses más relevantes para su organización.</span><span class="sxs-lookup"><span data-stu-id="42f5b-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="42f5b-146">Para agregar una marca o interés, especifíquelo en el área de entrada para obtener sugerencias basadas en términos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="42f5b-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="42f5b-147">Si no enumeramos una marca o interés que está buscando, envíenos sus comentarios utilizando el vínculo **Sugerir**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="42f5b-148">Revisar la preferencias de enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="42f5b-148">Review enrichment preferences</span></span>

<span data-ttu-id="42f5b-149">Revise sus preferencias de enriquecimiento predeterminadas y actualícelas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="42f5b-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla de la ventana de preferencias de enriquecimiento.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="42f5b-151">Seleccione la entidad que desea enriquecer</span><span class="sxs-lookup"><span data-stu-id="42f5b-151">Select entity to enrich</span></span>

<span data-ttu-id="42f5b-152">Seleccione **Entidad enriquecida** y elija el conjunto de datos del cliente que desea enriquecer con datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="42f5b-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="42f5b-153">Puede seleccionar la entidad Cliente para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="42f5b-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="42f5b-154">Asignar sus campos</span><span class="sxs-lookup"><span data-stu-id="42f5b-154">Map your fields</span></span>

<span data-ttu-id="42f5b-155">Asigne campos de su entidad de cliente unificada para definir el segmento demográfico que desea que utilice el sistema para enriquecer los datos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="42f5b-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="42f5b-156">Mapa del país o región y al menos los atributos de fecha de nacimiento o género.</span><span class="sxs-lookup"><span data-stu-id="42f5b-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="42f5b-157">Además, debe asignar al menos una de las ciudades (y estado o provincia) o códigos postales.</span><span class="sxs-lookup"><span data-stu-id="42f5b-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="42f5b-158">Seleccione **Editar** para definir la asignación de campos y seleccione **Aplicar** cuando termine.</span><span class="sxs-lookup"><span data-stu-id="42f5b-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="42f5b-159">Seleccione **Guardar** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="42f5b-160">Se admiten los siguientes formatos y valores, los valores no distinguen entre mayúsculas y minúsculas:</span><span class="sxs-lookup"><span data-stu-id="42f5b-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="42f5b-161">**Fecha de nacimiento**: eecomendamos que la fecha de nacimiento se convierta al tipo DateTime durante la ingestión de datos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="42f5b-162">Alternativamente, puede ser una cadena en [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), formato "aaaa-MM-dd" o "aaaa-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="42f5b-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="42f5b-163">**Género**: Masculino, Femenino, Desconocido</span><span class="sxs-lookup"><span data-stu-id="42f5b-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="42f5b-164">**Código postal**: códigos postales de cinco dígitos para EE. UU., código postal estándar en cualquier otro lugar</span><span class="sxs-lookup"><span data-stu-id="42f5b-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="42f5b-165">**Ciudad** : nombre de la ciudad en inglés</span><span class="sxs-lookup"><span data-stu-id="42f5b-165">**City**: City name in English</span></span>
- <span data-ttu-id="42f5b-166">**Estado o provincia**: abreviatura de dos letras para EE. UU. y Canadá.</span><span class="sxs-lookup"><span data-stu-id="42f5b-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="42f5b-167">Abreviatura de dos o tres letras para Australia.</span><span class="sxs-lookup"><span data-stu-id="42f5b-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="42f5b-168">No se aplica a Francia, Alemania ni al Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="42f5b-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="42f5b-169">**País/Región**:</span><span class="sxs-lookup"><span data-stu-id="42f5b-169">**Country/Region**:</span></span>

  - <span data-ttu-id="42f5b-170">EE.UU .: Estados Unidos de América, Estados Unidos, EE. UU., EE. UU., América</span><span class="sxs-lookup"><span data-stu-id="42f5b-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="42f5b-171">CA: Canadá, CA</span><span class="sxs-lookup"><span data-stu-id="42f5b-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="42f5b-172">GB: Reino Unido, UK, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda del Norte, Reino Unido de Gran Bretaña</span><span class="sxs-lookup"><span data-stu-id="42f5b-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="42f5b-173">AU: Australia, AU, Common Wealth of Australia</span><span class="sxs-lookup"><span data-stu-id="42f5b-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="42f5b-174">FR: Francia, FR, República francesa</span><span class="sxs-lookup"><span data-stu-id="42f5b-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="42f5b-175">DE: Alemania, Alemán, Deutschland, Allemagne, DE, República Federal de Alemania, República de Alemania</span><span class="sxs-lookup"><span data-stu-id="42f5b-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="42f5b-176">Revisar y nombrar el enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="42f5b-176">Review and name the enrichment</span></span>

<span data-ttu-id="42f5b-177">Finalmente, puede revisar la información y proporcionar un nombre para el enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="42f5b-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisión de intereses y poner un nombre a la página.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="42f5b-179">Actualizar enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="42f5b-179">Refresh enrichment</span></span>

<span data-ttu-id="42f5b-180">Ejecute el enriquecimiento después de configurar marcas, intereses y la asignación de campos para la demografía.</span><span class="sxs-lookup"><span data-stu-id="42f5b-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="42f5b-181">Para comenzar el proceso, seleccione **Ejecutar** en la página de configuración de marcas o intereses.</span><span class="sxs-lookup"><span data-stu-id="42f5b-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="42f5b-182">Además, puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una actualización programada.</span><span class="sxs-lookup"><span data-stu-id="42f5b-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="42f5b-183">Dependiendo del tamaño de los datos de sus clientes, puede llevar varios minutos completar una ejecución de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="42f5b-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="42f5b-184">Existen [seis tipos de estado](system.md#status-types) para tareas/procesos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="42f5b-185">Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="42f5b-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="42f5b-186">Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="42f5b-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="42f5b-187">Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.</span><span class="sxs-lookup"><span data-stu-id="42f5b-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="42f5b-188">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="42f5b-188">Enrichment results</span></span>

<span data-ttu-id="42f5b-189">Después de ejecutar el proceso de enriquecimiento, vaya a **Mis enriquecimientos** para revisar el número total de clientes enriquecidos y un desglose de marcas o intereses en los perfiles de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="42f5b-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Vista previa de resultados después de ejecutar el proceso de enriquecimiento":::

<span data-ttu-id="42f5b-191">Revise los datos enriquecidos seleccionando **Ver datos enriquecidos** en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="42f5b-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="42f5b-192">Los datos enriquecidos para las marcas van a la entidad **MarcaAffinityDeMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="42f5b-193">Los datos de intereses están en la entidad **InterésAfinidadDeMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="42f5b-194">También encontrará estas entidades indicadas en el grupo **Enriquecimiento** en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="42f5b-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="42f5b-195">Vea datos de enriquecimiento en la tarjeta del cliente</span><span class="sxs-lookup"><span data-stu-id="42f5b-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="42f5b-196">Las afinidades de marcas e intereses también se pueden ver en tarjetas de clientes individuales.</span><span class="sxs-lookup"><span data-stu-id="42f5b-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="42f5b-197">Vaya a **Clientes** y seleccione un perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="42f5b-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="42f5b-198">En la tarjeta del cliente, encontrará gráficos de las marcas o intereses por los que las personas del perfil demográfico de ese cliente tienen afinidad.</span><span class="sxs-lookup"><span data-stu-id="42f5b-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Tarjeta de cliente con datos enriquecidos":::

## <a name="next-steps"></a><span data-ttu-id="42f5b-200">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="42f5b-200">Next steps</span></span>

<span data-ttu-id="42f5b-201">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="42f5b-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="42f5b-202">Cree [Segmentos](segments.md), [Medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="42f5b-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
