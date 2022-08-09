---
title: Esquemas de entidad en Common Data Model
description: Trabajar con entidades en Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: cc65314f1b083694b60ac0a2625bea906be7272b
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183514"
---
# <a name="entity-schemas-in-common-data-model"></a>Esquemas de entidad en Common Data Model

[Common Data Model](/common-data-model/) (CDS) es una especificación declarativa y una definición de entidades estándar que representan los conceptos y actividades más usados en una variedad de aplicaciones empresariales y de productividad. Este modelo se está extendiendo también a datos observacionales y analíticos. Common Data Model ofrece entidades empresariales bien definidas, modulares y extensibles como Cuenta, Unidad de negocio, Caso, Contacto, Cliente potencial, Oportunidad y Producto, así como interacciones y relaciones con proveedores, trabajadores y clientes, como actividades y acuerdos de nivel de servicio. Cualquiera puede añadir y ampliar las definiciones de Common Data Model para capturar ideas adicionales específicas del negocio.

Se trata de un modelo de datos compartido que permite que las aplicaciones y los integradores de datos colaboren con más facilidad al proporcionar una definición de datos unificada. Common Data Model incluye un completo sistema de metadatos con entidades estándar, relaciones, jerarquías, características y mucho más. Se originó a partir de aplicaciones de Dynamics 365 y es de código abierto en GitHub con más de 260 entidades estándar. Un gran sistema de partners internos y externos aporta conceptos específicos del sector a Common Data Model.

Varios sistemas y plataformas implementan hoy en día Common Data Model, incluidos flujos de trabajo de Power BI y servicios de datos de Azure. Ya es compatible con Microsoft Dataverse, Dynamics 365, Power Apps, Power BI y los próximos servicios de datos de Azure, que acumulan valor directamente para la [Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>Esquemas de entidad de Customer Insights

Para establecer una vista integral del cliente y hacer que los modelos de Customer Insights estén disponibles en Common Data Model para la extensibilidad, hemos publicado los siguientes esquemas de entidad:

| Entidad | Descripción |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Una actividad realizada por un usuario que tiene un valor observacional para el negocio. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Una persona u organización que realizó o tiene el potencial de interactuar en actividades profesionales. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definición de KPI divididos por cero o más dimensiones (como usuarios activos mensuales, gasto total por cliente, coste promedio de adquisición del cliente) |
|[Segmento ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Define un grupo de miembros con rasgos comunes. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Miembros que participan en un segmento determinado. |

Para obtener más información, consulte la documentación sobre los [Esquemas de entidad de Customer Insights en Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Ver entidades utilizando el navegador para entidades de Common Data Model

Vea las entidades en el [Navegador de entidades de Common Data Model](https://microsoft.github.io/CDM/). Seleccione una entidad de la sección de la aplicación Insights para obtener la lista de entidades de Customer Insights y sus definiciones.

:::image type="content" source="media/CDM-entity-navigator.png" alt-text="Navegador para entidades de CDM que muestra la entidad CustomerActivity.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
