---
title: Segmentos sugeridos basados en actividad (vista preliminar)
description: Deje que el aprendizaje automático le ayude a encontrar segmentos nuevos e interesantes según la actividad de los clientes.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170610"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmentos sugeridos basados en actividad (vista preliminar)

Descubra segmentos interesantes de sus clientes en función de los datos de actividad de los clientes que se ingieren en Customer Insights. Algunos ejemplos de datos de actividad son las transacciones, la duración de las llamadas de asistencia, las compras o las devoluciones. Para sugerir segmentos, los datos de actividad se analizan en cuanto a actualidad, frecuencia y valor monetario (o duración). Alternativamente, puede generar [segmentos sugeridos para mejorar una medida o comprender mejor qué influye en un atributo](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Pestaña de segmentos sugeridos que muestra sugerencias de segmentos para segmentos basados en actividades y basados en atributos.":::

## <a name="categorize-customers-by-activity"></a>Categorizar a los clientes por actividad

Con los [datos de actividad](activities.md) disponibles en Customer Insights, podemos generar sugerencias que representen grupos de clientes:

- clientes más activos 
- clientes que han realizado más compras 
- clientes que generaron la mayor cantidad de ingresos 
- clientes que no han estado activos últimamente 
- clientes que interactúan frecuentemente con su negocio  

Si tiene un negocio minorista, puede averiguar qué clientes generan más ingresos y recompensarlos con un cupón. O bien, puede identificar clientes ocasionales y ofrecerles que se unan a un programa de recompensas para que visiten su negocio con más frecuencia.
Si ofrece atención médica pública y su objetivo es minimizar los gastos de los pacientes individuales, podría intentar reducir las visitas recurrentes brindando la mejor atención posible en la menor cantidad de visitas posible. En este caso, su objetivo es mantener baja la frecuencia de las visitas y minimizar los costes periódicos para los pacientes. Si no, puede identificar segmentos de pacientes que tienen citas frecuentes y altos costos periódicos y analizar estos casos para mejorar el tratamiento del individuo.

## <a name="required-data"></a>Datos necesarios

Las sugerencias se generan en función de los datos de entrada seleccionados.

- Perfiles de clientes: todos los clientes o miembros de un segmento específico.

- Período de tiempo: el mes pasado, el año pasado o cualquier plazo de tiempo personalizado.

- Tipo de actividad: compras, transacciones minoristas, transacciones en línea, casos de atención al cliente, suscripciones, etc.  

- Entidad en Customer Insights que contiene los datos de la actividad: la entidad UnifiedActivity o la entidad para una actividad específica.

- Dimensiones a incluir: actualidad, frecuencia o dimensión monetaria, según los requisitos de su empresa.

## <a name="generate-suggested-segments"></a>Generar segmentos sugeridos

1. Vaya a **Segmentos** y seleccione la pestaña **Sugerencias (versión preliminar)**.

1. Seleccione **Buscar nuevas sugerencias** y elija **Ver o anticipar el comportamiento del cliente**. Seleccione **Iniciar**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primer paso del asistente de configuración para un segmento sugerido según la actividad.":::

1. Proporcione los datos de entrada necesarios y seleccione **Siguiente**.

   - Elegir clientes: incluya todos los clientes o un segmento específico.
   - Elegir actividad: seleccione el tipo de actividad y las entidades que describen la actividad.
   - Preferencias: establezca el período de tiempo a considerar, los factores para las sugerencias y asigne los atributos.

1. Revise su entrada y seleccione **Ejecutar** para ejecutar el modelo y generar sugerencias.

Dependiendo de la cantidad de perfiles de clientes y de las actividades seleccionadas, puede tardar unos minutos en completarse.

Después de generar las sugerencias, puede filtrarlas por la dimensión o el valor que más le interese.

## <a name="manage-suggested-segments"></a>Administrar los segmentos sugeridos

Vaya a **Segmentos** y seleccione la pestaña **Sugerencias (versión preliminar)**. En la sección **Sugerencias basadas en actividades**, seleccione un segmento sugerido para ver las acciones disponibles.

- **Ver sugerencia** para ver los detalles del segmento, como la extensión de cada dimensión en comparación con el grupo objetivo. También resalta el número de miembros potenciales en el segmento y el porcentaje correspondiente del total de clientes.
- **Crear segmento** para guardar lo sugerido como un segmento. Se muestra en la pestaña **Todos los segmentos** y puede ser [actualizado o eliminado](segments.md). No puede editar los detalles del segmento. Sin embargo, puede cambiar los criterios de entrada para las sugerencias y generar sugerencias diferentes.
- **Editar sugerencias** para modificar los atributos configurados que reemplazarán las sugerencias actuales.
- **Actualizar sugerencias** para actualizar las sugerencias manteniendo los atributos configurados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
