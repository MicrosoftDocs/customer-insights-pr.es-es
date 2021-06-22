---
title: Cancelación de predicción de suscripción
description: Prediga si un cliente está en peligro por dejar de usar los productos o servicios de suscripción de su compañía.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 4e7065b61940ef0d7b2a30f96f6225df29e30383
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095669"
---
# <a name="subscription-churn-prediction-preview"></a>Predicción de pérdida de suscripciones (vista previa)

La predicción de pérdida de suscripciones ayuda a predecir si un cliente está en peligro por dejar de usar los productos o servicios de suscripción de su compañía. Puede crear una nueva predicción de pérdida de suscripciones en la página **Inteligencia** > **Predicciones**. Seleccione **Mis predicciones** para ver otras predicciones que ha creado.

> [!TIP]
> Pruebe el tutorial para una predicción de cancelación de suscripción con datos de ejemplo: [Guía de ejemplo de predicción de cancelación de suscripción](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos [permisos de colaborador](permissions.md).
- Conocimiento del negocio para comprender lo que significa la pérdida de suscripciones para su negocio. Admitimos definiciones de pérdida de suscripciones basadas en el tiempo, lo que significa que se considera perdido a un cliente cuando ha transcurrido un período de tiempo tras la finalización de su suscripción.
- Datos sobre sus suscripciones y su historial:
    - Identificadores de suscripción para distinguir suscripciones.
    - Identificadores de clientes para hacer coincidir suscripciones con sus clientes.
    - Fechas de eventos de suscripción, que definen fechas de inicio, fechas de finalización y las fechas en las que ocurrieron los eventos de suscripción.
    - Información de suscripción para definir si es una suscripción periódica y con qué frecuencia se renueva.
    - El esquema de datos semánticos para suscripciones requiere la siguiente información:
        - **Id. de suscripción:** Un identificador único de una suscripción.
        - **Fecha de finalización de la suscripción:** La fecha de vencimiento de la suscripción para el cliente.
        - **Fecha de inicio de la suscripción:** La fecha en que comienza la suscripción para el cliente.
        - **Fecha de transacción:** La fecha en que ocurrió un cambio de suscripción. Por ejemplo, un cliente que compra o cancela una suscripción.
        - **¿Es una suscripción periódica?** Un campo booleano verdadero/falso que determina si la suscripción se renovará con el mismo ID de suscripción sin intervención del cliente
        - **Frecuencia de periodicidad (en meses):** Para las suscripciones periódicas, es el período de renovación de la suscripción. Se representa en meses. Por ejemplo, una suscripción anual que se renueva automáticamente para un cliente cada año durante otro año tiene el valor 12.
        - (Opcional) **Importe de la suscripción:** El importe de dinero que un cliente paga por la renovación de la suscripción. Puede ayudar a identificar patrones para diferentes niveles de suscripciones.
- Datos sobre las actividades del cliente:
    - Identificadores de actividad para distinguir actividades del mismo tipo.
    - Identificadores de clientes para asignar actividades a sus clientes.
    - Información de actividad que contiene el nombre y la fecha de la actividad.
    - El esquema de datos semánticos para actividades del cliente incluye:
        - **Clave principal:** Un identificador único para una actividad. Por ejemplo, una visita a un sitio web o un registro de uso que muestra que el cliente vio un episodio de un programa de televisión.
        - **Marca de tiempo:** La fecha y hora del evento identificado por la clave principal.
        - **Evento:** El nombre del evento que desea usar. Por ejemplo, un campo llamado "UserAction" en un servicio de transmisión de vídeo podría tener el valor de "Visto".
        - **Detalles:** Información detallada sobre el evento. Por ejemplo, un campo llamado "ShowTitle" en un servicio de transmisión de vídeo podría tener el valor de un vídeo que el cliente ha visto.
- Características de los datos sugeridos
    - Datos históricos suficientes: datos de suscripción de al menos el doble del período tiempo seleccionado. Preferiblemente, dos o tres años de datos de suscripciones.
    - Estado de la suscripción: los datos incluyen suscripciones activas e inactivas para cada cliente, por lo que hay varias entradas por identificador de cliente.
    - Número de clientes: al menos 10 perfiles clientes, preferiblemente más de 1000 clientes únicos. El modelo no funcionará con menos de 10 clientes y datos históricos insuficientes.
    - Integridad de los datos: menos del 20 % de los valores que faltan en el campo de datos de la entidad proporcionada.
   
   > [!NOTE]
   > Necesitará al menos dos registros de actividad para el 50% de los clientes para los que desea calcular el abandono.

## <a name="create-a-subscription-churn-prediction"></a>Crear una predicción de pérdida de suscripciones

1. En las informaciones de público, vaya a **Inteligencia** > **Predicciones**.
1. Seleccione la ventana **Modelo de pérdida de suscripciones (vista previa)** y seleccione **Usar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Ventana Modelo de pérdida de suscripciones con botón Usar este modelo](media/subscription-churn-usethismodel.PNG "Ventana Modelo de pérdida de suscripciones con botón Usar este modelo")

