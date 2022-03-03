---
title: Comprender y gestionar las medidas
description: Descubra cómo las medidas ayudan a analizar y reflejar el rendimiento de su negocio.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359816"
---
# <a name="measures-overview"></a>Información general de las medidas

Las medidas le ayudan a comprender mejor los comportamientos de los clientes y el desempeño comercial. Se fijan en valores relevantes de los [perfiles unificados](data-unification.md). Por ejemplo, una empresa quiere ver el *gasto total por cliente* para comprender el historial o la medida de compra de un cliente individual de *ventas totales de la empresa* para comprender los ingresos a nivel agregado en toda la empresa.  

Las medidas se crean [usando el generador de medidas](measure-builder.md), una plataforma de consulta de datos con varios operadores y opciones de asignación sencillas. Le permite filtrar los datos, agrupar resultados, detectar [rutas de relaciones de entidades](relationships.md) y obtener una vista previa de los resultados. Puede [usar plantillas predefinidas](measure-templates.md) para configurar eficientemente medidas de uso común.

Utilice el generador de medidas para planificar actividades comerciales consultando datos de clientes y extraiga información. Por ejemplo, crear una medida del *gasto total por cliente* y el *retorno total por cliente* ayuda a identificar un grupo de clientes con un alto gasto pero que aporta alto rendimiento. Puede [crear un segmento](segments.md) basado en esas medidas para impulsar las próximas mejores acciones. 

## <a name="manage-your-measures"></a>Administrar sus medidas

Puede encontrar la lista de medidas en la página **Medidas**.

Encontrará información sobre el tipo de medida, el creador, la fecha de creación y el estado. Cuando selecciona una medida de la lista, puede obtener una vista previa del resultado y descargar un archivo CSV.

Para actualizar todas sus medidas al mismo tiempo, seleccione **Actualizar todo** sin seleccionar una medida específica.

:::image type="content" source="media/measure-actions.png" alt-text="Acciones para gestionar medidas individuales":::.

Seleccione una medida de la lista para las siguientes opciones:

- Seleccione el nombre de la medida para ver sus detalles.
- **Editar** la configuración de la medida.
- **Actualizar** la medida en función de los últimos datos.
- **Cambiar nombre** de la medida.
- **Eliminar** la medida.
- **Activar** o **Desactivar**. Las medidas inactivas no se actualizarán durante una [actualización programada](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Siguiente paso

Puede utilizar medidas existentes para crear [un segmento de clientes](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
