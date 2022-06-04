---
title: Revisar la unificación de datos
description: Revise los pasos de unificación de datos, cree perfiles de clientes unificados y revise los resultados
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741715"
---
# <a name="review-data-unification"></a>Revisar la unificación de datos

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Este último paso en el proceso de unificación muestra un resumen de los pasos del proceso y brinda la oportunidad de realizar cambios antes de crear el perfil unificado.

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisar y crear perfiles de cliente":::

## <a name="review-the-data-unification-steps"></a>Revisar los pasos de unificación de datos

1. Seleccione **Editar** en cualquiera de los pasos de unificación de datos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Crear perfiles de clientes**. La página **Unificar** se muestra mientras se crea el perfil de cliente unificado. El algoritmo de unificación tarda un tiempo en completarse y no puede cambiar la configuración hasta que se complete.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Cuando finaliza el proceso de unificación, la entidad de perfil de cliente unificado, denominada *Cliente*, figura en la página **Entidades** de la sección **Perfiles**. La primera ejecución de unificación exitosa crea la entidad de *Cliente* unificada. Todas las ejecuciones posteriores expanden esa entidad.

## <a name="review-the-results-of-data-unification"></a>Revisar los resultados de la unificación de datos

Después de la unificación, la página **Datos** > **Unificar** muestra el número de perfiles de clientes unificados. Los resultados de cada paso en el proceso de unificación se muestran en cada mosaico. Por ejemplo, **Campos de origen** muestra el número de atributos mapeados (campos) y **Registros duplicados** muestra el número de registros duplicados encontrados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la página Unificar datos después de unificar los datos.":::

> [!TIP]
> El icono **Condiciones coincidentes** se muestra solo si se seleccionaron varias entidades.

Le recomendamos que revise los resultados, particularmente la calidad de sus [reglas de coincidencia](data-unification-update.md#manage-match-rules) y refinarlas si es necesario.

Cuando sea necesario, [realice cambios en la configuración de unificación](data-unification-update.md) y vuelva a ejecutar el perfil unificado.

## <a name="next-step"></a>Paso siguiente

Configurar [actividades](activities.md), [enriquecimiento](enrichment-hub.md), [relaciones](relationships.md) o [medidas](measures.md) para obtener más información sobre sus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]