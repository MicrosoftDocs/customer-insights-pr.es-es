---
title: Enriquecer los perfiles de los clientes con datos de Microsoft
description: Utilice datos propios de Microsoft para enriquecer los datos de sus clientes con afinidades de marca e intereses.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 51b150cbf5d9cfb3a5df42e680bcfa57ec5496cb
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617899"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enriquezca los perfiles de los clientes con afinidades de marca e interés (versión preliminar)

Utilice datos propios de Microsoft para enriquecer los datos de sus clientes con afinidades de marca e intereses. Estas afinidades se basan en los datos de personas con datos demográficos similares a sus clientes. Esta información le ayuda a comprender y segmentar mejor a sus clientes en función de sus afinidades con marcas e intereses específicos.

En la información de público, vaya a **Datos** > **Enriquecimiento** para [configurar y ver enriquecimientos](enrichment-hub.md).

Para configurar el enriquecimiento de afinidades de marca, vaya a la pestaña **Descubrir** y seleccione **Enriquecer mis datos** en la ventana **Marcas**.

Para configurar el enriquecimiento de afinidades de intereses, vaya a la pestaña **Descubrir** y seleccione **Enriquecer mis datos** en la ventana **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Ventanas de marcas e intereses.](media/BrandsInterest-tile-Hub.png "Ventanas de marcas e intereses")

## <a name="how-we-determine-affinities"></a>Cómo determinamos las afinidades

Usamos los datos de búsqueda en línea de Microsoft para encontrar afinidades por marcas e intereses en varios segmentos demográficos (definidos por edad, género o ubicación). El volumen de búsqueda en línea de una marca o interés determina cuánta afinidad tiene un segmento demográfico, en comparación con otros segmentos, con esa marca o interés.

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

## <a name="supported-countriesregions"></a>Países/regiones admitidos

Actualmente admitimos las siguientes opciones de país/región: Australia, Canadá (inglés), Francia, Alemania, Reino Unido o Estados Unidos (inglés).

Para seleccionar un país o región, abra **Enriquecimiento de marcas** o **Enriquecimiento de intereses** y seleccione **Cambio** junto a **País o región**. En el panel **Configuración de país/región**, elija una opción y seleccione **Aplicar**.

### <a name="implications-related-to-country-selection"></a>Implicaciones relacionadas con la selección de países

