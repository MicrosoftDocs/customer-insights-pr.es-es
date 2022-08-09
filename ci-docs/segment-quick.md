---
title: Crear segmentos simples con segmentos rápidos
description: Cree segmentos sencillos de clientes para agruparlos en función de diversos atributos.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171143"
---
# <a name="create-simple-segments-with-quick-segments"></a>Crear segmentos simples con segmentos rápidos

Los segmentos rápidos le permiten crear segmentos simples con un solo operador rápidamente para obtener conocimientos de forma más rápida. Los segmentos rápidos solo se admiten en entornos para **clientes individuales**.

## <a name="create-a-new-segment-with-quick-segments"></a>Crear un nuevo segmento con segmentos rápidos

1. Vaya a **Segmentos**.

1. Seleccione **Nuevo** > **Crear a partir de**.
   - Seleccione la opción **Perfiles** para construir un segmento basado en la entidad *cliente unificado*.
   - Seleccione la opción **Medidas** para construir un segmento alrededor de medidas que haya creado previamente.
   - Selecciona la opción **Inteligencia** para crear un segmento alrededor de una de las entidades de salida que generó con las capacidades **Predicciones** o **Modelos personalizados**.

1. En el cuadro de diálogo **Nuevo segmento rápido**, seleccione un atributo en el campo desplegable **Campo**. Según su selección, el sistema proporciona diferentes valores.
   - Para los campos categóricos, se muestran los 10 principales recuentos de clientes. Elija un **Valor** y seleccione **Revisar**.
   - Para un atributo numérico, el sistema muestra qué valor de atributo corresponde al percentil de cada cliente. Elija un **Operador** y un **Valor**, luego seleccione **Revisar**.

1. El sistema le proporciona un **Tamaño de segmento estimado**. Elija si genera el segmento que ha definido o volver a volver para elegir un campo diferente.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nombre y estimación de un segmento rápido.":::

1. Proporcione un **Nombre** y un **Nombre de entidad de salida** para su segmento. Opcionalmente, agregue [etiquetas](work-with-tags-columns.md#manage-tags).

1. Seleccione **Guardar** para crear el segmento. Se muestra la página **Segmentos**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Pasos siguientes

[Exportar un segmento](export-destinations.md) y explorar la [Integración de tarjeta de cliente](customer-card-add-in.md) para usar segmentos en otras aplicaciones.

[!INCLUDE [footer-include](includes/footer-banner.md)]
