---
title: Predicción de recomendaciones del producto
description: Prediga los productos que es probable que un cliente compre o con los que interactúe.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598084"
---
# <a name="product-recommendation-prediction-preview"></a>Predicción de recomendaciones del producto (versión preliminar)

El modelo de recomendación de productos crea conjuntos de recomendaciones de productos predictivas. Las recomendaciones se basan en el comportamiento de compra anterior y en clientes con patrones de compra similares. Puede crear nuevas predicciones de recomendación de productos en la página **Inteligencia** > **Predicciones**. Seleccione **Mis predicciones** para ver otras predicciones que ha creado.

Las recomendaciones de productos pueden estar sujetas a las leyes y regulaciones locales, así como a las expectativas del cliente, que el modelo no está diseñado para tener en cuenta específicamente.  Como usuario de esta funcionalidad predictiva, **debe revisar las recomendaciones antes de entregárselas a sus clientes** para asegurarse de que está cumpliendo con las leyes o regulaciones aplicables, así como con las expectativas del cliente sobre lo que puede recomendar. 

Además, los resultados de este modelo le darán recomendaciones basadas en el identificador del producto. Su mecanismo de entrega deberá tomar los identificadores de producto que se predijeron y asignarlos al contenido apropiado para que sus clientes tengan en cuenta la localización, el contenido de imágenes y otros contenidos o comportamientos específicos de la empresa.

## <a name="sample-guide"></a>Guía de ejemplo

Si está interesado en probar esta función pero no tiene datos para completar los requisitos a continuación, puede [crear una implementación de ejemplo](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Conocimiento comercial para comprender los diferentes tipos de productos para su negocio y cómo sus clientes interactúan con ellos. Apoyamos la recomendación de productos que sus clientes han comprado previamente o las recomendaciones para nuevos productos.
- Datos sobre sus transacciones, compras y su historial:
    - Identificadores de transacciones para distinguir compras o transacciones.
    - Identificadores de clientes para asignar transacciones a sus clientes.
    - Fechas de eventos de transacción que especifican las fechas en las que ocurrió la transacción.
    - (Opcional) Información del identificador del producto para la transacción.
    - (Opcional) Si una transacción es una devolución o no.
    - El esquema de datos semánticos requiere la siguiente información:
        - **Id. de transacción:** un identificador único de una compra o transacción.
        - **Fecha de Transacción**: la fecha de la compra o transacción.
        - **Valor de la transacción**: el valor numérico de la compra o la transacción.
        - **Id. de producto único**: el identificador del producto o servicio adquirido si sus datos se encuentran en el nivel de artículo de línea.
        - (Opcional) **Compra o devolución**: un campo de verdadero/falso que identifica si la transacción fue una devolución o no. Si el **Valor de la transacción** es negativo, también usaremos esta información para inferir una devolución.


## <a name="create-a-product-recommendation-prediction"></a>Crear una predicción de recomendaciones de producto

1. En Customer Insights, vaya a **Inteligencia** > **Predicciones**.

1. Seleccione el mosaico **Modelo de recomendaciones de producto (versión preliminar)** y seleccione **Utilizar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Mosaico del Modelo de recomendaciones de producto con el botón Usar este modelo](media/product-recommendation-usethismodel.PNG "Mosaico del Modelo de recomendaciones de producto con el botón Usar este modelo")

1. Revise la información sobre los requisitos del modelo. Si tiene los datos requeridos, seleccione **Comenzar**.

### <a name="name-model"></a>Modelo de nombre

1. Proporcione un nombre para el modelo para distinguirlo de otros modelos.

1. Especifique un nombre para la entidad de salida usando solo letras y números, sin espacios. Ese es el nombre que usará la entidad del modelo. A continuación, seleccione **Siguiente**.

### <a name="define-product-recommendation-configuration"></a>Definir la configuración de recomendación de producto

1. Establezca el **Número de productos** que desea recomendar a un cliente. Este valor depende de cómo su método de entrega rellena los datos. Si puede recomendar tres productos, establezca este valor en consecuencia.
   
   >[!TIP]
   > Puede elegir **Guardar y cerrar** en cualquier momento para guardar la predicción como borrador. Encontrará el borrador predicción en la pestaña **Mis predicciones**.

1. Elija si desea **Sugerir productos que los clientes han comprado recientemente**.

