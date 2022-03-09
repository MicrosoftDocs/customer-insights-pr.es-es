---
title: Enriquecimiento de mejora de direcciones (contiene vídeo)
description: Enriquezca y normalice la información de direcciones de los perfiles de los clientes con los modelos de Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 067757019078d3a46b224ba259d2d097dfbbe381
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353657"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquecimiento de perfiles de clientes con direcciones mejoradas

Las direcciones de sus datos pueden no estar estructuradas, estar incompletas o ser incorrectas. Utilice los modelos de Microsoft para normalizar y enriquecer sus direcciones en el [Formato de Common Data Model](/common-data-model/schema/core/applicationcommon/address) para una mejor precisión y conocimientos.

## <a name="how-we-enhance-addresses"></a>Cómo mejoramos las direcciones

Nuestro modelo pasa por un proceso de dos pasos para mejorar una dirección. Primero, analiza la dirección para identificar sus componentes y los coloca en un formato estructurado. Posteriormente, usamos la IA para corregir, completar y estandarizar los valores en la dirección.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Ejemplo

La información de la dirección puede tener un formato no estándar y contener errores ortográficos. El modelo puede solucionar estos problemas y crear direcciones coherentes en perfiles de clientes unificados.

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

### <a name="limitations"></a>Limitaciones

Las direcciones mejoradas solo funcionan con los valores que ya existen en los datos de direcciones ingeridos. El modelo no hace lo siguiente: 

1. Verificar si la dirección es una dirección válida.
2. Verificar si alguno de los valores, como los códigos postales o los nombres de calles, son válidos.
3. Cambiar los valores que no reconoce.

El modelo utiliza técnicas basadas en el aprendizaje automático para mejorar las direcciones. Si bien aplicamos un umbral de confianza alto para cuando el modelo cambie un valor de entrada, como con cualquier modelo basado en aprendizaje automático, no se garantiza una precisión al cien por cien.

## <a name="supported-countries-or-regions"></a>Países o regiones compatibles

Actualmente admitimos direcciones mejoradas en estos países o regiones: 

- Australia
- Canadá
- Francia
- Alemania
- Italia
- Japón
- Reino Unido
- Estados Unidos

Las direcciones deben contener un valor de país o región. No procesamos direcciones de países o regiones que no son compatibles ni direcciones que no tienen ningún país o región proporcionado.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento**.

1. Seleccione **Enriquecer mis datos** en el mosaico **Direcciones mejoradas**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de pantalla del mosaico de direcciones mejoradas.":::

1. Selecciona el **Conjunto de datos de clientes** y elija la entidad que contiene las direcciones que desea enriquecer. Puede seleccionar la entidad *Cliente* para enriquecer direcciones en todos sus perfiles de clientes o seleccionar una entidad de segmento para enriquecer direcciones solo en perfiles de clientes contenidos en ese segmento.

1. Seleccione cómo se formatean las direcciones en el conjunto de datos. Escoja **Dirección de atributo único** si las direcciones de sus datos utilizan un solo campo. Escoja **Dirección de atributos múltiples** si las direcciones de sus datos utilizan más de un campo de datos.

   > [!NOTE]
   > El país o región es obligatorio tanto en las direcciones de atributo único como en las de atributos múltiples. Las direcciones que no contienen valores de país o región válidos o admitidos no se enriquecerán.

1.  Asigne los campos de direcciones de su entidad de cliente unificada.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página mejorada de asignación de campos de direcciones.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un nombre para el enriquecimiento y la entidad de salida.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento depende del tamaño de los datos de sus clientes.

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede ver una muestra de los datos enriquecidos en el mosaico **Vista previa de clientes enriquecidos**. Seleccione **Ver más** y seleccione la pestaña **Datos** para acceder a una vista detallada de cada perfil enriquecido.

### <a name="overview-card"></a>Tarjeta de descripción general

La tarjeta de descripción general muestra detalles sobre la cobertura del enriquecimiento. 

* **Direcciones procesadas y cambiadas**: el número de perfiles de cliente con direcciones que se enriquecieron con éxito.

* **Direcciones procesadas y no cambiadas**: el número de perfiles de clientes con direcciones que se reconocieron pero no cambiaron. Por lo general, sucede cuando los datos de entrada son válidos y no se pueden mejorar mediante el enriquecimiento.

* **Direcciones no procesadas y no cambiadas**: el número de perfiles con direcciones que no se reconocieron. Por lo general, para datos de entrada que no son válidos o no son compatibles con el enriquecimiento.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
