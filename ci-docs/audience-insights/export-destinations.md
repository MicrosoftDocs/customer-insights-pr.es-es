---
title: Exportar datos de Customer Insights
description: Administrar exportaciones para compartir datos.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896164"
---
# <a name="exports-preview-overview"></a>Información general del exportaciones (versión preliminar)

La página **Exportaciones** muestra todas las exportaciones configuradas. Las exportaciones comparten datos específicos con varias aplicaciones. Pueden incluir perfiles de clientes o entidades, esquemas y detalles de mapeo. Cada exportación requiere una [conexión, configurada por un administrador, para administrar la autenticación y el acceso](connections.md).

> [!NOTE]
> Hasta marzo de 2021, las exportaciones creaban una conexión al servicio correspondiente de forma automática. Las exportaciones ahora requieren una [conexión, creada y compartida por un administrador](connections.md) antes de poder crearlas.

Vaya a **Datos** > **Exportaciones** para ver la página de exportaciones. Todos los roles de usuario tienen acceso para ver las exportaciones configuradas. Uso del campo de búsqueda en la barra de comandos para buscar exportaciones por su nombre, nombre de conexión o tipo de conexión.

## <a name="set-up-a-new-export"></a>Configurar una nueva exportación

Para configurar o editar una exportación, debe tener conexiones disponibles. Las conexiones dependen de su [rol del usuario](permissions.md):
- Los administradores tienen acceso a todas las conexiones. También pueden crear nuevas conexiones al configurar una exportación.
- Los colaboradores pueden tener acceso a conexiones específicas. Dependen de los administradores para configurar y compartir conexiones. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Los visores solo pueden ver las exportaciones existentes, pero no crearlas.

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación** para crear un nuevo destino de exportación.

1. En el panel **Configurar exportación**, seleccione qué conexión usar. Las [conexiones](connections.md) son administradas por administradores. 

1. Proporcione los detalles requeridos y seleccione **Guardar** para crear la exportación.

### <a name="edit-an-export"></a>Editar una exportación

1. Seleccione los puntos suspensivos verticales del destino de exportación que desea editar.

1. Seleccione **Editar** en el menú desplegable.

1. Cambie los valores que desea actualizar y seleccione **Guardar**.

## <a name="view-exports-and-export-details"></a>Ver exportaciones y detalles de exportación

Después de crear los destinos de la exportación, se enumeran en **Datos** > **Exportaciones**. Todos los usuarios pueden ver qué datos se comparten y su estado más reciente.

1. Vaya a **Datos** > **Exportaciones**.

1. Los usuarios sin permisos de edición seleccionan **Vista** en vez de **Editar** para ver los detalles de la exportación.

1. Este panel lateral muestra la configuración de esta exportación. Sin permisos de edición, no puede cambiar valores. Seleccione **Cerrar** para volver a la página de exportaciones.

## <a name="run-exports-on-demand"></a>Ejecutar exportaciones según las necesidades

Después de configurar una exportación, se ejecutará con cada [actualización programada](system.md#schedule-tab) siempre que tenga una conexión que funcione.

Para exportar datos sin esperar una actualización programada, vaya a **Datos** > **Exportaciones**. Tiene dos opciones:

- Para ejecutar todas las exportaciones, seleccione **Ejecutar todo** en la barra de comandos. 
- Para ejecutar una sola exportación, seleccione los puntos suspensivos (...) en un elemento de la lista y luego elija **Ejecutar**.

## <a name="remove-an-export"></a>Quitar una exportación

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione los puntos suspensivos verticales para la exportación que desea quitar.

1. Seleccione **Quitar** del menú desplegable.

1. Confirme la eliminación seleccionando **Quitar** en la pantalla de confirmación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