1. Si ha seleccionado *no* recomendar productos comprados recientemente, configure la **Ventana para mirar atrás**. Esta configuración especifica el plazo de tiempo que el modelo considera antes de recomendar el producto al usuario nuevamente. Por ejemplo, indique que un cliente compra una computadora portátil cada 2 años. Esta ventana tendrá en cuenta el historial de compras de los últimos 2 años y, si encuentran un artículo, el artículo se filtrará en las recomendaciones.

1. Seleccione **Siguiente**

### <a name="add-required-data"></a>Agregar datos necesarios

1. Seleccione **Agregar datos** para **Historial de transacciones del cliente** y elija la entidad que proporciona la información del historial de transacciones/compras, como se describe en los [requisitos previos](#prerequisites).

1. Asigne los campos semánticos a los atributos dentro de su entidad de historial de compras y seleccione **Siguiente**. Para obtener descripciones de los campos, eche un vistazo a los [prerrequisitos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definir la relación de entidad](media/product-recommendation-purchasehistorymapping.PNG "Página del historial de compras que muestra los atributos semánticos que se asignan a los campos de la entidad del historial de compras seleccionada")

1. Si los campos no están rellenos, configure la relación entre su entidad de historial de compras y la entidad *Cliente*.
    1. Seleccione la **Entidad de historial de compras**.
    1. Seleccione el **Campo** que identifica al cliente en la entidad de historial de compras. Debe relacionarse con el identificador de cliente principal de su entidad *Cliente*.
    1. Seleccione la **Entidad de cliente** que coincida con su entidad de cliente principal.
    1. Escriba un nombre que describa la relación.
       > [!div class="mx-imgBorder"]
       > ![Página del historial de compras que muestra la creación de una relación con el cliente.](media/model-purchase-join.png "Página del historial de compras que muestra la creación de una relación con el cliente")

1. Seleccione **Guardar**.

1. Seleccione **Siguiente**.

### <a name="set-schedule-and-review-configuration"></a>Establecer la programación y revisar la configuración

1. Establezca una frecuencia para volver a entrenar su modelo. Esta configuración es importante para actualizar la precisión de las predicciones a medida que se importan nuevos datos en Customer Insights. La mayoría de las empresas pueden volver a entrenarse una vez al mes y obtener una buena precisión para sus predicciones.

1. Seleccione **Siguiente**.

1. Revise la configuración. Puede volver a cualquier parte de la configuración de predicción seleccionando **Editar** debajo del valor mostrado. O puede seleccionar un paso de configuración desde el indicador de progreso.

1. Si todos los valores están configurados correctamente, seleccione **Guardar y ejecutar** para comenzar el proceso de predicción. En la pestaña **Mis predicciones** puede ver el estado de sus predicciones. El proceso puede tardar varias horas en completarse dependiendo de la cantidad de datos utilizados en la predicción.

## <a name="review-a-prediction-status-and-results"></a>Revisar un estado y resultados de predicción

1. Vaya a la pestaña **Mis predicciones** en **Inteligencia** > **Predicciones**.
   > [!div class="mx-imgBorder"]
   > ![Vista de la página Mis predicciones](media/product-recommendation-mypredictions.PNG "Vista de la página Mis predicciones")

1. Seleccione la predicción que desea revisar.
   - **Nombre de predicción:** El nombre de la predicción proporcionado al crearla.
   - **Tipo de predicción:** El tipo de modelo utilizado para la predicción
   - **Entidad de salida:** Nombre de la entidad para almacenar la salida de la predicción. Puede encontrar una entidad con este nombre en **Datos** > **Entidades**.
   - **Campo previsto:** este campo se rellena solo para algunos tipos de predicciones y no se usa en la predicción de abandono.
   - **Estado:** el estado actual de la ejecución de la predicción.
        - **En cola:** La predicción está esperando que se ejecuten otros procesos.
        - **Actualizando:** La predicción actualmente está ejecutando la fase de "puntuación" del procesamiento para producir resultados que fluirán a la entidad de salida.
        - **Error:** La predicción ha fallado. Seleccione **Registros** para más detalles.
        - **Correcta:** La predicción ha tenido éxito. Seleccione **Ver** bajo los puntos suspensivos verticales para revisar la predicción
   - **Editada:** La fecha en que se modificó la configuración para la predicción.
   - **Última actualización:** La fecha en que la predicción actualizó los resultados en la entidad de salida.

1. Seleccione los puntos suspensivos verticales junto a la predicción cuyos resultados desea revisar y seleccione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista de opciones en el menú de puntos suspensivos verticales para una predicción que incluye editar, actualizar, ver, registrar y eliminar](media/product-recommendation-verticalellipses.PNG "Vista de opciones en el menú de puntos suspensivos verticales para una predicción que incluye editar, actualizar, ver, registrar y eliminar")

