---
title: Unificar campos de clientes o cuentas
description: Fusionar entidades para crear perfiles de cliente unificados.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740878"
---
# <a name="unify-customer-fields"></a>Unificar campos de cliente

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

En este paso del proceso de unificación, elija y excluya atributos para fusionarlos dentro de su entidad de perfil unificado. Por ejemplo, si tres entidades tenían datos de correo electrónico, es posible que desee mantener los tres campos de correo electrónico separados o fusionarlos en un solo campo de correo electrónico para el perfil unificado. El sistema combina automáticamente algunos atributos. Puede crear identificaciones de clientes únicas y estables y agrupar perfiles relacionados en un clúster.

:::image type="content" source="media/m3_unify.png" alt-text="Página de combinación en el proceso de unificación de datos que muestra una tabla con campos combinados que definen el perfil de cliente unificado.":::

## <a name="review-and-update-the-customer-fields"></a>Revisar y actualizar los campos de cliente

1. Revise la lista de campos que se unificarán bajo la pestaña **Campos de clientes** de la tabla. Realice cualquier cambio si corresponde.

   1. Para cualquier campo combinado, puede:
      - [Edición](#edit-a-merged-field)
      - [Cambiar nombre](#rename-fields)
      - [Separado](#separate-merged-fields)
      - [Excluir](#exclude-fields)
      - [Subir o bajar](#change-the-order-of-fields)

   1. Para cualquier campo individual, puede:
      - [Combinar campos](#combine-fields-manually)
      - [Combinar un grupo de campos](#combine-a-group-of-fields)
      - [Cambiar nombre](#rename-fields)
      - [Excluir](#exclude-fields)
      - [Subir o bajar](#change-the-order-of-fields)

1. Opcionalmente, [generar la configuración de identificación del cliente](#configure-customer-id-generation).

1. Opcionalmente, [agrupar perfiles en hogares o clústeres](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Siguiente paso: Revisar la unificación](review-unification.md)

### <a name="edit-a-merged-field"></a>Editar un campo combinado

1. Seleccione un campo combinado y elija **Editar**. Se muestra el panel Combinar campos.

1. Especifique cómo combinar o fusionar los campos de una de estas tres opciones:
    - **Importancia**: identifica el valor ganador según el rango de importancia especificado para los campos participantes. Es la opción de combinación predeterminada. Seleccione **Mover hacia arriba/hacia abajo** para establecer la clasificación de importancia.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opción Importancia en el diálogo de campos de combinación.":::

    - **Más reciente**: identifica el valor ganador basado en el más reciente. Requiere una fecha o un campo numérico para cada entidad participante en el ámbito de los campos de combinación para definir la antigüedad.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opción de menor antigüedad en el diálogo de campos de combinación.":::

    - **Menos reciente**: identifica el valor ganador basado en el menos reciente. Requiere una fecha o un campo numérico para cada entidad participante en el ámbito de los campos de combinación para definir la antigüedad.

1. Puede agregar más campos para participar en el proceso de combinación.

1. También puede cambiar el nombre del campo combinado.

1. Seleccione **Listo** para aplicar los cambios.

### <a name="rename-fields"></a>Cambiar el nombre de los campos

Cambie el nombre de campos combinados o separados. No puede cambiar el nombre de la entidad de salida.

1. Seleccione el campo y elija **Renombrar**.

1. Escriba aquí el nuevo nombre para mostrar.

1. Seleccione **Listo**.

### <a name="separate-merged-fields"></a>Separar campos combinados

Para separar los campos combinados, busque el atributo en la tabla. Los campos separados se muestran como puntos de datos individuales en el perfil de cliente unificado.

1. Seleccione el campo combinado y elija **Campos separados**.

1. Confirme la separación.

### <a name="exclude-fields"></a>Exluir campos

Excluya un campo combinado o separado del perfil de cliente unificado. Si el campo se utiliza en otros procesos, por ejemplo en un segmento, elimínelo de estos procesos antes de excluirlo del perfil del cliente.

1. Seleccione un campo combinado y elija **Excluir**.

1. Confirme la exclusión.

Para ver la lista de todos los campos excluidos, seleccione **Campos excluidos**. Si es necesario, puede volver a agregar el campo excluido.

### <a name="change-the-order-of-fields"></a>Cambiar el orden de los campos

Algunas entidades contienen más detalles que otras. Si una entidad incluye los datos más recientes sobre un campo, puede priorizarlo sobre otras entidades al combinar valores.

1. Seleccione el campo.
  
1. Escoja **Subir/Bajar** para establecer el orden o arrástrelos y suéltelos en la posición deseada.

### <a name="combine-fields-manually"></a>Combinar campos manualmente

Combine campos independientes para crear un atributo combinado.

1. Seleccione **Combinar** > **Campos**. Se muestra el panel Combinar campos.

1. Especifique la política del ganador de la combinación en el desplegable **Combinar campos por**.

1. Seleccione **Agregar campo** para combinar más campos.

1. Proporcione un **Nombre** y un **Nombre del campo de salida**.

1. Seleccione **Listo** para aplicar los cambios.

### <a name="combine-a-group-of-fields"></a>Combinar un grupo de campos

Tratar un grupo de campos como una sola unidad. Por ejemplo, si nuestros registros contienen los campos Dirección1, Dirección2, Ciudad, Estado y Código postal, no queremos fusionar la Dirección2 de un registro diferente, pensando que haría que nuestros datos fueran más completos.

1. Seleccione **Combinar** > **Grupo de campos**.

1. Especifique la política del ganador de la combinación en el desplegable **Clasificar grupos**.

1. Seleccione **Agregar** y elija si desea agregar más campos o grupos a los campos.

1. Proporcione un **Nombre** y un **Nombre de salida** para cada campo combinado.

1. Proporcione un **Nombre** para el grupo de campos.

1. Seleccione **Listo** para aplicar los cambios.

## <a name="configure-customer-id-generation"></a>Configurar la generaciónde id. de cliente

Defina cómo generar valores de ID de cliente, los identificadores de perfil de cliente únicos. El paso de unificar campos en el proceso de unificación de datos genera el identificador de perfil de cliente único. El identificador es el *CustomerId* de la entidad *Cliente* que resulta del proceso de unificación de datos.

*CustomerId* se basa en un hash del primer valor de las claves primarias ganadoras no nulas. Estas claves provienen de las entidades utilizadas en la unificación de datos y están influenciadas por el orden de coincidencia. Por lo tanto, el ID de cliente generado puede cambiar cuando cambia un valor de clave principal en la entidad principal del orden de coincidencia. El valor de clave principal no siempre representaría al mismo cliente.

La configuración de un Id. de cliente estable le permite evitar ese comportamiento.

1. Seleccione la pestaña **Claves**.

1. Pase el cursor sobre la fila **CustomerId** y seleccione **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control para personalizar la generación de id.":::

1. Seleccione hasta cinco campos que incluirán un id. de cliente único y serán más estables. Los registros que no coinciden con su configuración utilizan un id. configurado por el sistema en su lugar.  

1. Seleccione **Listo**.

## <a name="group-profiles-into-households-or-clusters"></a>Agrupar perfiles en hogares o clústeres

Puede definir reglas para agrupar perfiles relacionados en un clúster. Actualmente, hay dos tipos de clústeres disponibles: clústeres de hogar y personalizados. El sistema elige automáticamente un hogar con reglas predefinidas si la entidad *Cliente* contiene los campos semánticos *Person.LastName* y *Location.Address*. También puede crear un clúster con sus propias reglas y condiciones, similares a las [reglas de coincidencia](match-entities.md#define-rules-for-match-pairs).

1. Seleccione **Avanzado** > **Crear clúster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Control para crear un clúster nuevo.":::

1. Elija entre un clúster de **Hogar** o **Personalizado**. Si existen los campos semánticos *Person.LastName* y *Location.Address* en la entidad *Cliente*, el hogar se selecciona automáticamente.

1. Proporcione un nombre para el clúster y seleccione **Hecho**.

1. Seleccione la pestaña **Clústeres** para encontrar el clúster que creó.

1. Especifique las reglas y condiciones para definir su clúster.

1. Seleccione **Listo**. El clúster se cera cuando se completa el proceso de unificación. Los identificadores de clúster se agregan como nuevos campos a la entidad *Cliente*.

> [!div class="nextstepaction"]
> [Siguiente paso: Revisar la unificación](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
