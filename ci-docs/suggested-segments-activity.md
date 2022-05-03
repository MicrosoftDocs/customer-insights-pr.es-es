---
title: Segmentos sugeridos según la actividad.
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
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647789"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmentos sugeridos según los datos de actividad (versión preliminar)

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
Si está en el negocio de la atención médica, brinda atención médica pública y su objetivo es minimizar los gastos para pacientes individuales. Una forma de hacerlo podría ser reducir las visitas periódicas, proporcionando la mejor atención posible en el menor número de visitas posible. En este caso, su objetivo es mantener baja la frecuencia de las visitas y minimizar los costes periódicos para los pacientes. Si no, puede identificar segmentos de pacientes que tienen citas frecuentes y altos costos periódicos y analizar estos casos para mejorar el tratamiento del individuo. 

## <a name="required-data"></a>Datos necesarios

Las sugerencias se generan en función de los datos de entrada seleccionados. 

- Perfiles de clientes: todos los clientes o miembros de un segmento específico. 

- Período de tiempo: el mes pasado, el año pasado o cualquier plazo de tiempo personalizado.

- Tipo de actividad: compras, transacciones minoristas, transacciones en línea, casos de atención al cliente, suscripciones, etc.  

- Entidad en Customer Insights que contiene los datos de la actividad: la entidad UnifiedActivity o la entidad para una actividad específica. 

- Dimensiones a incluir: actualidad, frecuencia o dimensión monetaria, según los requisitos de su empresa.

## <a name="generate-suggested-segments"></a>Generar segmentos sugeridos

1. Vaya a **Segmentos**.

1. Seleccione la pestaña **Sugerencias (versión preliminar)**.

1. Seleccione **Buscar nuevas sugerencias** y elija **Ver o anticipar el comportamiento del cliente**. Seleccione **Iniciar** para empezar la experiencia guiada.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primer paso del asistente de configuración para un segmento sugerido según la actividad.":::

1. Proporcione los datos de entrada necesarios y seleccione **Siguiente** para continuar.

   - Elegir clientes: incluya todos los clientes o un segmento específico.
   - Elegir actividad: seleccione el tipo de actividad y las entidades que describen la actividad.
   - Preferencias: establezca el período de tiempo a considerar, los factores para las sugerencias y asigne los atributos.

1. Revise su entrada y seleccione **Ejecutar** para ejecutar el modelo y generar sugerencias.

1. Dependiendo de la cantidad de perfiles de clientes y de las actividades seleccionadas, puede tardar unos minutos en completarse. 

Después de generar las sugerencias, puede filtrarlas por la dimensión o el valor que más le interese. 

## <a name="view-details-of-a-suggested-segment"></a>Ver detalles de un segmento sugerido

Una vez generadas las sugerencias, las encontrará enumeradas en **Segmentos** > **Sugerencias (versión preliminar)** en la sección **Sugerencias basadas en actividades**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panel lateral ampliado que muestra datos detallados de un segmento sugerido.":::

Seleccione **Ver sugerencia** en un segmento sugerido para ver los detalles de ese segmento. El panel lateral proporciona detalles como la extensión de cada dimensión en comparación con el grupo objetivo. También resalta el número de miembros potenciales en el segmento y el porcentaje correspondiente del total de clientes. Si desea mantener la sugerencia como un segmento, seleccione **Crear segmento**.    

## <a name="save-a-suggestion-as-a-segment"></a>Guardar una sugerencia como segmento

1. Vaya a **Segmentos** > **Sugerencias (vista previa)**.

1. Seleccione el segmento que desea guardar. 

1. En el panel lateral, seleccione **Crear segmento**. 

1. Después de guardar el segmento, se mostrará en la lista de segmentos, en la pestaña **Todos los segmentos**. Ahora puede [actualizarse o eliminarse, como cualquier otro segmento](segments.md). No puede editar los detalles del segmento. Sin embargo, puede cambiar los criterios de entrada para las sugerencias y generar sugerencias diferentes.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Actualizar o editar un conjunto de sugerencias

1. vaya a **Segmentos** > **Sugerencias (versión preliminar)** y busque el segmento en la sección **Sugerencias basadas en actividades**.

1. Seleccione **Actualizar sugerencias** para actualizar las sugerencias manteniendo los atributos configurados. O seleccione **Editar sugerencias** para modificar los atributos configurados. El sistema volverá a ejecutar el proceso, generará sugerencias de segmento basadas en los datos más recientes y reemplazará las sugerencias actuales.

[!INCLUDE [footer-include](includes/footer-banner.md)]
