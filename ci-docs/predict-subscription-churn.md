---
title: Predecir el abandono de suscripciones (contiene vídeo)
description: Prediga si un cliente está en peligro por dejar de usar los productos o servicios de suscripción de su compañía.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610257"
---
# <a name="predict-subscription-churn"></a>Predecir el abandono de suscripción

Prediga si un cliente está en peligro por dejar de usar los productos o servicios de suscripción de su compañía. Los datos de la suscripción incluyen suscripciones activas e inactivas para cada cliente, por lo que hay varias entradas por identificador de cliente.

Debe tener conocimiento del negocio para comprender lo que significa la pérdida de suscripciones para su negocio. Admitimos definiciones de pérdida de suscripciones basadas en el tiempo, lo que significa que se considera perdido a un cliente cuando ha transcurrido un período de tiempo tras la finalización de su suscripción.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Pruebe la predicción de cancelación de suscripción con datos de ejemplo: [Guía de ejemplo de predicción de cancelación de suscripción](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos [permisos de colaborador](permissions.md).
- Al menos 10 perfiles clientes, preferiblemente más de 1000 clientes únicos.
- Identificador de cliente, un identificador único para hacer coincidir suscripciones con sus clientes.
- Datos de suscripción de al menos el doble del período tiempo seleccionado. Preferiblemente, dos o tres años de datos de suscripciones. El historial de suscripción debe incluir:
  - **Id. de suscripción:** un identificador único de una suscripción.
  - **Fecha de finalización de la suscripción:** la fecha de vencimiento de la suscripción para el cliente.
  - **Fecha de inicio de la suscripción:** la fecha en que comienza la suscripción para el cliente.
  - **Fecha de transacción:** la fecha en que ocurrió un cambio de suscripción. Por ejemplo, un cliente que compra o cancela una suscripción.
  - **¿Es una suscripción periódica?** campo booleano verdadero/falso que determina si la suscripción se renovará con el mismo ID de suscripción sin intervención del cliente
  - **Frecuencia de periodicidad (en meses):** para las suscripciones periódicas, el mes de renovación de la suscripción. Por ejemplo, una suscripción anual que se renueva automáticamente para un cliente cada año durante otro año tiene el valor 12.
  - **Importe de la suscripción:** importe de dinero que un cliente paga por la renovación de la suscripción. Puede ayudar a identificar patrones para diferentes niveles de suscripciones.
- Al menos dos registros de actividad para el 50% de los clientes para los que desea calcular el abandono. Las actividades del cliente deben incluir:
  - **Clave principal**: identificador único de una actividad. Por ejemplo, una visita a un sitio web o un registro de uso que muestra que el cliente vio un episodio de un programa de televisión.
  - **Marca de tiempo**: fecha y hora del evento, identificadas mediante la clave principal.
  - **Evento:** el nombre del evento que desea usar. Por ejemplo, un campo llamado "UserAction" en un servicio de transmisión de vídeo podría tener el valor de "Visto".
  - **Detalles:** Información detallada sobre el evento. Por ejemplo, un campo llamado "ShowTitle" en un servicio de transmisión de vídeo podría tener el valor de un vídeo que el cliente ha visto.
- Menos del 20 % de los valores que faltan en el campo de datos de la entidad proporcionada.

## <a name="create-a-subscription-churn-prediction"></a>Crear una predicción de pérdida de suscripciones

Seleccione **Guardar borrador** en cualquier momento para guardar la predicción como borrador. La predicción de borrador se muestra en la pestaña **Mis predicciones**.

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Modelo de abandono de clientes**.

1. Seleccione **Suscripción** para el tipo de abandono y luego **Empezar**.

1. Asigne un nombre a **este modelo** y a la **entidad de salida** para distinguirlos de otros modelos o entidades.

1. Seleccione **Siguiente**.

### <a name="define-customer-churn"></a>Definir abandono de clientes

1. Introduzca el número de **Días desde que finalizó la suscripción** que su empresa considera para que un cliente esté en un estado de pérdida. Este período suele equivaler a actividades comerciales como ofertas u otros esfuerzos de marketing que intentan evitar la pérdida del cliente.

1. Introduzca el número de **Días para mirar hacia el futuro para predecir el abandono**: Por ejemplo, predizca el riesgo de abandono de sus clientes durante los próximos 90 días para alinearse con sus esfuerzos de retención de marketing. Predecir el riesgo de abandono durante períodos de tiempo más largos o más cortos puede hacer que sean más difícil abordar los factores en el perfil de riesgo de abandono, en función de sus requisitos empresariales específicos.

1. Seleccione **Siguiente**.

### <a name="add-required-data"></a>Agregar datos necesarios

1. Seleccione **Agregar datos** para **Historial de suscripciones**.

1. Seleccione el tipo de actividad semántico **Suscripción** que contiene la información del historial de suscripciones necesaria. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron semánticamente cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo semántico, seleccione **Editar** y mapee sus datos.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Agregue los datos requeridos para el modelo de abandono de suscripciones":::

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Seleccione **Agregar datos** para **Actividades del cliente**.

1. Seleccione el tipo de actividad semántica que proporciona la información de actividad del cliente. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron semánticamente cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo semántico, seleccione **Editar** y mapee sus datos.

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Añade más actividades o selecciona **Siguiente**.

### <a name="set-update-schedule"></a>Definir la programación de actualizaciones

1. Elija la frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos en Customer Insights. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

### <a name="review-and-run-the-model-configuration"></a>Revisar y ejecutar la configuración del modelo

El paso **Revisar y ejecutar** muestra un resumen de la configuración y brinda la oportunidad de realizar cambios antes de crear el predicción.

1. Seleccione **Editar** en cualquiera de los pasos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Guardar y ejecutar** para comenzar a ejecutar el modelo. Seleccione **Listo**. La pestaña **Mis predicciones** se muestra mientras se crea predicción. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver los resultados de la predicción

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Mis predicciones**, seleccione la predicción que desea ver.

Hay tres secciones de datos principales en la página de resultados:

- **Rendimiento del modelo de entrenamiento**: los grados A, B o C indican el rendimiento de la predicción y puede ayudarlo a tomar la decisión de utilizar los resultados almacenados en la entidad de salida.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Imagen del cuadro de información de la puntuación del modelo con la puntuación de A.":::

  Las puntuaciones se determinan según las siguientes reglas:
  - **A** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es mayor que la tasa de abandono promedio histórica en al menos un 10 %.
  - **B** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es hasta un 10% mayor que la tasa de abandono promedio histórica.
  - **C** cuando el modelo predijo con precisión menos del 50% de las predicciones totales, o cuando el porcentaje de predicciones precisas para los clientes que abandonaron es menor que la tasa de abandono media histórica.
  
- **Probabilidad de pérdida (número de clientes)**: Grupos de clientes según su riesgo de pérdida previsto. Opcionalmente, [cree segmentos de clientes](prediction-based-segment.md) con alto riesgo de abandono. Dichos segmentos ayudan a comprender dónde debe estar el corte para la pertenencia del segmento.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Gráfico que muestra la distribución de los resultados de pérdida, desglosada en rangos de 0-100%":::

- **Factores más influyentes:** Hay muchos factores que se tienen en cuenta al crear su predicción. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Use estos factores para ayudar a validar los resultados de la predicción. O use esta información más tarde para [crear segmentos](.//prediction-based-segment.md) que puedan ayudar a influir en el riesgo de pérdida de clientes.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lista que muestra los factores influyentes y su importancia para predecir el resultado de abandono.":::

> [!NOTE]
> En la entidad de salida para este modelo, *ChurnScore* es la probabilidad pronosticada de abandono y *IsChurn* es una etiqueta binaria basada en *ChurnScore* con umbral de 0,5. Si este umbral predeterminado no funciona para su escenario, [cree un nuevo segmento](segments.md) con su umbral preferido. Para ver la puntuación de abandono, vaya a **Datos** > **Entidades** y vea la pestaña de datos para la entidad de salida que definió para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
