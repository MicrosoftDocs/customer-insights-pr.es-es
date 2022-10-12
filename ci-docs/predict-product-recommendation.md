---
title: Predecir recomendaciones del producto
description: Prediga los productos que es probable que un cliente compre o con los que interactúe.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610303"
---
# <a name="predict-product-recommendations"></a>Predecir recomendaciones del producto

El modelo de recomendación de productos crea conjuntos de recomendaciones de productos predictivas. Las recomendaciones se basan en el comportamiento de compra anterior y en clientes con patrones de compra similares. Este modelo es para consumidores individuales (B-a-C).

Debe tener conocimiento comercial sobre los diferentes tipos de productos para su negocio y cómo sus clientes interactúan con ellos. Apoyamos la recomendación de productos que sus clientes han comprado previamente o las recomendaciones para nuevos productos.

Las recomendaciones de productos pueden estar sujetas a las leyes y normativas locales y a las expectativas del cliente, que el modelo no está diseñado para tener en cuenta específicamente. Por tanto, **debe revisar las recomendaciones antes de entregarlas a sus clientes** para asegurarse de que está cumpliendo con las leyes o regulaciones aplicables, y las expectativas del cliente sobre lo que puede recomendar.

Los resultados de este modelo proporcionan recomendaciones basadas en el identificador del producto. Su mecanismo de entrega debe asignar los identificadores de producto previstos al contenido apropiado para que sus clientes tengan en cuenta la localización, el contenido de imágenes y otros contenidos o comportamientos específicos de la empresa.

