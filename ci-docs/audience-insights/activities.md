---
title: Actividades del cliente
description: Defina las actividades del cliente y visualícelas en la escala de tiempo del cliente.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304947"
---
# <a name="customer-activities"></a>Actividades del cliente

Combine las actividades de los clientes de [varios orígenes de datos](data-sources.md) en Dynamics 365 Customer Insights para crear una escala de tiempo que enumere las actividades cronológicamente. Incluya la escala de tiempo en las aplicaciones de Dynamics 365 con la solución [Complemento tarjeta de cliente](customer-card-add-in.md) o en un panel de Power BI.

## <a name="define-an-activity"></a>Definir una actividad

Sus orígenes de datos pueden incluir entidades con datos transaccionales y de actividad procedentes de varios orígenes de datos. Identifique estas entidades y seleccione las actividades que desea ver en la escala de tiempo del cliente. Elija la entidad que incluye las actividades de destino.

> [!NOTE]
> Una entidad debe tener como mínimo un atributo de tipo **Fecha** que se debe incluir en una escala de tiempo de cliente, y no se pueden agregar entidades sin campos de **Fecha**. El control **Agregar actividad** está deshabilitado si no se encuentra esa entidad.

1. En informaciones del público, vaya a **Datos** > **Ocupaciones**.

1. Seleccione **Agregar actividad** para iniciar la experiencia guiada para el proceso de configuración de la actividad.

1. En el paso **Datos de actividad**, establezca los valores para los siguientes campos:

   - **Nombre de la actividad**: seleccione un nombre para su actividad.
   - **Entidad**: seleccione una entidad que incluya datos transaccionales o de actividad.
   - **Clave principal**: seleccione el campo que identifica de manera única un registro. No debe contener valores duplicados, valores vacíos ni valores que faltan.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure los datos de la actividad con un nombre, entidad y clave principal.":::

1. Seleccione **Siguiente** para ir al siguiente paso.

1. En el paso **Relación**, configure los detalles que se utilizarán para conectar sus datos de actividad a su cliente correspondiente. Este paso visualiza la conexión entre entidades.  

   - **Primero**: campo externo de su entidad Actividad que se utilizará para establecer una relación con otra entidad.
   - **Segundo**: entidad de cliente de origen correspondiente con la que estará relacionada la entidad Actividad. Solo puede relacionar entidades de clientes de origen que se utilizan en el proceso de unificación de datos.
   - **Tercero**: si ya existe una relación entre esta entidad Actividad y la entidad de cliente de origen seleccionada, el nombre de la relación estará en modo de solo lectura. Si no existe tal relación, se creará una nueva relación con el nombre que proporcione en este cuadro.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina la relación de entidad.":::

1. Seleccione **Siguiente** para ir al siguiente paso. 

1. En el paso **Unificación de actividades**, elija el evento de la actividad y la hora de inicio de su actividad. 
   - **Campos obligatorios**
      - **Actividad del evento**: campo que es el evento para esta actividad.
      - **Marca de tiempo**: campo que representa la hora de inicio de su actividad.

   - **Campos opcionales**
      - **Detalle adicional**: campo con información relevante para esta actividad.
      - **Icono**: icono que mejor representa este tipo de actividad.
      - **Dirección web**: campo que contiene una dirección URL con información sobre esta actividad. Por ejemplo, el sistema transaccional que origina esta actividad. Esta URL puede ser cualquier campo de origen de datos, o puede construirse como un nuevo campo utilizando una transformación de Power Query. Los datos de la dirección URL se almacenarán en la entidad *Actividad unificada*, que se puede consumir subsiguientemente utilizando las [API](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifique los datos de la actividad del cliente en una entidad Actividad unificada.":::

1. Seleccione **Siguiente** para ir al siguiente paso. Puede elegir **Terminar y revisar** para guardar la actividad ahora con el tipo de actividad configurado en **Otros**. 

1. En el paso **Tipo de actividad**, elija el tipo de actividad y, opcionalmente, seleccione si desea asignar semánticamente algunos de los tipos de actividad para su uso en otras áreas de Customer Insights. Actualmente, los tipos de actividad *Suscripción* y *SalesOrderLine* se pueden asignar semánticamente después de acordar asignar los campos. Si un tipo de actividad no es relevante para la nueva actividad, puede elegir *Otros* o *Crear nuevo* para un tipo de actividad personalizada.

1. Seleccione **Siguiente** para ir al siguiente paso. 

1. En el paso **Revisar**, verifique sus selecciones. Vuelva a cualquiera de los pasos anteriores y actualice la información si es necesario.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Revise los campos especificados para una actividad.":::
   
1. Seleccione **Guardar actividad** para aplicar sus cambios y seleccionar **Listo** para volver a **Datos** > **Actividades**. Aquí puede ver qué actividades están configuradas para mostrarse en la escala de tiempo. 

1. En la página **Actividades**, seleccione **Ejecutar** para procesar la actividad. 

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.


## <a name="manage-existing-activities"></a>Administrar actividades existentes

En **Datos** > **Actividades**, puede ver todas sus actividades guardadas y administrarlas. Cada actividad está representada por una fila que también incluye detalles sobre el origen, la entidad y el tipo de actividad.

Las siguientes acciones están disponibles cuando selecciona una actividad. 

- **Editar**: abre la configuración de la actividad en el paso de revisión. Puede cambiar parte o toda la configuración actual desde este paso. Después de cambiar la configuración, seleccione **Guardar actividad** y luego seleccione **Ejecutar** para procesar los cambios.

- **Cambiar nombre**: abre un cuadro de diálogo en el que puede introducir un nombre diferente para la actividad seleccionada. Seleccione **Guardar** para aplicar los cambios.

- **Eliminar**: abre un cuadro de diálogo para confirmar la eliminación de la actividad seleccionada. También puede eliminar más de una actividad a la vez seleccionando las actividades y luego seleccionando el icono de eliminar. Seleccione **Eliminar** para confirmar la eliminación.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
