---
title: Analizar el sentimiento en los comentarios de los clientes (versión preliminar)
description: Aprenda a usar un modelo de análisis de sentimientos sobre los comentarios de los clientes en Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610487"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizar el sentimiento en los comentarios de los clientes (versión preliminar)

El análisis de opinión le permite sintetizar la opinión del cliente e identificar los aspectos comerciales como oportunidades de mejora. Esta característica de Customer Insights lo ayuda a comprender qué funciona bien y qué debe abordar. Puede ayudarlo a impulsar acciones comerciales que permitan experiencias que resulten en una alta satisfacción y lealtad del cliente.

## <a name="overview"></a>Introducción

La función de análisis de sentimientos genera dos conocimientos derivados por identificación de cliente. Una puntuación de sentimiento (de -5 a 5) y una lista de aspectos comerciales aplicables (áreas comerciales) que, juntos, lo ayudan a comprender mejor los comentarios de los clientes.

Este análisis le ayuda a:
- Obtenga una descripción general de los sentimientos de los clientes hacia una marca u organización
- Identifique a los clientes con sentimientos negativos para enfocar sus campañas y compromisos y optimícelos para obtener un mayor retorno  
- Identificar aspectos comerciales con problemas señalados por los clientes  
- Segmente a los clientes en función de sus sentimientos para ejecutar campañas personalizadas con esfuerzos específicos de ventas, marketing y soporte
- Optimice las operaciones comerciales abordando áreas de preocupación u oportunidades que mencionaron los clientes
- Reconocer los aspectos comerciales que están funcionando bien y recompensar a los clientes satisfechos a través de programas de fidelización y promoción

El modelo proporciona una lista de palabras que afectaron la decisión de los modelos de asignar un puntaje de sentimiento particular o un aspecto comercial a los comentarios de retroalimentación.  

Usamos dos **Modelos de procesamiento de lenguaje natural (NLP)**: el primero asigna a cada comentario de opinión una puntuación de sentimiento. El segundo modelo asocia cada comentario con todos los aspectos comerciales aplicables. Los modelos están formados en datos públicos de fuentes en redes sociales, comercio minorista, restaurantes, productos de consumo e industrias automotrices.
  
Los aspectos comerciales predefinidos para que el modelo se asocie con los datos de comentarios incluyen:
- Administración de cuentas
- Finalizar la compra y pagar
- Asistencia al cliente
- Recogida en tienda
- Empaquetado, envío y recuperación
- Pedido por adelantado
- Precio
- Privacidad y seguridad
- Promociones y recompensas
- Recibo y garantía
- Devolución, cambio y cancelación
- Precisión de proceso de entrega
- Calidad del sitio web o la aplicación

> [!NOTE]
> Actualmente, solo admitimos el análisis de opiniones sobre los comentarios de los clientes en inglés. Se admitirán más idiomas en el futuro. Si se cargan comentarios en otros idiomas, el modelo aún arrojará resultados. Sin embargo, estos resultados no serán exactos.

## <a name="prerequisites"></a>Requisitos previos

- Al menos [permisos de colaborador](permissions.md)
- Datos de retroalimentación de texto [unificados](data-unification.md). Le recomendamos encarecidamente que [configure sus entidades de datos de comentarios como entidades de actividad de tipo semántico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tipo de comentario).
- ID de cliente unificado (UCID) de la unificación de datos para hacer coincidir los registros de datos de comentarios de texto con un cliente individual.
- Id. de comentarios
- Marca de tiempo de comentario
- Texto de comentarios

Customer Insights puede procesar hasta 10 millones de registros de comentarios para una sola ejecución de modelo. El modelo puede analizar comentarios de hasta 128 palabras. Si un comentario de opinión es más largo, el análisis considera solo las primeras 128 palabras.

> [!NOTE]
> Solo se puede configurar una entidad de comentario. Si hay varias entidades de comentarios, combínelas en Power Query antes de la ingesta de datos.

## <a name="configure-a-sentiment-analysis"></a>Configurar un análisis de sentimiento

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Análisis de comentarios del cliente (versión preliminar)**.

1. Seleccione **Comenzar**.

1. Proporcione el **Nombre** del análisis y proporcione el **Nombre de la entidad de salida de aspecto de negocio** y el **Nombre de entidad de salida de puntuación de opiniones**.

1. Seleccione **Siguiente**.

1. Seleccione **Agregar datos** para **Comentarios del cliente**.

1. Seleccione el tipo de actividad semántica **Retroalimentación** que contiene los datos de retroalimentación. Si la actividad no se ha configurado, seleccione **aquí** y créela.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Paso de configuración para seleccionar actividades de comentario para el análisis de sentimiento.":::

1. Seleccione las actividades que desea para este análisis de sentimiento y, a continuación, seleccione **Siguiente**.

1. Asigne los atributos de sus datos a los atributos del modelo. 

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**. El paso **Revisar y ejecutar** muestra un resumen de la configuración y brinda la oportunidad de realizar cambios antes de crear el análisis.

1. Seleccione **Editar** en cualquiera de los pasos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Guardar y ejecutar** para comenzar a ejecutar el modelo. Seleccione **Listo**. La pestaña **Mis predicciones** se muestra mientras se crea predicción. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Ver resultados de análisis

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Mis predicciones**, seleccione la predicción que desea ver.

Hay dos pestañas de resultados.

### <a name="sumary-tab"></a>Pestaña Resumen

