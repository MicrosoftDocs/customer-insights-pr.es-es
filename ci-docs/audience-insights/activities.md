---
title: Actividades del cliente
description: Defina las actividades de los clientes y visualícelas en una línea de tiempo en los perfiles de los clientes.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: a2f1e8ecf49664a4bb2dc271131d437e50cfdd24
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359861"
---
# <a name="customer-activities"></a>Actividades del cliente

Combine las actividades de los clientes de [varios orígenes de datos](data-sources.md) en Dynamics 365 Customer Insights para crear una escala de tiempo que enumere las actividades cronológicamente. Incluya la escala de tiempo en las aplicaciones de Dynamics 365 con la solución [Complemento tarjeta de cliente](customer-card-add-in.md) o en un panel de Power BI.

## <a name="define-an-activity"></a>Definir una actividad

Sus orígenes de datos pueden incluir entidades con datos transaccionales y de actividad procedentes de varios orígenes de datos. Identifique estas entidades y seleccione las actividades que desea ver en la escala de tiempo del cliente. Elija la entidad que incluye las actividades de destino.

Una entidad debe tener como mínimo un atributo de tipo **Fecha** que se debe incluir en una escala de tiempo de cliente, y no se pueden agregar entidades sin campos de **Fecha**. El control **Agregar actividad** está deshabilitado si no se encuentra esa entidad.

1. En informaciones del público, vaya a **Datos** > **Ocupaciones**.

1. Seleccione **Agregar actividad** para iniciar la experiencia guiada para el proceso de configuración de la actividad.

1. En el paso **Datos de actividad**, establezca los valores para los siguientes campos:

   - **Nombre de la actividad**: seleccione un nombre para su actividad.
   - **Entidad**: seleccione una entidad que incluya datos transaccionales o de actividad.
   - **Clave principal**: seleccione el campo que identifica de manera única un registro. No debe contener valores duplicados, valores vacíos ni valores que faltan.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure los datos de la actividad con un nombre, entidad y clave principal.":::

1. Seleccione **Siguiente** para ir al siguiente paso.

1. En el paso **Relación**, configure los detalles para conectar sus datos de actividad a su registro de cliente correspondiente. Este paso visualiza la conexión entre entidades.  

   - **Primero**: campo externo de su entidad Actividad que se utilizará para establecer una relación con otra entidad.
   - **Segundo**: entidad de cliente de origen correspondiente con la que estará relacionada la entidad Actividad. Solo puede relacionar entidades de clientes de origen que se utilizan en el proceso de unificación de datos.
   - **Tercero**: si ya existe una relación entre esta entidad Actividad y la entidad de cliente de origen seleccionada, el nombre de la relación estará en modo de solo lectura. Si no existe tal relación, se creará una nueva relación con el nombre que proporcione en este cuadro.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina la relación de entidad.":::

   > [!TIP]
   > En entornos B2B, puede seleccionar entre entidades de cuenta y otras entidades. Si selecciona una entidad de cuenta, la ruta de relación se establece automáticamente. Para otras entidades, debe definir la ruta de relación sobre una o más entidades intermedias hasta llegar a una entidad de cuenta.

1. Seleccione **Siguiente** para ir al siguiente paso. 

1. En el paso **Unificación de actividades**, elija el evento de la actividad y la hora de inicio de su actividad. 
   - **Campos obligatorios**
      - **Actividad del evento**: campo que es el evento para esta actividad.
      - **Marca de tiempo**: campo que representa la hora de inicio de su actividad.

   - **Campos opcionales**
      - **Detalle adicional**: campo con información relevante para esta actividad.
      - **Icono**: icono que mejor representa este tipo de actividad.
      - **Dirección web**: campo que contiene una dirección URL con información sobre esta actividad. Por ejemplo, el sistema transaccional que origina esta actividad. Esta dirección URL puede ser cualquier campo del origen de datos, o puede construirse como un nuevo campo usando una transformación de Power Query. Los datos de la dirección URL se almacenarán en la entidad *Actividad unificada*, que se puede consumir subsiguientemente utilizando las [API](apis.md).

   - **Mostrar en escala de tiempo**
      - Elija si desea mostrar esta actividad en la vista de escala de tiempo de los perfiles de cliente. Seleccione **Sí** para mostrar la actividad en la línea de tiempo o **No** para ocultarla.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifique los datos de la actividad del cliente en una entidad Actividad unificada.":::

