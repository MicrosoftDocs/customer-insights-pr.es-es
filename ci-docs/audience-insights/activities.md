---
title: Actividades del cliente
description: Defina las actividades del cliente y visualícelas en la escala de tiempo del cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596750"
---
# <a name="customer-activities"></a>Actividades del cliente

Combine las actividades del cliente de [varias fuentes de datos](data-sources.md) en Dynamics 365 Customer Insights para crear una línea de tiempo del cliente que enumere las actividades en orden cronológico. Puede incluir la escala de tiempo en las aplicaciones de involucración del cliente en Dynamics 365 a través del [Complemento de tarjeta de cliente](customer-card-add-in.md), o en un panel Power BI.

## <a name="define-an-activity"></a>Definir una actividad

Sus orígenes de datos incluyen entidades con datos transaccionales y de actividad procedentes de varios orígenes de datos. Identifique estas entidades y seleccione las actividades que desea ver en la escala de tiempo del cliente. Elija la entidad que incluye las actividades de destino.

1. En informaciones del público, vaya a **Datos** > **Ocupaciones**.

1. Seleccione **Agregar actividad**.

   > [!NOTE]
   > Una entidad debe tener como mínimo un atributo de tipo **Fecha** que se debe incluir en una escala de tiempo de cliente, y no se pueden agregar entidades sin campos de **Fecha**. El control **Agregar actividad** está deshabilitado si no se encuentra esa entidad.

1. En el panel **Agregar actividad**, establezca los valores de los siguientes campos:

   - **Entidad**: seleccione una entidad que incluya datos transaccionales o de actividad.
   - **Clave principal**: seleccione el campo que identifica de manera única un registro. No debe contener valores duplicados, valores vacíos ni valores que faltan.
   - **Marca de tiempo**: seleccione el campo que representa la hora de inicio de la actividad.
   - **Evento**: seleccione el campo que es el evento de la actividad.
   - **Dirección web**: Seleccione el campo que representa una URL proporcionando información adicional sobre esta actividad. Por ejemplo, el sistema transaccional que origina esta actividad. Esta URL puede ser cualquier campo de origen de datos, o puede construirse como un nuevo campo utilizando una transformación de Power Query. Estos datos de URL se almacenarán en la entidad de Interfaz unificada, que se puede consumir en sentido descendente utilizando API.
   - **Detalles**: opcionalmente, seleccione el campo que se agrega para obtener más detalles.
   - **Icono**: opcionalmente, seleccione el icono que representa esta actividad.
   - **Tipo de actividad**: Defina la referencia del tipo de actividad como Common Data Model que mejor describe la definición semántica de la actividad.

1. En la sección **Configurar relación**, configure los detalles que se utilizarán para conectar los datos de actividad a su cliente correspondiente.

    - **Campo de entidad de actividad**: seleccione el campo en su entidad Actividad que se utilizará para establecer una relación con otra entidad.
    - **Entidad de cliente**: seleccione la entidad de cliente origen correspondiente con la que estará relacionada su entidad de actividad. Puede relacionarse solo con aquellas entidades de clientes de origen que se utilizan en el proceso de unificación de datos.
    - **Campo de entidad de cliente**: este campo muestra la clave principal de la entidad del cliente de origen seleccionada en el proceso de asignación. Este campo de clave principal en la entidad del cliente de origen se utiliza para establecer una relación con la entidad de actividad.
    - **Nombre**: si ya existe una relación entre esta entidad de actividad y la entidad de cliente de origen seleccionada, el nombre de la relación estará en modo de solo lectura. Si no existe tal relación, se creará una nueva relación con el nombre proporcionado aquí.
   
   > [!div class="mx-imgBorder"]
   > ![Definir la relación de entidad](media/activities-entities-define.png "Definir la relación de entidad")

1. Seleccione **Guardar** para aplicar los cambios.

1. En la página **Actividades**, seleccione **Ejecutar**.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="edit-an-activity"></a>Editar una actividad

1. En informaciones del público, vaya a **Datos** > **Ocupaciones**.

2. Seleccione la entidad de la actividad que quiere editar y seleccione **Editar**. O bien, puede pasar el cursor sobre la fila de la entidad y seleccionar el icono **Editar**.

3. Haga clic en el icono **Editar**.

4. En el panel **Editar actividad**, actualice los valores y seleccione **Guardar**.

5. En la página **Actividades**, seleccione **Ejecutar**.

## <a name="delete-an-activity"></a>Eliminar una actividad

1. En informaciones del público, vaya a **Datos** > **Ocupaciones**.

2. Seleccione la entidad de la actividad que quiere quitar y seleccione **Eliminar**. O bien, puede pasar el cursor sobre la fila de la entidad y seleccionar el icono **Eliminar**. Además, puede seleccionar varias entidades de actividad para eliminarlas a la vez.
   > [!div class="mx-imgBorder"]
   > ![Editar o eliminar las relaciones entre entidades](media/activities-entities-edit-delete.png "Editar o eliminar las relaciones entre entidades")

3. Seleccione el icono **Eliminar**.

4. Confirme la eliminación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]