---
title: Fusionar entidades en la unificación de datos
description: Fusionar entidades para crear perfiles de cliente unificados.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: eb08ab38d23bf22a17896b63c93e6821431b002a
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046643"
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

1. Seleccione un campo combinado.
  
1. Seleccione **Mostrar más** y elija **Excluir**.

1. Confirme la exclusión.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios. 

En la página **Combinar**, seleccione **Campos excluidos** para ver la lista de todos los campos excluidos. Este panel le permite volver a agregar campos excluidos.

## <a name="edit-a-merged-field"></a>Editar un campo combinado

1.  Seleccione un campo combinado.

1.  Seleccione **Mostrar más** y elija **Editar**.

1.  Especifique cómo combinar o fusionar los campos de una de estas tres opciones:
    - **Importancia**: identifica el valor ganador según el rango de importancia especificado para los campos participantes. Es la opción de combinación predeterminada. Seleccione **Mover hacia arriba/hacia abajo** para establecer la clasificación de importancia.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opción Importancia en el diálogo de campos de combinación."::: 
    - **Más reciente**: identifica el valor ganador basado en el más reciente. Requiere una fecha o un campo numérico para cada entidad participante en el ámbito de los campos de combinación para definir la antigüedad.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opción de menor antigüedad en el diálogo de campos de combinación.":::
    - **Menos reciente**: identifica el valor ganador basado en el menos reciente. Requiere una fecha o un campo numérico para cada entidad participante en el ámbito de los campos de combinación para definir la antigüedad.

1.  Puede agregar más campos para participar en el proceso de combinación.

1.  También puede cambiar el nombre del campo combinado.

1. Seleccione **Listo** para aplicar los cambios.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios. 

## <a name="combine-fields-manually"></a>Combinar campos manualmente

Especifique un atributo combinado manualmente.

1. En la página **Combinar**, seleccione **Combinar**.

1. Elija la opción **Campos**.

1. Especifique la política del ganador de la combinación en el desplegable **Combinar campos por**.

1. Elija un campo a agregar. Seleccione **Agregar campos** para combinar más campos.

1. Proporcione un **Nombre** y un **Nombre del campo de salida**.

1. Seleccione **Listo** para aplicar los cambios.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios. 

## <a name="combine-a-group-of-fields"></a>Combinar un grupo de campos

Tratar un grupo de campos como una sola unidad. Por ejemplo, cuando nuestros registros contienen los campos Dirección1, Dirección2, Ciudad, Estado y Código postal. Es probable que no queramos fusionar la Dirección2 de un registro diferente, pensando que haría que nuestros datos fueran más completos

1. En la página **Combinar**, seleccione **Combinar**.

1. Elija la opción **Grupo de campos**.

1. Especifique la política del ganador de la combinación en el desplegable **Clasificar grupos**.

1. Seleccione **Agregar** y elija si desea agregar más campos o grupos adicionales a los campos.

1. Proporcione un **Nombre** y un **Nombre de salida** para cada campo combinado.

1. Proporcione un **Nombre** para el grupo de campos. 

1. Seleccione **Listo** para aplicar los cambios.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios.

## <a name="change-the-order-of-fields"></a>Cambiar el orden de los campos

Algunas entidades contienen más detalles que otras. Si una entidad incluye los datos más recientes sobre un campo, puede priorizarlo sobre otras entidades al combinar valores.

1. Seleccione el campo combinado.
  
1. Seleccione **Mostrar más** y elija **Editar**.

1. En el panel **Combinar campos**, seleccione **Mover hacia arriba/abajo** para establecer el orden o arrastrarlos y soltarlos en la posición deseada.

1. Confirme el cambio.

1. Seleccione **Guardar** y **Ejecutar** para procesar los cambios.

## <a name="configure-customer-id-generation"></a>Configurar la generaciónde id. de cliente 

Después de configurar los campos de combinación, puede definir cómo generar valores CustomerId, los identificadores únicos de perfil de cliente. El paso de combinación en el proceso de unificación de datos genera el identificador de perfil de cliente único. El identificador es el CustomerId de la entidad *Cliente* que resulta del proceso de unificación de datos. 

