---
title: Predicción de recomendaciones del producto
description: Prediga los productos que es probable que un cliente compre o con los que interactúe.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: fe6c0e8ba8236243682a4105535a0026c4343c3d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647949"
---
# <a name="product-recommendation-prediction"></a>Predicción de recomendaciones del producto

El modelo de recomendación de productos crea conjuntos de recomendaciones de productos predictivas. Las recomendaciones se basan en el comportamiento de compra anterior y en clientes con patrones de compra similares. Puede crear nuevas predicciones de recomendación de productos en la página **Inteligencia** > **Predicciones**. Seleccione **Mis predicciones** para ver otras predicciones que ha creado.

Las recomendaciones de productos pueden estar sujetas a las leyes y normativas locales y a las expectativas del cliente, que el modelo no está diseñado para tener en cuenta específicamente.  Como usuario de esta capacidad predictiva, **debe revisar las recomendaciones antes de entregarlas a sus clientes** para asegurarse de que está cumpliendo con las leyes o regulaciones aplicables, y las expectativas del cliente sobre lo que puede recomendar. 

Además, los resultados de este modelo le darán recomendaciones basadas en el identificador del producto. Su mecanismo de entrega deberá asignar los identificadores de producto previstos al contenido apropiado para que sus clientes tengan en cuenta la localización, el contenido de imágenes y otros contenidos o comportamientos específicos de la empresa.

## <a name="sample-guide"></a>Guía de ejemplo

Si está interesado en probar esta función pero no tiene datos para completar los requisitos a continuación, puede [crear una implementación de ejemplo](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.

- Conocimiento comercial para comprender los diferentes tipos de productos para su negocio y cómo sus clientes interactúan con ellos. Apoyamos la recomendación de productos que sus clientes han comprado previamente o las recomendaciones para nuevos productos.

- Datos sobre sus transacciones, compras y su historial:
    - Identificadores de transacciones para distinguir compras o transacciones.
    - Identificadores de clientes para asignar transacciones a sus clientes.
    - Fechas de eventos de transacción que especifican las fechas en las que ocurrió la transacción.
    - Información del identificador del producto para la transacción.
    - (Opcional) Una entidad de datos del catálogo de productos para utilizar un filtro de producto.
    - (Opcional) Si una transacción es una devolución o no.
    - El esquema de datos semánticos requiere la siguiente información:
        - **Id. de transacción:** un identificador único de una compra o transacción.
        - **Fecha de Transacción:** la fecha de la compra o transacción.
        - **Valor de la transacción**: el valor numérico de la compra o la transacción.
        - **Id. de producto único**: el identificador del producto o servicio adquirido si sus datos se encuentran en el nivel de artículo de línea.
        - (Opcional) **Compra o devolución:** un campo booleano donde el valor *true* identifica que una transacción fue una devolución. Si no se proporcionan los datos de compra o devolución, el modelo y el **Valor de la transacción** es negativo, también usaremos esta información para inferir una devolución.
- Características de los datos sugeridos
    - Datos históricos suficientes: al menos un año de datos transaccionales, preferiblemente de dos a tres años para incluir cierta estacionalidad.
    - Varias compras por cliente: tres o más transacciones por identificador de cliente.
    - Número de clientes: al menos 100 clientes, preferiblemente más de 10 000 clientes. El modelo no funcionará si hay menos de 100 clientes.

> [!NOTE]
> - El modelo requiere el historial de transacciones de sus clientes. La definición de transacción es bastante flexible. Cualquier dato que describa una interacción entre usuario y producto puede funcionar como entrada. Por ejemplo, comprar un producto, tomar una clase o asistir a un evento.
> - Actualmente, solo se puede configurar una entidad del historial de transacciones. Si hay varias entidades de compra, únalas en Power Query antes de la ingesta de datos.
> - Si el pedido y los detalles del pedido son entidades diferentes, únalas antes de usarlas en el modelo. El modelo no funciona solo con un identificador de pedido o un identificador de recibo en una entidad.


## <a name="create-a-product-recommendation-prediction"></a>Crear una predicción de recomendaciones de producto

1. En Customer Insights, vaya a **Inteligencia** > **Predicciones**.

1. Seleccione la ventana **Modelo de recomendaciones de producto** y seleccione **Usar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Icono del modelo de recomendaciones de producto con el botón Usar este modelo.](media/product-recommendation-usethismodel.PNG "Mosaico del Modelo de recomendaciones de producto con el botón Usar este modelo")

