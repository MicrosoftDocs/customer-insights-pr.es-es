---
title: Información general de las medidas
description: Descubra cómo las medidas ayudan a analizar y reflejar el rendimiento de su negocio.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170870"
---
# <a name="measures-overview"></a>Información general de las medidas

Las medidas le ayudan a comprender mejor los comportamientos de los clientes y el desempeño comercial. Se fijan en valores relevantes de los [perfiles unificados](data-unification.md). Por ejemplo, una empresa quiere ver el *gasto total por cliente* para comprender el historial o la medida de compra de un cliente individual de *ventas totales de la empresa* para comprender los ingresos a nivel agregado en toda la empresa.

cree medidas para planificar actividades comerciales consultando datos de clientes y extraiga información. Por ejemplo, cree una medida del *gasto total por cliente* y el *retorno total por cliente*, para ayudar a identificar un grupo de clientes con un alto gasto pero que aporta un gran retorno. Luego, [cree un segmento](segments.md) basado en esas medidas para impulsar las próximas mejores acciones.

## <a name="create-a-measure"></a>Crear una medida

Elija cómo crear una medida basada en su objetivo de público.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

- Desde cero con el generador de medidas: [Construya la suya propia](measure-builder.md).
- Desde medidas de uso común: [Utilizar plantillas predefinidas](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

Desde cero con el generador de medidas: [Construya la suya propia](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Administrar medidas existentes

Vaya a la página **Medidas** para ver las medidas que creó, su estado, su tipo de medida y la última vez que se actualizaron los datos. Puede ordenar la lista de medidas por cualquier columna o usar el cuadro de búsqueda para encontrar la medida que desea administrar.

Seleccione cerca de una medida para ver las acciones disponibles. Seleccione el nombre de la medida para obtener una vista previa del resultado y descargar un archivo CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Acciones para gestionar medidas individuales."lightbox="media/measures-actions.png":::

- **Edite** la medida para cambiar sus propiedades.
- **Actualice** la medida para incluir los últimos datos.
- **Cambiar nombre** de la medida.
- **Active** o **Desactive** la medida. Las medidas inactivas no se actualizarán durante una [actualización programada](system.md#schedule-tab) y tienen el **Estado** catalogado como **Omitido**, lo que indica que ni siquiera se intentó una actualización.
- **Etiqueta** para [administrar etiquetas](work-with-tags-columns.md#manage-tags) para la medida.
- **Eliminar** la medida.
- **Columnas** para [personalizar las columnas](work-with-tags-columns.md#customize-columns) de esa pantalla.
- **Filtro** para [filtrar en etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Buscar nombre** para buscar por nombre de medida.

## <a name="refresh-measures"></a>Actualizar medidas

Las medidas se pueden actualizar de forma automática o manualmente, a petición. Para actualizar manualmente una o más medidas, selecciónelas y elija **Actualizar**. A [programar una actualización automática](system.md#schedule-tab), vaya a **Administración** > **Sistema** > **Programar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
