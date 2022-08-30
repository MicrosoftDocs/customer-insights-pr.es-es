---
title: Revisar la unificación de datos
description: Revise los pasos de unificación de datos, cree perfiles de clientes unificados y revise los resultados
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303988"
---
# <a name="review-data-unification"></a>Revisar la unificación de datos

Revise el resumen de cambios, cree el perfil unificado y revise los resultados.

## <a name="review-and-create-customer-profiles"></a>Revisar y crear perfiles de cliente

Este último paso en el proceso de unificación muestra un resumen de los pasos del proceso y brinda la oportunidad de realizar cambios antes de crear el perfil unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisar y crear perfiles de cliente":::

1. Seleccione **Editar** en cualquiera de los pasos de unificación de datos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Crear perfiles de clientes** (o **Crear perfiles de cuenta** para B a B). La página **Unificar** se muestra mientras se crea el perfil de cliente unificado.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de pantalla de la página de Unify con mosaicos que muestran En cola o Actualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

El algoritmo de unificación tarda un tiempo en completarse y no puede cambiar la configuración hasta que se complete.

## <a name="view-the-results-of-data-unification"></a>Ver los resultados de la unificación de datos

Después de la unificación, la página **Datos** > **Unificar** muestra el número de perfiles de clientes unificados (o perfiles de cuentas para B a B). Los resultados de cada paso en el proceso de unificación se muestran en cada mosaico. Por ejemplo, **Campos de origen** muestra el número de atributos mapeados (campos) y **Registros duplicados** muestra el número de registros duplicados encontrados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la página Unificar datos después de unificar los datos.":::

> [!TIP]
> El icono **Condiciones coincidentes** se muestra solo si se seleccionaron varias entidades.

Le recomendamos que revise los resultados, particularmente la calidad de sus [reglas de coincidencia](data-unification-update.md#manage-match-rules) y refinarlas si es necesario.

Cuando sea necesario, [realice cambios en la configuración de unificación](data-unification-update.md) y vuelva a ejecutar el perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verificar entidades de salida de la unificación de datos

Vaya a **Datos** > **Entidades** para verificar las entidades de salida.

La entidad de perfil de cliente unificada se llama *Cliente* en la sección **Perfiles**. La primera ejecución de unificación exitosa crea la entidad de *Cliente* unificada. Todas las ejecuciones posteriores expanden esa entidad.

Las entidades de deduplicación y combinación se crean y se muestran en la sección **Sistema**. Se crea una entidad de desduplicación para cada una de las entidades de origen con el nombre **Deduplication_DataSource_Entity**. La entidad **ConflationMatchPairs** contiene información sobre coincidencias entre entidades.

Una entidad de resultado de la desduplicación contiene la siguiente información:
- Identificadores y claves
  - Campos de clave principal e ID alternativa. El campo ID alternativo consta de todos los ID alternativos identificados para un registro.
  - El campo Deduplication_GroupId muestra el grupo o clúster identificado dentro de una entidad que agrupa todos los registros similares según los campos de desduplicación especificados. Se utiliza para fines de procesamiento del sistema. Si no hay reglas de desduplicación manual especificadas y se aplican reglas de desduplicación definidas por el sistema, es posible que no encuentre este campo en la entidad de resultados de la desduplicación.
  - Deduplication_WinnerId: este campo contiene el identificador del elemento elegido en los grupos o clústeres identificados. Si Deduplication_WinnerId es el mismo que el valor de la clave principal para un registro, significa que el registro es el elegido.
- Campos utilizados para definir las reglas de desduplicación.
- Los campos Regla y Puntuación indican cuál de las reglas de desduplicación se aplicó y la puntuación devuelta por el algoritmo de coincidencia.

## <a name="next-step"></a>Paso siguiente

- Para B a B, realice opcionalmente la [unificación de contactos](data-unification-contacts.md).

- Para B a C, configure [actividades](activities.md), [enriquecimientos](enrichment-hub.md), [relaciones](relationships.md) o [medidas](measures.md) para obtener más información sobre sus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]
