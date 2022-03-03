---
title: Crear y modificar eventos
description: Cómo crear y modificar eventos refinados.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228224"
---
# <a name="create-and-modify-events"></a>Crear y modificar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un evento son datos que representan el comportamiento del usuario, como la actividad en un sitio web.

- Un evento *base* registra cuando un usuario ve una página (evento de visualización) o interactúa con el contenido (evento de acción).
- Un evento *refinado* es una vista virtual de un evento base. Usted define eventos refinados quitando y agregando propiedades o filtrando eventos basados en valores de propiedad.

## <a name="prerequisites"></a>Requisitos previos

Para obtener eventos, deberá conectar los datos de su sitio web a las conclusiones sobre la interacción con un fragmento de código simple. Para más información, vea [Instalar el SDK de web en un sitio web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Conectar primero sus datos.":::

## <a name="create-refined-events"></a>Crear eventos refinados

Utilice eventos refinados para reducir el alcance de un evento base para [exportar](export-events.md) o para eliminar propiedades que no son necesarias para la exposición.

> [!NOTE]
> Una vez que agregue el SDK de web a su sitio web, podrá ver sus eventos base y crear eventos refinados. 

Para ver sus eventos base:

1. Vaya a **Datos** en el panel de navegación izquierdo.

1. Seleccione **Eventos** para ver una lista de todos los eventos en el área de trabajo.

    :::image type="content" source="media/data-events.png" alt-text="Ver eventos.":::

Para crear un evento refinado a partir de un evento base: 

1. Vaya a **Datos** > **Eventos** y seleccione **+ Nuevos eventos** en la parte superior de la pantalla.

1. En el diálogo **Nuevos eventos**, seleccione **Crear eventos refinados** y luego seleccione **Siguiente**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Asistente de eventos nuevos.":::
     
1. En el diálogo **Nuevos eventos**, escriba la siguiente información:

   - Seleccione un evento de la lista desplegable **Eventos base**.
   - Indique un nombre para el cuadro **Nombre para mostrar de eventos refinados**.
   - Opcionalmente, actualice el **Nombre real** sugerido sin utilizar espacios.

1. Seleccione **Crear** para aplicar su configuración.

El evento refinado ahora aparece en su lista **Eventos**.

### <a name="edit-event-name"></a>Editar nombre de evento

Puede cambiar el nombre y las propiedades de un evento base o refinado.

1. Vaya a **Datos** > **Eventos**. 

1. Seleccione **Más [...]** para un evento y seleccione **Editar nombre**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opciones para crear eventos refinados.":::

3. Actualice el nombre del evento y seleccione **Cambiar nombre**.

### <a name="view-the-details-of-a-refined-event"></a>Ver los detalles de un evento refinado:

1. En la lista **Evento**, seleccione su evento base o refinado. 

1. Seleccione **Agregar y quitar propiedades** en la parte superior de la pantalla para abrir el panel **Editar propiedades**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Agregar y quitar propiedades.":::

1. Utilice las casillas de verificación para seleccionar las propiedades que desea mostrar y las que desea ocultar. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar propiedades para eventos refinados.":::

1. Seleccione **Confirmar** para aplicar su selección, y luego seleccione **Guardar**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Edite las propiedades seleccionadas para un evento refinado

1. Vaya a **Datos** > **Eventos** y seleccione los eventos refinados para abrir la vista detallada.
1. Seleccione **Agregar y quitar propiedades**. 
1. Edite la selección de las casillas.
1. Seleccione **Confirmar** y lueg **Guardar** para aplicar los cambios.

Para obtener más información sobre la exportación, consulte [Eventos de exportación](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
