---
title: Fusionar entidades en la unificación de datos
description: Fusionar entidades para crear perfiles de cliente unificados.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597854"
---
# <a name="merge-entities"></a>Combinar entidades

La fase de combinación es la última fase del proceso de unificación de datos. Su propósito es conciliar datos en conflicto. Los ejemplos de datos en conflicto podrían incluir un nombre de cliente que se encuentra en dos de sus conjuntos de datos pero que se muestra de manera un poco diferente en cada uno ("Grant Marshall" y "Grant Marshal"), o un número de teléfono que difiere en formato (617-803-091X y 617803091X). La combinación de esos puntos de datos en conflicto se realiza atributo por atributo.

Después de completar la [fase de coincidencia](match-entities.md), comience la fase de combinación seleccionando la ventana **Combinar** en la página **Unificar**.

## <a name="review-system-recommendations"></a>Revisar recomendaciones del sistema

En la página **Combinar**, puede elegir y excluir los atributos que se combinarán en la entidad de perfil de cliente unificado (el resultado del proceso de configuración). El sistema combina automáticamente algunos atributos.

### <a name="view-merged-attributes"></a>Ver atributos combinados

Para ver los atributos que se incluyen en uno de sus atributos combinados automáticamente, seleccione ese atributo combinado. Los dos atributos que componen ese atributo combinado aparecen en dos filas nuevas debajo del atributo combinado.

> [!div class="mx-imgBorder"]
> ![Seleccionar atributo combinado](media/configure-data-merge-profile-attributes.png "Seleccionar atributo combinado")

### <a name="separate-merged-attributes"></a>Separar atributos combinados

Para separar o combinar cualquiera de los atributos combinados automáticamente, busque el atributo en la tabla **Atributos del perfil**.

1. Seleccione el botón de puntos suspensivos (...).
  
2. En la lista desplegable, seleccione **Campos separados**.

### <a name="remove-merged-attributes"></a>Quitar atributos combinados

Para excluir un atributo de la entidad del perfil del cliente final, búsquelo en la tabla **Atributos de perfil**.

1. Seleccione el botón de puntos suspensivos (...).
  
2. En la lista desplegable, seleccione **No combinar**.

   El atributo pasa a la sección **Quitado de los registros de cliente**.

## <a name="manually-add-a-merged-attribute"></a>Agregar manualmente un atributo combinado

Para agregar un atributo combinado, vaya a la página **Combinar**.

1. Seleccione **Agregar atributo combinado**.

2. Proporcione un **Nombre** para identificarlo en la página **Combinar** más tarde.

3. Opcionalmente, proporcione un **Nombre para mostrar** que aparece en la entidad del perfil de cliente unificado.

4. Configure **Seleccionar atributos duplicados** para seleccionar los atributos que desea combinar desde las entidades coincidentes. También puede buscar atributos.

5. Establezca **Clasificar por importancia** para priorizar un atributo sobre los demás. Por ejemplo, si la entidad *WebAccountCSV* incluye los datos más precisos sobre el atributo *Nombres completos*, podría priorizar esta entidad sobre *ContactCSV* seleccionando *WebAccountCSV*. Por ello, *WebAccountCSV* pasa a primera prioridad, mientras que *ContactCSV* pasa a la segunda prioridad al extraer valores para el atributo *Nombre completo*.

## <a name="run-your-merge"></a>Ejecutar la combinación

Tanto si combina manualmente atributos como si deja que el sistema los combine, siempre puede ejecutar su combinación. Seleccione **Ejecutar** en la página **Combinación** para iniciar el proceso.

> [!div class="mx-imgBorder"]
> ![Guardar y ejecutar combinación de datos](media/configure-data-merge-save-run.png "Guardar y ejecutar combinación de datos")

Para realizar cambios adicionales y volver a ejecutar el paso, puede cancelar una fusión en curso. Seleccione **Actualizando...** y seleccione **Cancelar trabajo** en el panel lateral que aparece.

Después de **Actualizando...**, los cambios del texto cambian a **Correcto**. La fusión se ha completado y se han resuelto las contradicciones en los datos de acuerdo con las directivas que definió. Los atributos fusionados y no fusionados se incluyen en la entidad de perfil unificada. Los atributos excluidos no se incluyen en la entidad de perfil unificada.

Si no fue la primera vez que ejecutó una fusión con éxito, todos los procesos posteriores, incluidos el enriquecimiento, la segmentación y las medidas, se volverán a ejecutar automáticamente. Después de que se hayan vuelto a ejecutar todos los procesos posteriores, los perfiles de los clientes reflejan los cambios que haya realizado.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="next-step"></a>Paso siguiente

Configure las [actividades](activities.md), el [enriquecimiento](enrichment-microsoft-graph.md) o las [relaciones](relationships.md) para obtener más información sobre sus clientes.

Si ya configuró las actividades, el enriquecimiento o las relaciones o si definió los segmentos, se procesarán automáticamente para usar los últimos datos del cliente.




[!INCLUDE[footer-include](../includes/footer-banner.md)]