---
title: Información detallada de segmentos (vista previa)
description: Obtenga información sobre los segmentos existentes para ver las diferencias y los puntos en común.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171024"
---
# <a name="segment-insights-preview"></a>Información detallada de segmentos (vista previa)

Descubra información adicional y conocimientos sobre sus segmentos existentes. Descubra qué diferencia a dos segmentos o qué tienen en común.

## <a name="segment-overlap"></a>Superposición de segmento

El análisis de superposición de segmentos muestra cuántos y qué clientes son comunes a dos o más segmentos. Por ejemplo, cómo un segmento de clientes frecuentes se superpone a un segmento que contiene clientes que están satisfechos con su servicio o producto.
También puede analizar cómo cambia la superposición para atributos específicos.

### <a name="run-an-overlap-analysis"></a>Ejecutar un análisis de superposición

1. Vaya a **Segmentos** y seleccione la pestaña **Información (vista previa)**.

1. Seleccione **Nuevo** y elija la opción **Superposición** en el panel **Elegir tipo de información**.

1. Elija los segmentos de interés y seleccione **Siguiente**.

1. Opcionalmente, elija uno o más campos de interés para analizar superposiciones para cada valor de campo posible y seleccione **Siguiente**.

1. Proporcione un nombre para su análisis de superposición, un nombre para mostrar opcional y una descripción.

1. Seleccione **Guardar** para comenzar el análisis. El análisis de superposición está listo cuando el estado cambia de Actualizando a Correcto.

### <a name="view-and-optimize-an-overlap-analysis"></a>Ver y optimizar un análisis de superposición

1. Después de completar el análisis, busque detalles sobre esta información en **Segmentos** > **Información (vista previa)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Detalles de información de superposición de segmentos.":::

1. Seleccione una información para ver los resultados del análisis:

   - El número de miembros que se superponen a los segmentos seleccionados para el análisis.
   - El número de miembros incluidos en uno de los segmentos pero no en el resto de los segmentos.
   - Si seleccionó campos mientras configuraba el análisis de superposición, los encontrará en las pestañas correspondientes. Puede utilizar el menú desplegable de filtros para seleccionar cualquier nivel de atributo de interés y la tabla en la parte inferior mostrará los datos correspondientes.

## <a name="segment-differentiators"></a>Diferenciadores de segmentos

Los diferenciadores de segmento lo ayudan a descubrir qué diferencia un segmento del resto de sus clientes o de otro segmento. Seleccione un segmento y el sistema identifica los atributos del perfil y las medidas que distinguen el segmento seleccionado.

### <a name="run-a-differentiator-analysis"></a>Ejecutar un análisis diferenciador

1. Vaya a **Segmentos** y seleccione la pestaña **Información (vista previa)**.

1. Seleccione **Nuevo** y elija la opción **Diferenciadores** en el panel **Elegir tipo de información**.

1. Elija el segmento que desea analizar como **Segmento primario** y seleccione **Siguiente**.

1. Elija **Todos los clientes** o un **Segmento secundario** para comparar su segmento primario y seleccione **Siguiente**.

1. Opcionalmente, elija uno o más campos de interés para enfocar el análisis en atributos específicos y seleccione **Siguiente**.

1. Proporcione un nombre para su análisis de diferenciador, un nombre para mostrar opcional y una descripción.

1. Seleccione **Guardar** para comenzar el análisis. El análisis de diferenciador está listo cuando el estado cambia de Actualizando a Correcto.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Ver y optimizar un análisis de diferenciadores

1. Después de completar el análisis, vaya a **Segmentos** > **Información (versión preliminar)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Detalles de información de diferenciador de segmentos.":::

1. Seleccione una información para ver los resultados del análisis. Un análisis diferenciador incluye dos pestañas. La pestaña **Atributos** enumera los atributos de perfil considerados como diferenciadores. La pestaña **Medidas** enumera los diferenciadores. Cada pestaña incluye los siguientes detalles:

   - Lista clasificada de diferenciadores, ordenados por puntuación de diferencia.
   - La **Puntuación de diferencia** para cada diferenciador. La puntuación de diferencia representa el grado de diferencia de un atributo entre dos segmentos. Cuanto mayor sea la puntuación de diferencia, más difieren los atributos entre los dos segmentos. Seleccione una puntuación para abrir el panel **Puntuación de diferencia** con las distribuciones de valores para ese atributo.

## <a name="manage-segment-insights"></a>Administrar información de segmentos

Vaya a **Segmentos** > **Información (versión preliminar)** para ver las estadísticas de su segmento y administrarlas. Seleccione una información de segmento para ver las acciones disponibles.

- **Ver** el análisis de la información
- **Editar** la información para cambiar sus propiedades
- **Actualizar** la información para ejecutar el análisis nuevamente
- **Cambiar nombre** de la información
- **Eliminar** la información

[!INCLUDE [footer-include](includes/footer-banner.md)]
