---
title: Crear y administrar medidas
description: Defina medidas para analizar y reflejar el rendimiento y el estado de su negocio.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304827"
---
# <a name="define-and-manage-measures"></a>Definir y administrar medidas

Las medidas le ayudan a comprender mejor los comportamientos de los clientes y el desempeño comercial. Se fijan en valores relevantes de los [perfiles unificados](data-unification.md). Por ejemplo, una empresa quiere ver el *gasto total por cliente* para comprender el historial o la medida de compra de un cliente individual de *ventas totales de la empresa* para comprender los ingresos a nivel agregado en toda la empresa.  

Las medidas se crean utilizando el generador de medidas, una plataforma de consulta de datos con varios operadores y opciones de asignación sencillas. Le permite filtrar los datos, agrupar resultados, detectar [rutas de relaciones de entidades](relationships.md) y obtener una vista previa de los resultados.

Utilice el generador de medidas para planificar actividades comerciales consultando datos de clientes y extraiga información. Por ejemplo, crear una medida del *gasto total por cliente* y el *retorno total por cliente* ayuda a identificar un grupo de clientes con un alto gasto pero que aporta alto rendimiento. Puede [crear un segmento](segments.md) para impulsar las acciones más convenientes. 

## <a name="build-your-own-measure-from-scratch"></a>Crear su propia medida desde cero

Esta sección le guía a través de la creación de nuevas medidas desde cero. Puede crear una medida con atributos de datos a partir de entidades de datos que tengan una relación configurada para conectarse con la entidad Cliente. 

1. En las informaciones de público, vaya a **Medidas**.

1. Seleccione **Nuevo** y elija **Crear el suyo propio**.

1. Seleccione **Editar nombre** y proporcione un **Nombre** para la medida. 
   > [!NOTE]
   > Si su nueva configuración de medida tiene solo dos campos, por ejemplo, CustomerID y un cálculo, la salida se agregará como una nueva columna a la entidad generada por el sistema llamada Customer_Measure. Y podrá ver el valor de la medida en el perfil del cliente unificado. Otras medidas generarán sus entidades propias.

1. En el área de configuración, elija la función de agregación en el menú desplegable **Seleccionar función**. Las funciones de agregación incluyen: 
   - **Sum**
   - **Media**
   - **Contar**
   - **Contar únicos**
   - **Máximo**
   - **Min**
   - **Primero**: toma el primer valor del registro de datos
   - **Último**: toma el último valor que se agregó al registro de datos

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. Seleccione **Agregar atributo** para seleccionar los datos que necesita para crear esta medida.
   
   1. Seleccione la pestaña **Atributos**. 
   1. Entidad de datos: elija la entidad que incluye el atributo que desea medir. 
   1. Atributo de datos: elija el atributo que desea utilizar en la función de suma para calcular la medida. Puede seleccionar solo un atributo a la vez.
   1. También puede seleccionar un atributo de datos en una medida existente seleccionando la pestaña **Medidas**. O bien, puede buscar una entidad o nombre de medida. 
   1. Seleccione **Agregar** para agregar el atributo seleccionado a la medida.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccione un atributo para usar en los cálculos.":::

1. Para construir medidas más complejas, puede agregar más atributos o usar operadores matemáticos en su función de medida.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cree una medida compleja con operadores matemáticos.":::

1. Para agregar filtros, seleccione la opción **Filtrar** en el área de configuración. 
  
   1. En la sección **Agregar atributo** del panel **Filtros**, seleccione el atributo que desea utilizar para crear filtros.
   1. Configure los operadores de filtro para definir el filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar** para agregar los filtros para la medida.

1. Para agregar dimensiones, seleccione la opción **Dimensión** en el área de configuración. Las dimensiones se mostrarán a modo de columnas en la entidad de los resultados de la medida.
 
   1. Seleccione **Editar dimensiones** para agregar los atributos de datos según los cuales desea agrupar los valores de medida. Por ejemplo, ciudad o género. De forma predeterminada, la dimensión *CustomerID* se selecciona crear *medidas a nivel de cliente*. Puede eliminar la dimensión predeterminada si desea crear *medidas a nivel empresarial*.
   1. Seleccione **Listo** para agregar dimensiones a la medida.

1. Si hay valores en sus datos que necesita reemplazar con un número entero, por ejemplo, reemplace *NULL* con *0* y seleccione **Reglas**. Configure la regla y asegúrese de elegir solo números enteros como sustitución.

1. Si hay varias rutas entre la entidad de datos que asignó y la entidad *Cliente*, debe elegir una de las [rutas de relación de entidad identificadas](relationships.md). Los resultados de la medición pueden variar según la ruta seleccionada. 
   
   1. Seleccione **Preferencias de datos** y elija la ruta de la entidad que se debe utilizar para identificar su medida. Si solo hay un camino hacia la entidad *Cliente*, este control no se mostrará.
   1. Seleccione **Listo** para aplicar su selección. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccione la ruta de la entidad para la medida.":::

