---
title: Crear y gestionar segmentos
description: Cree segmentos de clientes para agruparlos en función de diversos atributos.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597081"
---
# <a name="create-and-manage-segments"></a>Crear y gestionar segmentos

Los segmentos le permite agrupar a los clientes según los atributos demográficos, transaccionales o de comportamiento. Puede usar segmentos para dirigir a los clientes campañas promocionales, actividades de ventas y acciones de atención al cliente con el fin de lograr sus objetivos empresariales.

Puede definir filtros complejos alrededor de la entidad Perfil del cliente y sus entidades relacionadas. Cada segmento, después del procesamiento, crea un conjunto de registros de entidades del cliente que puede exportar y sobre los que puede actuar. Se aplican algunos [límites de servicio](service-limits.md).

A menos que se indique lo contrario, todos los segmentos son **Segmentos dinámicos**, que se actualizan con programación periódica.

El siguiente ejemplo ilustra la capacidad de segmentación. Hemos definido un segmento para clientes que pidieron bienes por una cantidad mínima de $500 en los últimos 90 días *y* que participaron en una llamada de servicio al cliente que se escaló.

> [!div class="mx-imgBorder"]
> ![Varios grupos](media/segmentation-group1-2.png "Varios grupos")

## <a name="create-a-new-segment"></a>Crear un nuevo segmento

Los segmentos se gestionan en la página **Segmentos**.

1. En las informaciones de público, vaya a la página **Segmentos**.

1. Seleccione **Nuevo** > **Segmento en blanco**.

1. En el panel **Nuevo segmento**, elija un tipo de segmento y proporcione un **Nombre**.

   Opcionalmente, proporcione un nombre y una descripción que ayude a identificar el segmento.

1. Seleccione **Siguiente** para llegar a la página **Generador de segmentos**, donde define un grupo. Un grupo es un conjunto de clientes.

1. Elija la entidad que incluye el atributo por la que desea segmentar.

1. Elija el atributo de segmentación. Este atributo puede tener uno de los cuatro tipos de valores siguientes: numérico, cadena, fecha o booleano.

1. Elija un operador y un valor para el atributo seleccionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo del cliente")

   |Número |Definición  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |valor         |

8. Si la entidad está conectada a la entidad unificada del cliente a través de [relaciones](relationships.md), debe definir la ruta de relación para crear un segmento válido. Agregue las entidades de la ruta de relación hasta que pueda seleccionar la entidad **Customer : CustomerInsights** del menú desplegable. Luego escoja **Todos los registros** para cada condición.

   > [!div class="mx-imgBorder"]
   > ![Ruta de relación durante la creación del segmento](media/segments-multiple-relationships.png "Ruta de relación durante la creación del segmento")

1. De forma predeterminada, los segmentos generan una entidad de salida que contiene todos los atributos de los perfiles de clientes que coinciden con los filtros definidos. Si un segmento se basa en otras entidades distintas a la entidad *Cliente*, puede agregar más atributos de estas entidades a la entidad de salida. Seleccione **Atributos del proyecto** para elegir los atributos que se agregarán a la entidad de salida.  

   
   Ejemplo: un segmento se basa en una entidad que contiene datos de actividad del cliente que están relacionados con la entidad *Cliente*. El segmento busca a todos los clientes que llamaron a la mesa de ayuda en los últimos 60 días. Puede optar por agregar la duración de la llamada y el número de llamadas a todos los registros de clientes coincidentes en la entidad de salida. Esta información puede resultar útil para enviar un correo electrónico con vínculos útiles a artículos de ayuda en línea y preguntas frecuentes a los clientes que llaman con frecuencia.

1. Seleccione **Guardar** para guardar el segmento. Su segmento se guardará y procesará si se validan todos los requisitos. De lo contrario, se guardará como borrador.

1. Seleccione **Volver a Segmentos** para volver a la página **Segmentos**.

## <a name="manage-existing-segments"></a>Administrar segmentos existentes

En la página **Segmentos** puede ver todos sus segmentos guardados y administrarlos.

Cada segmento está representado por una fila que incluye información adicional sobre el segmento.

Puede ordenar los segmentos en una columna seleccionando el encabezado de la columna.

Use el cuadro **Buscar** en la esquina superior derecha para filtrar los segmentos.

> [!div class="mx-imgBorder"]
> ![Opciones para administrar un segmento ya existente](media/segments-selected-segment.png "Opciones para administrar un segmento ya existente")

