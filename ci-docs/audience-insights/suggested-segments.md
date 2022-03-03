---
title: Segmentos sugeridos con tecnología de aprendizaje automático
description: Deje que el aprendizaje automático le ayude a encontrar segmentos nuevos e interesantes según los atributos del cliente.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 82345a7d7cf7fd38d74080552799de0b92461d78
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353610"
---
# <a name="suggested-segments-preview"></a>Segmentos sugeridos (versión preliminar)

Descubra segmentos interesantes de sus clientes con la ayuda de un modelo de IA. Esta función con tecnología de aprendizaje automático sugiere segmentos basados en medidas o atributos del cliente. Puede ayudar a mejorar sus KPI o comprender mejor la influencia de los atributos en el contexto de otros atributos. 

> [!NOTE]
> La función de segmentos sugeridos utiliza medios automatizados para evaluar datos y hacer predicciones basadas en esos datos y, por lo tanto, tiene la capacidad de usarse como un método de elaboración de perfiles, tal como ese término se define en el Reglamento general de protección de datos ("RGPD"). El uso que haga de esta función para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones. Usted es responsable de garantizar que el uso de Dynamics 365 Customer Insights, incluida esta característica, cumpla con todas las leyes y regulaciones aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.

:::image type="content" source="media/suggested-segments.png" alt-text="Página de segmentos sugeridos que muestra detalles de una sugerencia en un panel lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentos sugeridos para mejorar sus KPI

Como usuario de informaciones de público, es probable que tenga una serie de [medidas creadas](measures.md) que ayudan a realizar un seguimiento de sus indicadores clave de rendimiento (KPI). Es importante comprender cómo ciertos atributos influyen en este KPI para crear segmentos y ejecutar una campaña altamente dirigida.   
Por ejemplo, rastrea una medida llamada *TotalSpendPerCustomer*. Como empresa, le gustaría ver crecer este número. La elección de una medida como atributo principal le permite seleccionar los atributos que desea evaluar para determinar su influencia. Digamos el *nivel de pertenencia*, el *período de pertenencia* y la *ocupación*. Customer Insights puede sugerir un segmento que le diga quiénes ejercen la mayor influencia de esa medida. Por ejemplo, los *Contables* que so miembros calidad *Oro* y que han estado en su negocio durante *al menos cinco años* son los que ejercen la mayor influencia de *TotalSpendPerCustomer*. Obtendrá un tamaño de segmento estimado para cada sugerencia. Puede utilizar esta información para crear campañas para las audiencias dirigidas.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprender qué influye en un atributo del cliente

Puede elegir un atributo de cliente en lugar de una medida como el atributo principal. Según su elección de los atributos de influencia, el modelo de IA crea una serie de sugerencias que muestran cómo los atributos seleccionados influyen en el atributo principal.   
Por ejemplo, elige *Miembro de recompensas (Sí/No)* como atributo principal. *Antigüedad*, *Ocupación*, y *Número de vales de soporte* se establecen como otros atributos de influencia. El modelo de IA podría sugerir segmentos que indiquen que la mayoría de los profesionales de TI con una antigüedad de más de dos años son miembros de recompensas. Otra sugerencia podría destacar que los contables con una antigüedad de más de un año y menos de tres vales de soporte son miembros de recompensas. 

## <a name="artificial-intelligence-usage"></a>Uso de la inteligencia artificial

Utilizando el atributo principal y los atributos de influencia, un algoritmo de árbol de decisión sugiere segmentos interesantes. Las sugerencias se basan en reglas o patrones que fueron recogidos por el algoritmo de IA. Solo los segmentos que difieren significativamente de la población promedio se muestran como sugerencias. La comparación con la población promedio se basa en la medida o atributo primario seleccionado.

### <a name="responsible-ai"></a>IA responsable

Los segmentos sugeridos le permiten seleccionar atributos para crear nuevos segmentos y procesar los datos que seleccione. Al elegir atributos, incluidos los atributos sensibles como raza, orientación sexual o género, debe asegurarse de que puede y debe procesar esos datos. Es responsable de cumplir las leyes aplicables a su organización y adherirse a los principios y políticas de privacidad de su organización.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Diferentes resultados para atributos primarios con valores categóricos y numéricos

Las sugerencias de segmentos son diferentes si elige un atributo numérico o un atributo categórico como atributo principal. Los valores de un atributo categórico contienen dos o más categorías o tipos. Un atributo numérico contiene datos cuantitativos y tiene un sentido de medición asociado.

Con un atributo numérico como *ingresos anuales* o *período de pertenencia* como atributo principal, el sistema sugiere segmentos que tienen un valor promedio mayor o menor del atributo numérico en comparación con todos los clientes.

