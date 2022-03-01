---
title: Ver y crear segmentos
description: Cómo crear, editar y eliminar segmentos y dónde usarlos.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036169"
---
# <a name="view-and-create-segments"></a>Ver y crear segmentos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Los segmentos le permiten identificar subconjuntos de visitantes según las características o las interacciones del sitio web. Los segmentos le permiten aplicar filtros y analizar esos subconjuntos. El análisis puede ayudar a examinar y responder a las tendencias en su negocio. 

:::image type="content" source="media/segments-page.png" alt-text="Captura de pantalla de la aplicación de información sobre el compromiso que muestra la lista de segmentos existentes en un espacio de trabajo.":::

## <a name="view-segments"></a>Ver segmentos

1. Vaya a **Datos** en el panel de navegación izquierdo. 

1. Seleccione la pestaña **Segmentos** para ver una lista de todos los segmentos en el espacio de trabajo. 

## <a name="create-a-segment"></a>Crear un segmento

Los segmentos constan de reglas y condiciones que están conectadas con operadores lógicos. Las condiciones aplican filtros a una dimensión seleccionada. Cada segmento puede utilizar hasta cinco dimensiones.

El siguiente ejemplo muestra un segmento con dos condiciones en una sola regla. Filtra todos los eventos del sitio web donde el navegador es Chrome y los sistemas operativos son iOS o Android.

:::image type="content" source="media/segment-sample.png" alt-text="Segmentos de ejemplo con dos condiciones en una regla para filtrar los eventos del sitio web.":::

Esta sección describe cómo crear un *segmento en blanco* desde cero.

1. Vaya a **Datos** > **Segmentos**.

1. Seleccione **Nuevo segmento**.

1. En la **Biblioteca de recursos**, elija el atributo por el que desea filtrar. Actualmente, solo puede crear segmentos basados en dimensiones.

1. Elija un operador y un valor para el atributo seleccionado. Se admiten las siguientes operaciones.
   - **es**: requiere una coincidencia exacta para incluir valores. Usa **igual a** para un solo valor o **cualquiera de** para incluir varios valores.
   - **no es**: requiere una coincidencia exacta para excluir valores. Usa **igual a** para un solo valor o **cualquiera de** para incluir varios valores.
   - **comienza con**: una cadena con la que comienzan los valores coincidentes.
   - **termina con**: una cadena con la que terminan los valores coincidentes.
   - **contiene**: una cadena contenida en valores coincidentes.

1. Para agregar más condiciones a un grupo, puede usar dos operadores lógicos. Los atributos proyectados se tienen en cuenta al utilizar operadores de conjuntos.
   - Operador **AND**: Ambas condiciones deben cumplirse como parte del proceso de segmentación. Esta opción es más útil cuando define condiciones en diferentes entidades.
   - Operador **OR**: Cualquiera de las condiciones debe cumplirse como parte del proceso de segmentación. Esta opción es más útil cuando define varias condiciones para la misma entidad.

1. Seleccione **Guardar** y ponga nombre al segmento. 

El segmento aparecerá en la página Segmentos y puede aplicarlo a todos los informes y embudos en el espacio de trabajo.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Utilice un segmento en un informe o embudo

Puede aplicar segmentos a un informe o un embudo para filtrarlos según las condiciones del segmento. Sin embargo, no puede aplicar segmentos al informe de uso en tiempo real.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Un informe de vistas de página con una lista desplegable ampliada para elegir qué segmentos aplicar.":::

Para aplicar un segmento, abra el informe o el embudo. Seleccione **Agregar condición** y elija **Filtrar por segmento**. Elija el segmento de la lista que quiera aplicar. El segmento se aplicará al informe. Si un gráfico no es compatible con el segmento, muestra un error.
 
Puede aplicar *hasta tres segmentos* a un informe o embudo.

## <a name="edit-a-segment"></a>Editar un segmento

1. Vaya a **Datos** > **Segmentos**.
1. Seleccione el segmento en la lista para abrirlo. 
1. Cambie o agregue valores según sea necesario.
1. Seleccione **Guardar** para aplicar los cambios.

## <a name="change-the-name-of-a-segment"></a>Cambiar el nombre de un segmento

1. Vaya a **Datos** > **Segmentos**.
1. En la lista de segmentos, seleccione **Más [...]**. 
1. En la lista desplegable, seleccione **Editar nombre**.
1. Escriba el nombre nuevo y seleccione **Renombrar**.

## <a name="delete-a-segment"></a>Eliminar un segmento

1. Vaya a **Datos** > **Segmentos**.
1. En la lista de segmentos, seleccione **Más [...]**. 
1. En el menú desplegable, elija **Eliminar**.
1. Seleccione **Eliminar** para confirmar.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
