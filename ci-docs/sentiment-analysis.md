---
title: Analizar el sentimiento en los comentarios de los clientes (versión preliminar)
description: Aprenda a usar un modelo de análisis de sentimientos sobre los comentarios de los clientes en Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055557"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizar el sentimiento en los comentarios de los clientes (versión preliminar)

Los clientes esperan productos, servicios y experiencias de alta calidad en estos días. Especialmente los clientes que comparten sus comentarios. Es muy complicado para las organizaciones analizar un volumen cada vez mayor de datos sin disminuir la precisión y sin aumentar el costo de mano de obra. Dynamics 365 Customer Insights ofrece un modelo de análisis de sentimientos para los comentarios de los clientes que permite a las organizaciones analizar sus datos con mayor precisión y a un costo menor.

El análisis de opinión le permite sintetizar la opinión del cliente e identificar los aspectos comerciales como oportunidades de mejora. Esta característica de Customer Insights lo ayuda a comprender qué funciona bien y qué debe abordar. Concéntrese en las áreas comerciales más relevantes e impactantes para mejorar la experiencia de sus clientes. En última instancia, puede ayudarlo a impulsar acciones comerciales que permitan experiencias que resulten en una alta satisfacción y lealtad del cliente.

## <a name="overview"></a>Introducción

La función de análisis de sentimientos genera dos conocimientos derivados por identificación de cliente. Una puntuación de sentimiento (de -5 a 5) y una lista de aspectos comerciales aplicables (áreas comerciales) juntos lo ayudan a comprender mejor los comentarios de los clientes. 

Esta información puede ayudarle a obtener los siguientes resultados: 
- Obtenga una descripción general de los sentimientos de los clientes hacia una marca u organización
- Identifique a los clientes con sentimientos negativos para enfocar sus campañas y compromisos y optimícelos para obtener un mayor retorno  
- Identificar aspectos comerciales con problemas señalados por los clientes  
- Segmente a los clientes en función de sus sentimientos para ejecutar campañas personalizadas con esfuerzos específicos de ventas, marketing y soporte
- Optimice las operaciones comerciales abordando áreas de preocupación u oportunidades que mencionaron los clientes
- Reconocer los aspectos comerciales que están funcionando bien y recompensar a los clientes satisfechos a través de programas de fidelización y promoción

Para garantizar que pueda confiar en los resultados de los modelos, proporcionamos información transparente sobre cómo los modelos toman decisiones. Obtendrá una lista de palabras que afectaron la decisión de los modelos de asignar un puntaje de sentimiento particular o un aspecto comercial a los comentarios de retroalimentación.  

Usamos dos **Modelos de procesamiento de lenguaje natural (NLP)**: el primero asigna a cada comentario de opinión una puntuación de sentimiento. El segundo modelo asocia cada comentario con todos los aspectos comerciales aplicables. Los modelos están formados en datos públicos de fuentes en redes sociales, comercio minorista, restaurantes, productos de consumo e industrias automotrices.    
  
Los aspectos comerciales predefinidos para que el modelo se asocie con los datos de comentarios incluyen:
-   Administración de cuentas
-   Finalizar la compra y pagar
-   Asistencia al cliente
-   Recogida en tienda
-   Empaquetado, envío y recuperación
-   Pedido por adelantado
-   Precio
-   Privacidad y seguridad
-   Promociones y recompensas
-   Recibo y garantía
-   Devolución, cambio y cancelación
-   Precisión de proceso de entrega
-   Calidad del sitio web o la aplicación

> [!NOTE]
> Actualmente, solo admitimos el análisis de opiniones sobre los comentarios de los clientes en inglés. Se admitirán más idiomas en el futuro. Si se cargan comentarios en otros idiomas, el modelo aún arrojará resultados. Sin embargo, estos resultados no serán exactos. 

## <a name="prerequisites"></a>Requisitos previos

El análisis de sentimiento se basa en datos de comentarios de texto que han pasado por el [proceso de unificación de datos](data-unification.md). Le recomendamos encarecidamente que [configure sus entidades de datos de comentarios como entidades de actividad de tipo semántico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tipo de comentario) de antemano. 

Para configurar un modelo de análisis de sentimiento, necesita al menos [permisos de colaborador](permissions.md).

Customer Insights puede procesar hasta 10 millones de registros de comentarios para una sola ejecución de modelo. El modelo puede analizar comentarios de hasta 128 palabras. Si un comentario de opinión es más largo, el análisis considera solo las primeras 128 palabras.

### <a name="data-requirements"></a>Requisitos de datos
  
Se requieren los siguientes atributos de datos:
- ID de cliente unificado (UCID) para hacer coincidir los registros de datos de comentarios de texto con un cliente individual. Esta identificación es el resultado del [proceso de unificación de datos](data-unification.md).
- Id. de comentarios
- Marca de tiempo de comentario
- Texto de comentarios   