Las siguientes acciones están disponibles cuando selecciona un segmento:

- **Ver** los detalles del segmento, incluida la tendencia del recuento de miembros de una vista previa de los miembros del segmento.
- **Editar** el segmento para cambiar sus propiedades.
- **Crear duplicado** de un segmento. Puede elegir editar sus propiedades de inmediato o simplemente guardar el duplicado.
- **Actualizar** el segmento para incluir los últimos datos.
- **Activar** o **Desactivar** el segmento. Los segmentos tienen dos estados posibles: activo o inactivo. Estos estados resultan útiles al editar un segmento. Para los segmentos inactivos, existe la definición de segmento, pero aún no contiene ningún cliente. Cuando activa un segmento, su estado cambia de "inactivo" a "activo" y comienza a buscar clientes que coincidan con la definición del segmento. Si una [actualización programada](system.md#schedule-tab) está configurada, los segmentos inactivos tienen el **Estado** catalogado como **Omitido**, lo que indica que ni siquiera se intentó una actualización. Cuando se activa un segmento inactivo, se actualizará y se incluirá en las actualizaciones programadas.
  Alternativamente, puede usar la funcionalidad **Programar más tarde** en el desplegable **Activar/Desactivar** para especificar una fecha y hora futuras para la activación y desactivación de un segmento en particular.
- **Cambiar nombre** de segmento.
- **Descargar** la lista de miembros como archivo .CSV.
- La opción **Agregar a** envía la lista de ID de cliente en el segmento para su procesamiento en otra aplicación.
- **Eliminar** el segmento.

## <a name="refresh-segments"></a>Actualizar segmentos

Puede actualizar todos los segmentos a la vez seleccionando **Actualizar todo** en la página **Segmentos** o puede actualizar uno o varios segmentos cuando los selecciona y elige **Actualizar** desde las opciones. Alternativamente, puede configurar una actualización periódica en **Administración** > **Sistema** > **Programar**.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="download-and-export-segments"></a>Descargar y exportar segmentos

Puede descargar segmentos a un archivo CSV o exportarlos a Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Descargar segmentos en un archivo CSV

1. En las informaciones de público, vaya a la página **Segmentos**.

2. Seleccione los puntos suspensivos en el mosaico de un segmento específico.

3. Seleccione **Descargar como CSV** en la lista desplegable de acciones.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportar segmentos a Dynamics 365 Sales

Antes de exportar segmentos a Dynamics 365 Sales, un administrador debe [crear el destino de exportación](export-destinations.md) para Dynamics 365 Sales.

1. En las informaciones de público, vaya a la página **Segmentos**.

2. Seleccione los puntos suspensivos en el mosaico de un segmento específico.

3. Seleccione **Agregar a** en la lista desplegable de acciones y seleccione el destino de exportación al que desee enviar los datos.

## <a name="draft-mode-for-segments"></a>Modo borrador para segmentos

Si no se cumplen todos los requisitos para procesar un segmento, puede guardar el segmento como borrador y acceder a él desde la página **Segmentos**.

Se guardará como segmento inactivo y no se puede activar hasta que sea válido.

## <a name="add-more-conditions-to-a-group"></a>Agregar más condiciones a un grupo

Para agregar más condiciones a un grupo, puede usar dos operadores lógicos:

- Operador **AND**: Ambas condiciones deben cumplirse como parte del proceso de segmentación. Esta opción es más útil cuando define condiciones en diferentes entidades.

- Operador **OR**: Cualquiera de las condiciones debe cumplirse como parte del proceso de segmentación. Esta opción es más útil cuando define varias condiciones para la misma entidad.

   > [!div class="mx-imgBorder"]
   > ![Operador OR donde cualquiera de las condiciones debe cumplirse](media/segmentation-either-condition.png "Operador OR donde cualquiera de las condiciones debe cumplirse")

Actualmente es posible anidar una operador **OR** bajo un operador **AND**, pero no al revés.

## <a name="combine-multiple-groups"></a>Combinar varios grupos

Cada grupo produce un conjunto específico de clientes. Puede combinar estos grupos para incluir a los clientes necesarios para su caso de negocios.

1. En las informaciones de público, vaya a la página **Segmentos** y seleccione un segmento.

2. Seleccione **Agregar grupo**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes agregar grupo](media/customer-group-add-group.png "Grupo de clientes agregar grupo")

