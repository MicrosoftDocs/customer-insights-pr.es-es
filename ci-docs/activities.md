---
title: Actividades del cliente
description: Defina las actividades de los clientes y visualícelas en una línea de tiempo en los perfiles de los clientes.
ms.date: 07/22/2022
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
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188160"
---
# <a name="customer-activities"></a>Actividades del cliente

Las actividades del cliente son acciones o eventos realizados por los clientes. Por ejemplo, las transacciones, la duración de las llamadas de asistencia, las reseñas de sitios web, las compras o las devoluciones. Estas actividades están contenidas en uno o más orígenes de datos. Con Customers Insights, consolide las actividades de sus clientes a partir de estos [orígenes de datos](data-sources.md) y asócielas con perfiles de clientes. Estas actividades aparecen cronológicamente en una escala de tiempo del perfil de cliente. Incluya la escala de tiempo en las aplicaciones de Dynamics 365 con la solución [Complemento de tarjeta de cliente](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definir una actividad

Una entidad debe tener como mínimo un atributo de tipo **Fecha**, que se debe incluir en una escala de tiempo del cliente. El control **Agregar actividad** está deshabilitado si no se encuentra esa entidad.

1. Vaya a **Datos** > **Actividades**.

1. Seleccione **Agregar actividad** para iniciar la experiencia guiada.

1. En el paso **Datos de actividad**, introduzca la siguiente información:

   - **Nombre de la actividad**: nombre de su actividad.
   - **Entidad de la actividad**: una entidad que incluye datos transaccionales o de actividad.
   - **Clave principal**: campo que identifica de manera única un registro. No debe contener valores duplicados, valores vacíos ni valores que faltan.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure los datos de la actividad con un nombre, entidad y clave principal.":::

1. Seleccione **Siguiente**.

1. En el paso **Relación**, seleccione **Agregar relación** para conectar sus datos de actividad a su registro de cliente correspondiente. Este paso visualiza la conexión entre entidades.  

   - **Clave externa de entidad**: campo de su entidad de actividad que se utilizará para establecer una relación con otra entidad.
   - **Nombre de entidad de destino**: entidad de cliente de origen correspondiente con la que estará relacionada la entidad de actividad. Solo puede relacionar entidades de clientes de origen que se utilizan en el proceso de unificación de datos.
   - **Nombre de la relación**: nombre que identifica la relación entre entidades. Si ya existe una relación entre esta entidad de actividad y la entidad de cliente de origen seleccionada, el nombre de la relación es de solo lectura.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina la relación de entidad.":::

   > [!TIP]
   > En entornos B2B, puede seleccionar entre entidades de cuenta y otras entidades. Si selecciona una entidad de cuenta, la ruta de relación se establece automáticamente. Para otras entidades, debe definir la ruta de relación sobre una o más entidades intermedias hasta llegar a una entidad de cuenta.

1. Seleccione **Aplicar** para crear la relación.

1. Seleccione **Siguiente**.

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

1. Seleccione **Siguiente** para elegir el tipo de actividad, o seleccione **Terminar y revisar** para guardar la actividad con el tipo de actividad configurado en **Otros**.

1. En el paso **Tipo de actividad**, elija el tipo de actividad y, opcionalmente, seleccione si desea asignar semánticamente algunos de los tipos de actividad para su uso en otras áreas de Customer Insights. Actualmente, los tipos de actividad *Comentario*, *Lealtad*, *SalesOrder*, *SalesOrderLine* y *Suscripción* admiten la semántica después de aceptar asignar los campos. Si un tipo de actividad no es relevante para la nueva actividad, puede elegir *Otros* o *Crear nuevo* para un tipo de actividad personalizada.

1. Seleccione **Siguiente**.

1. En el paso **Revisar**, verifique sus selecciones. Vuelva a cualquiera de los pasos anteriores y actualice la información si es necesario.

1. Seleccione **Guardar actividad** para aplicar sus cambios y seleccionar **Listo** para volver a **Datos** > **Actividades**. Se muestra la actividad creada.

1. Después de crear todas sus actividades, seleccione **Ejecutar** para procesarlas.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Administrar actividades existentes

Vaya a **Datos** > **Actividades** para ver sus actividades guardadas, su entidad de origen, el tipo de actividad y si están incluidas en la escala de tiempo del cliente. Puede ordenar la lista de actividades por cualquier columna o usar el cuadro de búsqueda para encontrar la actividad que desea administrar.

Seleccione una actividad para ver las acciones disponibles.

- **Edite** la actividad para cambiar su configuración. La configuración se abre en el paso de revisión. Después de cambiar la configuración, seleccione **Guardar actividad** y luego seleccione **Ejecutar** para procesar los cambios.
- **Cambie el nombre** de la actividad. Seleccione **Guardar** para aplicar los cambios.
- **Elimine** la actividad. Para eliminar más de una actividad a la vez, seleccione las actividades y luego **Eliminar**. Confirme la eliminación.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver escalas de tiempo de actividades en perfiles de clientes

1. Si ha seleccionado **Mostrar en escala de tiempo de actividades** en la configuración de actividad, vaya a **Clientes** y seleccione un perfil de cliente para ver las actividades del cliente en la sección **Escala de tiempo de actividades**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Ver actividades configuradas en Perfiles de clientes.":::

1. Para filtrar actividades en la escala de tiempo:

   - Seleccione uno o más iconos de actividad para refinar sus resultados e incluir solo los tipos seleccionados.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtra actividades por tipo usando los iconos.":::

   - Seleccione **Filtrar** para abrir un panel de filtro para configurar los filtros de la escala de tiempo. Puede filtrar por *ActivityType* y/o *Fecha*. Seleccione **Aplicar**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Utilice el panel de filtro para configurar las condiciones del filtro.":::

1. Para quitar filtros, seleccione **Borrar filtros** o seleccione **Filtro** y borre la casilla del filtro.

> [!NOTE]
> Los filtros de actividad se eliminan cuando abandona un perfil de cliente. Tiene que aplicarlos cada vez que abra un perfil de cliente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