1. Revise la información sobre los requisitos del modelo. Si tiene los datos requeridos, seleccione **Comenzar**.

### <a name="name-model"></a>Modelo de nombre

1. Proporcione un nombre para el modelo para distinguirlo de otros modelos.

1. Especifique un nombre para la entidad de salida usando solo letras y números, sin espacios. Ese es el nombre que usará la entidad del modelo. A continuación, seleccione **Siguiente**.

### <a name="define-product-recommendation-configuration"></a>Definir la configuración de recomendación de producto

1. Establezca el **Número de productos** que desea recomendar a un cliente. Este valor depende de cómo su método de entrega rellena los datos. Si puede recomendar tres productos, establezca este valor en consecuencia.
   
   >[!TIP]
   > Puedes elegir **Guardar borrador** en cualquier momento para guardar la predicción como borrador. Encontrará el borrador predicción en la pestaña **Mis predicciones**.

1. Elija si desea incluir productos que los clientes hayan comprado recientemente en el campo **Se esperan compras repetidas**.

1. Establecer la **Ventana de mirar atrás**. Esta configuración especifica el plazo de tiempo que el modelo considera antes de recomendar el producto al usuario nuevamente. Por ejemplo, indique que un cliente compra un portátil cada dos años. Esta ventana verá el historial de compras de los últimos dos años y, si encuentran un artículo, el artículo se filtrará de las recomendaciones.

1. Seleccione **Siguiente**

### <a name="add-required-data"></a>Agregar datos necesarios

1. Seleccione **Agregar datos** y elija el tipo de actividad en el panel lateral que contiene la transacción requerida o la información del historial de compras.

1. En **Elegir actividades**, elija las actividades específicas de la actividad seleccionada en las que le gustaría que se centrara el cálculo.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Panel lateral que muestra la elección de actividades específicas de tipo semántico.":::

1. Si aún no ha asignado la actividad a un tipo semántico, seleccione **Editar** para hacerlo. Se abre la experiencia guiada para mapear actividades semánticas. Mapee los datos a los campos correspondientes del tipo de actividad seleccionado.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Tipo de actividad de configuración de página.":::

1. Después de asignar la actividad al tipo semántico correspondiente, seleccione **Siguiente** para continuar 
 
1. Asigne los atributos semánticos a los campos necesarios para ejecutar el modelo.

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**.


### <a name="configure-product-filters"></a>Configurar filtros de producto

A veces, solo ciertos productos son ventajosos o apropiados para el tipo de predicción que crea. Los filtros de productos le permiten identificar un subconjunto de productos con características específicas para recomendar a sus clientes. El modelo usará todos los productos disponibles para aprender patrones, pero solo usará los productos que coincidan con el filtro del producto en su salida.

1. En el paso **Agregar información del producto**, agregue su catálogo de productos con información para cada producto. Asigne la información requerida y seleccione **Siguiente**.

3. En el paso **Filtros de productos**, elija entre las siguientes opciones.

   * **Sin filtros**: utilice todos los productos de la predicción de la recomendación del producto.

   * **Definir filtros de productos específicos**: utilice productos específicos en la predicción de la recomendación del producto.

1. Seleccione **Siguiente**.

1. Si elige definir un filtro de producto, debe definirlo ahora. En el panel **Atributos del catálogo de productos**, seleccione los atributos de su *entidad Catálogo de productos* que desea incluir en el filtro.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panel lateral que muestra los atributos en la entidad del catálogo de productos a seleccionar para los filtros de productos.":::

1. Elija si desea el filtro de producto para utilizar los conectores **y** u **o** para combinar lógicamente su selección de atributos del catálogo de productos.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Ejemplo de configuración de filtros de producto combinados con conectores lógicos AND.":::

1. Seleccione **Siguiente**.

### <a name="set-update-schedule-and-review-configuration"></a>Establecer la programación de actualización y revisar la configuración

1. Establezca una frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se importan nuevos datos en Customer Insights. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

1. Revise la configuración. Puede volver a cualquier parte de la configuración de predicción seleccionando **Editar** debajo del valor mostrado. O puede seleccionar un paso de configuración desde el indicador de progreso.

1. Si todos los valores están configurados correctamente, seleccione **Guardar y ejecutar** para comenzar el proceso de predicción. En la pestaña **Mis predicciones** puede ver el estado de sus predicciones. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

