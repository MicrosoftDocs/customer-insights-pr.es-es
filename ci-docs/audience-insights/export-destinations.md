---
title: Exportar datos de Customer Insights
description: Administrar exportaciones para compartir datos.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253061"
---
# <a name="exports-preview-overview"></a>Información general del exportaciones (versión preliminar)

La página **Exportaciones** muestra todas las exportaciones configuradas. Las exportaciones comparten datos específicos con varias aplicaciones. Pueden incluir perfiles de clientes o entidades, esquemas y detalles de mapeo. Cada exportación requiere una [conexión, configurada por un administrador, para administrar la autenticación y el acceso](connections.md).

Vaya a **Datos** > **Exportaciones** para ver la página de exportaciones. Todos los roles de usuario tienen acceso para ver las exportaciones configuradas. Uso del campo de búsqueda en la barra de comandos para buscar exportaciones por su nombre, nombre de conexión o tipo de conexión.

## <a name="set-up-a-new-export"></a>Configurar una nueva exportación

Para configurar o editar una exportación, debe tener conexiones disponibles. Las conexiones dependen de su [rol del usuario](permissions.md):
- Los administradores tienen acceso a todas las conexiones. También pueden crear nuevas conexiones al configurar una exportación.
- Los colaboradores pueden tener acceso a conexiones específicas. Dependen de los administradores para configurar y compartir conexiones. La lista de exportaciones muestra a los contribuyentes si pueden editar o solo ver una exportación en la columna **Sus permisos**. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Los visores solo pueden ver las exportaciones existentes, pero no crearlas.

### <a name="define-a-new-export"></a>Definir una nueva exportación

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, seleccione **Agregar exportación**.

1. En el panel **Configurar exportación**, seleccione qué conexión usar. Las [conexiones](connections.md) son administradas por administradores. 

1. Proporcione los detalles requeridos y seleccione **Guardar** para crear la exportación.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definir una nueva exportación basada en una exportación existente

1. Vaya a **Datos** > **Exportaciones**.

1. En la lista de exportaciones, seleccione la exportación que desea duplicar.

1. Seleccione **Crear duplicado** en la barra de comandos para abrir el panel **Configurar exportación** con los detalles de la exportación seleccionada.

1. Revise y adapte la exportación y seleccione **Guardar** para crear una nueva exportación.

### <a name="edit-an-export"></a>Editar una exportación

1. Vaya a **Datos** > **Exportaciones**.

1. En la lista de exportaciones, seleccione la exportación que desea editar.

1. En la barra de comandos, seleccione **Editar**.

1. Cambie los valores que desea actualizar y seleccione **Guardar**.

## <a name="view-exports-and-export-details"></a>Ver exportaciones y detalles de exportación

Después de crear los destinos de la exportación, se enumeran en **Datos** > **Exportaciones**. Todos los usuarios pueden ver qué datos se comparten y su estado más reciente.

1. Vaya a **Datos** > **Exportaciones**.

1. Los usuarios sin permisos de edición seleccionan **Vista** en vez de **Editar** para ver los detalles de la exportación.

1. El panel lateral muestra la configuración de una exportación. Sin permisos de edición, no puede cambiar valores. Seleccione **Cerrar** para volver a la página de exportaciones.

## <a name="schedule-and-run-exports"></a>Programar y ejecutar exportaciones

Cada exportación que configure tiene un programa de actualización. Durante una actualización, el sistema busca datos nuevos o actualizados para incluirlos en una exportación. De forma predeterminada, las exportaciones se ejecutan como parte de cada [actualización programada del sistema](system.md#schedule-tab). Puede personalizar el programa de actualización o desactivarlo para ejecutar exportaciones manualmente.

Los programas de exportación dependen del estado de su entorno. Si hay actualizaciones en [dependencias](system.md#refresh-policies) en curso cuando debe comenzar una exportación programada, el sistema primero completará las dependencias y luego ejecutará la exportación. Puede ver cuándo se actualizó por última vez una exportación en la columna **Actualizado**.

### <a name="schedule-exports"></a>Programar exportaciones

Usted puede definir programas de actualización personalizados para exportaciones individuales o varias exportaciones a la vez. El horario definido actualmente se enumera en la columna **Programación** de la lista de exportación. El permiso para cambiar el horario es el mismo que para [editar y definir exportaciones](export-destinations.md#set-up-a-new-export). 

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione la exportación que quiere programar.

1. En la barra de comandos, seleccione **Programar**.

1. En el panel **Exportación programada**, establezca **Programar ejecución** a **Activado** para ejecutar la exportación automáticamente. Establézcalo en **Desactivado** para actualizarlo manualmente.

1. Para exportaciones actualizadas automáticamente, elija un valor de **Periodicidad** y especifique los detalles para ello. El tiempo definido se aplica a todas las instancias de una periodicidad. Es el momento en que una exportación debería comenzar a actualizarse.

1. Aplique y active sus cambios seleccionando **Guardar**.

Al editar la programación de varias exportaciones, debe realizar una selección en **Mantener o invalidad programaciones**:
- **Mantener programaciones individuales**: conserva la programación previamente definida para las exportaciones seleccionadas y solo deshabilitarlas o habilitarlas.
- **Definir un nuevo programa para todas las exportaciones seleccionadas**: anula las programaciones existentes de las exportaciones seleccionadas.

### <a name="run-exports-on-demand"></a>Ejecutar exportaciones según las necesidades

Para exportar datos sin esperar una actualización programada, vaya a **Datos** > **Exportaciones**.

- Para ejecutar todas las exportaciones, seleccione **Ejecutar todo** en la barra de comandos. Esta acción solo ejecutará exportaciones que tengan una programación activa.
- Para ejecutar una sola exportación, selecciónela en la lista y seleccione **Ejecutar** en la barra de comandos. Así es como se ejecutan las exportaciones sin una programación activa. 

## <a name="remove-an-export"></a>Quitar una exportación

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione la exportación que desee quitar.

1. En la barra de comandos, seleccione **Quitar**.

1. Confirme la eliminación seleccionando **Quitar** en la pantalla de confirmación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
