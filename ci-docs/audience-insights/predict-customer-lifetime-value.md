---
title: Predicción del valor de la vida del cliente (CLV)
description: Predecir el potencial de ingresos de los clientes activos en el futuro.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 04c4252aae374cf25c16b71415ee4a89b51b0040
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954600"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Predicción del valor de tiempo de vida del cliente (CLV) (versión preliminar)

Predecir el valor potencial (ingresos) que los clientes activos individuales aportarán a su negocio durante un período de tiempo futuro definido. Esta función puede ayudarle a lograr varios objetivos: 
- Identificar clientes de alto valor y procesar esta información
- Crear segmentos de clientes estratégicos basados en su valor potencial para ejecutar campañas personalizadas con iniciativas de ventas, marketing y soporte específicas
- Guiar el desarrollo de productos centrándose en funciones que aumenten el valor para el cliente
- Optimizar la estrategia de ventas o marketing y asigne el presupuesto de manera más precisa para llegar al cliente
- Reconocer y recompensar a los clientes de alto valor mediante programas de fidelización o recompensas 

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, reflexione sobre lo que CLV significa para su negocio. Actualmente, admitimos CLV basado en transacciones de predicción. El valor previsto de un cliente se basa en el historial de transacciones comerciales. Para crear la predicción, necesita al menos permisos de [colaborador](permissions.md).

Dado que configurar y ejecutar un modelo CLV no toma mucho tiempo, considere la posibilidad de crear varios modelos con diferentes preferencias de entrada y compare los resultados del modelo para ver qué escenario de modelo se adapta mejor a sus necesidades comerciales.

###  <a name="data-requirements"></a>Requisitos de datos

Los siguientes datos son obligatorios y, cuando se marcan como opcionales, es que se recomiendan para un mayor rendimiento del modelo. Cuantos más datos puede procesar el modelo, más precisa será la predicción. Por lo tanto, le recomendamos que ingiera más datos de actividad de los clientes, si están disponibles.

- Identificador de cliente: identificador único para hacer coincidir las transacciones con un cliente individual

- Historial de transacciones: registro de transacciones históricas con el siguiente esquema de datos semánticos
    - **Id. de transacción**: identificador único de cada transacción
    - **Fecha de la transacción**: fecha, preferiblemente una marca de tiempo de cada transacción
    - **Importe de la transacción**: valor monetario (por ejemplo, ingresos o margen de beneficios) de cada transacción
    - **Etiqueta asignada a las devoluciones** (opcional): valor booleano que indica si la transacción es una devolución 
    - **Id. de producto** (opcional): id. de producto del producto involucrado en la transacción

- Datos adicionales (opcional), por ejemplo
    - Actividades web: historial de visitas al sitio web, historial de correo electrónico
    - Actividades de fidelización: historial de acumulación y canje de puntos de recompensa por fidelidad
    - Registro del servicio al cliente, llamada de servicio, reclamación o devolución
- Datos sobre las actividades del cliente (opcional):
    - Identificadores de actividad para distinguir actividades del mismo tipo
    - Identificadores de clientes para asignar actividades a sus clientes
    - Información de actividad que contiene el nombre y la fecha de la actividad
    - El esquema de datos semánticos para actividades incluye: 
        - **Clave principal**: un identificador único de una actividad
        - **Marca de tiempo**: fecha y hora del evento, identificadas mediante la clave principal
        - **Evento (nombre de actividad)**: el nombre del evento que desea usar
        - **Detalles (importe o valor)**: detalles sobre la actividad del cliente

- Características de los datos sugeridos
    - Datos históricos suficientes: al menos un año de datos transaccionales. Preferiblemente de dos a tres años de datos transaccionales para predecir el CLV durante un año.
    - Varias compras por cliente: idealmente, al menos dos o tres transacciones por id. de cliente, preferiblemente en varias fechas.
    - Número de clientes: al menos 100 clientes únicos, preferiblemente más de 10 000 clientes. El modelo no funcionará con menos de 100 clientes y datos históricos insuficientes
    - Compleción de los datos: menos del 20% de valores ausentes en los campos obligatorios de los datos de entrada   

> [!NOTE]
> - El modelo requiere el historial de transacciones de sus clientes. Actualmente, solo se puede configurar una entidad del historial de transacciones. Si hay varias entidades de compra/transacción, puede unirlas en Power Query antes de la ingesta de datos.
> - Sin embargo, para obtener datos adicionales sobre la actividad del cliente (opcional), puede agregar tantas entidades de actividad del cliente como desee para que el modelo las considere.