> [!TIP]
> El análisis de sentimiento requiere el texto del comentario de sus clientes. Actualmente solo se puede configurar una entidad de comentario. Si hay varias entidades de comentarios, puede unirlas en Power Query antes de que comience la ingesta de datos.

## <a name="configure-a-sentiment-analysis"></a>Configurar un análisis de sentimiento 

1. En Customer Insights, vaya a **Inteligencia** > **Predicciones**.

1. En el mosaico **Análisis de sentimiento del cliente**, seleccione **Modelo de uso**.

1. En el panel **Análisis de opinión del cliente (vista previa)**, seleccione **Comenzar**.

1. En el paso **Nombre del modelo**, proporcione un **Nombre** para su análisis. 

1. Proporcione el **Nombre de la entidad de salida del aspecto comercial** y el **Nombre de la entidad de salida de puntuación de sentimiento**, después seleccione **Siguiente**.

1. En el paso **Datos requeridos**, seleccione **Agregar datos**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Agregue flujo de datos en el modelo de análisis de sentimiento.":::

1. En el panel **Agregar datos**, elija el tipo semántico **Comentario** de la lista.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Paso de configuración para seleccionar actividades de comentario para el análisis de sentimiento.":::

1. Seleccione las actividades que desea para este análisis de sentimiento y, a continuación, seleccione **Siguiente**.
 
1. Asigne los atributos de sus datos a los atributos del modelo. Seleccione **Guardar** para aplicar sus selecciones. 

1. Verá el estado de la asignación de datos. Seleccione **Siguiente** para continuar. 

1. En el paso **Revise los detalles de su modelo**, valide la configuración de su análisis de sentimiento. Puede volver a cualquier parte de la configuración de predicción. Seleccione **Guardar y ejecutar** para iniciar el análisis. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Paso de revisión para el modelo de sentimiento que muestra todos los elementos configurados.":::

1. Seleccione **Hecho** para salir de la experiencia de configuración. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados. 

## <a name="review-analysis-status"></a>Revisar el estado del análisis

1.  Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.
2.  Seleccione la predicción que desea revisar.
- **Nombre de predicción**: nombre de la predicción proporcionada al crearlo.
- **Tipo de predicción**: tipo de modelo utilizado para la predicción.
- **Entidad de salida**: nombre de la entidad para guardar la salida de la predicción. Vaya a **Datos** > **Entidades** para encontrar la entidad con este nombre.
- **Campo previsto**: este campo se rellena solo para algunos tipos de predicciones y no se usa en la predicción del valor del tiempo de vida del cliente.
- **Estado**: estado de la ejecución de la predicción.
  - **Puesto en cola**: la predicción está esperando a que se completen otros procesos.
  - **Actualización**: la predicción se está ejecutando actualmente para crear resultados que fluirán hacia la entidad de salida.
  - **Errores**: la ejecución de la predicción ha presentado errores. Revise los registros para más detalles.
  - **Correcta**: la predicción ha tenido éxito. Seleccione Vista en los puntos suspensivos verticales para revisar los resultados de la predicción.
- **Editada**: la fecha en que se modificó la configuración para la predicción.
- **Última actualización**: fecha en la que la predicción actualizada da como resultado la entidad de salida.

## <a name="manage-sentiment-analysis"></a>Administrar análisis de sentimiento

Puede optimizar, solucionar problemas, actualizar o eliminar predicciones. Revise un informe de usabilidad de datos de entrada para descubrir cómo hacer que un predicción sea más rápido y confiable. Para obtener más información, consulte [Administrar predicciones](manage-predictions.md).

## <a name="review-analysis-results"></a>Revisar resultados de análisis
 
1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**. 
1. Seleccione el nombre de la predicción para la que desea revisar los resultados. En este caso, seleccione el análisis de sentimiento que desea revisar. 

### <a name="summary-tab"></a>Pestaña Resumen

Hay cuatro secciones principales de datos dentro de la página de resultados. 

