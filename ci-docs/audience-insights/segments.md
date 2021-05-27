---
title: Segmentos de conclusiones del público
description: Descripción general de los segmentos y cómo crearlos y gestionarlos.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034033"
---
# <a name="segments-overview"></a>Información general de los segmentos

Los segmentos le permite agrupar a los clientes según los atributos demográficos, transaccionales o de comportamiento. Puede usar segmentos para dirigir a los clientes campañas promocionales, actividades de ventas y acciones de atención al cliente con el fin de lograr sus objetivos empresariales.

Los perfiles de clientes que coinciden con los filtros de una definición de segmento se denominan *miembros* de un segmento. Se aplican algunos [límites de servicio](service-limits.md).

## <a name="create-a-new-segment"></a>Crear un nuevo segmento

Hay múltiples formas de crear un nuevo segmento: 

- Segmento complejo con creador de segmentos: [Segmento en blanco](segment-builder.md#create-a-new-segment)
- Segmentos simples con un operador: [Segmento rápido](segment-builder.md#quick-segments)
- Forma con tecnología de IA para encontrar clientes similares: [Clientes similares](find-similar-customer-segments.md)
- Sugerencias con tecnología de IA basadas en medidas o atributos: [Segmentos sugeridos para mejorar las medidas](suggested-segments.md)
- Sugerencias basadas en actividades: [Segmentos sugeridos basados en la actividad del cliente](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Obtener conocimientos sobre los segmentos existentes

Descubra información adicional sobre sus segmentos existentes con [Conocimientos sobre segmentos](segment-insights.md). Descubra qué diferencia a dos segmentos o qué tienen en común.

## <a name="find-similar-customers"></a>Buscar clientes similares

Encuentre clientes que sean similares a los miembros de un segmento seleccionado con la ayuda de la inteligencia artificial. Para más información, consulte [Clientes similares](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Administrar segmentos existentes

Vaya a la página **Segmentos** para ver todos los segmentos guardados y administrarlos.

Cada segmento está representado por una fila que incluye información adicional sobre el segmento.

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

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
