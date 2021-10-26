---
title: Ver y crear métricas
description: Cómo crear, editar y eliminar métricas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623743"
---
# <a name="view-and-create-metrics"></a>Ver y crear métricas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Las métricas ayudan a comprender el comportamiento de sus visitantes. Agregan propiedades de eventos y miden estadísticas y rendimiento de sus propiedades web.  

Suponga que está ejecutando una promoción de marketing en su sitio web. Puede utilizar métricas para realizar un seguimiento de la cantidad de visitantes o usuarios únicos que llegaron a su sitio web durante la promoción. El análisis de métricas lo ayuda a comprender mejor al público de su sitio web. Combinar métricas con [dimensiones](dimensions.md) en un [informe personalizado](custom-reports.md) le permite medir el comportamiento para comprender a sus usuarios. Por ejemplo, puede separar a los visitantes en categorías nuevas y recurrentes para identificar las diferencias de interés e intención entre los grupos.

## <a name="view-metrics"></a>Visualización de métricas

Las estadísticas de participación incluyen agregaciones de propiedades de eventos de uso común como métricas del sistema: 

- Visitantes
- Visitas
- Vistas de página
- Clics

Estas métricas del sistema se basan en propiedades de eventos existentes en eventos base.

1. Vaya a **Datos** en el panel de navegación izquierdo. 
1. Seleccione la pestaña **Métricas** para ver una lista de todas las métricas en el espacio de trabajo. 
   > [!NOTE]
   > Las métricas generadas por el sistema son de solo lectura. No puede editarlos ni eliminarlos. Solo puede crear y editar métricas personalizadas.

## <a name="create-a-metric"></a>Crear una métrica

Los administradores de entornos y espacios de trabajo pueden crear métricas. Las propiedades del evento deben enviarse al espacio de trabajo antes de crear una métrica. Puede crear métricas basadas en las propiedades de los eventos que envían los eventos base o utilizar el SDK web para [enviar propiedades de eventos personalizados](advanced-SDK-implementation.md).

1. Vaya a **Datos** > **Métricas**.
1. Seleccione **Nueva métrica** para abrir el diálogo **Biblioteca de recursos** y **Nueva métrica sin título**.

   :::image type="content" source="media/new-metric.png" alt-text="Agregar una métrica a un evento.":::

1. En el diálogo **Nueva métrica sin título**, seleccione la lista desplegable **Formato** y elija el tipo de datos **Entero** o **Doble**. Entero es un número entero. Para Doble, puede elegir uno y tres lugares decimales.

   :::image type="content" source="media/create-new-metric.png" alt-text="Crear una nueva métrica.":::
   
5. En el panel **Biblioteca de recursos**, busque la propiedad del evento en la que basar la métrica.
6. Seleccione el **signo más (+)** junto a la propiedad para usarla en la fórmula. Solo puede crear una fórmula basada en una propiedad. 
7. Elija una de las siguientes funciones de agregado. 

   - Suma: el total aritmético de todos los valores 
   - Promedio: el promedio medio de todos los valores
   - Recuento: el número total de valores
   - Recuento de valores únicos: el número total de valores únicos

   Después de definir la métrica, verá una vista previa de la actividad de la métrica durante la última hora.

1. Seleccione **Guardar**. 
1. Especifique un nombre para la métrica y seleccione **Guardar**.

La métrica puede tardar hasta un minuto antes de poder usarla para [crear informes personalizados](custom-reports.md).

## <a name="edit-a-metric"></a>Editar una métrica

Solo puede editar métricas personalizadas.

1. Vaya a **Datos** > **Métricas**.
1. Seleccione la métrica en la lista.
1. Cambiar la definición de la métrica
1. Seleccione **Guardar**.

## <a name="change-the-name-of-a-metric"></a>Cambiar el nombre de una métrica

Solo puede cambiar el nombre de las métricas personalizadas.

1. Vaya a **Datos** > **Métricas**.
1. Seleccione **Más [...]** para una métrica y elija **Editar nombre**.
1. Cambiar el nombre. 
1. Seleccione **Cambiar nombre**.

## <a name="delete-a-metric"></a>Eliminar una métrica

Solo puede eliminar métricas personalizadas.

1. Vaya a **Datos** > **Métricas**.
1. Seleccione **Más [...]** para una métrica y elija **Eliminar**.

   :::image type="content" source="media/delete-metric.png" alt-text="Eliminar una métrica para un evento.":::

1. Seleccione **Eliminar** para confirmar la eliminación.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