3. Seleccione uno de los siguientes operadores de conjuntos: **Unión**, **Intersección** o **Excepto**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes agregar unión](media/customer-group-union.png "Grupo de clientes agregar unión")

   Seleccione un operador de conjuntos para definir un nuevo grupo. Guarde diferentes grupos para determinar qué datos se mantienen:

   - **Unión** une los dos grupos.

   - **Intersección** superpone los dos grupos. Solo se retienen en el grupo unificado los datos que *son comunes* a ambos grupos.

   - **Exceptuar** combina los dos grupos. Solo se retienen en el grupo A los datos que *no son comunes* a los datos del grupo B.

## <a name="view-processing-history-and-segment-members"></a>Ver el historial de procesamiento y los miembros del segmento

Puede ver datos consolidados sobre un segmento revisando sus detalles.

En la página **Segmentos**, seleccione el segmento que desea revisar.

La parte superior de la página incluye un gráfico de tendencia que visualiza cambios en el recuento de miembros. Pase el puntero sobre los puntos de datos para ver el recuento de miembros en una fecha específica.

Puede actualizar el período de tiempo de la visualización.

> [!div class="mx-imgBorder"]
> ![Segmentar intervalo de tiempo](media/segment-time-range.png "Segmentar intervalo de tiempo")

La parte inferior contiene una lista de los miembros del segmento.

> [!NOTE]
> Los campos que aparecen en esta lista se basan en los atributos de las entidades de su segmento.
>
>La lista es una vista previa de los miembros del segmento coincidentes y muestra los primeros 100 registros de su segmento para que pueda evaluarlo rápidamente y revisar sus definiciones si es necesario. Para ver todos los registros coincidentes, debe [exportar el segmento](export-destinations.md).

## <a name="quick-segments"></a>Segmentos rápidos

Además del generador de segmentos, hay otra ruta para crear segmentos. Los segmentos rápidos le permiten crear segmentos simples con un solo operador rápidamente y con información instantánea.

1. En la página **Segmentos**, seleccione **Nuevo** > **Crear rápidamente desde**.

   - Seleccione la opción **Perfiles** para construir un segmento basado en la entidad del cliente unificada.
   - Seleccione la opción **Medidas** para crear un segmento alrededor de cada uno de los tipos de medidas de Atributo del cliente que haya creado previamente en la página **Medidas**.
   - Selecciona la opción **Inteligencia** para crear un segmento alrededor de una de las entidades de salida que generó con las capacidades **Predicciones** o **Modelos personalizados**.

2. En el cuadro de diálogo **Nuevo segmento rápido**, seleccione un atributo en el campo desplegable **Campo**.

3. El sistema proporcionará información adicional que le ayudará a crear mejores segmentos de sus clientes.
   - Para los campos categóricos, mostraremos los 10 principales recuentos de clientes. Elija un **Valor** y seleccione **Revisar**.

   - Para un atributo numérico, el sistema mostrará qué valor de atributo corresponde al percentil de cada cliente. Elija un **Operador** y un **Valor**, luego seleccione **Revisar**.

4. El sistema le proporcionará un **Tamaño de segmento estimado**. Puede elegir si genera el segmento que ha definido o volver a visitarlo para obtener un tamaño de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nombre y estimación de un segmento rápido](media/quick-segment-name.png "Nombre y estimación de un segmento rápido")

5. Dé un **Nombre** al segmento. Opcionalmente, proporcione un **Nombre para mostrar**.

6. Seleccione **Guardar** para crear el segmento.

7. Una vez que el segmento ha terminado de procesarse, puede verlo como cualquier otro segmento que haya creado.

Para los siguientes escenarios, recomendamos utilizar el generador de segmentos en lugar de la capacidad de segmentos recomendada:

- Crear segmentos con filtros en campos categóricos donde el operador es diferente al operador **Es**
- Crear segmentos con filtros en campos numéricos donde el operador es diferente a los operadores **Entre**, **Mayor que** y **Menor que**
- Crear segmentos con filtros en campos de tipo de fecha

## <a name="next-steps"></a>Pasos siguientes

[Exportar un segmento](export-destinations.md) y explorar la [Tarjeta de cliente](customer-card-add-in.md) y [Conectores](export-power-bi.md) para obtener información a nivel del cliente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]