Un atributo categórico como *satisfacción del cliente* como atributo principal da como resultado segmentos sugeridos que tienen un porcentaje mayor o menor de clientes que pertenecen a una categoría en particular en comparación con el porcentaje de todos los clientes que pertenecen a esa misma categoría. Por ejemplo, *satisfacción del cliente* se elige como el atributo principal y consta de tres categorías (*Baja*, *Media* y *Alta*). Para cada categoría, se sugerirán segmentos que tengan un porcentaje mayor o menor de clientes que pertenecen a esa categoría en comparación con la proporción de todos los clientes en la misma categoría. Si el 22 % de todos los clientes tienen satisfacción *Alta*, entonces, solo los segmentos que tienen una mayor o menor proporción de clientes con una satisfacción *Alta* en comparación con el 22 % se sugerirán para esa categoría. Del mismo modo, se sugerirán segmentos para cada una de las otras categorías (*Baja* y *Media*) si son estadísticamente significativos.

> [!NOTE]
> Actualmente, solo admitimos atributos categóricos primarios que tienen hasta 10 categorías. Si desea ver sugerencias de segmentos basadas en un atributo principal con más de 10 categorías, recomendamos agrupar algunas de las categorías para reducir el número de categorías a 10 o menos. Esta limitación solo se aplica a los atributos primarios. Para influir en los atributos categóricos, actualmente admitimos un máximo de 100 categorías.

## <a name="generate-suggested-segments"></a>Generar segmentos sugeridos

1. Vaya a **Segmentos**.

1. Seleccione la pestaña **Sugerencias (versión preliminar)**.

1. Seleccione **Obtener nuevas sugerencias** para iniciar la experiencia guiada.

1. Elija una medida o atributo de cliente en lugar de un atributo principal y seleccione **Siguiente**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Elección del atributo principal para sugerencias sobre los segmentos sugeridos.":::

1. Seleccione los atributos de influencia y seleccione **Guardar**.
   
   > [!TIP]
   > La selección de varios atributos de influencia mejora las posibilidades de evaluar cómo influyen en el atributo principal. No incluya atributos que no influyan en el atributo principal. Por ejemplo, si todos sus clientes son de un país específico, no incluya el atributo *país* porque no tendrá ningún impacto en la salida.

1. Dependiendo de la cantidad de perfiles de clientes y atributos seleccionados, puede llevar unos minutos procesar los atributos seleccionados. 

## <a name="view-details-of-a-suggested-segment"></a>Ver detalles de un segmento sugerido

Una vez que el modelo de IA haya generado las sugerencias, las encontrará enumeradas en **Segmentos** > **Sugerencias (vista previa)**.
 
Seleccione un segmento sugerido para revisar los detalles de esa sugerencia. También puede revisar los valores de los atributos o las reglas que el modelo de IA aprendió para sugerir el segmento seleccionado.

## <a name="save-a-suggestion-as-a-segment"></a>Guardar una sugerencia como segmento

1. Vaya a **Segmentos** > **Sugerencias (vista previa)**.

1. Seleccione el segmento que desea guardar. 

1. En el panel lateral, seleccione **Guardar como segmento**. 

1. Después de guardar el segmento, se mostrará en la lista de segmentos en la pestaña **Todos los segmentos**. Ahora puede ser [actualizada, editada o eliminada como cualquier otro segmento](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Actualizar o editar un conjunto de sugerencias

1. Vaya a **Segmentos** > **Sugerencias (vista previa)**.

1. Seleccione **Actualizar sugerencias** para actualizar las sugerencias manteniendo los atributos configurados. O seleccione **Editar atributos** para modificar los atributos configurados. El sistema volverá a ejecutar el modelo de IA, generará sugerencias de segmento basadas en los datos más recientes y reemplazará las sugerencias actuales.

## <a name="limitations"></a>Limitaciones

1. Discrepancia de tamaño de segmento estimada: si elige un atributo principal que contiene valores vacíos, puede afectar el tamaño del segmento estimado en las sugerencias de segmento. Al guardar dicho segmento, el tamaño real del segmento puede ser diferente de la estimación inicial.
 
2. Los atributos primarios de tipo booleano no funcionan: actualmente, solo admitimos tipos de datos numéricos y de cadena como atributo primario.

3. Los segmentos sugeridos no son lo suficientemente distintos: tenga en cuenta que los atributos seleccionados y la distribución de valores de esos atributos influyen en los resultados. Puede cambiar sus atributos de influencia o incluso su atributo principal para obtener resultados diferentes.



[!INCLUDE[footer-include](../includes/footer-banner.md)]