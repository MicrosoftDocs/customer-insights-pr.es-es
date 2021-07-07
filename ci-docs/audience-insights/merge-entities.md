---
title: Fusionar entidades en la unificación de datos
description: Fusionar entidades para crear perfiles de cliente unificados.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305675"
---
# <a name="merge-entities"></a>Combinar entidades

La fase de combinación es la última fase del proceso de unificación de datos. Su propósito es conciliar datos en conflicto. Los ejemplos de datos en conflicto podrían incluir un nombre de cliente que se encuentra en dos de sus conjuntos de datos pero que se muestra de manera un poco diferente en cada uno ("Grant Marshall" y "Grant Marshal"), o un número de teléfono que difiere en formato (617-803-091X y 617803091X). La combinación de esos puntos de datos en conflicto se realiza atributo por atributo.

:::image type="content" source="media/merge-fields-page.png" alt-text="Página de combinación en el proceso de unificación de datos que muestra una tabla con campos combinados que definen el perfil de cliente unificado.":::

Después de completar la [fase de coincidencia](match-entities.md), comience la fase de combinación seleccionando la ventana **Combinar** en la página **Unificar**.

## <a name="review-system-recommendations"></a>Revisar recomendaciones del sistema

En **Datos** > **Unificar** > **Combinar**, elija y excluya atributos a fusionar dentro de su entidad de perfil de cliente unificado. El perfil de cliente unificado es el resultado del proceso de unificación de datos. El sistema combina automáticamente algunos atributos.

Para ver los atributos que se incluyen en uno de sus atributos combinados automáticamente, seleccione ese atributo combinado en la pestaña **Campos de clientes** de la tabla. Los dos atributos que componen ese atributo combinado aparecen en dos filas nuevas debajo del atributo combinado.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separar, renombrar, excluir y editar campos combinados

Puede cambiar la forma en que el sistema procesa los atributos combinados para generar el perfil de cliente unificado. Seleccione **Mostrar más** y elija lo que quiere cambiar.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opciones en el menú desplegable Mostrar más para administrar atributos combinados.":::

Para obtener más información, consulte las secciones siguientes.

## <a name="separate-merged-fields"></a>Separar campos combinados

Para separar los campos combinados, busque el atributo en la tabla. Los campos separados se muestran como puntos de datos individuales en el perfil de cliente unificado. 

1. Seleccione el campo combinado.
  
1. Seleccione **Mostrar más** y elija **Separar campos**.
 
1. Confirme la separación.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios.

## <a name="rename-merged-fields"></a>Cambiar el nombre de los campos combinados

Cambie el nombre para mostrar de los atributos combinados. No puede cambiar el nombre de la entidad de salida.

1. Seleccione el campo combinado.
  
1. Seleccione **Mostrar más** y elija **Renombrar**.

1. Confirme el nombre para mostrar cambiado. 

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios.

## <a name="exclude-merged-fields"></a>Excluir campos combinados

Excluya un atributo del perfil de cliente unificado. Si el campo se utiliza en otros procesos, por ejemplo en un segmento, elimínelo de estos procesos antes de excluirlo del perfil del cliente. 

1. Seleccione el campo combinado.
  
1. Seleccione **Mostrar más** y elija **Excluir**.

1. Confirme la exclusión.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios. 

En la página **Combinar**, seleccione **Campos excluidos** para ver la lista de todos los campos excluidos. Este panel le permite volver a agregar campos excluidos.

## <a name="manually-combine-fields"></a>Combinar campos manualmente

Especifique un atributo combinado manualmente. 

1. En la página **Combinar**, seleccione **Combinar campos**.

1. Proporcione un **Nombre** y un **Nombre del campo de salida**.

1. Elija un campo a agregar. Seleccione **Agregar campos** para combinar más campos.

1. Confirme la exclusión.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios. 

## <a name="change-the-order-of-fields"></a>Cambiar el orden de los campos

Algunas entidades contienen más detalles que otras. Si una entidad incluye los datos más recientes sobre un campo, puede priorizarlo sobre otras entidades al combinar valores.

1. Seleccione el campo combinado.
  
1. Seleccione **Mostrar más** y elija **Editar**.

1. En el panel **Combinar campos**, seleccione **Mover hacia arriba/abajo** para establecer el orden o arrastrarlos y soltarlos en la posición deseada.

1. Confirme el cambio.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios.

## <a name="run-your-merge"></a>Ejecutar la combinación

Tanto si combina manualmente atributos como si deja que el sistema los combine, siempre puede ejecutar su combinación. Seleccione **Ejecutar** en la página **Combinación** para iniciar el proceso.

> [!div class="mx-imgBorder"]
> ![Guardar y ejecutar combinación de datos](media/configure-data-merge-save-run.png "Guardar y ejecutar combinación de datos")

Escoja **Ejecutar solo la combinación** si solo desea ver la salida reflejada en la entidad de cliente unificada. Los procesos posteriores se actualizarán como esté [definido en el programa de actualización](system.md#schedule-tab).

Escoja **Ejecutar procesos de combinación y posteriores** para actualizar el sistema con sus cambios. Todos los procesos, incluido el enriquecimiento, los segmentos y las medidas, se volverán a ejecutar automáticamente. Una vez finalizados todos los procesos posteriores, los perfiles del cliente reflejan cualquier cambio que haya realizado.

Para realizar más cambios y volver a ejecutar el paso, puede cancelar una combinación en curso. Seleccione **Actualizando...** y seleccione **Cancelar trabajo** en el panel lateral que aparece.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="next-step"></a>Paso siguiente

Configure las [actividades](activities.md), el [enriquecimiento](enrichment-hub.md) o las [relaciones](relationships.md) para obtener más información sobre sus clientes.

Si ya configuró actividades, enriquecimiento o segmentos, se procesarán automáticamente para utilizar los datos más recientes del cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