Hay cuatro secciones principales de datos dentro de la página de resultados.

- **Puntuación de sentimiento media**: las puntuaciones de sentimiento le ayudan a comprender el sentimiento general de todos los clientes.
  - **Negativa** (-5 > 2)
  - **Neutra** (-1 > 1)
  - **Positiva** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representación visual del sentimiento general del cliente.":::

- **Distribución de clientes por puntuación de sentimiento**: los clientes se clasifican en grupos negativos, neutrales y positivos en función de sus puntuaciones de sentimiento. Pase el cursor sobre las barras en el histograma para ver la cantidad de clientes y la puntuación de sentimiento media en cada grupo. Estos datos le pueden ayudar [a crear segmentos de clientes](prediction-based-segment.md) en función de sus puntuaciones de sentimiento.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras que muestra la opinión del cliente en los tres grupos de opinión.":::

- **Puntuación de sentimiento media a lo largo del tiempo**: el sentimiento del cliente puede cambiar con el tiempo. Proporcionamos tendencias en los sentimientos de sus clientes para el rango de tiempo de sus datos. Esta vista le ayuda a medir el efecto de las promociones de temporada, los lanzamientos de productos u otras intervenciones con límites de tiempo en la opinión del cliente. Vea el gráfico seleccionando el año de interés en el menú desplegable.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico de historial con la puntuación de opinión a lo largo del tiempo representada como una línea.":::

- **Sentimiento a través de los aspectos comerciales**: el sentimiento promedio en los aspectos comerciales lo ayuda a evaluar qué aspectos de su negocio ya satisfacen a los clientes o requieren más atención. Los registros de comentarios que no se alinean con ninguno de los aspectos comerciales admitidos se clasifican en **Otro**. Ordene los datos seleccionando cualquier columna.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspectos comerciales con el valor de la opinión asociado y el número de clientes que lo mencionan.":::

  Seleccione el nombre de un aspecto comercial para ver cómo el modelo identifica un aspecto comercial:

  - **Palabras influyentes** : las principales palabras que influyeron en la identificación del modelo de IA de un aspecto comercial en los comentarios de los clientes.
    **Mostrar palabras ofensivas**: le permite incluir palabras ofensivas en la lista a partir de los datos originales de comentarios de los clientes. De forma predeterminada, está desactivado.  El enmascaramiento de palabras ofensivas funciona con un modelo de IA y es posible que no detecte todas las palabras ofensivas. Si detecta una palabra ofensiva que no se filtró como se esperaba, háganoslo saber.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palabras influyentes con la palanca para mostrar u ocultar palabras ofensivas.":::

  - **Ejemplos de comentarios**:registros de comentarios reales en sus datos. Las palabras están codificadas por colores según su influencia en la identificación de un aspecto comercial.

### <a name="influential-words-analysis-tab"></a>Pestaña de análisis de palabras influyentes

Hay tres secciones de información adicional que explican cómo funciona el modelo de sentimiento.
  
- **Principales palabras que contribuyen a la opinión positiva**: las principales palabras que influyeron en la identificación del modelo de IA de sentimientos positivos en los comentarios de los clientes.  

- **Principales palabras que contribuyen a la opinión negativa**: las principales palabras que influyeron en la identificación del modelo de IA de opiniones negativas en los comentarios de los clientes.

- **Muestras de comentarios**: registros de comentarios reales, uno con una opinión negativa y otro con una opinión positiva. Las palabras en los registros de comentarios se resaltan según su contribución a la puntuación de opinión asignada. Las palabras que contribuyen a una puntuación de opinión positiva se resaltan en verde. Las palabras que contribuyen a una puntuación negativa se resaltan en rojo.
   Seleccione **Ver más** para cargar más ejemplos de comentarios.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Ejemplos de análisis de sentimientos sobre los comentarios de los clientes.":::

**Mostrar palabras ofensivas**: le permite incluir palabras ofensivas en la lista a partir de los datos originales de comentarios de los clientes. De forma predeterminada, está desactivado.  El enmascaramiento de palabras ofensivas funciona con un modelo de IA y es posible que no detecte todas las palabras ofensivas. Si detecta una palabra ofensiva que no se filtró como se esperaba, háganoslo saber.

## <a name="act-on-analysis-results"></a>Actuar con resultados de análisis

Para crear nuevos segmentos de clientes desde la página de resultados del análisis de sentimiento, seleccione **Crear segmentos** en la parte superior de la página de resultados del modelo.

## <a name="potential-bias"></a>Sesgo potencial

Al igual que con cualquier función que utilice inteligencia artificial predictiva, podría haber un sesgo potencial en los datos que utiliza para predecir la opinión del cliente. Por ejemplo, si solo recopila comentarios digitalmente, podría perder los comentarios de los clientes que principalmente hacen negocios con usted en persona, lo que podría afectar el resultado de la función.

Como esta característica utiliza medios automatizados para evaluar datos y hacer predicciones basadas en esos datos, por lo tanto, tiene la capacidad de usarse como un método de creación de perfiles, según lo define el Reglamento General de Protección de Datos ("GDPR"). El uso que haga de esta función para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones. Usted es responsable de asegurarse de que su uso de Dynamics 365 Customer Insights, incluido el análisis de sentimiento, cumple con todas las leyes y reglamentos aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.

[!INCLUDE [footer-include](includes/footer-banner.md)]

