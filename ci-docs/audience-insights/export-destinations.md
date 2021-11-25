---
title: Exportar datos de Customer Insights
description: Administrar exportaciones para compartir datos.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: bff0486fdb3a02ecb0aa86e81abe1c506e234bc5
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732184"
---
# <a name="exports-preview-overview"></a>Información general del exportaciones (versión preliminar)

La página **Exportaciones** muestra todas las exportaciones configuradas. Las exportaciones comparten datos específicos con varias aplicaciones. Pueden incluir perfiles de clientes, entidades, esquemas y detalles de asignación. Cada exportación requiere una [conexión, configurada por un administrador, para administrar la autenticación y el acceso](connections.md).

Vaya a **Datos** > **Exportaciones** para ver la página de exportaciones. Todos los roles de usuario pueden ver las exportaciones configuradas. Utilice el campo de búsqueda en la barra de comandos para buscar exportaciones por su nombre, nombre de conexión o tipo de conexión.

## <a name="export-types"></a>Tipos de exportación

Hay dos tipos principales de exportaciones:  

- **Exportaciones de salida de datos** le permite exportar cualquier tipo de entidad disponible en conclusiones del público. Las entidades que seleccione para exportar se exportan con todos los campos de datos, metadatos, esquemas y detalles de asignación. 
- **Exportaciones de segmentos** le permite exportar entidades de segmento desde conclusiones del público. Los segmentos representan una lista de perfiles de clientes. Al configurar la exportación, seleccione los campos de datos incluidos, según el sistema de destino al que está exportando los datos. 

### <a name="export-segments"></a>Exportar segmentos

**Exportación de segmentos en entornos para cuentas de negocio (B2B) o consumidores individuales (B2C)**  
La mayoría de las opciones de exportación admiten ambos tipos de entornos. La exportación de segmentos a diversos sistemas de destino tiene requisitos específicos. En términos generales, un miembro del segmento, el perfil del cliente, contiene información de contacto. Si bien este suele ser el caso de los segmentos basados en consumidores individuales (B2C), no es necesariamente el caso de los segmentos basados en cuentas de negocio (B2B). 

**Entornos de exportación de segmentos para cuentas de negocio (B2B)**  
- Los segmentos en el contexto de entornos para cuentas de negocio se basan en la entidad *cuenta*. Para exportar segmentos de cuenta tal como están, el sistema de destino debe admitir segmentos de cuenta puros. Este es el caso de [LinkedIn](export-linkedin-ads.md) cuando elige la opción **empresa** al definir la exportación.
- Todos los demás sistemas de destino requieren campos de la entidad de contacto. Para garantizar que los segmentos de cuenta puedan recuperar datos de contactos relacionados, la definición de segmento debe proyectar los atributos de la entidad de contacto. Más información sobre cómo [configurar segmentos y atributos del proyecto](segment-builder.md).

**Exportación de segmentos en entornos para consumidores individuales (B2C)**  
- Los segmentos en el contexto de entornos para clientes individuales se basan en la entidad *perfil de cliente unificado*. Se puede exportar cada segmento que cumpla con los requisitos de los sistemas de destino (por ejemplo, una dirección de correo electrónico).

**Límites a las exportaciones de segmentos**  
- Los sistemas de destino de terceros pueden limitar la cantidad de perfiles de clientes que puede exportar. 
- Para clientes individuales, verá el número real de miembros del segmento cuando seleccione un segmento para exportar. Recibirá una advertencia si un segmento es demasiado grande. 
- Para cuentas de negocio, verá la cantidad de cuentas en un segmento; sin embargo, no se muestra el número de contactos que pueden proyectarse. En algunos casos, esto podría llevar a que el segmento exportado contenga más perfiles de clientes de los que acepta el sistema de destino. Si excede los límites de los resultados de los sistemas de destino se omitirá la exportación. 

## <a name="set-up-a-new-export"></a>Configurar una nueva exportación  
Para configurar o editar una exportación, debe tener conexiones disponibles. Las conexiones dependen de su [rol del usuario](permissions.md):
- Los **administradores** tienen acceso a todas las conexiones. También pueden crear nuevas conexiones al configurar una exportación.
- Los **colaboradores** pueden tener acceso a conexiones específicas. Dependen de los administradores para configurar y compartir conexiones. La lista de exportaciones muestra a los contribuyentes si pueden editar o solo ver una exportación en la columna **Sus permisos**. Para obtener más información, vaya a [Permitir que los colaboradores utilicen una conexión para exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Los **espectadores** solo puede ver las exportaciones existentes, no crearlas.

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

1. Los usuarios sin permisos de edición seleccionan **Vista** en lugar de **Editar** para ver los detalles de la exportación.

1. El panel lateral muestra la configuración de una exportación. Sin permisos de edición, no puede cambiar valores. Seleccione **Cerrar** para volver a la página de exportaciones.

## <a name="schedule-and-run-exports"></a>Programar y ejecutar exportaciones

Cada exportación que configure tiene un programa de actualización. Durante una actualización, el sistema busca datos nuevos o actualizados para incluirlos en una exportación. De forma predeterminada, las exportaciones se ejecutan como parte de cada [actualización programada del sistema](system.md#schedule-tab). Puede personalizar el programa de actualización o desactivarlo para ejecutar exportaciones manualmente.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Los programas de exportación dependen del estado de su entorno. Si hay actualizaciones en curso en [dependencias](system.md#refresh-processes) cuando debe comenzar una exportación programada, el sistema primero completará las actualizaciones y luego ejecutará la exportación. Puede ver cuándo se actualizó por última vez una exportación en la columna **Actualizado**.

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