## <a name="create-a-customer-lifetime-value-prediction"></a>Crear una predicción del valor de tiempo de vida del cliente

1. En las informaciones de público, vaya a **Inteligencia** > **Predicciones**.

1. Seleccione el icono **Valor de por vida del cliente** y seleccione **Modelo de uso**. 

1. En el panel **Valor de por vida del cliente (vista previa)**, seleccione **Empezar**.

1. Asigne un nombre a **este modelo** y a la **entidad de salida** para distinguirlos de otros modelos o entidades.

1. Seleccione **Siguiente**.

### <a name="define-model-preferences"></a>Definir preferencias de modelo

1. Establecer un **Período de tiempo de predicción** para definir durante qué período en el futuro quiere predecir el CLV.    
   De forma predeterminada, la unidad está configurada como meses. Puede cambiarlo a años para avanzar más en el futuro.

   > [!TIP]
   > Para predecir con precisión el CLV para el período de tiempo que establezca, necesita un período comparable de datos históricos. Por ejemplo, si desea predecir el CLV para los próximos 12 meses, se recomienda que tenga al menos de 18 a 24 meses de datos históricos.

1. Especifique qué significa **Clientes activos** para su negocio. Establezca el período de tiempo en el que un cliente debe haber tenido al menos una transacción para ser considerado activo. El modelo solo predecirá CLV para clientes activos. 
   - **Dejar que el modelo calcule el intervalo de compra (recomendado)**: el modelo analiza sus datos y determina un período de tiempo basado en compras históricas.
   - **Establecer el intervalo manualmente**: si tiene una definición comercial específica de un cliente activo, elija esta opción y configure el período de tiempo en consecuencia.

