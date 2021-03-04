---
title: Crear y administrar medidas
description: Defina medidas para analizar y reflejar el rendimiento y el estado de su negocio.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269949"
---
# <a name="define-and-manage-measures"></a>Definir y administrar medidas

Las medidas le ayudan a comprender mejor el comportamiento de los clientes y el rendimiento de la empresa recuperando valores relevantes de los [perfiles unificados](data-unification.md). Por ejemplo, una empresa quiere ver el *gasto total por cliente* para comprender el historial de compras de cada cliente. O medir las *ventas totales de la empresa* para comprender los ingresos a globales en la totalidad de la empresa.  

Las medidas se crean utilizando el generador de medidas, una plataforma de consulta de datos con varios operadores y opciones de asignación sencillas. Le permite filtrar los datos, agrupar resultados, detectar [rutas de relaciones de entidades](relationships.md) y obtener una vista previa de los resultados.

Utilice el generador de medidas para planificar actividades comerciales consultando datos de clientes y extraiga información. Por ejemplo, crear una medida del *gasto total por cliente* y el *retorno total por cliente* ayuda a identificar un grupo de clientes con un alto gasto pero que aporta alto rendimiento. Puede [crear un segmento](segments.md) para impulsar las acciones más convenientes. 

## <a name="create-a-measure"></a>Crear una medida

Esta sección le guía a través de la creación de nuevas medidas desde cero. Puede crear una medida con atributos de datos a partir de entidades de datos que tengan una relación configurada para conectarse con la entidad Cliente. 

1. En las informaciones de público, vaya a **Medidas**.

1. Seleccione **Nuevo**.

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

1. Si hay varias rutas entre la entidad de datos que asignó y la entidad Cliente, debe elegir una de las [rutas de relación de entidad](relationships.md) identificadas. Los resultados de la medición pueden variar según la ruta seleccionada.
   1. Seleccione **Preferencias de datos** y elija la ruta de la entidad que se debe utilizar para identificar su medida.
   1. Seleccione **Listo** para aplicar su selección. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccione la ruta de la entidad para la medida.":::

1. Para agregar más cálculos para la medida, seleccione **Nuevo cálculo**. Solo puede usar entidades en la misma ruta de la entidad para los nuevos cálculos. Aparecerán más cálculos a modo de columnas nuevas en la entidad de los resultados de la medida.

1. Seleccione **...** en el cálculo para **Duplicar**, **Cambiar el nombre**, o **Eliminar** un cálculo de una medida.

1. En el área **Vista previa**, verá el esquema de datos de la entidad de los resultados de la medida, incluidos los filtros y las dimensiones. La vista previa reacciona dinámicamente a los cambios en la configuración.

1. Seleccione **Ejecutar** para calcular los resultados de la medida configurada. Seleccione **Guardar y cerrar** si desea mantener la configuración actual y ejecutar la medida más tarde.

1. Vaya a **Medidas** para ver la medida recién creada en la lista.

## <a name="manage-your-measures"></a>Administrar sus medidas

Después de [crear una medida](#create-a-measure), verá una lista de medidas en la página **Medidas**.

Encontrará información sobre el tipo de medida, el creador, la fecha de creación y el estado. Cuando selecciona una medida de la lista, puede obtener una vista previa del resultado y descargar un archivo .CSV.

Para actualizar todas sus medidas al mismo tiempo, seleccione **Actualizar todo** sin seleccionar una medida específica.

> [!div class="mx-imgBorder"]
> ![Acciones para gestionar medidas individuales](media/measure-actions.png "Acciones para gestionar medidas individuales")

Seleccione una medida de la lista para las siguientes opciones:

- Seleccione el nombre de la medida para ver sus detalles.
- **Editar** la configuración de la medida.
- **Actualizar** la medida en función de los últimos datos.
- **Cambiar nombre** de la medida.
- **Eliminar** la medida.
- **Activar** o **Desactivar**. Las medidas inactivas no se actualizarán durante una [actualización programada](system.md#schedule-tab).

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="next-step"></a>Siguiente paso

Puede utilizar medidas existentes para crear [un segmento de cliente](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]