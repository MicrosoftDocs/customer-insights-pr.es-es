---
title: Información general del exportaciones (versión preliminar)
description: Administrar exportaciones para compartir datos.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245348"
---
# <a name="exports-preview-overview"></a>Información general del exportaciones (versión preliminar)

 Las exportaciones le permiten compatir datos específicos con varias aplicaciones. Pueden incluir perfiles de clientes, entidades, esquemas y detalles de asignación. Cada exportación requiere una [conexión, configurada por un administrador, para administrar la autenticación y el acceso](connections.md). La página **Exportaciones** muestra todas las exportaciones configuradas.

## <a name="export-types"></a>Tipos de exportación

Hay dos tipos principales de exportaciones:  

- **Exportaciones de salida de datos**: exporte cualquier tipo de entidad disponible en Customer Insights. Las entidades que seleccione para exportar se exportan con todos los campos de datos, metadatos, esquemas y detalles de asignación.
- **Exportaciones de segmentos**: exporte entidades de segmento desde Customer Insights. Los segmentos representan una lista de perfiles de clientes. Al configurar la exportación, seleccione los campos de datos incluidos, según el sistema de destino al que esté exportando los datos.

### <a name="export-segments"></a>Exportar segmentos

**Exportación de segmentos en entornos para cuentas de negocio (B2B) o consumidores individuales (B2C)**  
La mayoría de las opciones de exportación admiten ambos tipos de entornos. La exportación de segmentos a diversos sistemas de destino tiene requisitos específicos. 

**Exportación de segmentos en entornos para consumidores individuales (B2C)**  
- Los segmentos en el contexto de entornos para clientes individuales se basan en la entidad *perfil de cliente unificado*. Se puede exportar cada segmento que cumpla con los requisitos de los sistemas de destino (por ejemplo, una dirección de correo electrónico).

**Entornos de exportación de segmentos para cuentas de negocio (B2B)**  
- Los segmentos en el contexto de entornos para cuentas de negocio se basan en la entidad *cuenta*. Para exportar segmentos de cuenta tal como están, el sistema de destino debe admitir segmentos de cuenta puros. Este es el caso de [LinkedIn](export-linkedin-ads.md) cuando elige la opción **empresa** al definir la exportación.
- Todos los demás sistemas de destino requieren campos de la entidad de contacto. Para garantizar que los segmentos de cuenta puedan recuperar datos de contactos relacionados, la definición de segmento debe proyectar los atributos de la entidad de contacto. Más información sobre cómo [configurar segmentos y atributos del proyecto](segment-builder.md).

**Límites a las exportaciones de segmentos**  
- Los sistemas de destino de terceros pueden limitar la cantidad de perfiles de clientes que puede exportar. 
- Para clientes individuales, verá el número real de miembros del segmento cuando seleccione un segmento para exportar. Recibirá una advertencia si un segmento es demasiado grande. 
- Para cuentas de negocio, verá la cantidad de cuentas en un segmento; sin embargo, no se muestra el número de contactos que pueden proyectarse. En algunos casos, esto podría llevar a que el segmento exportado contenga más perfiles de clientes de los que acepta el sistema de destino. Si excede los límites del sistema de destino, se omite la exportación.

## <a name="set-up-a-new-export"></a>Configurar una nueva exportación