- **Puntuación de sentimiento media**: le ayuda a comprender el sentimiento general de todos los clientes. Las puntuaciones de sentimiento se agrupan en tres categorías: 
  1.    Negativa (-5 > 2)
  2.    Neutral (-1 > 1)
  3.    Positiva (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representación visual del sentimiento general del cliente.":::

- **Distribución de clientes por puntuación de sentimiento**: los clientes se clasifican en grupos negativos, neutrales y positivos en función de sus puntuaciones de sentimiento. Pase el cursor sobre las barras en el histograma para ver la cantidad de clientes y la puntuación de sentimiento media en cada grupo. Estos datos le pueden ayudar [a crear segmentos de clientes](segments.md) en función de sus puntuaciones de sentimiento.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras que muestra la opinión del cliente en los tres grupos de opinión.":::

- **Puntuación de sentimiento media a lo largo del tiempo**: el sentimiento del cliente puede cambiar con el tiempo. Proporcionamos tendencias en los sentimientos de sus clientes para el rango de tiempo de sus datos. Esta vista puede ayudarlo a medir el efecto de las promociones de temporada, los lanzamientos de productos u otras intervenciones con límites de tiempo en la opinión del cliente. Vea el gráfico seleccionando el año de interés en el menú desplegable. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico de historial con la puntuación de opinión a lo largo del tiempo representada como una línea.":::
 
- **Opinión a través de los aspectos comerciales**: esta tabla enumera el sentimiento promedio en todos los aspectos comerciales. Puede ayudarlo a evaluar qué aspectos de su negocio ya satisfacen a los clientes o aspectos que requieren más atención. Los registros de comentarios que no se alinean con ninguno de los aspectos comerciales admitidos se clasifican en **Otro**. La tabla se ordena alfabéticamente de forma predeterminada. Puede modificar la clasificación seleccionando un encabezado de tabla.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspectos comerciales con el valor de la opinión asociado y el número de clientes que lo mencionan.":::
 
  Seleccione el nombre de un aspecto comercial para ver información adicional sobre cómo el modelo identifica un aspecto comercial. Hay dos partes en este panel: 

  - **Palabras influyentes** : muestra las principales palabras que influyeron en la identificación del modelo de IA de un aspecto comercial en los comentarios de los clientes. 
    **Mostrar palabras ofensivas**: le permite incluir palabras ofensivas en la lista a partir de los datos originales de comentarios de los clientes. De forma predeterminada, está desactivado.  El enmascaramiento de palabras ofensivas funciona con un modelo de IA y es posible que no detecte todas las palabras ofensivas. Seguimos iterando y entrenando el clasificador para un rendimiento óptimo. Si detecta una palabra ofensiva que no se filtró como se esperaba, háganoslo saber. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palabras influyentes con la palanca para mostrar u ocultar palabras ofensivas.":::
 
  - **Ejemplos de comentarios**: muestra registros de comentarios reales en sus datos. Las palabras están codificadas por colores según su influencia en la identificación de un aspecto comercial. 


### <a name="influential-words-analysis-tab"></a>Pestaña de análisis de palabras influyentes

Hay tres secciones de información adicional que explican cómo funciona el modelo de sentimiento.
  
1. **Principales palabras que contribuyen a la opinión positiva**: muestra las principales palabras que influyeron en la identificación del modelo de IA de sentimientos positivos en los comentarios de los clientes.  
2. **Principales palabras que contribuyen a la opinión negativa**: muestra las principales palabras que influyeron en la identificación del modelo de IA de opiniones negativas en los comentarios de los clientes.  
3. **Muestras de comentarios**: muestra registros de comentarios reales, uno con una opinión negativa y otro con una opinión positiva. Las palabras en los registros de comentarios se resaltan según su contribución a la puntuación de opinión asignada. Las palabras que contribuyen a una puntuación de opinión positiva se resaltan en verde. Las palabras que contribuyen a una puntuación negativa se resaltan en rojo.
   Seleccione **Ver más** para cargar más muestras de comentarios que ofrezcan más información y contexto sobre cómo funciona el modelo de opinión.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Ejemplos de análisis de sentimientos sobre los comentarios de los clientes.":::
 
**Mostrar palabras ofensivas**: le permite incluir palabras ofensivas en la lista a partir de los datos originales de comentarios de los clientes. De forma predeterminada, está desactivado.  El enmascaramiento de palabras ofensivas funciona con un modelo de IA y es posible que no detecte todas las palabras ofensivas. Seguimos iterando y entrenando el clasificador para un rendimiento óptimo. Si detecta una palabra ofensiva que no se filtró como se esperaba, háganoslo saber. 

## <a name="act-on-analysis-results"></a>Actuar con resultados de análisis

Puede comenzar fácilmente a crear nuevos segmentos de clientes desde la página de resultados del análisis de sentimiento seleccionando **Crear segmentos** en la parte superior de la página de resultados del modelo.

:::image type="content" source="media/create-segment-model.png" alt-text="Barra de comandos con opciones en modelos predicción.":::
 
## <a name="potential-bias"></a>Sesgo potencial

Al igual que con cualquier función que utilice inteligencia artificial predictiva, debe tener en cuenta el sesgo potencial en los datos que utiliza para predecir la opinión del cliente. Por ejemplo, si solo recopila comentarios digitalmente, podría perder los comentarios de los clientes que principalmente hacen negocios con usted en persona, lo que podría afectar el resultado de la función.

Como esta característica utiliza medios automatizados para evaluar datos y hacer predicciones basadas en esos datos, por lo tanto, tiene la capacidad de usarse como un método de creación de perfiles, según lo define el Reglamento General de Protección de Datos ("GDPR"). El uso que haga de esta función para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones. Usted es responsable de asegurarse de que su uso de Dynamics 365 Customer Insights, incluido el análisis de sentimiento, cumple con todas las leyes y reglamentos aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.

[!INCLUDE [footer-include](includes/footer-banner.md)]

