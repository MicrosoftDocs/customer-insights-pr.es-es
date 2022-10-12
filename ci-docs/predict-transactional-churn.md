---
title: Predicción de abandono de transacciones (contiene vídeo)
description: Predizca si un cliente está en riesgo de dejar de comprar sus productos o servicios.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610533"
---
# <a name="predict-transaction-churn"></a>Predicir abandono de transacciones

La predicción de abandono transaccional ayuda a predecir si un cliente ya no comprará sus productos o servicios en una ventana de tiempo determinada.

Debe tener conocimiento del negocio para comprender lo que significa la pérdida de suscripciones para su negocio. Admitimos definiciones de abandono basadas en el tiempo, lo que significa que se considera que un cliente ha abandonado después de un período sin compras.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para entornos basados en cuentas comerciales, podemos predecir la pérdida de transacciones de una cuenta y también una combinación de cuenta y otro nivel de información como la categoría de producto. Por ejemplo, agregar una dimensión puede ayudar a detrminar la probabilidad de que la cuenta "Contoso" deje de comprar la categoría de producto "material de oficina". Además, para las cuentas comerciales, también podemos utilizar la inteligencia artificial para generar una lista de posibles razones por las que es probable que una cuenta abandone una categoría de información de nivel secundario.

> [!TIP]
> Pruebe la predicción de abandono de transacciones usando datos de ejemplo: [Guía de ejemplo de predicción de abandono de transacciones](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos [permisos de colaborador](permissions.md).
- Al menos 10 perfiles clientes, preferiblemente más de 1000 clientes únicos.
- Identificador de cliente, un identificador único para hacer coincidir transacciones con sus clientes.
- Datos de transacciones para al menos el doble de la ventana de tiempo seleccionada, como dos o tres años de historial de transacciones. Idealmente, al menos dos transacciones por cliente. El historial de transacciones debe incluir:
  - **Id. de transacción**: identificador único de una compra o transacción.
  - **Fecha de transacción**: fecha de la compra o transacción.
  - **Valor de la transacción**: el importe en moneda/valor numérico de la transacción.
  - **Id. de producto único**: identificador del producto o servicio adquirido si sus datos se encuentran en el nivel de artículo de línea.
  - **Si esta transacción fue una devolución**: un campo de verdadero/falso que identifica si la transacción fue una devolución o no. Si el **Valor de la transacción** es negativo, se inferirá una devolución.
- Datos de actividad del cliente:
  - Identificador de cliente, un identificador único para asignar actividades a sus clientes.
  - **Clave principal**: identificador único de una actividad. Por ejemplo, una visita a un sitio web o un registro de uso que muestre que el cliente probó una muestra de su producto.
  - **Marca de tiempo**: fecha y hora del evento, identificadas mediante la clave principal.
  - **Evento:** el nombre del evento que desea usar. Por ejemplo, un campo llamado "UserAction" en una tienda de comestibles podría ser un cupón utilizado por el cliente.
  - **Detalles:** Información detallada sobre el evento. Por ejemplo, un campo llamado "CouponValue" en una tienda de comestibles podría ser el valor en metálico del cupón.
- Menos del 20 % de los valores que faltan en el campo de datos de la entidad proporcionada

Para cuentas comerciales (B-a-B), agregue datos de clientes alineados con atributos más estáticos para garantizar que el modelo funcione mejor:
- **CustomerID:** identificador único de un cliente.
- **Fecha de creación:** la fecha en que se agregó inicialmente el cliente.
- **Estado o Provincia:** La ubicación del estado o provincia de un cliente.
- **País:** el país de un cliente.
- **Sector:** el tipo de sector de un cliente. Por ejemplo, un campo llamado "Sector" en un tostador de café podría indicar si el cliente era minorista.
- **Clasificación:** la categorización de un cliente para su negocio. Por ejemplo, un campo llamado "ValueSegment" en un tostador de café podría ser el nivel de cliente según el tamaño del cliente.

> [!NOTE]
> Para una empresa con una alta frecuencia de compra de los clientes (cada pocas semanas), se recomienda seleccionar una ventana predicción más corta y una definición de abandono. Para una frecuencia de compra baja (cada pocos meses o una vez al año), elija una ventana predicción más larga y una definición de abandono.

## <a name="create-a-transaction-churn-prediction"></a>Crear una predicción de abandono de transacciones

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Modelo de abandono de clientes**.

1. Seleccione **Transacción** para el tipo de abandono y luego **Empezar**.

1. Asigne un nombre a **este modelo** y a la **entidad de salida** para distinguirlos de otros modelos o entidades.

1. Seleccione **Siguiente**.

### <a name="define-customer-churn"></a>Definir abandono de clientes

Seleccione **Guardar borrador** en cualquier momento para guardar la predicción como borrador. La predicción de borrador se muestra en la pestaña **Mis predicciones**.

1. Establecer la **Ventana de predicción**. Por ejemplo, predizca el riesgo de abandono de sus clientes durante los próximos 90 días para alinearse con sus esfuerzos de retención de marketing. Predecir el riesgo de abandono durante un período de tiempo más largo o más corto puede hacer que sea más difícil abordar los factores en su perfil de riesgo de abandono, pero depende de sus requisitos comerciales específicos.

1. Introduzca el número de días para definir el abandono en el campo **Definición de abandono**. Por ejemplo, si un cliente no ha realizado una compra en los últimos 30 días, es posible que considere que se ha agotado para su negocio.

1. Seleccione **Siguiente**.

### <a name="add-purchase-history"></a>Agregar historial de compras

1. Seleccione **Agregar datos** para **Historial de transacciones de cliente**.

1. Seleccione el tipo de actividad semántica, **Órdenes de venta** o **Línea de pedido de ventas**, que contiene la información del historial de transacciones. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron semánticamente cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo semántico, seleccione **Editar** y mapee sus datos.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panel lateral que muestra la elección de actividades específicas de tipo semántico.":::

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Añade más actividades o selecciona **Siguiente**.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Agregar datos adicionales (opcional)

1. Seleccione **Agregar datos** para **Actividades del cliente**.

1. Seleccione el tipo de actividad semántico que contiene los datos que le gustaría usar. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron semánticamente cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo semántico, seleccione **Editar** y mapee sus datos.

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleccione el nivel de predicción

La mayoría de las predicciones se crean a nivel de cliente. En algunas situaciones, es posible que eso no sea lo suficientemente detallado para satisfacer sus necesidades comerciales. Use esta función para predecir el abandono de una sucursal de un cliente, por ejemplo, en lugar de para el cliente en su conjunto.

1. Seleccione **Seleccionar entidad para un nivel secundario**. Si la opción no está disponible, asegúrese de haber completado la sección anterior.

1. Expanda las entidades de las que le gustaría elegir el nivel secundario, o use el cuadro de filtro de búsqueda para filtrar las opciones seleccionadas.

1. Elija el atributo que le gustaría usar como nivel secundario, luego seleccione **Agregar**.

1. Seleccione **Siguiente**.

> [!NOTE]
> Las entidades disponibles en esta sección se muestran porque tienen una relación con la entidad que eligió en la sección anterior. Si no ve la entidad que desea agregar, asegúrese de que tenga una relación válida presente en **Relaciones**. Para esta configuración solo son válidas las relaciones de varios a uno y de uno a uno.

### <a name="add-additional-data-optional"></a>Agregar datos adicionales (opcional)

1. Seleccione **Agregar datos** para **Actividades del cliente**.

1. Seleccione el tipo de actividad semántico que contiene los datos que le gustaría usar. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron semánticamente cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo semántico, seleccione **Editar** y mapee sus datos.

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**

1. Opcionalmente, seleccione **Agregar datos** para **Datos de clientes**.

1. Asigne los atributos semánticos a campos de sus propios datos de clientes identificados. Los datos de los campos utilizados no deben cambiar con frecuencia para garantizar el rendimiento óptimo del modelo. Por ejemplo, si seleccionara un campo para "Clasificación" que cambiara cada mes, solo tendría el último valor usado en la predicción, aunque históricamente el mismo valor podría no aplicarse al cliente al crear los patrones predicción.

1. Seleccione **Siguiente**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Proporcione una lista opcional de cuentas de referencia

Agregue una lista de sus clientes y cuentas comerciales que desea utilizar como puntos de referencia. Los [detalles de estas cuentas de referencia](#view-prediction-results) incluyen su puntuación de abandono y las características más influyentes que afectaron a su predicción de abandono.

1. Seleccione **+ Agregar clientes**.

1. Elija los clientes que actúen como referencia.

1. Seleccione **Siguiente**.

---

### <a name="set-update-schedule"></a>Definir la programación de actualizaciones

1. Para el paso **Actualizaciones de datos**, elija una frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos en Customer Insights. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

### <a name="review-and-run-the-model-configuration"></a>Revisar y ejecutar la configuración del modelo

El paso **Revisar y ejecutar** muestra un resumen de la configuración y brinda la oportunidad de realizar cambios antes de crear el predicción.

1. Seleccione **Editar** en cualquiera de los pasos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Guardar y ejecutar** para comenzar a ejecutar el modelo. Seleccione **Listo**. La pestaña **Mis predicciones** se muestra mientras se crea predicción. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver los resultados de la predicción

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Mis predicciones**, seleccione la predicción que desea ver.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

Hay tres secciones de datos principales en la página de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

Hay tres secciones de datos principales en la página de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Una página de información **Análisis de características influyentes** contiene cuatro secciones de datos:

- En el panel derecho, seleccione un elemento de **Clientes destacados** o **Clientes de referencia**. Ambas listas están ordenadas por valor decreciente de la puntuación de abandono, ya sea que la puntuación sea solo para el cliente o una puntuación combinada para los clientes y un nivel secundario como la categoría de producto. El elemento seleccionado determina el contenido de esta página.

  - **Clientes destacados**: Lista de 10 clientes que tienen el mayor riesgo de abandono y el menor riesgo de abandono según sus puntuaciones de abandono.
  - **Clientes de referencia**: Lista de hasta 10 clientes que fueron seleccionados al configurar el modelo.

- **Puntuación de abandono:** Muestra la puntuación de abandono del elemento seleccionado en el panel derecho.

- **Distribución del riesgo de abandono:** Muestra la distribución del riesgo de abandono entre los clientes y el percentil en el que se encuentra el cliente seleccionado.

- **Principales características que aumentan y disminuyen el riesgo de abandono:** muestra las cinco características principales que aumentaron y disminuyeron el riesgo de abandono para el elemento seleccionado en el panel derecho. Muestra el valor de la característica para ese elemento y su influencia en la puntuación de abandono para cada característica que influye. También se muestra el valor promedio de cada función en los segmentos de clientes de bajo, medio y alto riesgo de abandono. Ayuda a contextualizar mejor los valores de las características más influyentes para el artículo seleccionado y compararlo con los segmentos de clientes de bajo, medio y alto riesgo de abandono.

  - Bajo: cuentas o combinaciones de cuenta y nivel secundario con una puntuación de abandono entre 0 y 0,33.
  - Medio: cuentas o combinaciones de cuentas y niveles secundarios con una puntuación de abandono entre 0,33 y 0,66.
  - Alto: cuentas o combinaciones de cuentas y niveles secundarios con una puntuación de abandono mayor que 0,66.

  Cuando predice el abandono a nivel de cuenta, todas las cuentas se tienen en consideración al calcular los valores promedio de las funciones para los segmentos de abandono. Para predicciones de abandono en el nivel secundario para cada cuenta, el cálculo de los segmentos de abandono depende del nivel secundario del elemento seleccionado en el panel lateral. Por ejemplo, si un artículo tiene un nivel secundario de categoría de producto (material de oficina), solo se considerarán los artículos que tengan material de oficina como categoría de producto al calcular los valores de característica promedio para los segmentos de abandono. Esta lógica se aplica para garantizar una comparación justa de los valores de característica del artículo con los valores promedio en los segmentos de bajo, medio y alto riesgo de abandono.

  En algunos casos, el valor medio de los segmentos de bajo, medio o alto riesgo de abandono está vacío o no está disponible porque no hay elementos que pertenezcan a los segmentos de abandono correspondientes según la definición anterior.

  La interpretación de los valores en las columnas promedio bajo, medio y alto es diferente para características categóricas como región o industria. Debido a que la noción de valor de característica "promedio" no se aplica a las características categóricas, los valores en estas columnas son la proporción de clientes en los segmentos de abandono alto, medio o bajo que tienen el mismo valor de la característica categórica en comparación con el elemento. seleccionado en el panel lateral.

---

 > [!NOTE]
 > En la entidad de salida para este modelo, *ChurnScore* muestra la probabilidad pronosticada de abandono y *IsChurn* es una etiqueta binaria basada en *ChurnScore* con umbral de 0,5. Si este umbral predeterminado no funciona para su escenario, [cree un nuevo segmento](segments.md#create-a-segment) con su umbral preferido. No todos los clientes son necesariamente clientes activos. Es posible que algunos de ellos no hayan tenido ninguna actividad durante mucho tiempo y ya se considera que han abandonado, según su definición de abandono. Predecir el riesgo de abandono de los clientes que ya han abandonado no es útil porque no son el público de interés.
>
> Para ver la puntuación de abandono, vaya a **Datos** > **Entidades** y vea la pestaña de datos para la entidad de salida que definió para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
