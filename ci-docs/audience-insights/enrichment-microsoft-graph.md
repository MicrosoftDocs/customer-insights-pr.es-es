---
title: Enriquecer los perfiles de los clientes con Microsoft Graph
description: Utilice datos de propiedad de Microsoft Graph para enriquecer los datos de sus clientes con afinidades de marca e interés.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407016"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enriquezca los perfiles de los clientes con afinidades de marca e interés (versión preliminar)

Utilice datos de propiedad de Microsoft Graph para enriquecer los datos de sus clientes con afinidades de marca e interés. Estas afinidades se determinan en función de los datos de personas con datos demográficos similares a los de sus clientes. Esta información le ayuda a comprender y segmentar mejor a sus clientes en función de sus afinidades con marcas e intereses específicos.

En la información de público, vaya a **Datos** > **Enriquecimiento** para [configurar y ver enriquecimientos](enrichment-hub.md).

Para configurar el enriquecimiento de afinidades de marca, vaya a la pestaña **Descubrir** y seleccione **Enriquecer mis datos** en la ventana **Marcas**.

Para configurar el enriquecimiento de afinidades de intereses, vaya a la pestaña **Descubrir** y seleccione **Enriquecer mis datos** en la ventana **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Ventanas Marcas y aficiones](media/BrandsInterest-tile-Hub.png "Ventanas Marcas y aficiones")

## <a name="about-microsoft-graph"></a>Acerca de Microsoft Graph

Utilizamos los datos de búsqueda en línea de Microsoft Graph para encontrar afinidades para marcas e intereses en varios segmentos demográficos (definidos por edad, género o ubicación). El volumen de búsqueda en línea de una marca o interés determina cuánta afinidad tiene un segmento demográfico, en comparación con otros segmentos, con esa marca o interés.

