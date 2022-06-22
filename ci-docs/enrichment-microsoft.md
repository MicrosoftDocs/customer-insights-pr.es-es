---
title: Enriquezca los perfiles de los clientes con datos de marcas e intereses de Microsoft
description: Utilice datos de propiedad de Microsoft para enriquecer los datos de sus clientes con afinidades y Cuota de presencia.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953786"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enriquezca los perfiles de los clientes con afinidades y Cuota de presencia (vista previa)

Utilice datos de propiedad de Microsoft para enriquecer los datos de sus clientes con afinidades de marca, intereses y Cuota de presencia (SoV). Estas afinidades y SoV se basan en datos de un público con demográficas similares a las de sus clientes. Esta información le ayuda a comprender y segmentar mejor a sus clientes en función de sus afinidades o SoV con marcas e intereses específicos.

## <a name="how-we-determine-affinities-and-sov"></a>Cómo determinamos las afinidades y el SoV

Usamos los datos de búsqueda en línea de Microsoft para encontrar afinidades y SoV para marcas e intereses en varios segmentos demográficos (definidos por edad, género o ubicación). El volumen de búsqueda en línea de una marca o interés constituye la base para determinar la afinidad o SoV. Sin embargo, cada uno proporciona una perspectiva diferente para comprender a sus clientes.

- La afinidad es una comparación entre segmentos demográficos. Puede utilizar esta información para identificar los segmentos demográficos que tienen la mayor afinidad por una marca o interés determinados, en comparación con otros segmentos.

- Cuota de presencia es una comparación entre sus marcas o intereses seleccionados. Puede utilizar esta información para identificar qué marca o interés tiene la mayor participación en un segmento demográfico determinado, en comparación con otras marcas o intereses que seleccionó.

## <a name="affinity-level-and-score"></a>Nivel de afinidad y puntuación

En cada perfil de cliente enriquecido, proporcionamos dos valores relacionados: nivel de afinidad y puntuación de afinidad. Estos valores le ayudan a determinar el nivel de afinidad para el segmento demográfico de ese perfil, para una marca o interés, en comparación con otros segmentos demográficos.

El *nivel de afinidad* consta de cuatro niveles y la *puntuación de afinidad* se calcula en una escala de 100 puntos que se asigna a los niveles de afinidad.

|Nivel de afinidad |Puntuación de afinidad  |
|---------|---------|
|Muy alto     | 85-100       |
|Alto     | 70-84        |
|Medio     | 35-69        |
|Bajo     | 1-34        |

Dependiendo de la granularidad que desee para medir la afinidad, puede utilizar el nivel de afinidad o la puntuación. La puntuación de afinidad le brinda un control más preciso.

## <a name="share-of-voice-sov"></a>Cuota de presencia (SoV)

Calculamos la SoV en una escala de 100 puntos. La SoV total en todas las marcas o intereses para cada perfil de cliente enriquecido suma 100. A diferencia de las afinidades, SoV es relativa a las marcas e intereses que seleccione. Por ejemplo, los valores de SoV para 'Microsoft' pueden ser diferentes si las marcas seleccionadas son ('Microsoft', 'GitHub') versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Países/regiones admitidos

Actualmente admitimos las siguientes opciones de país/región: Australia, Canadá (inglés), Francia, Alemania, Reino Unido o Estados Unidos (inglés).

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

   - Para configurar las afinidades de marca y el enriquecimiento de SoV, vaya a **Enriquecer mis datos** en el mosaico **Marcas**.

   - Para configurar las afinidades de intereses y el enriquecimiento de SoV, vaya a **Enriquecer mis datos** en el mosaico **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Ventanas de marcas e intereses.](media/BrandsInterest-tile-Hub.png "Ventanas de marcas e intereses")

1. Revise el resumen y luego seleccione **Siguiente**.

1. Para cambiar su país o región, seleccione **Cambiar** junto a **País/Región**. En el panel **Configuración de país/región**, elija un [país/región compatible](#supported-countriesregions) y seleccione **Aplicar**.

   > [!NOTE]
   > A la hora de elegir sus propias marcas, el sistema proporciona sugerencias basadas en el país o región seleccionados. Cuando elige un sector, obtendrá las marcas o los intereses más relevantes según el país o la región seleccionados.

1. Elija hasta cinco marcas o intereses usando una o ambas de estas opciones:

   - **Sector**: seleccione su sector en la lista desplegable y luego elija entre las principales marcas o intereses para ese sector.
   - **Elegir su propio**: introduzca una marca o interés que sea relevante para su organización y luego elija entre las sugerencias coincidentes. Si no enumeramos una marca o interés que está buscando, envíenos sus comentarios utilizando el vínculo **Sugerir**.

1. Seleccione **Siguiente** y revise sus preferencias de enriquecimiento predeterminadas y actualícelas según sea necesario.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla de la ventana de preferencias de enriquecimiento.":::

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos de cliente** y elija el perfil o segmento que desea enriquecer con datos de Microsoft. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

1. Seleccione **Siguiente**.

1. Asigne sus campos de su entidad de cliente unificada a los datos de Microsoft.

   > [!NOTE]
   > Se requieren al menos los atributos Fecha de nacimiento o Género. Se requiere país/región y al menos ciudad (y estado/provincia) o código postal. Recomendamos que la fecha de nacimiento se convierta al tipo DateTime durante la ingesta de datos. Alternativamente, puede ser una cadena en [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formato "aaaa-MM-dd" o "aaaa-MM-ddTHH: mm:ss".

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Escriba un nombre para el enriquecimiento. El **Nombre de la entidad resultante** se selecciona automáticamente.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisión de intereses y poner un nombre a la página.":::

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

   Cuándo se enriquezcan perfiles, enriqueceremos todos los perfiles de clientes para los que obtenemos datos de las marcas e intereses seleccionados, incluidos los perfiles que no se encuentran en el país o región seleccionados. Por ejemplo, si seleccionó Alemania, enriqueceremos los perfiles ubicados en los Estados Unidos si tenemos datos disponibles para las marcas e intereses seleccionados en los Estados Unidos.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Vista previa de resultados después de ejecutar el proceso de enriquecimiento.":::

Los resultados incluyen las gráficas **Nivel de afinidad** o **Cuota de presencia**

Las entidades creadas a partir de los enriquecimientos se enumeran bajo el grupo **Enriquecimiento** en **Datos** > **Entidades**. Los datos enriquecidos de las marcas van a las entidades **BrandAffinityFromMicrosoft** y **BrandShareOfVoiceFromMicrosoft**. Los datos de intereses están en las entidades **InterestAffinityFromMicrosoft** y **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vea datos de enriquecimiento en la tarjeta del cliente

La SoV de marca e interés también se puede ver en tarjetas de clientes individuales. Vaya a **Clientes** y seleccione un perfil de cliente. En la ficha de cliente encontrará gráficos para la SoV de marca o interés según el perfil demográfico del cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Tarjeta de cliente con datos enriquecidos.":::

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