### <a name="name-model"></a>Nombre del modelo

1. Proporcione un nombre para el modelo para distinguirlo de otros modelos.
1. Proporcione un nombre para la entidad de salida utilizando solo letras y números, sin espacios. Ese es el nombre que usará la entidad del modelo. A continuación, seleccione **Siguiente**.

### <a name="define-customer-churn"></a>Definir abandono de clientes

1. Introduzca el número de **Días desde que finalizó la suscripción** que su empresa considera para que un cliente esté en un estado de pérdida. Este período suele equivaler a actividades comerciales como ofertas u otros esfuerzos de marketing que intentan evitar la pérdida del cliente.
1. Ingrese el número de **Días para investigar el futuro para predecir el abandono** para establecer una ventana para predecir el abandono. Por ejemplo, para predecir el riesgo de abandono de sus clientes durante los próximos 90 días para alinearse con sus esfuerzos de retención de marketing. Predecir el riesgo de abandono durante períodos de tiempo más largos o más cortos puede hacer que sean más difícil abordar los factores en el perfil de riesgo de abandono, en función de sus requisitos empresariales específicos. Seleccione **Siguiente** para continuar
   >[!TIP]
   > Puede elegir **Guardar y cerrar** en cualquier momento para guardar la predicción como borrador. Encontrará el borrador de predicción en la pestaña **Mis predicciones** para continuar.

### <a name="add-required-data"></a>Agregar datos necesarios