Para configurar o editar una exportación, debe tener disponibles las conexiones correctas. Las conexiones dependen de su [rol del usuario](permissions.md):
- Los **administradores** tienen acceso a todas las conexiones. También pueden crear nuevas conexiones al configurar una exportación.
- Los **colaboradores** pueden tener acceso a conexiones específicas. Dependen de los administradores para configurar y compartir conexiones. La lista de exportaciones muestra a los contribuyentes si pueden editar o solo ver una exportación en la columna **Sus permisos**. Para obtener más información, vaya a [Permitir que los colaboradores utilicen una conexión para exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Los **espectadores** solo puede ver las exportaciones existentes, no crearlas.

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, seleccione **Agregar exportación**.

1. En el panel **Configurar exportación**, seleccione qué [conexión](connections.md) usar.

1. Proporcione los detalles requeridos y seleccione **Guardar** para crear la exportación. Para obtener los detalles requeridos, revise la documentación de Customer Insights para la exportación específica.

## <a name="manage-existing-exports"></a>Administrar exportaciones existentes

Vaya a **Datos** > **Exportaciones** para ver las exportaciones, su nombre de conexión, tipo de conexión y estado. Todos los roles de usuario pueden ver las exportaciones configuradas. Puede ordenar la lista de exportaciones por cualquier columna o usar el cuadro de búsqueda para encontrar la exportación que desea administrar.

Seleccione una exportación para ver las acciones disponibles.

:::image type="content" source="media/exports_showmore.png" alt-text="Página de exportaciones.":::

- **Vea** o **Edite** la exportacion. Los usuarios sin permisos de edición seleccionan **Vista** en lugar de **Editar** para ver los detalles de la exportación.
- **Ejecute** la exportación para exportar los datos más recientes.
- **Crear duplicado** de una exportación.
- **[Programar](#schedule-and-run-exports)** la exportación.
- **Separe la conexión** para eliminar la conexión para esta exportación. La separación no elimina la conexión, pero desactiva la exportación. La columna **Conexión utilizada** muestra Sin conexión.
- **Quite** la exportación.

## <a name="schedule-and-run-exports"></a>Programar y ejecutar exportaciones

Cada exportación que configure tiene un programa de actualización. Durante una actualización, el sistema busca datos nuevos o actualizados para incluirlos en una exportación. De forma predeterminada, las exportaciones se ejecutan como parte de cada [actualización programada del sistema](schedule-refresh.md). Puede personalizar el programa de actualización o desactivarlo para ejecutar exportaciones manualmente.

Los programas de exportación dependen del estado de su entorno. Si hay actualizaciones en curso en [dependencias](system.md#refresh-processes) cuando debe comenzar una exportación programada, el sistema primero completará las actualizaciones y luego ejecutará la exportación. La columna **Actualizado** muestra cuándo se actualizó por última vez una exportación.

### <a name="schedule-exports"></a>Programar exportaciones

Defina simultáneamente programas de actualización personalizados para exportaciones individuales o varias exportaciones. El horario definido actualmente se enumera en la columna **Programación** de la lista de exportación. El permiso para cambiar el horario es el mismo que para [editar y definir exportaciones](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione la exportación que quiere programar.

1. Seleccionar **Programación**.

1. En el panel **Exportación programada**, establezca **Programar ejecución** a **Activado** para ejecutar la exportación automáticamente. Establézcalo en **Desactivado** para actualizarlo manualmente.

1. Para exportaciones actualizadas automáticamente, elija un valor de **Periodicidad** y especifique los detalles para ello. El tiempo definido se aplica a todas las instancias de una periodicidad. Es el momento en que una exportación debería comenzar a actualizarse.

1. Seleccione **Guardar**.

Al editar la programación de varias exportaciones, realice una selección en **Mantener o invalidar programaciones**:

- **Mantener programaciones individuales**: conserve la programación previamente definida para las exportaciones seleccionadas y solo deshabilítelas o habilítelas.
- **Definir un nuevo programa para todas las exportaciones seleccionadas**: anula las programaciones existentes de las exportaciones seleccionadas.

### <a name="run-exports-on-demand"></a>Ejecutar exportaciones según las necesidades

Para exportar datos sin esperar una actualización programada, vaya a **Datos** > **Exportaciones**.

- Para ejecutar todas las exportaciones, seleccione **Ejecutar todo** en la barra de comandos. Solo se ejecutan las exportaciones que tengan una programación activa. Para ejecutar una exportación que no está activa, ejecute una única exportación.
- Para ejecutar una sola exportación, selecciónela en la lista y seleccione **Ejecutar** en la barra de comandos.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
