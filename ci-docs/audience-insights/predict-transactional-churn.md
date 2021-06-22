---
title: Predicción de abandono transaccional
description: Predizca si un cliente está en riesgo de dejar de comprar sus productos o servicios.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0e587739f9f4d03942d70a72de4f9378822054d
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095623"
---
# <a name="transactional-churn-prediction-preview"></a>Predicción de abandono transaccional (versión preliminar)

La predicción de abandono transaccional ayuda a predecir si un cliente ya no comprará sus productos o servicios en una ventana de tiempo determinada. Puede crear nuevas predicciones de abandono en **Inteligencia** > **Predicciones**. Seleccione **Mis predicciones** para ver otras predicciones que ha creado.

> [!TIP]
> Pruebe el tutorial para una predicción de abandono transaccional con datos de ejemplo: [Guía de ejemplo (versión preliminar) de predicción de abandono transaccional](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Conocimiento del negocio para comprender lo que significa la pérdida de suscripciones para su negocio. Admitimos definiciones de abandono basadas en el tiempo, lo que significa que se considera que un cliente ha abandonado después de un período sin compras.
- Datos sobre sus transacciones/compras y su historial:
    - Identificadores de transacciones para distinguir compras/transacciones.
    - Identificadores de clientes para hacer coincidir las transacciones con sus clientes.
    - Fechas de eventos de transacción, que definen las fechas en las que ocurrió la transacción.
    - El esquema de datos semánticos para compras/transacciones requiere la siguiente información:
        - **Id. de transacción:** un identificador único de una compra o transacción.
        - **Fecha de Transacción:** la fecha de la compra o transacción.
        - **Valor de la transacción:** el importe en moneda/valor numérico de la transacción o el artículo.
        - (Opcional) **Id. de producto único:** el id. del producto o servicio adquirido si sus datos se encuentran en el nivel de artículo de línea.
        - (Opcional) **Si esta transacción fue una devolución:** un campo de verdadero/falso que identifica si la transacción fue una devolución o no. Si el **Valor de la transacción** es negativo, también usaremos esta información para inferir una devolución.
- (Opcional) Datos sobre las actividades del cliente:
    - Identificadores de actividad para distinguir actividades del mismo tipo.
    - Identificadores de clientes para asignar actividades a sus clientes.
    - Información de actividad que contiene el nombre y la fecha de la actividad.
    - El esquema de datos semánticos para actividades del cliente incluye:
        - **Clave principal:** Un identificador único para una actividad. Por ejemplo, una visita a un sitio web o un registro de uso que muestre que el cliente probó una muestra de su producto.
        - **Marca de tiempo:** La fecha y hora del evento identificado por la clave principal.
        - **Evento:** El nombre del evento que desea usar. Por ejemplo, un campo llamado "UserAction" en una tienda de comestibles podría ser un cupón utilizado por el cliente.
        - **Detalles:** Información detallada sobre el evento. Por ejemplo, un campo llamado "CouponValue" en una tienda de comestibles podría ser el valor en metálico del cupón.
- Características de los datos sugeridos
    - Datos históricos suficientes: datos de transacciones de al menos el doble del período tiempo seleccionado. Preferiblemente, dos o tres años de datos de suscripciones. 
    - Varias compras por cliente: lo idóneo es que sean al menos dos transacciones por cliente.
    - Número de clientes: al menos 10 perfiles clientes, preferiblemente más de 1000 clientes únicos. El modelo no funcionará con menos de 10 clientes y datos históricos insuficientes.
    - Integridad de los datos: menos del 20 % de los valores que faltan en el campo de datos de la entidad proporcionada.

> [!NOTE]
> Para una empresa con una alta frecuencia de compra de los clientes (cada pocas semanas), se recomienda seleccionar una ventana predicción más corta y una definición de abandono. Para una frecuencia de compra baja (cada pocos meses o una vez al año), elija una ventana predicción más larga y una definición de abandono.

## <a name="create-a-transactional-churn-prediction"></a>Crear una predicción de abandono transaccional

1. En Customer Insights, vaya a **Inteligencia** > **Predicciones**.

1. Seleccione el mosaico **Modelo de abandono de clientes (versión preliminar)** y seleccione **Utilizar este modelo**.
   
1. En el panel **Modelo de abandono de clientes**, elija **Transaccional** y seleccione **Comenzar**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de pantalla con la opción transaccional seleccionada en el panel Modelo de abandono del cliente.":::

### <a name="name-model"></a>Modelo de nombre

1. Proporcione un nombre para el modelo para distinguirlo de otros modelos.

1. Proporcione un nombre para la entidad de salida utilizando solo letras y números, sin espacios. Ese es el nombre que usará la entidad del modelo. 

1. Seleccione **Siguiente**.

### <a name="define-customer-churn"></a>Definir abandono de clientes

1. Establezca una ventana de días para predecir el abandono en el campo **Identificar los clientes que pueden abandonar a la siguiente**. Por ejemplo, predizca el riesgo de abandono de sus clientes durante los próximos 90 días para alinearse con sus esfuerzos de retención de marketing. Predecir el riesgo de abandono durante un período de tiempo más largo o más corto puede hacer que sea más difícil abordar los factores en su perfil de riesgo de abandono, pero depende de sus requisitos comerciales específicos. 
   >[!TIP]
   > Puede elegir **Guardar y cerrar** en cualquier momento para guardar la predicción como borrador. Encontrará el borrador de predicción en la pestaña **Mis predicciones** para continuar.

1. Introduzca el número de días para definir el abandono en el campo **Un cliente ha abandonado si no ha realizado compras en:**. Por ejemplo, si un cliente no ha realizado compras en los últimos 30 días, es posible que considere que se ha agotado para su negocio. 

1. Seleccione **Siguiente** para continuar

### <a name="add-required-data"></a>Agregar datos necesarios

1. Seleccione **Agregar datos** para **Historial de compras** y elija la entidad que proporciona la información del historial de transacciones/compras, como se describe en los [prerrequisitos](#prerequisites).

1. Asigne los campos semánticos a los atributos dentro de su entidad de historial de compras y seleccione **Siguiente**. Para obtener descripciones de los campos, eche un vistazo a los [prerrequisitos](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapear campos semánticos de la entidad de compra.":::

1. Si los campos a continuación no están rellenos, configure la relación entre su entidad de historial de compras y la entidad de cliente.
    1. Seleccione la **Entidad de historial de compras**.
    1. Seleccione el **Campo** que identifica al cliente en la entidad de historial de compras. Debe relacionarse con el ID de cliente principal de su entidad Cliente.
    1. Seleccione la **Entidad de cliente** que coincida con su entidad de cliente principal.
    1. Escriba un nombre que describa la relación.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Página del historial de compras que muestra la creación de una relación con el cliente.":::
   
1. Seleccione **Siguiente**.

1. Opcionalmente, seleccione **Agregar datos** para **Actividades del cliente**. Elija la entidad que proporciona la información de actividad del cliente como se describe en los requisitos previos.

1. Asigne los campos semánticos a los atributos dentro de su entidad de actividad del cliente y seleccione **Siguiente**. Para obtener descripciones de los campos, eche un vistazo a los [prerrequisitos](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Asignar campos de clientes para datos transaccionales.":::

1. Seleccione un tipo de actividad que coincida con el tipo de actividad del cliente que está configurando. Seleccione **Crear nuevo** y elija un tipo de actividad disponible o cree un nuevo tipo.

1. Deberá configurar la relación desde la entidad de actividad del cliente hasta la entidad de cliente.
    1. Seleccione el campo que identifica al cliente en la tabla de actividad de compras. Puede estar directamente relacionado con el id. de cliente principal de su entidad de cliente.
    1. Seleccione la entidad de cliente que coincida con su entidad de cliente principal
    1. Escriba un nombre que describa la relación.

1. Seleccione **Guardar**.

1. Si tiene otras actividades de clientes que le gustaría incluir, repita los pasos anteriores.

1. Seleccione **Siguiente**.

### <a name="set-schedule-and-review-configuration"></a>Establecer programación y revisar la configuración

1. Establezca una frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

1. Revise la configuración de la predicción. Puede volver a los pasos anteriores seleccionando **Editar** en el valor mostrado. O puede seleccionar un paso de configuración desde el indicador de progreso.

1. Si todos los valores están configurados correctamente, seleccione **Guardar y ejecutar** para comenzar el proceso de predicción. En la pestaña **Mis predicciones** puede ver el estado de sus predicciones. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

## <a name="review-a-prediction-status-and-results"></a>Revisar un estado y resultados de predicción

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.

1. Seleccione la predicción que desea revisar.
   - **Nombre de predicción:** nombre de la predicción proporcionada al crearlo.
   - **Tipo de predicción:** tipo de modelo utilizado para la predicción
   - **Entidad de salida:** Nombre de la entidad para almacenar la salida de la predicción. Puede encontrar una entidad con este nombre en **Datos** > **Entidades**.    
     En la entidad de salida, *ChurnScore* es la probabilidad pronosticada de abandono y *IsChurn* es una etiqueta binaria basada en *ChurnScore* con umbral de 0,5. Es posible que el umbral predeterminado no funcione para su escenario. [Cree un nuevo segmento](segments.md#create-a-new-segment) con su umbral preferido.
     No todos los clientes son necesariamente clientes activos. Es posible que algunos de ellos no hayan tenido ninguna actividad durante mucho tiempo y ya se considera que han abandonado, según su definición de abandono. Predecir el riesgo de abandono de los clientes que ya han abandonado no es útil porque no son una audiencia de interés.
   - **Campo previsto:** este campo se rellena solo para algunos tipos de predicciones y no se usa en la predicción de abandono.
   - **Estado:** estado de la ejecución de la predicción.
        - **Puesto en cola:** la predicción está esperando a que se ejecuten otros procesos.
        - **Actualización:** la predicción se está ejecutando actualmente para producir resultados que fluirán hacia la entidad de salida.
        - **Errores:** la ejecución de la predicción ha presentado errores. [Revise los registros](manage-predictions.md#troubleshoot-a-failed-prediction) para más detalles.
        - **Correcta:** la predicción ha tenido éxito. Seleccione **Ver** bajo los puntos suspensivos verticales para revisar la predicción
   - **Editada:** La fecha en que se modificó la configuración para la predicción.
   - **Última actualización:** La fecha en que la predicción actualizó los resultados en la entidad de salida.

1. Seleccione los puntos suspensivos verticales junto a la predicción cuyos resultados desea revisar y seleccione **Ver**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vea el control para ver los resultados de una predicción.":::   

1. Hay tres secciones de datos principales en la página de resultados:
    1. **Rendimiento del modelo de entrenamiento:** A, B o C son puntuaciones posibles. Esta puntuación indica el rendimiento de la predicción y puede ayudarle a tomar la decisión de usar los resultados almacenados en la entidad de salida. Las puntuaciones se determinan según las siguientes reglas:
         
         - **A** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es mayor que la tasa de referencia en al menos un 10 %.
            
         - **B** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es hasta un 10 % mayor que la referencia.
            
         - **C** cuando el modelo predijo con precisión menos del 50 % de las predicciones totales, o cuando el porcentaje de predicciones precisas para los clientes que abandonaron es inferior a la referencia.
               
         - **Referencia** toma la entrada de ventana de tiempo predicción para el modelo (por ejemplo, un año) y el modelo crea diferentes fracciones de tiempo dividiendo por 2 hasta que llega a un mes o menos. Utiliza estas fracciones para crear una regla de negocio para los clientes que no han comprado en este plazo de tiempo. Estos clientes se consideran abandonados. La regla de negocio basada en el tiempo con la mayor capacidad para predecir quién es probable que abandone se elige como modelo de referencia.
            
    1. **Probabilidad de pérdida (número de clientes):** Grupos de clientes según su riesgo de pérdida previsto. Estos datos pueden ayudarle más adelante si desea crear un segmento de clientes con alto riesgo de pérdida. Dichos segmentos ayudan a comprender dónde debe estar el corte para la pertenencia del segmento.
       
    1. **Factores más influyentes:** Hay muchos factores que se tienen en cuenta al crear su predicción. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Puede usar estos factores para ayudar a validar sus resultados de predicción. O puede usar esta información más tarde para [crear segmentos](segments.md) que puedan ayudar a influir en el riesgo de pérdida de clientes.

## <a name="manage-predictions"></a>Administrar predicciones

Es posible optimizar, solucionar problemas, actualizar o eliminar predicciones. Revise un informe de usabilidad de datos de entrada para descubrir cómo hacer que un predicción sea más rápido y confiable. Para obtener más información, consulte [Administrar predicciones](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
