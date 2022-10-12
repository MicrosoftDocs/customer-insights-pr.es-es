---
title: Predecir valor de tiempo de vida del cliente (CLV)
description: Predecir el potencial de ingresos de los clientes activos en el futuro.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610395"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predecir valor de tiempo de vida del cliente (CLV)

Predecir el valor potencial (ingresos) que los clientes activos individuales aportarán a su negocio durante un período de tiempo futuro definido. Esta predicción le ayuda a:

- Identificar clientes de alto valor y procesar esta información.
- Crear segmentos de clientes estratégicos basados en su valor potencial para ejecutar campañas personalizadas con iniciativas de ventas, marketing y soporte específicas.
- Guiar el desarrollo de productos centrándose en funciones que aumenten el valor para el cliente.
- Optimizar la estrategia de ventas o marketing y asigne el presupuesto de manera más precisa para llegar al cliente.
- Reconocer y recompensar a los clientes de alto valor mediante programas de fidelización o recompensas.

Determinar qué significa CLV para su negocio. Admitimos CLV basado en transacciones de predicción. El valor previsto de un cliente se basa en el historial de transacciones comerciales. Considere la posibilidad de crear varios modelos con diferentes preferencias de entrada y compare los resultados del modelo para ver qué escenario de modelo se adapta mejor a sus necesidades comerciales.

