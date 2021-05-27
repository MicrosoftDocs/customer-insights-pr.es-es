---
title: Abordar el enriquecimiento de la mejora
description: Enriquezca y normalice la información de direcciones de los perfiles de los clientes con los modelos de Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965599"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="cb914-103">Enriquecimiento de perfiles de clientes con direcciones mejoradas</span><span class="sxs-lookup"><span data-stu-id="cb914-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="cb914-104">Las direcciones de sus datos pueden no estar estructuradas, estar incompletas o ser incorrectas.</span><span class="sxs-lookup"><span data-stu-id="cb914-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="cb914-105">Utilice los modelos de Microsoft para normalizar y enriquecer sus direcciones en el [Formato de Common Data Model](/common-data-model/schema/core/applicationcommon/address) para una mejor precisión y conocimientos.</span><span class="sxs-lookup"><span data-stu-id="cb914-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="cb914-106">Cómo mejoramos las direcciones</span><span class="sxs-lookup"><span data-stu-id="cb914-106">How we enhance addresses</span></span>

<span data-ttu-id="cb914-107">Nuestro modelo pasa por un proceso de dos pasos para mejorar una dirección.</span><span class="sxs-lookup"><span data-stu-id="cb914-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="cb914-108">Primero, analiza la dirección para identificar sus componentes y los coloca en un formato estructurado.</span><span class="sxs-lookup"><span data-stu-id="cb914-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="cb914-109">Luego, usamos inteligencia artificial para corregir, completar y estandarizar los valores en la dirección.</span><span class="sxs-lookup"><span data-stu-id="cb914-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="cb914-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb914-110">Example</span></span>

<span data-ttu-id="cb914-111">La información de la dirección puede tener un formato no estándar y contener errores ortográficos.</span><span class="sxs-lookup"><span data-stu-id="cb914-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="cb914-112">El modelo puede solucionar estos problemas y crear direcciones coherentes en perfiles de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="cb914-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="cb914-113">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="cb914-113">Limitations</span></span>

<span data-ttu-id="cb914-114">Las direcciones mejoradas solo funcionan con los valores que ya existen en los datos de direcciones ingeridos.</span><span class="sxs-lookup"><span data-stu-id="cb914-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="cb914-115">El modelo no hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb914-115">The model doesn't:</span></span> 

1. <span data-ttu-id="cb914-116">Verificar si la dirección es una dirección válida.</span><span class="sxs-lookup"><span data-stu-id="cb914-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="cb914-117">Verificar si alguno de los valores, como los códigos postales o nombres de calles, es válido.</span><span class="sxs-lookup"><span data-stu-id="cb914-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="cb914-118">Cambiar valores que no reconoce.</span><span class="sxs-lookup"><span data-stu-id="cb914-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="cb914-119">El modelo utiliza técnicas basadas en el aprendizaje automático para mejorar las direcciones.</span><span class="sxs-lookup"><span data-stu-id="cb914-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="cb914-120">Si bien aplicamos un umbral de confianza alto para cuando el modelo cambia un valor de entrada, como con cualquier modelo basado en ML, no se garantiza una precisión del 100 %.</span><span class="sxs-lookup"><span data-stu-id="cb914-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="cb914-121">Países o regiones compatibles</span><span class="sxs-lookup"><span data-stu-id="cb914-121">Supported countries or regions</span></span>

<span data-ttu-id="cb914-122">Actualmente admitimos direcciones enriquecidas en estos países o regiones:</span><span class="sxs-lookup"><span data-stu-id="cb914-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="cb914-123">Australia</span><span class="sxs-lookup"><span data-stu-id="cb914-123">Australia</span></span>
- <span data-ttu-id="cb914-124">Canadá</span><span class="sxs-lookup"><span data-stu-id="cb914-124">Canada</span></span>
- <span data-ttu-id="cb914-125">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="cb914-125">United Kingdom</span></span>
- <span data-ttu-id="cb914-126">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="cb914-126">United States</span></span>

<span data-ttu-id="cb914-127">Las direcciones deben contener un valor de país o región.</span><span class="sxs-lookup"><span data-stu-id="cb914-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="cb914-128">No procesamos direcciones de países o regiones que no son compatibles ni direcciones que no tienen ningún país o región proporcionado.</span><span class="sxs-lookup"><span data-stu-id="cb914-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="cb914-129">Configurar el enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="cb914-129">Configure the enrichment</span></span>

1. <span data-ttu-id="cb914-130">Vaya a **Datos** > **Enriquecimiento**.</span><span class="sxs-lookup"><span data-stu-id="cb914-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="cb914-131">Seleccione **Enriquecer mis datos** en el mosaico **Direcciones mejoradas**.</span><span class="sxs-lookup"><span data-stu-id="cb914-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de pantalla del mosaico de direcciones mejoradas.":::

1. <span data-ttu-id="cb914-133">Selecciona el **Conjunto de datos de clientes** y elija la entidad que contiene las direcciones que desea enriquecer.</span><span class="sxs-lookup"><span data-stu-id="cb914-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="cb914-134">Puede seleccionar la entidad *Cliente* para enriquecer direcciones en todos sus perfiles de clientes o seleccionar una entidad de segmento para enriquecer direcciones solo en perfiles de clientes contenidos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="cb914-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="cb914-135">Seleccione cómo se formatean las direcciones en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="cb914-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="cb914-136">Escoja **Dirección de atributo único** si las direcciones de sus datos utilizan un solo campo.</span><span class="sxs-lookup"><span data-stu-id="cb914-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="cb914-137">Escoja **Dirección de atributos múltiples** si las direcciones de sus datos utilizan más de un campo de datos.</span><span class="sxs-lookup"><span data-stu-id="cb914-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cb914-138">El país o la región son obligatorios, tanto en la dirección de atributo único como en la de atributos múltiples.</span><span class="sxs-lookup"><span data-stu-id="cb914-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="cb914-139">Las direcciones que no contienen valores de país o región válidos o admitidos no se enriquecerán</span><span class="sxs-lookup"><span data-stu-id="cb914-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="cb914-140">Asigne los campos de direcciones de su entidad de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="cb914-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página mejorada de asignación de campos de direcciones.":::

1. <span data-ttu-id="cb914-142">Seleccione **Siguiente** para completar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="cb914-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="cb914-143">Proporcione un nombre para el enriquecimiento y la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="cb914-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="cb914-144">Seleccione **Guardar enriquecimiento** después de revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="cb914-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="cb914-145">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="cb914-145">Enrichment results</span></span>

<span data-ttu-id="cb914-146">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="cb914-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="cb914-147">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cb914-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cb914-148">El tiempo de procesamiento depende del tamaño de los datos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="cb914-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="cb914-149">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="cb914-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="cb914-150">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="cb914-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="cb914-151">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="cb914-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb914-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cb914-152">Next steps</span></span>

<span data-ttu-id="cb914-153">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="cb914-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="cb914-154">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="cb914-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