1. Seleccione **Siguiente** para ir al siguiente paso. Puede elegir **Terminar y revisar** para guardar la actividad ahora con el tipo de actividad configurado en **Otros**. 

1. En el paso **Tipo de actividad**, elija el tipo de actividad y, opcionalmente, seleccione si desea asignar semánticamente algunos de los tipos de actividad para su uso en otras áreas de Customer Insights. Actualmente, los tipos de actividad *Comentarios*, *Fidelidad*, *SalesOrder*, *SalesOrderLine* y *Subscripción* se pueden asignar semánticamente después de acordar asignar los campos. Si un tipo de actividad no es relevante para la nueva actividad, puede elegir *Otros* o *Crear nuevo* para un tipo de actividad personalizada.

1. Seleccione **Siguiente** para ir al siguiente paso. 

1. En el paso **Revisar**, verifique sus selecciones. Vuelva a cualquiera de los pasos anteriores y actualice la información si es necesario.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Revise los campos especificados para una actividad.":::
   
1. Seleccione **Guardar actividad** para aplicar sus cambios y seleccionar **Listo** para volver a **Datos** > **Actividades**. Aquí puede ver qué actividades están configuradas para mostrarse en la escala de tiempo. 

1. En la página **Actividades**, seleccione **Ejecutar** para procesar la actividad. 

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Administrar actividades existentes

En **Datos** > **Actividades**, puede ver todas sus actividades guardadas y administrarlas. Cada actividad está representada por una fila que también incluye detalles sobre el origen, la entidad y el tipo de actividad.

Las siguientes acciones están disponibles cuando selecciona una actividad. 

- **Editar**: abre la configuración de la actividad en el paso de revisión. Puede cambiar parte o toda la configuración actual desde este paso. Después de cambiar la configuración, seleccione **Guardar actividad** y luego seleccione **Ejecutar** para procesar los cambios.

- **Cambiar nombre**: abre un cuadro de diálogo en el que puede introducir un nombre diferente para la actividad seleccionada. Seleccione **Guardar** para aplicar los cambios.

- **Eliminar**: abre un cuadro de diálogo para confirmar la eliminación de la actividad seleccionada. También puede eliminar más de una actividad a la vez seleccionando las actividades y luego seleccionando el icono de eliminar. Seleccione **Eliminar** para confirmar la eliminación.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver escalas de tiempo de actividades en perfiles de clientes

Después de configurar las actividades del cliente, seleccione **Mostrar en escala de tiempo de actividades** en la configuración de actividad para encontrar todas las actividades de su cliente en su perfil de cliente.

Para abrir la escala de tiempo de un cliente, vaya a **Clientes** y elija el perfil de cliente que desea ver.

Si un cliente ha participado en una actividad que ha configurado, lo encontrará en la sección **Escala de tiempo de actividades**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Ver actividades configuradas en Perfiles de clientes.":::

Hay varias formas de filtrar actividades en la escala de tiempo de actividades:

- Puede seleccionar uno o varios de los iconos de actividad para refinar sus resultados e incluir solo los tipos seleccionados.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtra actividades por tipo usando los iconos.":::

- Puede elegir **Filtrar** para abrir un panel de filtro para configurar los filtros de la escala de tiempo.

   1. Puede filtrar por *Tipo de actividad* y *Fecha*
   1. Seleccione **Aplicar** para usar los filtros en la escala de tiempo de actividades.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilice el panel de filtro para configurar las condiciones del filtro.":::

Para quitar filtros, seleccione la **x** junto a cada filtro aplicado a la escala de tiempo o seleccione **Borrar filtros**.


> [!NOTE]
> Los filtros de actividad se eliminan cuando abandona un perfil de cliente. Tiene que aplicarlos cada vez que abre un perfil de cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
