---
title: Acerca de los informes personalizados
description: Cómo crear y personalizar informes.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582898"
---
# <a name="create-and-edit-custom-reports"></a>Crear y editar informes personalizados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Además de los informes predefinidos (OOB), puede crear un informe personalizado con visualizaciones de gráficos y tablas para ayudarle a comprender el comportamiento del usuario. En este artículo se explica cómo crear un informe con los datos que necesita mediante visualizaciones de tablas y gráficos. Para obtener información sobre informes OOB, consulte [Ver informes](view-reports.md).

## <a name="create-a-custom-report"></a>Crear un informe personalizado

1. Vaya a **Analizar** > **Personalizado** para acceder a la lista de informes personalizados.

1. Seleccione **Nuevo informe** para comenzar a crear un informe personalizado.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nuevos informes personalizados.":::

1. Decida qué tipo de informe desea crear:

    - Seleccione **Agregar elemento visual** en la barra de comandos para crear una visualización de tabla predeterminada.
    - O seleccione una visualización de columna, barra, línea, área, circular, de anillo o de tabla en el panel **Editor de informes**.

1. En la sección **Datos** del panel **Editor de visualización**, elija una de las opciones disponibles (por ejemplo, vistas de página) del desplegable **Métrica**. También puede agregar **Dimensiones** (por ejemplo, país) para mostrar en la visualización. Para más información, vea [Ver y crear métricas](metrics.md) y [Ver y crear dimensiones](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Elija una métrica para el informe.":::

1. Selecciona la sección **Diseño** del panel **Editor de visualización** para agregar **Texto del título** y active o desactive **Título**.  También puede cambiar el tipo de visualización seleccionando otro gráfico, como **gráfico circular**.

1. Para cambiar el tamaño y la posición de una visualización:
   - Seleccione la visualización y luego arrastre una de las esquinas o bordes para ajustar su tamaño.
   - Seleccione la visualización y muévala a una nueva posición. También puede utilizar las teclas de dirección para cambiar la posición.
1. Para añadir otra visualización, seleccione **Agregar elemento visual** en la barra de comandos.
1. Después de agregar las visualizaciones que desea añadir al informe, seleccione **Guardar** en la barra de comandos.

1. Proporcione un nombre para el informe personalizado y seleccione **Guardar** para crearlo.
 
## <a name="filter-a-custom-report"></a>Filtrar un informe personalizado

Puede seleccionar el período de tiempo o el intervalo de fechas en un informe personalizado para centrarse en un valor o período de tiempo.

Para seleccionar un período de tiempo, en la esquina superior derecha de la vista del informe, seleccione un valor de la lista desplegable del informe. También puede elegir un **Intervalo de fechas fijo*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrar por hora o intervalo de fechas.":::

Para la mayoría de los informes, seleccione **+ Agregar condición**, para elegir una dimensión o segmento para filtrar el informe. Para más información, vea [Ver y crear segmentos](segments.md).

## <a name="edit-a-custom-report"></a>Editar un informe personalizado

1. Vaya a **Analizar** > **Personalizado** para acceder a la lista de informes personalizados.

1. En la lista de informes personalizados, seleccione **Más [...]** 

1. Elija **Editar nombre** para cambiar el nombre del informe.

1. Seleccione el nombre del informe y utilice las opciones de **+ Agregar elemento visual** y **Editar** para agregar, eliminar, cambiar de posición o cambiar el tamaño de las visualizaciones.

1. Para cambiar las propiedades de una visualización, seleccione el objeto visual, seleccione **...** y luego **Editar visual**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Editar propiedades de gráficos para informes personalizados.":::

1. Tras la edición del informe, seleccione **Guardar** para aplicar los cambios. 

## <a name="delete-a-custom-report"></a>Eliminar un informe personalizado

1. Vaya a **Analizar** > **Personalizado** para acceder a la lista de informes personalizados.

1. En la lista de informes personalizados, seleccione **...**

1. Seleccione **Eliminar** para eliminar el informe.

1. Confirme su elección para eliminar el informe de forma permanente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