1. Defina el percentil del **Cliente de alto valor** para permitir que el modelo proporcione resultados que se ajusten a la definición de su negocio.
    - **Cálculo del modelo (recomendado)**: el modelo analiza sus datos y determina qué podría ser un cliente de alto valor para su negocio en función del historial de transacciones de sus clientes. El modelo utiliza una regla heurística (inspirada según la regla 80/20 o Ley de Pareto) para encontrar la proporción de clientes de alto valor. El porcentaje de clientes que contribuyeron al 80 % de los ingresos acumulados para su empresa en el período histórico se consideran clientes de alto valor. Normalmente, menos del 30-40 % de los clientes contribuyen al 80 % de los ingresos acumulados. Sin embargo, este número puede variar según su negocio e industria.    
    - **Porcentaje de clientes activos principales**: defina los clientes de alto valor para su negocio como un percentil de los principales clientes activos que pagan. Por ejemplo, puede utilizar esta opción para definir a los clientes de alto valor como el 20 % más importante de los futuros clientes de pago.

    Si su empresa define a los clientes de alto valor de una manera diferente, [no dude en comunicárnoslo, ya que estaremos encantados de saber cómo](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Seleccione **Siguiente** para ir al paso siguiente.

### <a name="add-required-data"></a>Agregar datos necesarios

1. En el paso **Datos necesarios**, seleccione **Agregar datos** para **Historial de compras** y elija la entidad que proporciona la información del historial de transacciones, como se describe en los [requisitos previos](#prerequisites).

1. Asigne los campos semánticos a los atributos dentro de su entidad de historial de compras y seleccione **Siguiente**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Imagen del paso de configuración para asignar atributos de datos para los datos requeridos.":::
 
1. Si los campos a continuación no están rellenos, configure la relación en su entidad de historial de compras para la entidad *Cliente* y seleccione **Guardar**.
    1. Seleccione la entidad de historial de compras.
    1. Seleccione el campo que identifica al cliente en la entidad de historial de compras. Debe relacionarse con el ID de cliente principal de su entidad Cliente.
    1. Seleccione la entidad que se corresponde con la entidad de cliente principal.
    1. Escriba un nombre que describa la relación.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Imagen del paso de configuración para definir la relación con la entidad cliente.":::

1. Seleccione **Siguiente**.

### <a name="add-optional-data"></a>Agregar datos opcionales

Los datos que reflejan las interacciones clave del cliente (como la web, el servicio al cliente y los registros de eventos) agregan contexto a los registros de transacciones. Si se encuentran más patrones en los datos de actividad de sus clientes, se puede mejorar la precisión de las predicciones. 

1. En el paso **Datos adicionales (opcional)**, seleccione **Agregar datos**. Elija la entidad de la actividad del cliente que proporciona la información de actividad del cliente como se describe en los [requisitos previos](#prerequisites).

1. Asigne los campos semánticos a los atributos dentro de su entidad de actividad del cliente y seleccione **Siguiente**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Imagen del paso de configuración para asignar campos para los datos requeridos.":::

1. Seleccione un tipo de actividad que coincida con el tipo de actividad del cliente que está agregando. Elija entre los tipos de actividad existentes o agregue un nuevo tipo de actividad.

1. Configure la relación en la entidad de actividad de cliente para la entidad *Cliente*.
    
    1. Seleccione el campo que identifica al cliente en la tabla de actividad de compras. Puede estar directamente relacionado con el identificador de cliente principal de su entidad de *Cliente*.
    1. Seleccione la entidad *Cliente* que coincida con su entidad *Cliente* principal.
    1. Escriba un nombre que describa la relación.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Imagen del paso en el flujo de configuración para agregar datos adicionales y configurar la actividad con ejemplos completados.":::

1. Seleccione **Guardar**.    
    Agregue más datos si hay otras actividades de clientes que desea incluir.

1. Seleccione **Siguiente**.

### <a name="set-update-schedule"></a>Definir la programación de actualizaciones

1. En el paso **Programa de actualización de datos**, elija la frecuencia para reentrenar su modelo en función de los datos más recientes. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos en las informaciones de público. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.


### <a name="review-and-run-the-model-configuration"></a>Revisar y ejecutar la configuración del modelo

1. En el paso **Revisar los detalles de su modelo**, valide la configuración de la predicción. Puede volver a cualquier parte de la configuración de predicción seleccionando **Editar** debajo del valor mostrado. También puede seleccionar un paso de configuración en el indicador del progreso.

1. Si todos los valores están configurados correctamente, seleccione **Guardar y ejecutar** para comenzar a ejecutar el modelo. En la pestaña **Mis predicciones**, puede ver el estado del proceso de predicción. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

## <a name="review-prediction-status-and-results"></a>Revisar el estado y los resultados de la predicción

### <a name="review-prediction-status"></a>Revisar el estado de predicción

1.  Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.
2.  Seleccione la predicción que desea revisar.

- **Nombre de predicción**: nombre de la predicción proporcionada al crearlo.
- **Tipo de predicción**: tipo de modelo utilizado para la predicción
- **Entidad de salida**: nombre de la entidad para guardar la salida de la predicción. Vaya a **Datos** > **Entidades** para encontrar la entidad con este nombre.
- **Campo previsto**: este campo se rellena solo para algunos tipos de predicciones y no se usa en la predicción del valor del tiempo de vida del cliente.
- **Estado**: estado de la ejecución de la predicción.
    - **Puesto en cola**: la predicción está esperando a que se completen otros procesos.
    - **Actualización**: la predicción se está ejecutando actualmente para crear resultados que fluirán hacia la entidad de salida.
    - **Errores**: la ejecución de la predicción ha presentado errores. [Revise los registros](#troubleshoot-a-failed-prediction) para más detalles.
    - **Correcta**: la predicción ha tenido éxito. Seleccione **Vista** en los puntos suspensivos verticales para revisar los resultados de la predicción.
- **Editada**: la fecha en que se modificó la configuración para la predicción.
- **Última actualización**: la fecha en que la predicción actualizó los resultados en la entidad de salida.


### <a name="review-prediction-results"></a>Revisar los resultados de la predicción

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.

1. Seleccione la predicción cuyos resultados desea revisar.

Hay tres secciones de datos principales en la página de resultados.

- **Rendimiento del modelo de entrenamiento**: A, B o C son posibles puntuaciones. Esta puntuación indica el rendimiento de la predicción y puede ayudarlo a tomar la decisión de utilizar los resultados almacenados en la entidad de salida. Seleccione **Más información sobre esta puntuación** para comprender mejor las métricas de rendimiento del modelo subyacente y cómo se obtuvo la calificación de rendimiento del modelo final.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagen del cuadro de información de la puntuación del modelo con la puntuación de A.":::

  Utilizando la definición de clientes de alto valor proporcionada al configurar la predicción, el sistema evalúa el rendimiento del modelo de IA en la predicción de los clientes de alto valor en comparación con un modelo de referencia.    

  Las puntuaciones se determinan según las siguientes reglas:
  - **A** cuando el modelo predijo con precisión al menos un 5 % más de clientes de alto valor en comparación con el modelo de referencia.
  - **B** cuando el modelo predijo con precisión entre un 0 % y un 5 % más de clientes de alto valor en comparación con el modelo de referencia.
  - **C** cuando el modelo predijo con precisión menos clientes de alto valor en comparación con el modelo de referencia.

  El panel **Calificación del modelo** muestra más detalles sobre el rendimiento del modelo de IA y el modelo de referencia. El modelo de referencia utiliza un enfoque no basado en IA para calcular el valor de vida del cliente basado principalmente en las compras históricas realizadas por los clientes.     
  La fórmula estándar utilizada para calcular el CLV mediante el modelo de referencia:    

  _**CLV para cada cliente** = Compra mensual promedio realizada por el cliente en la ventana de cliente activo * Número de meses en el período de predicción de CLV * Tasa de retención general de todos los clientes*_

  El modelo de IA se compara con el modelo de referencia basado en dos métricas de rendimiento del modelo.
  
  - **Tasa de éxito en la predicción de clientes de alto valor**

    Vea la diferencia en la predicción de clientes de alto valor utilizando el modelo de IA en comparación con el modelo de referencia. Por ejemplo, una tasa de éxito del 84 % significa que de todos los clientes de alto valor en los datos de entrenamiento, el modelo de IA pudo capturar con precisión el 84 %. Luego, comparamos esta tasa de éxito con la tasa de éxito del modelo de referencia para registrar el cambio relativo. Este valor se utiliza para asignar una puntuación al modelo.

  - **Métricas de errores**
    
    Otra métrica le permite revisar el rendimiento general del modelo en términos de error en la predicción de valores futuros. Usamos la métrica general Root Mean Squared Error (RMSE) para evaluar este error. RMSE es una forma estándar de medir el error de un modelo al predecir datos cuantitativos. El RMSE del modelo de IA se compara con el RMSE del modelo de referencia y se informa la diferencia relativa.

  El modelo de IA prioriza la clasificación precisa de los clientes de acuerdo con el valor que aportan a su negocio. Por lo tanto, solo se utiliza la tasa de éxito de la predicción de clientes de alto valor para obtener la puntuación final del modelo. La métrica RMSE detecta valores atípicos. En escenarios en los que tiene un pequeño porcentaje de clientes con valores de compra extraordinariamente altos, es posible que la métrica general del RMSE no ofrezca una imagen completa del rendimiento del modelo.   

- **Valor de los clientes por percentil**: utilizando su definición de clientes de alto valor, los clientes se agrupan en clientes de bajo valor y de alto valor, según sus predicciones de CLV, y se muestran en un gráfico. Al pasar el cursor sobre las barras en el histograma, puede ver el número de clientes en cada grupo y el CLV promedio de ese grupo. Estos datos pueden ayudar si desea [crear segmentos de clientes](segments.md) según sus predicciones de CLV.

- **Factores más influyentes**: se consideran varios factores al crear su predicción de CLV según los datos de entrada proporcionados al modelo de IA. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Puede utilizar estos factores para ayudar a validar los resultados de la predicción. Estos factores también brindan más información sobre los factores más influyentes que contribuyeron a predecir el CLV en todos sus clientes.

## <a name="refresh-a-prediction"></a>Actualizar una predicción

Las predicciones se actualizan automáticamente en el mismo [programa en que se actualizan sus datos](system.md#schedule-tab) según lo configurado en los ajustes. También puede actualizarlas manualmente.

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.
2. Seleccione los puntos suspensivos verticales junto a la predicción que desea actualizar.
3. Seleccione **Actualizar**.

## <a name="delete-a-prediction"></a>Eliminar una predicción

Eliminar un predicción también elimina su entidad de salida.

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.
2. Seleccione los puntos suspensivos verticales junto a la predicción que desea eliminar.
3. Seleccione **Eliminar**.

## <a name="troubleshoot-a-failed-prediction"></a>Solucionar problemas de una predicción con errores

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.
2. Seleccione los puntos suspensivos verticales junto a la predicción para la que desea ver los registros de errores.
3. Seleccione **Registros**.
4. Revisar todos los errores. Hay varios tipos de errores que pueden producirse, y describen qué condición causó el error. Por ejemplo, un error para el que no hay suficientes datos para predecir con precisión se resuelve normalmente cargando datos adicionales en las informaciones de público.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