> [!TIP]
> Pruebe la recomendación de producto predicción usando datos de muestra: [Recomendación de producto predicción guía de muestra](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos [permisos de colaborador](permissions.md)
- Al menos 100 clientes, preferiblemente más de 10 000 clientes.
- Identificador de cliente, un identificador único para hacer coincidir las transacciones con un cliente individual
- Al menos un año de datos transaccionales, preferiblemente de dos a tres años para incluir cierta estacionalidad. Idealmente, al menos tres o más transacciones por ID de cliente. El historial de transacciones debe incluir:
  - **Id. de transacción**: identificador único de una compra o transacción.
  - **Fecha de transacción**: fecha de la compra o transacción.
  - **Valor de la transacción**: valor numérico de la compra o la transacción.
  - **Id. de producto único**: identificador del producto o servicio adquirido si sus datos se encuentran en el nivel de artículo de línea.
  - **Compra o devolución:** valor booleano verdadero/falso donde el valor *true* identifica que una transacción fue una devolución. Si no se proporcionan los datos de compra o devolución en el modelo y el **Valor de la transacción** es negativo, inferimos una devolución.
- Una entidad de datos del catálogo de productos para utilizar como filtro de producto.

> [!NOTE]
> - El modelo requiere el historial de transacciones de sus clientes, donde transacción es cualquier dato que describa una interacción usuario-producto. Por ejemplo, comprar un producto, tomar una clase o asistir a un evento.
> - Solo se puede configurar una entidad del historial de transacciones. Si hay varias entidades de compra, combínelas en Power Query antes de la ingesta de datos.
> - Si el pedido y los detalles del pedido son entidades diferentes, únalas antes de usarlas en el modelo. El modelo no funciona solo con un identificador de pedido o un identificador de recibo en una entidad.

## <a name="create-a-product-recommendation-prediction"></a>Crear una predicción de recomendaciones de producto

Seleccione **Guardar borrador** en cualquier momento para guardar la predicción como borrador. La predicción de borrador se muestra en la pestaña **Mis predicciones**.

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Crear**, seleccione **Usar modelo** en la ventana **Recomendaciones de producto (versión preliminar)**.

1. Seleccione **Comenzar**.

1. Asigne un nombre a **este modelo** y a la **entidad de salida** para distinguirlos de otros modelos o entidades.

1. Seleccione **Siguiente**.

### <a name="define-product-recommendation-preferences"></a>Definir las preferencias de recomendación de producto

1. Establezca el **Número de productos** para recomendar a un cliente. Este valor depende de cómo su método de entrega rellena los datos.

1. Elija si desea incluir productos que los clientes hayan comprado previamente en el campo **Se esperan compras repetidas**.

1. Establezca **Ventana para mirar atrás** con el plazo de tiempo que el modelo considera antes de recomendar el producto al usuario nuevamente. Por ejemplo, indique que un cliente compra un portátil cada dos años. El modelo consulta el historial de compras de los últimos dos años y, si encuentran un artículo, el artículo se filtra de las recomendaciones.

1. Seleccione **Siguiente**

### <a name="add-purchase-history"></a>Agregar historial de compras

1. Seleccione **Agregar datos** para **Historial de transacciones de cliente**.

1. Seleccione el tipo de actividad semántico **SalesOrderLine** que contiene la transacción requerida o la información del historial de compras. Si la actividad no se ha configurado, seleccione **aquí** y créela.

1. Bajo **Actividades**, si los atributos de la actividad se asignaron semánticamente cuando se creó la actividad, elija los atributos o la entidad específicos en los que desea que se centre el cálculo. Si no se produjo el mapeo semántico, seleccione **Editar** y mapee sus datos.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Panel lateral que muestra la elección de actividades específicas de tipo semántico.":::

1. Seleccione **Siguiente** y revise los atributos necesarios para este modelo.

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**.

### <a name="add-product-information-and-filters"></a>Agregar información del producto y filtros

A veces, solo ciertos productos son ventajosos o apropiados para el tipo de predicción que crea. Usar filtros de productos para identificar un subconjunto de productos con características específicas para recomendar a sus clientes. El modelo usará todos los productos disponibles para aprender patrones, pero solo usará los productos que coincidan con el filtro del producto en su salida.

1. Agregue su entidad de catálogo de productos que contiene información para cada producto. Asigne la información requerida y seleccione **Guardar**.

1. Seleccione **Siguiente**.

1. Seleccione **Filtros de producto**:

   - **Sin filtros**: utilice todos los productos de la predicción de la recomendación del producto.

   - **Definir filtros de productos específicos**: utilice productos específicos en la predicción de la recomendación del producto. En el panel **Atributos del catálogo de productos**, seleccione los atributos de su entidad de catálogo de productos que desea incluir en el filtro.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panel lateral que muestra los atributos en la entidad del catálogo de productos a seleccionar para los filtros de productos.":::

1. Elija si desea el filtro de producto para utilizar los conectores **y** u **o** para combinar lógicamente su selección de atributos del catálogo de productos.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Ejemplo de configuración de filtros de producto combinados con conectores lógicos AND.":::

1. Seleccione **Siguiente**.

### <a name="set-update-schedule"></a>Definir la programación de actualizaciones

1. Elija una frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se ingieren nuevos datos en Customer Insights. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

### <a name="review-and-run-the-model-configuration"></a>Revisar y ejecutar la configuración del modelo

El paso **Revisar y ejecutar** muestra un resumen de la configuración y brinda la oportunidad de realizar cambios antes de crear el predicción.

1. Seleccione **Editar** en cualquiera de los pasos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Guardar y ejecutar** para comenzar a ejecutar el modelo. Seleccione **Listo**. La pestaña **Mis predicciones** se muestra mientras se crea predicción. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver los resultados de la predicción

1. Vaya a **Inteligencia** > **Predicciones**.

1. En la pestaña **Mis predicciones**, seleccione la predicción que desea ver.

Hay cinco secciones principales de datos dentro de la página de resultados.

- **Rendimiento del modelo**: los grados A, B o C indican el rendimiento de la predicción y puede ayudarlo a tomar la decisión de utilizar los resultados almacenados en la entidad de salida.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Imagen del resultado de rendimiento del modelo con la puntuación A.":::

  Las puntuaciones se determinan según las siguientes reglas:
  - **A** cuando la métrica "Success @ K" es al menos un 10 % más que la línea de base.
  - **B** cuando la métrica "Success @ K" es de 0 % a 10 % superior a la línea de base.
  - **C** cuando la métrica "Success @ K" es inferior a la línea de base.
  - **Valor de referencia**: los productos más recomendados por el recuento de compras en todos los clientes + las reglas aprendidas identificadas por el modelo = un conjunto de recomendaciones para los clientes. Luego, las predicciones se comparan con los productos destacados, calculados según el número de clientes que compraron el producto. Si un cliente tiene al menos un producto en sus productos recomendados que también se vio en los productos destacados, se considera parte del valor de referencia. Por ejemplo, si 10 de estos clientes tuvieran un producto recomendado comprado de un total de 100 clientes, el valor de referencia es 10 %.
  - **Success @ K**: se crean recomendaciones para todos los clientes y se comparan con el conjunto de validación del período de tiempo de las transacciones. Por ejemplo, en un período de 12 meses, el mes 12 se reserva como un conjunto de datos de validación. Si el modelo predice al menos una cosa que compraría en el mes 12 basándose en lo que aprendió de los 11 meses anteriores, el cliente aumentaría la métrica "Success @ K".

- **Productos más sugeridos (con recuento)**: los cinco productos principales que se predijeron para sus clientes.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Gráfico que muestra los 5 productos más recomendados.":::

- **Factores clave de recomendación** el modelo utiliza el historial de transacciones de los clientes para hacer recomendaciones de productos. Aprende patrones basados en compras pasadas y encuentra similitudes entre clientes y productos. Estas similitudes se utilizan luego para generar recomendaciones de productos.
  Los siguientes factores podrían influir en una recomendación de producto generada por el modelo.
  - **Transacciones pasadas**: Un producto recomendado se basó en patrones de compra anteriores. Por ejemplo, el modelo puede recomendar un *Ratón Surface Arc* si alguien compró recientemente un *Surface Book 3* y un *Lápiz de Surface*. El modelo aprendió que, históricamente, muchos clientes habían comprado un *Ratón Surface Arc* después de comprar un *Surface Book 3* y un *Lápiz de Surface*.
  - **Similitud del cliente**: históricamente, un producto recomendado fue comprado por otros clientes que muestran patrones de compra similares. Por ejemplo, se recomendó a John unos *Auriculares Surface 2* porque Jennifer y Brad compraron recientemente *Auriculares Surface 2*. El modelo cree que John es similar a Jennifer y Brad porque históricamente han tenido patrones de compra similares.
  - **Similitud de producto**: un producto recomendado es similar a otros productos que el cliente había comprado anteriormente. El modelo considera que dos productos son similares si fueron comprados juntos o por clientes similares. Por ejemplo, alguien recibe una recomendación para una *unidad de almacenamiento USB* porque previamente compraron un *adaptador USB-C a USB* y el modelo cree que la *unidad de almacenamiento USB* es parecida al *adaptador USB-C a USB* basándose en patrones de compra históricos.

  Cada recomendación de producto está influenciada por uno o más de estos factores. El porcentaje de recomendaciones en las que cada factor influyente jugó un papel se representa en un gráfico. En el siguiente ejemplo, el 100 % de las recomendaciones fueron influenciadas por transacciones pasadas, el 60 % por la similitud de clientes y el 22 % por similitud de productos. Desplácese sobre las barras del gráfico para ver el porcentaje exacto en el que contribuyeron los factores influyentes.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Factores de recomendación clave aprendidos por el modelo para generar recomendaciones de productos.":::

- **Estadísticas de datos**: una descripción general del número de transacciones, clientes y productos que tuvo en cuenta el modelo. Se basa en los datos de entrada que se utilizaron para aprender patrones y generar recomendaciones de productos.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Estadísticas de datos en torno a los datos de entrada utilizados por el modelo para aprender patrones.":::
  
  El modelo usa todos los datos disponibles para aprender patrones. Por lo tanto, si utiliza el filtrado de productos en la configuración del modelo, esta sección muestra la cantidad total de productos que el modelo analizó para aprender patrones, que pueden diferir de la cantidad de productos que coinciden con los criterios de filtrado definidos. El filtrado se aplica a la salida generada por el modelo.

- **Recomendaciones de productos de ejemplo**: una muestra de recomendaciones que el modelo cree que es probable que el cliente compre. Si se agrega un catálogo de productos, los identificadores de productos se reemplazan por nombres de productos.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lista que muestra sugerencias de alta confianza para un grupo selecto de clientes individuales.":::

> [!NOTE]
> En la entidad de salida de este modelo, *Puntuación* muestra la medida cuantitativa de la recomendación. El modelo recomienda productos con una puntuación más alta antes que los productos con una puntuación más baja. Para ver la puntuación, vaya a **Datos** > **Entidades** y vea la pestaña de datos para la entidad de salida que definió para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