El CustomerId de la entidad Cliente se basa en un hash del primer valor de las claves primarias ganadoras no nulas. Estas claves provienen de las entidades utilizadas en la fase de coincidencia y fusión y están influenciadas por el orden de coincidencia. Por lo tanto, el CustomerID generado puede cambiar cuando cambia un valor de clave principal en la entidad principal del orden de coincidencia. Por tanto, es posible que el valor de clave principal no siempre represente al mismo cliente.

La configuración de un Id. de cliente estable le permite evitar ese comportamiento.

**Configurar un id. de cliente único**

1. Vaya a **Unificar** > **Combinar**.

1. Seleccione la pestaña **Claves**. 

1. Coloque el cursor sobre la fila **CustomerId** y seleccione la opción **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control para personalizar la generación de id.":::

1. Seleccione hasta cinco campos que incluirán un id. de cliente único y serán más estables. Los registros que no coinciden con su configuración utilizan un id. configurado por el sistema en su lugar.  

1. Seleccione **Listo** y ejecute el proceso de combinación para aplicar sus cambios.

## <a name="group-profiles-into-households-or-clusters"></a>Agrupar perfiles en hogares o clústeres

Como parte del proceso de configuración de generación de perfiles de cliente, puede definir reglas para agrupar perfiles relacionados en un clúster. Actualmente, hay dos tipos de clústeres disponibles: clústeres de hogar y personalizados. El sistema elige automáticamente un hogar con reglas predefinidas si la entidad *Cliente* contiene los campos semánticos *Person.LastName* y *Location.Address*. También puede crear un clúster con sus propias reglas y condiciones, similares a las [reglas de coincidencia](match-entities.md#define-rules-for-match-pairs).

**Definir un hogar o un clúster**

1. Vaya a **Unificar** > **Combinar**.

1. En la pestaña **Combinar**, seleccione **Avanzado** > **Crear clúster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Control para crear un clúster nuevo.":::

1. Elija entre un clúster de **Hogar** o **Personalizado**. Si existen los campos semánticos *Person.LastName* y *Location.Address* en la entidad *Cliente*, el hogar se selecciona automáticamente.

1. Proporcione un nombre para el clúster y seleccione **Hecho**.

1. Seleccione la pestaña **Clústeres** para encontrar el clúster que creó.

1. Especifique las reglas y condiciones para definir su clúster.

1. Seleccione **Ejecutar** para ejecutar el proceso de combinación y crear el clúster.

Después de ejecutar el proceso de combinación, los identificadores de clúster se agregan como nuevos campos a la entidad *Cliente*.

## <a name="run-your-merge"></a>Ejecutar la combinación

Tanto si combina manualmente atributos como si deja que el sistema los combine, siempre puede ejecutar su combinación. Seleccione **Ejecutar** en la página **Combinación** para iniciar el proceso.

> [!div class="mx-imgBorder"]
> ![Guardar y ejecutar combinación de datos.](media/configure-data-merge-save-run.png "Guardar y ejecutar combinación de datos")

Escoja **Ejecutar solo la combinación** si solo desea ver la salida reflejada en la entidad de cliente unificada. Los procesos posteriores se actualizarán como esté [definido en el programa de actualización](system.md#schedule-tab).

Escoja **Ejecutar procesos de combinación y posteriores** para actualizar el sistema con sus cambios. Todos los procesos, incluido el enriquecimiento, los segmentos y las medidas, se volverán a ejecutar automáticamente. Una vez finalizados todos los procesos posteriores, los perfiles del cliente reflejan cualquier cambio que haya realizado.

Para realizar más cambios y volver a ejecutar el paso, puede cancelar una combinación en curso. Seleccione **Actualizando...** y seleccione **Cancelar trabajo** en el panel lateral que aparece.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Ruta de exploración en profundidad para acceder a los detalles del proceso desde el vínculo de estado de la tarea.":::

## <a name="next-step"></a>Paso siguiente

Configure las [actividades](activities.md), el [enriquecimiento](enrichment-hub.md) o las [relaciones](relationships.md) para obtener más información sobre sus clientes.

Si ya configuró actividades, enriquecimiento o segmentos, se procesarán automáticamente para utilizar los datos más recientes del cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