1. Seleccione **Agregar datos** para **Historial de suscripciones** y elija la entidad que proporciona la información del historial de suscripciones como se describe en los [prerrequisitos](#prerequisites).
1. Si los campos a continuación no se rellenan, configure la relación desde la entidad del historial de suscripciones con la entidad de cliente.
    1. Selecciona la **Entidad de historial de suscripciones**.
    1. Selecciona el **Campo** que identifique al cliente en la entidad del historial de suscripciones. Debe relacionarse con el ID de cliente principal de su entidad Cliente.
    1. Seleccione la **Entidad de cliente** que coincida con su entidad de cliente principal.
    1. Escriba un nombre que describa la relación.
       > [!div class="mx-imgBorder"]
       > ![Página del historial de suscripciones que muestra la creación de una relación con el cliente](media/subscription-churn-subscriptionhistoryrelationship.PNG "Página del historial de suscripciones que muestra la creación de una relación con el cliente")
1. Seleccione **Siguiente**.
1. Asigne los campos semánticos a atributos en la entidad del historial de suscripciones y seleccione **Guardar**. Para obtener descripciones de los campos, eche un vistazo a los [prerrequisitos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Página del historial de suscripciones que muestra los atributos semánticos que se asignan a campos en la entidad del historial de suscripciones seleccionada](media/subscription-churn-subscriptionhistorymapping.PNG "Página del historial de suscripciones que muestra los atributos semánticos que se asignan a campos en la entidad del historial de suscripciones seleccionada")
1. Seleccione **Agregar datos** para **Actividades del cliente** y elija la entidad que proporciona la información de actividad del cliente como se describe en los prerrequisitos.
1. Seleccione un tipo de actividad que coincida con el tipo de actividad del cliente que está configurando.  Seleccione **Crear nuevo** y proporcione un nombre si no ve una opción que coincida con el tipo de actividad que necesita.
1. Deberá configurar la relación desde la entidad de actividad del cliente hasta la entidad de cliente.
    1. Seleccione el campo que identifique al cliente en la tabla de actividades del cliente, que puede estar directamente relacionado con el ID de cliente principal de su entidad de cliente.
    1. Seleccione la entidad de cliente que coincida con su entidad de cliente principal
    1. Escriba un nombre que describa la relación.
1. Seleccione **Siguiente**.
1. Asigne los campos semánticos a atributos en la entidad de actividad de cliente y seleccione **Guardar**. Para obtener descripciones de los campos, eche un vistazo a los [prerrequisitos](#prerequisites).
1. (Opcional) Si tiene otras actividades de clientes que le gustaría incluir, repita los pasos anteriores.
   > [!div class="mx-imgBorder"]
   > ![Definir la relación de entidad](media/subscription-churn-customeractivitiesmapping.PNG "Página de actividades del cliente que muestra los atributos semánticos que se asignan a campos en la entidad de actividad del cliente seleccionada")
1. Seleccione **Siguiente**.

### <a name="set-schedule-and-review-configuration"></a>Establecer programación y revisar la configuración

1. Establezca una frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos en las informaciones de público. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.
1. Seleccione **Siguiente**.
1. Revise la configuración. Puede volver a cualquier parte de la configuración de predicción seleccionando **Editar** debajo del valor mostrado. O puede seleccionar un paso de configuración desde el indicador de progreso.
1. Si todos los valores están configurados correctamente, seleccione **Guardar y ejecutar** para comenzar el proceso de predicción. En la pestaña **Mis predicciones** puede ver el estado de sus predicciones. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

## <a name="review-a-prediction-status-and-results"></a>Revisar un estado y resultados de predicción

1. Vaya a la pestaña **Mis predicciones** en **Inteligencia** > **Predicciones**.
   > [!div class="mx-imgBorder"]
   > ![Vista de la página Mis predicciones](media/subscription-churn-mypredictions.PNG "Vista de la página Mis predicciones")
1. Seleccione la predicción que desea revisar.
   - **Nombre de predicción:** El nombre de la predicción proporcionado al crearla.
   - **Tipo de predicción:** El tipo de modelo utilizado para la predicción
   - **Entidad de salida:** Nombre de la entidad para almacenar la salida de la predicción. Puede encontrar una entidad con este nombre en **Datos** > **Entidades**.    
     En la entidad de salida, *ChurnScore* es la probabilidad pronosticada de abandono y *IsChurn* es una etiqueta binaria basada en *ChurnScore* con umbral de 0,5. Es posible que el umbral predeterminado no funcione para su escenario. [Cree un nuevo segmento](segments.md#create-a-new-segment) con su umbral preferido.
   - **Campo de predicción:** Este campo se completa solo para algunos tipos de predicciones, y no se usa en la predicción de pérdida de suscripciones.
   - **Estado:** el estado actual de la ejecución de la predicción.
        - **En cola:** La predicción está esperando que se ejecuten otros procesos.
        - **Actualizando:** La predicción actualmente está ejecutando la fase de "puntuación" del procesamiento para producir resultados que fluirán a la entidad de salida.
        - **Error:** La predicción ha fallado. Seleccione **Registros** para más detalles.
        - **Correcta:** La predicción ha tenido éxito. Seleccione **Ver** bajo los puntos suspensivos verticales para revisar la predicción
   - **Editada:** La fecha en que se modificó la configuración para la predicción.
   - **Última actualización:** La fecha en que la predicción actualizó los resultados en la entidad de salida.
1. Seleccione los puntos suspensivos verticales junto a la predicción cuyos resultados desea revisar y seleccione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista de opciones en el menú de puntos suspensivos verticales para una predicción que incluye editar, actualizar, ver, registrar y eliminar](media/subscription-churn-verticalellipses.PNG "Vista de opciones en el menú de puntos suspensivos verticales para una predicción que incluye editar, actualizar, ver, registrar y eliminar")
1. Hay tres secciones de datos principales en la página de resultados:
    1. **Rendimiento del modelo de entrenamiento:** A, B o C son puntuaciones posibles. Esta puntuación indica el rendimiento de la predicción y puede ayudarle a tomar la decisión de usar los resultados almacenados en la entidad de salida.
        - Las puntuaciones se determinan según las siguientes reglas:
            - **A** cuando el modelo predijo con precisión al menos el 50% de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es mayor que la tasa de abandono media histórica en al menos el 10% de la tasa de abandono media histórica.
            - **B** cuando el modelo predijo con precisión al menos el 50% de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es hasta un 10% mayor que la tasa de abandono media histórica de la tasa de abandono media histórica.
            - **C** cuando el modelo predijo con precisión menos del 50% de las predicciones totales, o cuando el porcentaje de predicciones precisas para los clientes que abandonaron es menor que la tasa de abandono media histórica.
               > [!div class="mx-imgBorder"]
               > ![Vista del resultado del rendimiento del modelo](media/subscription-churn-modelperformance.PNG "Vista del resultado del rendimiento del modelo")
    1. **Probabilidad de pérdida (número de clientes):** Grupos de clientes según su riesgo de pérdida previsto. Estos datos pueden ayudarle más adelante si desea crear un segmento de clientes con alto riesgo de pérdida. Dichos segmentos ayudan a comprender dónde debe estar el corte para la pertenencia del segmento.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que muestra la distribución de los resultados de pérdida, desglosada en rangos de 0-100%](media/subscription-churn-resultdistribution.PNG "Gráfico que muestra la distribución de los resultados de pérdida, desglosada en rangos de 0-100%")
    1. **Factores más influyentes:** Hay muchos factores que se tienen en cuenta al crear su predicción. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Puede usar estos factores para ayudar a validar sus resultados de predicción. O puede usar esta información más tarde para [crear segmentos](segments.md) que puedan ayudar a influir en el riesgo de pérdida de clientes.
       > [!div class="mx-imgBorder"]
       > ![Lista que muestra los factores influyentes y su importancia para predecir el resultado de pérdida.](media/subscription-churn-influentialfactors.PNG "Lista que muestra los factores influyentes y su importancia para predecir el resultado de pérdida.")

## <a name="manage-predictions"></a>Administrar predicciones

Es posible optimizar, solucionar problemas, actualizar o eliminar predicciones. Revise un informe de usabilidad de datos de entrada para descubrir cómo hacer que un predicción sea más rápido y confiable. Para obtener más información, consulte [Administrar predicciones](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
