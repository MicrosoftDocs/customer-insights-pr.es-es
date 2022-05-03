---
title: Predicción de abandono de transacciones (contiene vídeo)
description: Predizca si un cliente está en riesgo de dejar de comprar sus productos o servicios.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e55ca8c6926fa0bda05aaf52fd799ca25f7f585f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648019"
---
# <a name="transaction-churn-prediction"></a>Predicción de abandono de transacciones

La predicción de abandono transaccional ayuda a predecir si un cliente ya no comprará sus productos o servicios en una ventana de tiempo determinada. Puede crear nuevas predicciones de abandono en **Inteligencia** > **Predicciones**. Seleccione **Mis predicciones** para ver otras predicciones que ha creado. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para entornos basados en cuentas comerciales, podemos predecir la pérdida de transacciones de una cuenta y también una combinación de cuenta y otro nivel de información como la categoría de producto. Agregar una dimensión puede ayudar a averiguar la probabilidad de que la cuenta "Contoso" deje de comprar la categoría de producto "material de oficina". Además, para las cuentas comerciales, también podemos utilizar la inteligencia artificial para generar una lista de posibles razones por las que es probable que una cuenta abandone una categoría de información de nivel secundario.

> [!TIP]
> Pruebe el tutorial para una predicción de abandono de transacciones usando datos de ejemplo: [Guía de ejemplo de predicción de abandono de transacciones](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisitos previos

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Conocimiento del negocio para comprender lo que significa la pérdida de suscripciones para su negocio. Admitimos definiciones de abandono basadas en el tiempo, lo que significa que se considera que un cliente ha abandonado después de un período sin compras.
- Datos sobre sus transacciones/compras y su historial:
    - Identificadores de transacciones para distinguir compras/transacciones.
    - Identificadores de clientes para hacer coincidir las transacciones con sus clientes.
    - Fechas de eventos de transacción, que definen las fechas en las que ocurrió la transacción.
    - El esquema de datos semánticos para compras/transacciones requiere la siguiente información:
        - **Id. de transacción**: un identificador único de una compra o transacción.
        - **Fecha de transacción**: la fecha de la compra o transacción.
        - **Valor de la transacción**: el importe en moneda/valor numérico de la transacción o el artículo.
        - (Opcional) **Id. de producto único**: el id. del producto o servicio adquirido si sus datos se encuentran en el nivel de artículo de línea.
        - (Opcional) **Si esta transacción fue una devolución**: un campo de verdadero/falso que identifica si la transacción fue una devolución o no. Si el **Valor de la transacción** es negativo, también usaremos esta información para inferir una devolución.
- (Opcional) Datos sobre las actividades del cliente:
    - Identificadores de actividad para distinguir actividades del mismo tipo.
    - Identificadores de clientes para asignar actividades a sus clientes.
    - Información de actividad que contiene el nombre y la fecha de la actividad.
    - El esquema de datos semánticos para actividades del cliente incluye:
        - **Clave principal:** Un identificador único para una actividad. Por ejemplo, una visita a un sitio web o un registro de uso que muestre que el cliente probó una muestra de su producto.
        - **Marca de tiempo:** La fecha y hora del evento identificado por la clave principal.
        - **Evento:** El nombre del evento que desea usar. Por ejemplo, un campo llamado "UserAction" en una tienda de comestibles podría ser un cupón utilizado por el cliente.
        - **Detalles:** Información detallada sobre el evento. Por ejemplo, un campo llamado "CouponValue" en una tienda de comestibles podría ser el valor en metálico del cupón.

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Conocimiento del negocio para comprender lo que significa la pérdida de suscripciones para su negocio. Admitimos definiciones de abandono basadas en el tiempo, lo que significa que se considera que un cliente ha abandonado después de un período sin compras.
- Datos sobre sus transacciones/compras y su historial:
    - Identificadores de transacciones para distinguir compras/transacciones.
    - Identificadores de clientes para hacer coincidir las transacciones con sus clientes.
    - Fechas de eventos de transacción, que definen las fechas en las que ocurrió la transacción.
    - El esquema de datos semánticos para compras/transacciones requiere la siguiente información:
        - **Id. de transacción**: un identificador único de una compra o transacción.
        - **Fecha de transacción**: la fecha de la compra o transacción.
        - **Valor de la transacción**: el importe en moneda/valor numérico de la transacción o el artículo.
        - (Opcional) **Id. de producto único**: el id. del producto o servicio adquirido si sus datos se encuentran en el nivel de artículo de línea.
        - (Opcional) **Si esta transacción fue una devolución**: un campo de verdadero/falso que identifica si la transacción fue una devolución o no. Si el **Valor de la transacción** es negativo, también usaremos esta información para inferir una devolución.
- (Opcional) Datos sobre las actividades del cliente:
    - Identificadores de actividad para distinguir actividades del mismo tipo.
    - Identificadores de clientes para asignar actividades a sus clientes.
    - Información de actividad que contiene el nombre y la fecha de la actividad.
    - El esquema de datos semánticos para actividades del cliente incluye:
        - **Clave principal:** Un identificador único para una actividad. Por ejemplo, una visita a un sitio web o un registro de uso que muestre que el cliente probó una muestra de su producto.
        - **Marca de tiempo:** La fecha y hora del evento identificado por la clave principal.
        - **Evento:** El nombre del evento que desea usar. Por ejemplo, un campo llamado "UserAction" en una tienda de comestibles podría ser un cupón utilizado por el cliente.
        - **Detalles:** Información detallada sobre el evento. Por ejemplo, un campo llamado "CouponValue" en una tienda de comestibles podría ser el valor en metálico del cupón.
- (Opcional) Datos sobre sus clientes:
    - Estos datos deben alinearse con atributos más estáticos para garantizar que el modelo funcione mejor.
    - El esquema de datos semánticos para los datos del cliente incluye:
        - **CustomerID:** identificador único de un cliente.
        - **Fecha de creación:** la fecha en que se agregó inicialmente el cliente.
        - **Estado o Provincia:** La ubicación del estado o provincia de un cliente.
        - **País:** el país de un cliente.
        - **Sector:** el tipo de sector de un cliente. Por ejemplo, un campo llamado "Sector" en un tostador de café podría indicar si el cliente era minorista.
        - **Clasificación:** la categorización de un cliente para su negocio. Por ejemplo, un campo llamado "ValueSegment" en un tostador de café podría ser el nivel de cliente según el tamaño del cliente.

---

- Características de los datos sugeridos
    - Datos históricos suficientes: datos de transacciones de al menos el doble del período tiempo seleccionado. Preferiblemente, dos o tres años de historial de transacciones. 
    - Varias compras por cliente: lo idóneo es que sean al menos dos transacciones por cliente.
    - Número de clientes: al menos 10 perfiles clientes, preferiblemente más de 1000 clientes únicos. El modelo no funcionará con menos de 10 clientes y datos históricos insuficientes.
    - Integridad de los datos: menos del 20 % de los valores que faltan en el campo de datos de la entidad proporcionada.

> [!NOTE]
> Para una empresa con una alta frecuencia de compra de los clientes (cada pocas semanas), se recomienda seleccionar una ventana predicción más corta y una definición de abandono. Para una frecuencia de compra baja (cada pocos meses o una vez al año), elija una ventana predicción más larga y una definición de abandono.

## <a name="create-a-transaction-churn-prediction"></a>Crear una predicción de abandono de transacciones

1. En Customer Insights, vaya a **Inteligencia** > **Predicciones**.

1. Seleccione la ventana **Modelo de abandono de clientes** y seleccione **Usar este modelo**.

1. En el panel **Modelo de abandono de clientes**, elija **Transacción** y seleccione **Comenzar**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de pantalla con la opción de transacción seleccionada en el panel Modelo de abandono de clientes.":::
 
### <a name="name-model"></a>Modelo de nombre

1. Proporcione un nombre para el modelo para distinguirlo de otros modelos.

1. Proporcione un nombre para la entidad de salida utilizando solo letras y números, sin espacios. Ese es el nombre que usará la entidad del modelo. 

1. Seleccione **Siguiente**.

### <a name="define-customer-churn"></a>Definir abandono de clientes

1. Establecer la **Ventana de predicción**. Por ejemplo, predizca el riesgo de abandono de sus clientes durante los próximos 90 días para alinearse con sus esfuerzos de retención de marketing. Predecir el riesgo de abandono durante un período de tiempo más largo o más corto puede hacer que sea más difícil abordar los factores en su perfil de riesgo de abandono, pero depende de sus requisitos comerciales específicos.
   >[!TIP]
   > Puedes elegir **Guardar borrador** en cualquier momento para guardar la predicción como borrador. Encontrará el borrador de predicción en la pestaña **Mis predicciones** para continuar.

1. Introduzca el número de días para definir el abandono en el campo **Definición de abandono**. Por ejemplo, si un cliente no ha realizado compras en los últimos 30 días, es posible que considere que se ha agotado para su negocio. 

1. Seleccione **Siguiente** para continuar.

### <a name="add-required-data"></a>Agregar datos necesarios

1. Seleccione **Agregar datos** y elija el tipo de actividad en el panel lateral que contiene la transacción requerida o la información del historial de compras.

1. En **Seleccionar actividades**, elija las actividades específicas del tipo de actividad seleccionado en las que desea que se centre el cálculo.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panel lateral que muestra la elección de actividades específicas de tipo semántico.":::

   Si aún no ha asignado la actividad a un tipo semántico, seleccione **Editar** para hacerlo. Se abre la experiencia guiada para mapear actividades semánticas. Mapee los datos a los campos correspondientes del tipo de actividad seleccionado.

1. Asigne los atributos semánticos a los campos necesarios para ejecutar el modelo. Si los campos a continuación no están rellenos, configure la relación entre su entidad de historial de compras y la entidad *Cliente*. Seleccione **Guardar**.

1. En el paso **Agregar datos requeridos**, seleccione **Siguiente** para continuar si no desea agregar más actividades.


# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Agregar datos adicionales (opcional)

Configure la relación en la entidad de actividad de cliente para la entidad *Cliente*.

1. Seleccione el campo que identifica al cliente en la tabla de actividad de compras. Puede estar directamente relacionado con el identificador de cliente principal de su entidad de *Cliente*.

1. Seleccione la entidad que es su principal entidad *Cliente*.

1. Escriba un nombre que describa la relación.

#### <a name="customer-activities"></a>Actividades del cliente

1. Opcionalmente, seleccione **Agregar datos** para **Actividades del cliente**.

1. Seleccione el tipo de actividad semántica que contiene los datos que le gustaría usar, luego seleccione una o más actividades en la sección **Actividades**.

1. Seleccione un tipo de actividad que coincida con el tipo de actividad del cliente que está configurando. Seleccione **Crear nuevo** y elija un tipo de actividad disponible o cree un nuevo tipo.

1. Seleccione **Siguiente** y, a continuación, **Guardar**.

1. Si tiene otras actividades de clientes que le gustaría incluir, repita los pasos anteriores.

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleccione el nivel de predicción

La mayoría de las predicciones se crean a nivel de cliente. En algunas situaciones, es posible que eso no sea lo suficientemente detallado para satisfacer sus necesidades comerciales. Puede utilizar esta función para predecir el abandono de una sucursal de un cliente, por ejemplo, en lugar de para el cliente en su conjunto.

1. Para crear un predicción a un nivel más detallado que el del cliente, seleccione **Seleccionar entidad para un nivel secundario**. Si la opción no está disponible, asegúrese de haber completado la sección anterior.

1. Expanda las entidades de las que le gustaría elegir el nivel secundario, o use el cuadro de filtro de búsqueda para filtrar las opciones seleccionadas.

1. Elija el atributo que le gustaría usar como nivel secundario, luego seleccione **Agregar**.

1. Seleccione **Siguiente**.

> [!NOTE]
> Las entidades disponibles en esta sección se muestran porque tienen una relación con la entidad que eligió en la sección anterior. Si no ve la entidad que desea agregar, asegúrese de que tenga una relación válida presente en **Relaciones**. Para esta configuración solo son válidas las relaciones de varios a uno y de uno a uno.

### <a name="add-additional-data-optional"></a>Agregar datos adicionales (opcional)

Configure la relación en la entidad de actividad de cliente para la entidad *Cliente*.

1. Seleccione el campo que identifica al cliente en la tabla de actividad de compras. Puede estar directamente relacionado con el identificador de cliente principal de su entidad de *Cliente*.

1. Seleccione la entidad que es su principal entidad *Cliente*.

1. Escriba un nombre que describa la relación.

#### <a name="customer-activities"></a>Actividades del cliente

1. Opcionalmente, seleccione **Agregar datos** para **Actividades del cliente**.

1. Seleccione el tipo de actividad semántica que contiene los datos que le gustaría usar, luego seleccione una o más actividades en la sección **Actividades**.

1. Seleccione un tipo de actividad que coincida con el tipo de actividad del cliente que está configurando. Seleccione **Crear nuevo** y elija un tipo de actividad disponible o cree un nuevo tipo.

1. Seleccione **Siguiente** y, a continuación, **Guardar**.

1. Si tiene otras actividades de clientes que le gustaría incluir, repita los pasos anteriores.

#### <a name="customers-data"></a>Datos de clientes

1. Opcionalmente, seleccione **Agregar datos** para **Datos de clientes**.

1. Asigne los atributos semánticos a campos de sus propios datos de clientes identificados. Los datos de los campos utilizados no deben cambiar con frecuencia para garantizar el rendimiento óptimo del modelo. Por ejemplo, si seleccionara un campo para "Clasificación" que cambiara cada mes, solo tendría el último valor usado en la predicción, aunque históricamente el mismo valor podría no aplicarse al cliente al crear los patrones predicción.

1. Seleccione **Siguiente**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Proporcione una lista opcional de cuentas de referencia

Agregue una lista de sus clientes y cuentas comerciales que desea utilizar como puntos de referencia. Obtendrá [detalles de estas cuentas de referencia](#review-a-prediction-status-and-results) incluida su puntuación de abandono y las características más influyentes que afectaron a su predicción de abandono.

1. Seleccione **+ Agregar clientes**.

1. Elija los clientes que actúen como referencia.

1. Seleccione **Siguiente** para continuar.

---

### <a name="set-schedule-and-review-configuration"></a>Establecer la programación y revisar la configuración

1. Establezca una frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

1. Revise la configuración de la predicción. Puede volver a los pasos anteriores seleccionando **Editar** en el valor mostrado. O puede seleccionar un paso de configuración desde el indicador de progreso.

1. Si todos los valores están configurados correctamente, seleccione **Guardar y ejecutar** para comenzar el proceso de predicción. En la pestaña **Mis predicciones** puede ver el estado de sus predicciones. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

## <a name="review-a-prediction-status-and-results"></a>Revisar un estado y resultados de predicción

1. Vaya a **Inteligencia** > **Predicciones** y seleccione la pestaña **Mis predicciones**.

1. Seleccione la predicción que desea revisar.
   - **Nombre de predicción**: nombre de la predicción proporcionada al crearlo.
   - **Tipo de predicción**: tipo de modelo utilizado para la predicción
   - **Entidad de salida**: nombre de la entidad para guardar la salida de la predicción. Puede encontrar una entidad con este nombre en **Datos** > **Entidades**.
     En la entidad de salida, *ChurnScore* es la probabilidad pronosticada de abandono y *IsChurn* es una etiqueta binaria basada en *ChurnScore* con umbral de 0,5. Es posible que el umbral predeterminado no funcione para su escenario. [Cree un nuevo segmento](segments.md#create-a-new-segment) con su umbral preferido.
     No todos los clientes son necesariamente clientes activos. Es posible que algunos de ellos no hayan tenido ninguna actividad durante mucho tiempo y ya se considera que han abandonado, según su definición de abandono. Predecir el riesgo de abandono de los clientes que ya han abandonado no es útil porque no son el público de interés.
   - **Campo previsto**: este campo se rellena solo para algunos tipos de predicciones y no se usa en la predicción de abandono.
   - **Estado**: estado de la ejecución de la predicción.
        - **Puesto en cola**: la predicción está esperando a que se ejecuten otros procesos.
        - **Actualización**: la predicción se está ejecutando actualmente para producir resultados que fluirán hacia la entidad de salida.
        - **Errores**: la ejecución de la predicción ha presentado errores. [Revise los registros](manage-predictions.md#troubleshoot-a-failed-prediction) para más detalles.
        - **Correcta**: la predicción ha tenido éxito. Seleccione **Ver** bajo los puntos suspensivos verticales para revisar la predicción
   - **Editada**: la fecha en que se modificó la configuración para la predicción.
   - **Última actualización**: la fecha en que la predicción actualizó los resultados en la entidad de salida.

1. Seleccione los puntos suspensivos verticales junto a la predicción cuyos resultados desea revisar y seleccione **Ver**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vea el control para ver los resultados de una predicción.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

1. Hay tres secciones de datos principales en la página de resultados:
   - **Rendimiento del modelo de entrenamiento**: A, B o C son puntuaciones posibles. Esta puntuación indica el rendimiento de la predicción y puede ayudarle a tomar la decisión de usar los resultados almacenados en la entidad de salida. Las puntuaciones se determinan según las siguientes reglas: 
        - **A** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es mayor que la tasa de referencia en al menos un 10 %.
            
        - **B** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es hasta un 10 % mayor que la referencia.
            
        - **C** cuando el modelo predijo con precisión menos del 50 % de las predicciones totales, o cuando el porcentaje de predicciones precisas para los clientes que abandonaron es inferior a la referencia.
               
        - **Referencia** toma la entrada de ventana de tiempo predicción para el modelo (por ejemplo, un año) y el modelo crea diferentes fracciones de tiempo dividiendo por 2 hasta que llega a un mes o menos. Utiliza estas fracciones para crear una regla de negocio para los clientes que no han comprado en este plazo de tiempo. Estos clientes se consideran abandonados. La regla de negocio basada en el tiempo con la mayor capacidad para predecir quién es probable que abandone se elige como modelo de referencia.
            
    - **Probabilidad de pérdida (número de clientes)**: Grupos de clientes según su riesgo de pérdida previsto. Estos datos pueden ayudarle más adelante si desea crear un segmento de clientes con alto riesgo de pérdida. Dichos segmentos ayudan a comprender dónde debe estar el corte para la pertenencia del segmento.
       
    - **Factores más influyentes**: Hay muchos factores que se tienen en cuenta al crear su predicción. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Puede usar estos factores para ayudar a validar sus resultados de predicción, o puede usar esta información más adelante para [crear segmentos](segments.md) que podrían ayudar a influir en el riesgo de abandono de los clientes.


# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

1. Hay tres secciones de datos principales en la página de resultados:
   - **Rendimiento del modelo de entrenamiento**: A, B o C son puntuaciones posibles. Esta puntuación indica el rendimiento de la predicción y puede ayudarle a tomar la decisión de usar los resultados almacenados en la entidad de salida. Las puntuaciones se determinan según las siguientes reglas: 
        - **A** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es mayor que la tasa de referencia en al menos un 10 %.
            
        - **B** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es hasta un 10 % mayor que la referencia.
            
        - **C** cuando el modelo predijo con precisión menos del 50 % de las predicciones totales, o cuando el porcentaje de predicciones precisas para los clientes que abandonaron es inferior a la referencia.
               
        - **Referencia** toma la entrada de ventana de tiempo predicción para el modelo (por ejemplo, un año) y el modelo crea diferentes fracciones de tiempo dividiendo por 2 hasta que llega a un mes o menos. Utiliza estas fracciones para crear una regla de negocio para los clientes que no han comprado en este plazo de tiempo. Estos clientes se consideran abandonados. La regla de negocio basada en el tiempo con la mayor capacidad para predecir quién es probable que abandone se elige como modelo de referencia.
            
    - **Probabilidad de pérdida (número de clientes)**: Grupos de clientes según su riesgo de pérdida previsto. Estos datos pueden ayudarle más adelante si desea crear un segmento de clientes con alto riesgo de pérdida. Dichos segmentos ayudan a comprender dónde debe estar el corte para la pertenencia del segmento.
       
    - **Factores más influyentes**: Hay muchos factores que se tienen en cuenta al crear su predicción. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Puede usar estos factores para ayudar a validar sus resultados de predicción, o puede usar esta información más adelante para [crear segmentos](segments.md) que podrían ayudar a influir en el riesgo de abandono de los clientes.


1. Para cuentas comerciales, encontrará una página de información **Análisis de características influyentes**. Contiene cuatro secciones de datos:

    - El elemento seleccionado en el panel derecho determina el contenido de esta página. Seleccione un elemento de **Clientes destacados** o **Clientes de referencia**. Ambas listas están ordenadas por valor decreciente de la puntuación de abandono, ya sea que la puntuación sea solo para el cliente o una puntuación combinada para los clientes y un nivel secundario como la categoría de producto.
        
        - **Clientes destacados**: Lista de 10 clientes que tienen el mayor riesgo de abandono y el menor riesgo de abandono según sus puntuaciones de abandono. 
        - **Clientes de referencia**: Lista de hasta 10 clientes que fueron seleccionados al configurar el modelo.
 
    - **Puntuación de abandono:** Muestra la puntuación de abandono del elemento seleccionado en el panel derecho.
    
    - **Distribución del riesgo de abandono:** Muestra la distribución del riesgo de abandono entre los clientes y el percentil en el que se encuentra el cliente seleccionado. 
    
    - **Principales características que aumentan y disminuyen el riesgo de abandono:** Para el elemento seleccionado en el panel derecho se enumeran las cinco características principales que aumentaron y disminuyeron el riesgo de abandono. Para cada característica influyente, usted encuentra el valor de la característica para ese elemento y su influencia en la puntuación de abandono. También se muestra el valor promedio de cada función en los segmentos de clientes de bajo, medio y alto riesgo de abandono. Ayuda a contextualizar mejor los valores de las características más influyentes para el artículo seleccionado y compararlo con los segmentos de clientes de bajo, medio y alto riesgo de abandono.

       - Bajo: cuentas o combinaciones de cuenta y nivel secundario con una puntuación de abandono entre 0 y 0,33
       - Medio: cuentas o combinaciones de cuentas y niveles secundarios con una puntuación de abandono entre 0,33 y 0,66
       - Alto: cuentas o combinaciones de cuentas y niveles secundarios con una puntuación de abandono mayor que 0,66
    
       Cuando predice el abandono a nivel de cuenta, todas las cuentas se tienen en consideración al calcular los valores promedio de las funciones para los segmentos de abandono. Para predicciones de abandono en el nivel secundario para cada cuenta, el cálculo de los segmentos de abandono depende del nivel secundario del elemento seleccionado en el panel lateral. Por ejemplo, si un artículo tiene un nivel secundario de categoría de producto = material de oficina, solo se considerarán los artículos que tengan material de oficina como categoría de producto al calcular los valores de característica promedio para los segmentos de abandono. Esta lógica se aplica para garantizar una comparación justa de los valores de característica del artículo con los valores promedio en los segmentos de bajo, medio y alto riesgo de abandono.

       En algunos casos, el valor medio de los segmentos de bajo, medio o alto riesgo de abandono está vacío o no está disponible porque no hay elementos que pertenezcan a los segmentos de abandono correspondientes según la definición anterior.
       
       > [!NOTE]
       > La interpretación de los valores en las columnas promedio bajo, medio y alto es diferente para características categóricas como región o industria. Debido a que la noción de valor de característica "promedio" no se aplica a las características categóricas, los valores en estas columnas son la proporción de clientes en los segmentos de abandono alto, medio o bajo que tienen el mismo valor de la característica categórica en comparación con el elemento. seleccionado en el panel lateral.

---

## <a name="manage-predictions"></a>Administrar predicciones

Es posible optimizar, solucionar problemas, actualizar o eliminar predicciones. Revise un informe de usabilidad de datos de entrada para descubrir cómo hacer que un predicción sea más rápido y confiable. Para obtener más información, vaya a [Administrar predicciones](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