## <a name="review-a-prediction-status-and-results"></a>Revisar un estado y resultados de predicción

1. Vaya a la pestaña **Mis predicciones** en **Inteligencia** > **Predicciones**.
   > [!div class="mx-imgBorder"]
   > ![Vista de la página Mis predicciones.](media/product-recommendation-mypredictions.PNG "Vista de la página Mis predicciones")

1. Seleccione la predicción que desea revisar.
   - **Nombre de predicción:** El nombre de la predicción proporcionado al crearla.
   - **Tipo de predicción:** El tipo de modelo utilizado para la predicción
   - **Entidad de salida:** Nombre de la entidad para almacenar la salida de la predicción. Puede encontrar una entidad con este nombre en **Datos** > **Entidades**.    
      *Puntuación* en la entidad de salida hay una medida cuantitativa de la recomendación. El modelo recomienda productos con una puntuación más alta antes que los productos con una puntuación más baja.
   - **Campo de predicción**: este campo se completa solo para algunos tipos de predicciones, y no se usa en la predicción de recomendación de productos.
   - **Estado:** el estado actual de la ejecución de la predicción.
        - **En cola:** La predicción está esperando que se ejecuten otros procesos.
        - **Actualizando:** La predicción actualmente está ejecutando la fase de "puntuación" del procesamiento para producir resultados que fluirán a la entidad de salida.
        - **Error:** La predicción ha fallado. Seleccione **Registros** para más detalles.
        - **Correcta:** La predicción ha tenido éxito. Seleccione **Ver** bajo los puntos suspensivos verticales para revisar la predicción
   - **Editada:** La fecha en que se modificó la configuración para la predicción.
   - **Última actualización:** La fecha en que la predicción actualizó los resultados en la entidad de salida.

1. Seleccione los puntos suspensivos verticales junto a la predicción cuyos resultados desea revisar y seleccione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista de opciones en el menú de puntos suspensivos verticales para una predicción que incluye editar, actualizar, ver, registrar y eliminar.](media/product-recommendation-verticalellipses.PNG "Vista de opciones en el menú de puntos suspensivos verticales para una predicción que incluye editar, actualizar, ver, registrar y eliminar")

