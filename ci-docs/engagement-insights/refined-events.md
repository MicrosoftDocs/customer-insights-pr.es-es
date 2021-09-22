---
title: Crear y modificar eventos refinados
description: Cómo crear y modificar eventos refinados.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034795"
---
# <a name="create-and-modify-refined-events"></a>Crear y modificar eventos refinados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Un evento son datos que representan el comportamiento del usuario, como la actividad en un sitio web.

- Un evento *base* registra cuando un usuario ve una página (evento de visualización) o interactúa con el contenido (evento de acción).
- Un evento *refinado* es una vista virtual de un evento base. Usted define eventos refinados quitando y agregando propiedades o filtrando eventos basados en valores de propiedad.

Utilice eventos refinados para reducir el alcance de un evento base para [exportar](export-events.md) o para eliminar propiedades que no son necesarias para la exposición.

## <a name="create-refined-events"></a>Crear eventos refinados

Hay tres formas de crear un evento refinado a partir de un evento base. 

1. Vaya a **Datos** > **Eventos** y elija una de las siguientes opciones:
    - Seleccione **Nuevos eventos** y luego seleccione **Crear eventos refinados**.
    - Seleccione un evento base para abrir una vista detallada y seleccione **Crear eventos refinados** en el menú superior.
    - Seleccione **Más [...]** para abrir el menú de acceso directo para un evento base. Luego seleccione **Crear eventos refinados**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opciones para crear eventos refinados.":::

1. En el cuadro de diálogo **Crear eventos refinados**, introduzca la siguiente información:

- Seleccione un evento de la lista desplegable **Eventos base** si está creando un nuevo evento.
- Indique un nombre para el cuadro **Nombre para mostrar de eventos refinados**.
- Opcionalmente, actualice el **Nombre real** sugerido sin utilizar espacios.

3. Seleccione **Crear** para aplicar su configuración.

1. En la vista detallada de su evento refinado, seleccione **Agregar y quitar propiedades** para abrir el panel **Editar propiedades**. 

1. Utilice las casillas de verificación para seleccionar las propiedades que desea mostrar y las que desea ocultar. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar propiedades para eventos refinados.":::

1. Seleccione **Confirmar** para aplicar su selección.

1. Seleccione **Guardar** para guardar la configuración.

## <a name="edit-refined-events"></a>Editar eventos refinados

Puede cambiar el nombre y las propiedades de un evento refinado.

### <a name="edit-event-name"></a>Editar nombre de evento

1. Vaya a **Datos** > **Eventos**. 
1. Seleccione **Más [...]** para un evento y seleccione **Editar nombre**.
1. Actualice el nombre del evento y seleccione **Cambiar nombre**.

### <a name="edit-selected-properties"></a>Editar propiedades seleccionadas

1. Vaya a **Datos** > **Eventos** y seleccione los eventos refinados para abrir la vista detallada.
1. Seleccione **Agregar y quitar propiedades**. 
1. Edite la selección de las casillas.
1. Seleccione **Confirmar** y lueg **Guardar** para aplicar los cambios.

Para obtener más información sobre la exportación, consulte [Eventos de exportación](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
