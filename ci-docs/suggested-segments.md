---
title: Segmentos sugeridos basados en medidas (versión preliminar)
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
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170978"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segmentos sugeridos basados en medidas (versión preliminar)

Descubra segmentos interesantes de sus clientes con la ayuda de un modelo de IA. Esta función con tecnología de aprendizaje automático sugiere segmentos basados en medidas o atributos del cliente. Puede ayudar a mejorar sus indicadores clave de rendimiento (KPI) o comprender mejor la influencia de los atributos en el contexto de otros atributos.

> [!NOTE]
> La característica de segmentos sugeridos utiliza medios automatizados para evaluar datos y hacer predicciones basadas en esos datos. Por lo tanto, tiene la capacidad de ser utilizado como un método de generación de perfiles, tal como se define ese término en el Reglamento General de Protección de Datos ("RGPD"). El uso que haga de esta función para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones. Usted es responsable de garantizar que el uso de Dynamics 365 Customer Insights, incluida esta característica, cumpla con todas las leyes y regulaciones aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.

:::image type="content" source="media/suggested-segments.png" alt-text="Página de segmentos sugeridos que muestra detalles de una sugerencia en un panel lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentos sugeridos para mejorar sus KPI

Si utiliza [medidas creadas](measures.md) para ayudar a realizar un seguimiento de sus KPI, cree segmentos para ver las influencias en los KPI. Puede utilizar esta información para ejecutar una campaña muy específica.

Por ejemplo, rastrea una medida llamada *TotalSpendPerCustomer*. Como empresa, le gustaría ver crecer este número. La elección de una medida como atributo principal le deja seleccionar los atributos que desea evaluar para determinar su influencia. Digamos el *nivel de pertenencia*, el *período de pertenencia* y la *ocupación*. Customer Insights puede sugerir un segmento que le diga quiénes ejercen la mayor influencia de esa medida. Por ejemplo, los *Contables* que so miembros calidad *Oro* y que han estado en su negocio durante *al menos cinco años* son los que ejercen la mayor influencia de *TotalSpendPerCustomer*. Obtendrá un tamaño de segmento estimado para cada sugerencia. Puede utilizar esta información para crear campañas para los públicos dirigidos.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprender qué influye en un atributo del cliente

Puede elegir un atributo de cliente en lugar de una medida como el atributo principal. Según su elección de los atributos de influencia, el modelo de IA crea una serie de sugerencias que muestran cómo los atributos seleccionados influyen en el atributo principal.

Por ejemplo, elige *Miembro de recompensas (Sí/No)* como atributo principal. *Antigüedad*, *Ocupación*, y *Número de vales de soporte* se establecen como otros atributos de influencia. El modelo de IA podría sugerir segmentos que indiquen que la mayoría de los profesionales de TI con una antigüedad de más de dos años son miembros de recompensas. Otra sugerencia podría destacar que los contables con una antigüedad de más de un año y menos de tres vales de soporte son miembros de recompensas.

## <a name="artificial-intelligence-usage"></a>Uso de la inteligencia artificial

Utilizando el atributo principal y los atributos de influencia, un algoritmo de árbol de decisión sugiere segmentos interesantes. Las sugerencias se basan en reglas o patrones que fueron recogidos por el algoritmo de IA. Solo los segmentos que difieren significativamente de la población promedio se muestran como sugerencias. La comparación con la población promedio se basa en la medida o atributo primario seleccionado.

### <a name="responsible-ai"></a>IA responsable

Con los segmentos sugeridos, seleccione atributos para crear nuevos segmentos y procesar los datos que seleccione. Al elegir atributos, incluidos los atributos sensibles como raza, orientación sexual o género, debe asegurarse de que puede y debe procesar esos datos. Es responsable de cumplir las leyes aplicables a su organización y adherirse a los principios y políticas de privacidad de su organización.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Diferentes resultados para atributos primarios con valores categóricos y numéricos

Las sugerencias de segmentos son diferentes si elige un atributo numérico o un atributo categórico como atributo principal. Los valores de un atributo categórico contienen dos o más categorías o tipos. Un atributo numérico contiene datos cuantitativos y tiene un sentido de medición asociado.