1. Hay cinco secciones principales de datos dentro de la página de resultados:
    1. **Rendimiento del modelo de entrenamiento:** A, B o C son puntuaciones posibles. Esta puntuación indica el rendimiento de la predicción y puede ayudarle a tomar la decisión de usar los resultados almacenados en la entidad de salida.
        - Las puntuaciones se determinan según las siguientes reglas:
            - **A**: el modelo será considerado de calidad **A** si la métrica "Success @ K" es al menos un 10 % superior al valor de referencia. 
            - **B**: el modelo será considerado de calidad **B** si la métrica "Success @ K" es entre 0 % y 10 % superior al valor de referencia.
            - **C**: el modelo será considerado de calidad **c** si la métrica "Success @ K" es menor que el valor de referencia.
               
               > [!div class="mx-imgBorder"]
               > ![Vista del resultado del rendimiento del modelo.](media/product-recommendation-modelperformance.PNG "Vista del resultado del rendimiento del modelo")
            - **Valor de referencia**: el modelo toma los productos más recomendados por el recuento de compras en todos los clientes y utiliza reglas aprendidas identificadas por el modelo para crear un conjunto de recomendaciones para los clientes. Luego, las predicciones se comparan con los productos destacados, calculados según el número de clientes que compraron el producto. Si un cliente tiene al menos un producto en sus productos recomendados que también se vio en los productos destacados, se considera parte del valor de referencia. Si hubiera 10 de estos clientes que tuvieran un producto recomendado comprado de un total de 100 clientes, el valor de referencia sería 10 %.
            - **Success @ K**: con un conjunto de períodos de tiempo de validación de transacciones, se crean recomendaciones para todos los clientes y se comparan con el conjunto de validación de transacciones. Por ejemplo, en un período de 12 meses, el mes 12 podría reservarse como un conjunto de datos de validación. Si el modelo predice al menos una cosa que compraría en el mes 12 basándose en lo que aprendió de los 11 meses anteriores, el cliente aumentaría la métrica "Success @ K".
    
    1. **Productos más sugeridos (con recuento)**: los cinco productos principales que se predijeron para sus clientes.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que muestra los 5 productos más recomendados.](media/product-recommendation-topproducts.PNG "Gráfico que muestra los 5 productos más recomendados")
    
    1. **Factores clave de recomendación** el modelo utiliza el historial de transacciones de los clientes para hacer recomendaciones de productos. Aprende patrones basados en compras pasadas y encuentra similitudes entre clientes y productos. Estas similitudes se utilizan luego para generar recomendaciones de productos.
    Los siguientes son los factores que podrían influir en una recomendación de producto generada por el modelo. 
        - **Transacciones pasadas**: el modelo utilizó patrones de compra en el pasado para generar recomendaciones de productos. Por ejemplo, el modelo puede recomendar un _Ratón Surface Arc_ si alguien compró recientemente un _Surface Book 3_ y un _Lápiz de Surface_. El modelo aprendió que, históricamente, muchos clientes habían comprado un _Ratón Surface Arc_ después de comprar un _Surface Book 3_ y un _Lápiz de Surface_.
        - **Similitud del cliente**: históricamente, un producto recomendado fue comprado por otros clientes que muestran patrones de compra similares. Por ejemplo, se recomendó a John unos _Auriculares Surface 2_ porque Jennifer y Brad compraron recientemente _Auriculares Surface 2_. El modelo cree que John es similar a Jennifer y Brad porque históricamente han tenido patrones de compra similares.
        - **Similitud de producto**: un producto recomendado es similar a otros productos que el cliente había comprado anteriormente. El modelo considera que dos productos son similares si fueron comprados juntos o por clientes similares. Por ejemplo, alguien recibe una recomendación para una _unidad de almacenamiento USB_ porque previamente compraron un _adaptador USB-C a USB_ y el modelo cree que la _unidad de almacenamiento USB_ es parecida al _adaptador USB-C a USB_ basándose en patrones de compra históricos.

        Cada recomendación de producto está influenciada por uno o más de estos factores. El porcentaje de recomendaciones en las que cada factor influyente jugó un papel se representa en un gráfico. En el siguiente ejemplo, el 100 % de las recomendaciones fueron influenciadas por transacciones pasadas, el 60 % por la similitud de clientes y el 22 % por similitud de productos. Desplácese sobre las barras del gráfico para ver el porcentaje exacto en el que contribuyeron los factores influyentes.

        > [!div class="mx-imgBorder"]
        > ![Factores clave de recomendación.](media/product-recommendation-keyrecommendationfactors.png "Factores de recomendación clave aprendidos por el modelo para generar recomendaciones de productos")
       
     
   1. **Estadísticas de datos**: ofrece una descripción general del número de transacciones, clientes y productos que tuvo en cuenta el modelo. Se basa en los datos de entrada que se utilizaron para aprender patrones y generar recomendaciones de productos.

      > [!div class="mx-imgBorder"]
      > ![Estadísticas de datos.](media/product-recommendation-datastatistics.png "Estadísticas de datos en torno a los datos de entrada y salida utilizados por el modelo para aprender patrones")

      Esta sección muestra estadísticas sobre los puntos de datos que fueron utilizados por el modelo para aprender patrones y generar recomendaciones de productos. El filtrado, tal como se configura en la configuración del modelo, se aplicará a la salida generada por el modelo. Sin embargo, el modelo usa todos los datos disponibles para aprender patrones. Por lo tanto, si utiliza el filtrado de productos en la configuración del modelo, esta sección mostrará la cantidad total de productos que el modelo analizó para aprender patrones, que pueden diferir de la cantidad de productos que coinciden con los criterios de filtrado definidos.

   1. **Recomendaciones de productos de alta confianza**: una muestra de recomendaciones proporcionadas a sus clientes que el modelo cree que es probable que el cliente compre.    
      Si se agrega un catálogo de productos, los identificadores de productos se reemplazan por nombres de productos. Los nombres de los productos proporcionan información más procesable e intuitiva sobre las predicciones.
       > [!div class="mx-imgBorder"]
       > ![Lista que muestra sugerencias de alta confianza para un grupo selecto de clientes individuales.](media/product-recommendation-highconfidence.PNG "Lista que muestra sugerencias de alta confianza para un grupo selecto de clientes individuales")

## <a name="manage-predictions"></a>Administrar predicciones

Es posible optimizar, solucionar problemas, actualizar o eliminar predicciones. Revise un informe de usabilidad de datos de entrada para descubrir cómo hacer que un predicción sea más rápido y confiable. Para obtener más información, consulte [Administrar predicciones](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