1. Hay tres secciones de datos principales en la página de resultados:
    1. **Rendimiento del modelo de entrenamiento:** A, B o C son puntuaciones posibles. Esta puntuación indica el rendimiento de la predicción y puede ayudarle a tomar la decisión de usar los resultados almacenados en la entidad de salida.
        - Las puntuaciones se determinan según las siguientes reglas:
            - **A**: el modelo será considerado de calidad **A** si la métrica "Success @ K" es al menos un 10 % superior al valor de referencia. 
            - **B**: el modelo será considerado de calidad **B** si la métrica "Success @ K" es entre 0 % y 10 % superior al valor de referencia.
            - **C**: el modelo será considerado de calidad **C** si la métrica "Success @ K" menor que el valor de referencia.
               
               > [!div class="mx-imgBorder"]
               > ![Vista del resultado del rendimiento del modelo](media/product-recommendation-modelperformance.PNG "Vista del resultado del rendimiento del modelo")
            - **Valor de referencia**: el modelo toma los productos más recomendados por el recuento de compras en todos los clientes y utiliza reglas aprendidas identificadas por el modelo para crear un conjunto de recomendaciones para los clientes. Luego, las predicciones se comparan con los productos destacados, calculados según el número de clientes que compraron el producto. Si un cliente tiene al menos un producto en sus productos recomendados que también se vio en los productos destacados, se considera parte del valor de referencia. Si hubiera 10 de estos clientes que tuvieran un producto recomendado comprado de un total de 100 clientes, el valor de referencia sería 10 %.
            - **Success @ K**: con un conjunto de períodos de tiempo de validación de transacciones, se crean recomendaciones para todos los clientes y se comparan con el conjunto de validación de transacciones. Por ejemplo, en un período de 12 meses, el mes 12 podría reservarse como un conjunto de datos de validación. Si el modelo predice al menos una cosa que compraría en el mes 12 basándose en lo que aprendió de los 11 meses anteriores, el cliente aumentaría la métrica "Success @ K".
    
    1. **Productos más sugeridos (con recuento)**: los 5 productos principales que se predijeron para sus clientes.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que muestra los 5 productos más recomendados](media/product-recommendation-topproducts.PNG "Gráfico que muestra los 5 productos más recomendados")
    
    1. **Recomendaciones de productos de alta confianza**: una muestra de recomendaciones proporcionadas a sus clientes que el modelo cree que es probable que el cliente compre.
       > [!div class="mx-imgBorder"]
       > ![Lista que muestra sugerencias de alta confianza para un grupo selecto de clientes individuales](media/product-recommendation-highconfidence.PNG "Lista que muestra sugerencias de alta confianza para un grupo selecto de clientes individuales")

## <a name="fix-a-failed-prediction"></a>Corregir una predicción fallida

1. Vaya a la pestaña **Mis predicciones** en **Inteligencia** > **Predicciones**.

1. Seleccione la predicción para cuyos registros de errores desea ver y seleccione **Registros**.

1. Revisar todos los errores. Hay varios tipos de errores que pueden producirse, y describen qué condición causó el error. Por ejemplo, un error de que no hay suficientes datos para predecir con precisión generalmente se resuelve cargando datos adicionales en Customer Insights.

## <a name="refresh-a-prediction"></a>Actualizar una predicción

Las predicciones se actualizan automáticamente en el mismo [programa en que se actualizan sus datos](system.md#schedule-tab) según lo configurado en los ajustes.

1. Vaya a la pestaña **Mis predicciones** en **Inteligencia** > **Predicciones**.

1. Seleccione los puntos suspensivos verticales junto a la predicción que desea actualizar.

1. Seleccione **Actualizar**.

## <a name="delete-a-prediction"></a>Eliminar una predicción

Eliminar un predicción también elimina su entidad de salida.

1. Vaya a la pestaña **Mis predicciones** en **Inteligencia** > **Predicciones**.

1. Seleccione los puntos suspensivos verticales junto a la predicción que desea eliminar.

1. Seleccione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]