1. Para agregar más cálculos para la medida, seleccione **Nuevo cálculo**. Solo puede usar entidades en la misma ruta de la entidad para los nuevos cálculos. Aparecerán más cálculos a modo de columnas nuevas en la entidad de los resultados de la medida.

1. Seleccione **...** en el cálculo para **Duplicar**, **Cambiar el nombre**, o **Eliminar** un cálculo de una medida.

1. En el área **Vista previa**, verá el esquema de datos de la entidad de los resultados de la medida, incluidos los filtros y las dimensiones. La vista previa reacciona dinámicamente a los cambios en la configuración.

1. Seleccione **Ejecutar** para calcular los resultados de la medida configurada. Seleccione **Guardar y cerrar** si desea mantener la configuración actual y ejecutar la medida más tarde.

1. Vaya a **Medidas** para ver la medida recién creada en la lista.

## <a name="use-a-template-to-build-a-measure"></a>Usar una plantilla para construir una medida

Puede utilizar plantillas predefinidas de medidas de uso común para crearlas. Las descripciones detalladas de las plantillas y una experiencia guiada le ayudan a crear medidas de manera eficiente. Las plantillas se basan en datos asignados de la entidad *Actividad unificada*. Así que asegúrese de haber configurado [actividades del cliente](activities.md) antes de crear una medida a partir de una plantilla.

Plantillas de medida disponibles: 
- Valor medio de transacción (ATV)
- Valor total de la transacción
- Ingresos medios diarios
- Ingresos medios anuales
- Recuento de transacciones
- Puntos de fidelización ganados
- Puntos de fidelización canjeados
- Saldo de puntos de fidelización
- Vida útil activa del cliente
- Duración de suscripción de fidelización
- Tiempo desde la última compra

El siguiente procedimiento describe los pasos para crear una nueva medida usando una plantilla.

1. En las informaciones de público, vaya a **Medidas**.

1. Seleccione **Nuevo** y seleccione **Elegir una plantilla**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla del menú desplegable al crear una nueva medida con resaltado en la plantilla.":::

1. Encuentre la plantilla que se adapte a sus necesidades y seleccione **Elegir plantilla**.

1. Revise los datos requeridos y seleccione **Comenzar** si tiene todos los datos en su lugar.

1. En el panel **Editar nombre**, establezca el nombre de su medida y la entidad de salida. 

1. Seleccione **Listo**.

1. En la sección **Establecer período de tiempo**, defina el período de tiempo de los datos a utilizar. Elija si desea que la nueva medida cubra todo el conjunto de datos seleccionando **Todo el tiempo** o si desea que la medida se centre en un **Período de tiempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que muestra la sección del período de tiempo al configurar una medida a partir de una plantilla.":::

1. En la siguiente sección, seleccione **Agregar datos** para elegir las actividades y asignar los datos correspondientes a partir de su entidad *Actividad unificada*.

    1. Paso 1 de 2: En **Tipo de actividad**, elija el tipo de entidad que desea utilizar. Para **Actividades**, seleccione las entidades que desea asignar.
    1. Paso 2 de 2: Elija el atributo de la entidad *Actividad unificada* para el componente requerido por la fórmula. Por ejemplo, para el valor de transacción promedio, es el atributo que representa el valor de la transacción. Para **Marca de tiempo de la actividad**, elija el atributo de la entidad Actividad unificada que representa la fecha y hora de la actividad.
   
1. Una vez que la asignación de datos se haya realizado correctamente, puede ver el estado como **Completo** y el nombre de las actividades y atributos asignadas.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de pantalla de una configuración de plantilla de medida completa.":::

1. Ahora puede seleccionar **Ejecutar** para calcular los resultados de la medida. Para refinarlo más tarde, seleccione **Guardar borrador**.

## <a name="manage-your-measures"></a>Administrar sus medidas

Puede encontrar la lista de medidas en la página **Medidas**.

Encontrará información sobre el tipo de medida, el creador, la fecha de creación y el estado. Cuando selecciona una medida de la lista, puede obtener una vista previa del resultado y descargar un archivo CSV.

Para actualizar todas sus medidas al mismo tiempo, seleccione **Actualizar todo** sin seleccionar una medida específica.

> [!div class="mx-imgBorder"]
> ![Acciones para gestionar medidas individuales](media/measure-actions.png "Acciones para gestionar medidas individuales.").

Seleccione una medida de la lista para las siguientes opciones:

- Seleccione el nombre de la medida para ver sus detalles.
- **Editar** la configuración de la medida.
- **Actualizar** la medida en función de los últimos datos.
- **Cambiar nombre** de la medida.
- **Eliminar** la medida.
- **Activar** o **Desactivar**. Las medidas inactivas no se actualizarán durante una [actualización programada](system.md#schedule-tab).

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, la última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="next-step"></a>Siguiente paso

Puede utilizar medidas existentes para crear [un segmento de clientes](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