> [!TIP]
> Pruebe el CLV predicción usando datos de muestra: [Guía de muestra de predicción del valor de por vida del cliente (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos permisos de [colaborador](permissions.md)
- Al menos 100 clientes únicos, preferiblemente más de 10 000 clientes
- Identificador de cliente, un identificador único para hacer coincidir las transacciones con un cliente individual
- Al menos un año de historial de transacciones, preferiblemente dos o tres. Idealmente, al menos dos o tres transacciones por id. de cliente, preferiblemente en varias fechas. El historial de transacciones debe incluir:
  - **Id. de transacción**: identificador único de cada transacción
  - **Fecha de la transacción**: fecha o marca de tiempo de cada transacción
  - **Importe de la transacción**: valor monetario (por ejemplo, ingresos o margen de beneficios) de cada transacción
  - **Etiqueta asignada a las devoluciones**: valor booleano verdadero/falso que indica si la transacción es una devolución
  - **Id. de producto** id. de producto del producto involucrado en la transacción
- Datos sobre las actividades del cliente:
  - **Clave principal**: identificador único de una actividad
  - **Marca de tiempo**: fecha y hora del evento, identificadas mediante la clave principal
  - **Evento (nombre de actividad)**: nombre del evento que desea usar
  - **Detalles (importe o valor)**: detalles sobre la actividad del cliente
- Datos adicionales como:
  - Actividades web: historial de visitas al sitio web o historial de correo electrónico
  - Actividades de fidelización: historial de acumulación y canje de puntos de recompensa por fidelidad
  - Registro del servicio al cliente, llamada de servicio, reclamación o devolución
  - Información del perfil del cliente
- Menos del 20 % de valores faltantes en los campos obligatorios

> [!NOTE]
> Solo se puede configurar una entidad del historial de transacciones. Si hay varias entidades de compra o transacción, combínelas en Power Query antes de la ingesta de datos.

## <a name="create-a-customer-lifetime-value-prediction"></a>Crear una predicción del valor de tiempo de vida del cliente

Seleccione **Guardar borrador** en cualquier momento para guardar la predicción como borrador. La predicción de borrador se muestra en la pestaña **Mis predicciones**.

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Valor de vida útil del cliente**.

1. Seleccione **Comenzar**.

1. Asigne un nombre a **este modelo** y a la **entidad de salida** para distinguirlos de otros modelos o entidades.

1. Seleccione **Siguiente**.

### <a name="define-model-preferences"></a>Definir preferencias de modelo

1. Establecer un **Período de tiempo de predicción** para definir durante qué período en el futuro quiere predecir el CLV. De forma predeterminada, la unidad está configurada como meses.

   > [!TIP]
   > Para predecir con precisión el CLV para el período de tiempo establecido, necesita un período comparable de datos históricos. Por ejemplo, si desea predecir el CLV para los próximos 12 meses, tenga al menos de 18 a 24 meses de datos históricos.

1. Establezca el período de tiempo en el que un cliente debe haber tenido al menos una transacción para ser considerado activo. El modelo solo predice CLV para **clientes activos**.
   - **Dejar que el modelo calcule el intervalo de compra (recomendado)**: el modelo analiza sus datos y determina un período de tiempo basado en compras históricas.
   - **Establecer intervalo manualmente**: período de tiempo para su definición de un cliente activo.

1. Defina el percentil de **Cliente de alto valor**.
    - **Modelo de cálculo (recomendado)**: el modelo usa la regla 80/20. El porcentaje de clientes que contribuyeron al 80 % de los ingresos acumulados para su empresa en el período histórico se consideran clientes de alto valor. Normalmente, menos del 30-40 % de los clientes contribuyen al 80 % de los ingresos acumulados. Sin embargo, este número puede variar según su negocio e industria.
    - **Porcentaje de los mejores clientes activos**: Percentil específico para un cliente de alto valor. Por ejemplo, introduzca **25** para definir los clientes de alto valor como el 25 % más importante de los futuros clientes de pago.

    Si su empresa define a los clientes de alto valor de una manera diferente, [no dude en comunicárnoslo, ya que estaremos encantados de saber cómo](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Seleccione **Siguiente**.

### <a name="add-required-data"></a>Agregar datos necesarios

1. Seleccione **Agregar datos** para **Historial de transacciones de cliente**.

1. Seleccione el tipo de actividad semántica, **Órdenes de venta** o **Línea de pedido de ventas**, que contiene el historial de transacciones. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron semánticamente cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo semántico, seleccione **Editar** y mapee sus datos.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Agregue los datos requeridos para el modelo CLV":::

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Añade más actividades o selecciona **Siguiente**.

### <a name="add-optional-activity-data"></a>Agregar datos de actividad opcionales

Los datos que reflejan las interacciones clave del cliente (como la web, el servicio al cliente y los registros de eventos) agregan contexto a los registros de transacciones. Si se encuentran más patrones en los datos de actividad de sus clientes, se puede mejorar la precisión de las predicciones.

1. Seleccione **Agregar datos** bajo **Mejorar la información del modelo con datos adicionales de las actividades**.

1. Seleccione un tipo de actividad que coincida con el tipo de actividad del cliente que está agregando. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo, seleccione **Editar** y mapee sus datos.

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**.

1. [Agregue datos de clientes opcionales](#add-optional-customer-data) o seleccione **Siguiente** y vaya a [Establecer programa de actualización](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Agregar datos del cliente opcionales

Seleccione entre 18 atributos de perfil de cliente de uso común para incluirlos como entrada al modelo. Estos atributos pueden conducir a resultados de modelo más personalizados, relevantes y procesables para sus casos de uso empresarial.

Por ejemplo: Contoso Coffee quiere predecir el valor de la vida útil del cliente para dirigirse a clientes de alto valor con una oferta personalizada relacionada con el lanzamiento de su nueva máquina de café exprés. Contoso usa el modelo CLV y agrega los 18 atributos de perfil de cliente para ver qué factores influyen en sus clientes de mayor valor. Encuentran que la ubicación del cliente es el factor más influyente para estos clientes.
Con esta información, organizan un evento local para el lanzamiento de la máquina de café exprés y se asocian con proveedores locales para ofrecer ofertas personalizadas y una experiencia especial en el evento. Sin esta información, es posible que Contoso solo haya enviado correos electrónicos de marketing genéricos y haya perdido la oportunidad de personalizar para este segmento local de sus clientes de alto valor.

1. Seleccione **Agregar datos** bajo **Mejorar la información del modelo aún más con datos adicionales de los clientes**.

1. Para **Entidad**, elija **Cliente: CustomerInsights** para seleccionar el perfil de cliente unificado que se asigna a los datos de atributos del cliente. Para **Id. del cliente**, elija **System.Customer.CustomerId**.

1. Asigne más campos si los datos están disponibles en sus perfiles unificados de clientes.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Ejemplo de campos asignados para datos de perfil de cliente.":::

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**.

### <a name="set-update-schedule"></a>Definir la programación de actualizaciones

1. Elija la frecuencia para reentrenar su modelo en función de los datos más recientes. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos en Customer Insights. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

### <a name="review-and-run-the-model-configuration"></a>Revisar y ejecutar la configuración del modelo

El paso **Revisar y ejecutar** muestra un resumen de la configuración y brinda la oportunidad de realizar cambios antes de crear el predicción.

1. Seleccione **Editar** en cualquiera de los pasos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Guardar y ejecutar** para comenzar a ejecutar el modelo. Seleccione **Listo**. La pestaña **Mis predicciones** se muestra mientras se crea predicción. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver los resultados de la predicción

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Mis predicciones**, seleccione la predicción que desea ver.

Hay tres secciones de datos principales en la página de resultados.

- **Rendimiento del modelo de entrenamiento**: los grados A, B o C indican el rendimiento de la predicción y puede ayudarlo a tomar la decisión de utilizar los resultados almacenados en la entidad de salida.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagen del cuadro de información de la puntuación del modelo con la puntuación de A.":::

  Customer Insights evalúa cómo el rendimiento del modelo de IA en la predicción de clientes de alto valor en comparación con un modelo de referencia.

  Las puntuaciones se determinan según las siguientes reglas:
  - **A** cuando el modelo predijo con precisión al menos un 5 % más de clientes de alto valor en comparación con el modelo de referencia.
  - **B** cuando el modelo predijo con precisión entre un 0 % y un 5 % más de clientes de alto valor en comparación con el modelo de referencia.
  - **C** cuando el modelo predijo con precisión menos clientes de alto valor en comparación con el modelo de referencia.
  
  Seleccione [**Obtener más información acerca de esta puntuación**](#learn-about-the-score) para abrir el panel **Calificación del modelo**, que muestra más detalles sobre el rendimiento del modelo de IA y el modelo de referencia. Le ayudará a comprender mejor las métricas de rendimiento del modelo subyacente y cómo se obtuvo la calificación de rendimiento del modelo final. El modelo de referencia utiliza un enfoque no basado en IA para calcular el valor de vida del cliente basado principalmente en las compras históricas realizadas por los clientes.

- **Valor de los clientes por percentil**: los clientes de bajo y alto valor se muestran en un gráfico. Pase el cursor sobre las barras en el histograma para ver el número de clientes en cada grupo y el CLV promedio de ese grupo. Opcionalmente, [cree segmentos de clientes](prediction-based-segment.md) según sus predicciones de CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valor de los clientes por percentil para el modelo CLV":::

- **Factores más influyentes**: se consideran varios factores al crear su predicción de CLV según los datos de entrada proporcionados al modelo de IA. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Use estos factores para ayudar a validar los resultados de la predicción. Estos factores también brindan más información sobre los factores más influyentes que contribuyeron a predecir el CLV en todos sus clientes.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Factores más influyentes para el modelo CLV":::

### <a name="learn-about-the-score"></a>Obtener más información acerca de la puntuación

La fórmula estándar utilizada para calcular el CLV mediante el modelo de referencia:

 _**CLV para cada cliente** = Compra mensual promedio realizada por el cliente en la ventana de cliente activo * Número de meses en el período de predicción de CLV * Tasa de retención general de todos los clientes_

El modelo de IA se compara con el modelo de referencia basado en dos métricas de rendimiento del modelo.
  
- **Tasa de éxito en la predicción de clientes de alto valor**

  Vea la diferencia en la predicción de clientes de alto valor utilizando el modelo de IA en comparación con el modelo de referencia. Por ejemplo, una tasa de éxito del 84 % significa que de todos los clientes de alto valor en los datos de entrenamiento, el modelo de IA pudo capturar con precisión el 84 %. Luego, comparamos esta tasa de éxito con la tasa de éxito del modelo de referencia para registrar el cambio relativo. Este valor se utiliza para asignar una puntuación al modelo.

- **Métricas de errores**

  Consulte el rendimiento general del modelo en términos de error en la predicción de valores futuros. Usamos la métrica general Root Mean Squared Error (RMSE) para evaluar este error. RMSE es una forma estándar de medir el error de un modelo al predecir datos cuantitativos. El RMSE del modelo de IA se compara con el RMSE del modelo de referencia y se informa la diferencia relativa.

El modelo de IA prioriza la clasificación precisa de los clientes de acuerdo con el valor que aportan a su negocio. Por lo tanto, solo se utiliza la tasa de éxito de la predicción de clientes de alto valor para obtener la puntuación final del modelo. La métrica RMSE detecta valores atípicos. En escenarios en los que tiene un pequeño porcentaje de clientes con valores de compra extraordinariamente altos, es posible que la métrica general del RMSE no ofrezca una imagen completa del rendimiento del modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