Con un atributo numérico como *ingresos anuales* o *período de pertenencia* como atributo principal, el sistema sugiere segmentos que tienen un valor promedio mayor o menor del atributo numérico en comparación con todos los clientes.

Un atributo categórico como *satisfacción del cliente* como atributo principal da como resultado segmentos sugeridos que tienen un porcentaje mayor o menor de clientes que pertenecen a una categoría en particular en comparación con el porcentaje de todos los clientes que pertenecen a esa misma categoría. Por ejemplo, *satisfacción del cliente* se elige como el atributo principal y consta de tres categorías (*Baja*, *Media* y *Alta*). Para cada categoría, se sugerirán segmentos que tengan un porcentaje mayor o menor de clientes que pertenecen a esa categoría en comparación con la proporción de todos los clientes de la misma categoría. Si el 22 % de todos los clientes tienen satisfacción *Alta*, entonces, solo los segmentos que tienen una mayor o menor proporción de clientes con una satisfacción *Alta* en comparación con el 22 % se sugerirán para esa categoría. Del mismo modo, se sugerirán segmentos para cada una de las otras categorías (*Baja* y *Media*) si son estadísticamente significativos.

> [!NOTE]
> Actualmente, solo admitimos atributos categóricos primarios que tienen hasta 10 categorías. Si desea ver sugerencias de segmentos basadas en un atributo principal con más de 10 categorías, recomendamos agrupar algunas de las categorías para reducir el número de categorías a 10 o menos. Esta limitación solo se aplica a los atributos primarios. Para influir en los atributos categóricos, actualmente admitimos un máximo de 100 categorías.

## <a name="generate-suggested-segments"></a>Generar segmentos sugeridos

1. Vaya a **Segmentos** y seleccione la pestaña **Sugerencias (versión preliminar)**.

1. Seleccione **Buscar nuevas sugerencias** y elija **Mejorar una medida/métrica**. Seleccione **Iniciar**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Elija mejorar la medida en los segmentos sugeridos.":::

1. Elija una medida o atributo de cliente en lugar de un atributo principal y seleccione **Siguiente**.

1. Seleccione los atributos de influencia y seleccione **Ejecutar**.

   > [!TIP]
   > La selección de varios atributos de influencia mejora las posibilidades de evaluar cómo influyen en el atributo principal. No incluya atributos que no influyan en el atributo principal. Por ejemplo, si todos sus clientes son de un país específico, no incluya el atributo *país* porque no tendrá ningún impacto en la salida.

Dependiendo de la cantidad de perfiles de clientes y atributos seleccionados, puede llevar unos minutos procesar los atributos seleccionados.

## <a name="manage-suggested-segments"></a>Administrar los segmentos sugeridos

Vaya a **Segmentos** y seleccione la pestaña **Sugerencias (versión preliminar)**. En la sección **Sugerencias de segmentos basadas en actividades**, seleccione un segmento sugerido para ver las acciones disponibles.

- **Vea** los detalles de los segmentos sugeridos y los valores de los atributos o las reglas que el modelo de IA aprendió.
- **Guardar como segmento** guarda la sugerencia como un segmento. Se muestra en la pestaña **Todos los segmentos** y puede [actualizarse, editarse eliminarse](segments.md).
- **Edite atributos** y modifique los atributos configurados que reemplazarán las sugerencias actuales.
- **Actualizar sugerencias** para actualizar las sugerencias manteniendo los atributos configurados.

## <a name="limitations"></a>Limitaciones

1. Discrepancia de tamaño de segmento estimada: si elige un atributo principal que contiene valores vacíos, puede afectar el tamaño del segmento estimado en las sugerencias de segmento. Al guardar dicho segmento, el tamaño real del segmento puede ser diferente de la estimación inicial.

2. Los atributos primarios de tipo booleano no funcionan: actualmente, solo admitimos tipos de datos numéricos y de cadena como atributo primario.

3. Los segmentos sugeridos no son lo suficientemente distintos: tenga en cuenta que los atributos seleccionados y la distribución de valores de esos atributos influyen en los resultados. Puede cambiar sus atributos de influencia o incluso su atributo principal para obtener resultados diferentes.

[!INCLUDE [footer-include](includes/footer-banner.md)]