[Más información acerca de Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Puntuación y confianza de afinidad

La **puntuación de afinidad** se calcula sobre una escala de 100 puntos, donde 100 representa el segmento que tiene la mayor afinidad por una marca o interés.

La **confianza de afinidad** también se calcula en una escala de 100 puntos. Indica el nivel de confianza del sistema para el que tiene afinidad un segmento para la marca o el interés. El nivel de confianza se basa en el tamaño del segmento y la granularidad del segmento. El tamaño del segmento está determinado por la cantidad de datos que tenemos para un segmento dado. La granularidad del segmento se determina por la cantidad de atributos (edad, sexo, ubicación) que están disponibles en un perfil.

No normalizamos las puntuaciones para su conjunto de datos. En consecuencia, es posible que no vea todos los posibles valores de puntuación de afinidad para su conjunto de datos. Por ejemplo, puede que no haya un perfil de cliente enriquecido con una puntuación de afinidad de 100 en sus datos. Eso es posible si no existen clientes en el segmento demográfico que obtuvieron una puntuación de 100 para una determinada marca o interés.

> [!TIP]
> Cuando [crea segmentos](segments.md) utilizando puntuaciones de afinidad, revise la distribución de puntuaciones de afinidad para su conjunto de datos antes de decidir los umbrales de puntuación apropiados. Por ejemplo, una puntuación de afinidad de 10 puede considerarse significativa en un conjunto de datos que tiene una puntuación de afinidad más alta de solo 25 para una marca o interés determinado.

## <a name="supported-countriesregions"></a>Países/regiones admitidos

Actualmente admitimos las siguientes opciones de país/región: Australia, Canadá (inglés), Francia, Alemania, Reino Unido o Estados Unidos (inglés).

Para seleccionar un país, abra **Enriquecimiento de marcas** o **Enriquecimiento de intereses** y seleccione **Cambiar** junto a **País/Región**. En el panel **Configuración de país/región**, elija una opción y seleccione **Aplicar**.

### <a name="implications-related-to-country-selection"></a>Implicaciones relacionadas con la selección de países

- Cuando esté [eligiendo sus propias marcas](#define-your-brands-or-interests), proporcionaremos sugerencias basadas en el país/región seleccionado.

- Al [elegir una industria](#define-your-brands-or-interests), identificaremos las marcas o intereses más relevantes en función del país/región seleccionado.

- Al [asignar sus campos](#map-your-fields), si el campo País/Región no está asignado, usaremos los datos de Microsoft Graph del país/región seleccionado para enriquecer los perfiles de sus clientes. También usaremos esa selección para enriquecer los perfiles de sus clientes que no tienen datos de país/región disponibles.

- Cuando esté [enriqueciendo perfiles](#refresh-enrichment), enriqueceremos todos los perfiles de clientes para los que tenemos datos de Microsoft Graph disponibles para las marcas e intereses seleccionados, incluidos los perfiles que no se encuentran en el país/región seleccionado. Por ejemplo, si seleccionó Alemania, enriqueceremos los perfiles ubicados en los Estados Unidos si tenemos datos de Microsoft Graph disponibles para las marcas e intereses seleccionados en los Estados Unidos.

## <a name="configure-enrichment"></a>Configurar enriquecimiento

La configuración del enriquecimiento de marcas o intereses consta de dos pasos:

### <a name="define-your-brands-or-interests"></a>Defina sus marcas o intereses

Seleccione una de las siguientes opciones:

- **Sector**: el sistema identifica las principales marcas o intereses relevantes para su sector y enriquece los datos de sus clientes con ellos.
- **Elegir el suyo propio**: seleccione hasta cinco elementos de la lista de marcas o intereses más relevantes para su organización.

Para agregar una marca o interés, especifíquelo en el área de entrada para obtener sugerencias basadas en términos coincidentes. Si no enumeramos una marca o interés que está buscando, envíenos sus comentarios utilizando el vínculo **Sugerir**.

### <a name="map-your-fields"></a>Asignar sus campos

Asigne campos desde su entidad de cliente unificada a al menos dos atributos para definir el segmento demográfico que desea que usemos para enriquecer los datos de sus clientes. Seleccione **Editar** para definir la asignación de campos y seleccione **Aplicar** cuando termine. Seleccione **Guardar** para completar la asignación de campos.

Se admiten los siguientes formatos y valores, los valores no distinguen entre mayúsculas y minúsculas:

- **Fecha de nacimiento**: eecomendamos que la fecha de nacimiento se convierta al tipo DateTime durante la ingestión de datos. Alternativamente, puede ser una cadena en [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), formato "aaaa-MM-dd" o "aaaa-MM-ddTHH:mm:ssZ".
- **Género**: Masculino, Femenino, Desconocido
- **Código postal**: códigos postales de cinco dígitos para EE. UU., código postal estándar en cualquier otro lugar
- **Ciudad** : nombre de la ciudad en inglés
- **Estado o provincia**: abreviatura de dos letras para EE. UU. y Canadá. Abreviatura de dos o tres letras para Australia. No se aplica a Francia, Alemania ni al Reino Unido.
- **País/Región**:

  - EE.UU .: Estados Unidos de América, Estados Unidos, EE. UU., EE. UU., América
  - CA: Canadá, CA
  - GB: Reino Unido, UK, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda del Norte, Reino Unido de Gran Bretaña
  - AU: Australia, AU, Common Wealth of Australia
  - FR: Francia, FR, República francesa
  - DE: Alemania, Alemán, Deutschland, Allemagne, DE, República Federal de Alemania, República de Alemania

## <a name="refresh-enrichment"></a>Actualizar enriquecimiento

Ejecute el enriquecimiento después de configurar marcas, intereses y la asignación de campos para la demografía. Para comenzar el proceso, seleccione **Ejecutar** en la página de configuración de marcas o intereses. Además, puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una actualización programada.
Dependiendo del tamaño de los datos de sus clientes, puede llevar varios minutos completar una ejecución de enriquecimiento.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Después de ejecutar el proceso de enriquecimiento, vaya a **Mis enriquecimientos** para revisar el número total de clientes enriquecidos y un desglose de marcas o intereses en los perfiles de clientes enriquecidos.

:::image type="content" source="media/my-enrichments.png" alt-text="Vista previa de resultados después de ejecutar el proceso de enriquecimiento":::

Revise los datos enriquecidos seleccionando **Ver datos enriquecidos** en el gráfico. Los datos enriquecidos para las marcas van a la entidad **MarcaAffinityDeMicrosoft**. Los datos de intereses están en la entidad **InterésAfinidadDeMicrosoft**. También encontrará estas entidades indicadas en el grupo **Enriquecimiento** en **Datos** > **Entidades**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vea datos de enriquecimiento en la tarjeta del cliente

Las afinidades de marcas e intereses también se pueden ver en tarjetas de clientes individuales. Vaya a **Clientes** y seleccione un perfil de cliente. En la tarjeta del cliente, encontrará gráficos de las marcas o intereses por los que las personas del perfil demográfico de ese cliente tienen afinidad.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Tarjeta de cliente con datos enriquecidos":::

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Cree [Segmentos](segments.md), [Medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.