- A la hora de [elegir sus propias marcas](#define-your-brands-or-interests), el sistema proporciona sugerencias basadas en el país o región seleccionados.

- Cuando [elige un sector](#define-your-brands-or-interests), obtendrá las marcas o los intereses más relevantes según el país o la región seleccionados.

- Cuándo se [enriquezcan perfiles](#refresh-enrichment), enriqueceremos todos los perfiles de clientes para los que obtenemos datos de las marcas e intereses seleccionados, incluidos los perfiles que no se encuentran en el país o región seleccionados. Por ejemplo, si seleccionó Alemania, enriqueceremos los perfiles ubicados en los Estados Unidos si tenemos datos disponibles para las marcas e intereses seleccionados en los Estados Unidos.

## <a name="configure-enrichment"></a>Configurar enriquecimiento

Una experiencia guiada le ayuda a configurar los enriquecimientos. 

### <a name="define-your-brands-or-interests"></a>Defina sus marcas o intereses

Elija hasta cinco marcas o intereses usando una o ambas de estas opciones:

- **Sector**: seleccione su sector en la lista desplegable y luego elija entre las principales marcas o intereses para ese sector.
- **Elegir su propio**: introduzca una marca o interés que sea relevante para su organización y luego elija entre las sugerencias coincidentes. Si no enumeramos una marca o interés que está buscando, envíenos sus comentarios utilizando el vínculo **Sugerir**.

### <a name="review-enrichment-preferences"></a>Revisar la preferencias de enriquecimiento

Revise sus preferencias de enriquecimiento predeterminadas y actualícelas según sea necesario.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla de la ventana de preferencias de enriquecimiento.":::

### <a name="select-entity-to-enrich"></a>Seleccione la entidad que desea enriquecer

Seleccione **Entidad enriquecida** y elija el conjunto de datos del cliente que desea enriquecer con datos de Microsoft. Puede seleccionar la entidad Cliente para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.

### <a name="map-your-fields"></a>Asignar sus campos

Asigne campos de su entidad de cliente unificada para definir el segmento demográfico que desea que utilice el sistema para enriquecer los datos de sus clientes. Mapa del país o región y al menos los atributos de fecha de nacimiento o género. Además, debe asignar al menos una de las ciudades (y estado o provincia) o códigos postales. Seleccione **Editar** para definir la asignación de campos y seleccione **Aplicar** cuando termine. Seleccione **Guardar** para completar la asignación de campos.

Se admiten los siguientes formatos y valores (los valores no distinguen entre mayúsculas y minúsculas):

- **Fecha de nacimiento**: eecomendamos que la fecha de nacimiento se convierta al tipo DateTime durante la ingestión de datos. Alternativamente, puede ser una cadena en [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formato "aaaa-MM-dd" o "aaaa-MM-ddTHH: mm:ss".
- **Género**: Masculino, Femenino, Desconocido.
- **Código postal**: códigos postales de cinco dígitos para Estados Unidos, código postal estándar en cualquier otro lugar.
- **Ciudad**: nombre de la ciudad en inglés.
- **Estado o provincia**: abreviatura de dos letras para EE. UU. y Canadá. Abreviatura de dos o tres letras para Australia. No se aplica a Francia, Alemania ni al Reino Unido.
- **País/Región**:

  - EE.UU .: Estados Unidos de América, Estados Unidos, EE. UU., EE. UU., América
  - CA: Canadá, CA
  - GB: Reino Unido, UK, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda del Norte, Reino Unido de Gran Bretaña
  - AU: Australia, AU, Mancomunidad de Australia
  - FR: Francia, FR, República francesa
  - DE: Alemania, Alemán, Deutschland, Allemagne, DE, República Federal de Alemania, República de Alemania

## <a name="review-and-name-the-enrichment"></a>Revisar y nombrar el enriquecimiento

Finalmente, puede revisar la información y proporcionar un nombre para el enriquecimiento.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisión de intereses y poner un nombre a la página.":::

## <a name="refresh-enrichment"></a>Actualizar enriquecimiento

Ejecute el enriquecimiento después de configurar marcas, intereses y la asignación de campos para la demografía. Para comenzar el proceso, seleccione **Ejecutar** en la página de configuración de marcas o intereses. Además, puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una actualización programada.

Dependiendo del tamaño de los datos de sus clientes, puede llevar varios minutos completar una ejecución de enriquecimiento.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, la última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Después de ejecutar el proceso de enriquecimiento, vaya a **Mis enriquecimientos** para revisar el número total de clientes enriquecidos y un desglose de marcas o intereses en los perfiles de clientes enriquecidos.

:::image type="content" source="media/my-enrichments.png" alt-text="Vista previa de resultados después de ejecutar el proceso de enriquecimiento.":::

Revise los datos enriquecidos seleccionando **Ver datos enriquecidos** en el gráfico. Los datos enriquecidos para las marcas van a la entidad **MarcaAffinityDeMicrosoft**. Los datos de intereses están en la entidad **InterésAfinidadDeMicrosoft**. También encontrará estas entidades indicadas en el grupo **Enriquecimiento** en **Datos** > **Entidades**.

Verá un gráfico con la cantidad de perfiles de clientes enriquecidos a lo largo del tiempo y una vista previa de la entidad enriquecida. Seleccione **Mostrar más** en el mosaico de vista previa para abrir la entidad enriquecida.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vea datos de enriquecimiento en la tarjeta del cliente

Las afinidades de marcas e intereses también se pueden ver en tarjetas de clientes individuales. Vaya a **Clientes** y seleccione un perfil de cliente. En la tarjeta del cliente, encontrará gráficos de las marcas o intereses por los que las personas del perfil demográfico de ese cliente tienen afinidad.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Tarjeta de cliente con datos enriquecidos.":::

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
