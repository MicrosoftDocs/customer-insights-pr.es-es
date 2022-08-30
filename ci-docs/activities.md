---
title: Actividades de contacto comercial o de clientes
description: Defina las actividades de los clientes o contacto comercial y visualícelas en una línea de tiempo en los perfiles de los clientes.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
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
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304126"
---
# <a name="customer-or-business-contact-activities"></a>Actividades de contacto comercial o de clientes

Las actividades del cliente son acciones o eventos realizados por clientes o contactos comerciales. Por ejemplo, las transacciones, la duración de las llamadas de asistencia, las reseñas de sitios web, las compras o las devoluciones. Estas actividades están contenidas en uno o más orígenes de datos. Con Customers Insights, consolide las actividades de sus clientes a partir de estos [orígenes de datos](data-sources.md) y asócielas con perfiles de clientes. Estas actividades aparecen cronológicamente en una escala de tiempo del perfil de cliente. Incluya la escala de tiempo en las aplicaciones de Dynamics 365 con la solución [Complemento de tarjeta de cliente](customer-card-add-in.md).

## <a name="define-a-customer-activity"></a>Defina una actividad de cliente

Una entidad debe tener como mínimo un atributo de tipo **Fecha**, que se debe incluir en una escala de tiempo del cliente. El control **Agregar actividad** está deshabilitado si no se encuentra esa entidad.

1. Vaya a **Datos** > **Actividades**.

1. Seleccione **Agregar actividad** para iniciar la experiencia guiada.

1. En el paso **Datos de actividad**, introduzca la siguiente información:

   - **Nombre de la actividad**: seleccione un nombre para su actividad.
   - **Entidad de actividad**: seleccione una entidad que incluya datos transaccionales o de actividad.
   - **Clave principal**: seleccione el campo que identifica de manera única un registro. No debe contener valores duplicados, valores vacíos ni valores que faltan.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure los datos de la actividad con un nombre, entidad y clave principal.":::

1. Seleccione **Siguiente**.

1. En el paso **Relación**, seleccione **Agregar relación** para conectar sus datos de actividad a su registro de cliente correspondiente. Este paso visualiza la conexión entre entidades.  

   - **Clave externa**: campo externo de su entidad Actividad que se utilizará para establecer una relación con otra entidad.
   - **Nombre de entidad de destino**: entidad de cliente de origen correspondiente con la que estará relacionada la entidad de actividad. Solo puede relacionar entidades de clientes de origen que se utilizan en el proceso de unificación de datos.
   - **Nombre de la relación**: si ya existe una relación entre esta entidad de actividad y la entidad de cliente de origen seleccionada, el nombre de la relación estará en modo de solo lectura. Si no existe tal relación, se creará una nueva relación con el nombre que proporcione en este cuadro.

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

## <a name="manage-existing-customer-activities"></a>Administrar actividades de cliente existentes

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

> [!NOTE]
> Los filtros de actividad se eliminan cuando abandona un perfil de cliente. Tiene que aplicarlos cada vez que abra un perfil de cliente.

## <a name="define-a-contact-activity"></a>Defina una actividad de contacto

Para cuentas comerciales (B-to-B), utilice una entidad *ContactProfile* para capturar las actividades de los contactos. Puede ver en el cronograma de actividad de una cuenta qué contacto fue responsable de cada actividad. La mayoría de los pasos siguen la configuración de mapeo de actividades de cliente.

   > [!NOTE]
   > Para definir una actividad a nivel de contacto, una entidad *ContactProfile* debe ser creada, ya sea como un [perfil de contacto unificado](data-unification-contacts.md) o a través de [mapeo semántico](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Debe tener los atributos **AccountID** y **ContactID** para cada registro dentro de los datos de su actividad.
  
1. Vaya a **Datos** > **Actividades**.

1. Seleccione **Agregar actividad**.

1. Nombre la actividad, seleccione la entidad de actividad de origen y seleccione la clave principal de la entidad de actividad.

1. En el paso **Relaciones**, cree una relación indirecta entre los datos de la fuente de su actividad y las cuentas, utilizando sus datos de contacto como una entidad intermediaria. Para obtener más información, vea [rutas de relaciones directas e indirectas](relationships.md#relationship-paths).
   - Relación de ejemplo para una actividad llamada *Compras*:
      - **Datos de actividad de origen de compras** > **Datos de contacto** en el atributo **ContactID**
      - **Datos de contacto** > **Datos de cuenta** en el atributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Ejemplo de configuración de relaciones.":::

1. Después de configurar Relaciones, seleccione **Siguiente** y complete la configuración de su mapeo de actividades. Para conocer los pasos detallados sobre la creación de actividades, consulte [definir una actividad de cliente](#define-a-customer-activity).

1. Ejecute sus asignaciones de actividad.

1. Sus actividades a nivel de contacto ahora serán visibles en la línea de tiempo de su cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final después de configurar las actividades de contacto":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtrado de línea de tiempo de actividad a nivel de contacto

Después de configurar un mapeo de actividad a nivel de contacto y ejecutarlo, se actualizará la línea de tiempo de actividad para sus clientes. Incluye sus ID o nombres, según su configuración de *ContactProfile*, para las actividades en las que actuaron. Puede filtrar actividades por contactos en la línea de tiempo para ver contactos específicos que le interesan. Además, puede ver todas las actividades que no están asignadas a un contacto específico seleccionando **Actividades no asignadas a un contacto**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opciones de filtrado disponibles para actividades a nivel de contacto.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
