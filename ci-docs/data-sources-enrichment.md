---
title: Enriquecimiento de origen de datos
description: Enriquezca los orígenes de datos antes de pasar por el proceso de unificación de datos.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800302"
---
# <a name="enrichment-for-data-sources-preview"></a>Enriquecimiento de orígenes de datos (versión preliminar)

Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de sus clientes antes de la unificación de datos. Los enriquecimientos origen de datos ayudan a producir datos más completos y de mayor calidad que pueden ayudar a lograr mejores resultados una vez que unifique sus datos. Por ejemplo, el uso de un formato normalizado y estandarizado para las direcciones aumenta la calidad de los resultados de las coincidencias. Para obtener una lista de los enriquecimientos admitidos, consulte [opciones de enriquecimiento de origen de datos admitidas](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Enriquecer un origen de datos

Debe tener los permisos Colaborador o Administrador para crear o editar enriquecimientos. Para obtener más información, vea [Permisos](permissions.md).  

1. Vaya a **Datos** > **Unificar**. Seleccione la entidad que desea enriquecer y seleccione un atributo como clave principal para la entidad. Para obtener más información, consulte [Seleccionar clave principal](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione los puntos suspensivos verticales (&vellip;) junto al origen de datos que desea enriquecer y seleccione **Enriquecer**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Página de enriquecimiento de orígenes de datos.":::

   La pestaña **Descubrir** muestra las [opciones de enriquecimiento de origen de datos admitidas](#supported-data-source-enrichments).

1. Seleccione **Enriquecer mis datos** para configurar un enriquecimiento de origen de datos. El nombre de la entidad resultante se completa automáticamente.

## <a name="supported-data-source-enrichments"></a>Enriquecimientos de orígenes de datos admitidos

Los siguientes enriquecimientos están disponibles para los orígenes de datos. Revise los pasos detallados para el enriquecimiento para aprender a configurarlo.

- [Direcciones mejoradas](enrichment-enhanced-addresses.md)
- [Datos de empresa mejorados](enrichment-enhanced-company-data.md)
- [Datos de identidad de LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Administrar enriquecimientos de origen de datos existentes

Vaya a la pestaña **Mis enriquecimientos** para ver todos los enriquecimientos configurados.

Seleccione el enriquecimiento para ver las opciones disponibles. También puede seleccionar los puntos suspensivos verticales (&vellip;) en un elemento de la lista para ver las opciones. Si configuró varios enriquecimientos, puede usar el cuadro de búsqueda para encontrarlos rápidamente.

Puede ver, editar, ejecutar o eliminar un enriquecimiento de origen de datos. Para obtener más información, consulte [Administrar enriquecimientos existentes](enrichment-hub.md).
