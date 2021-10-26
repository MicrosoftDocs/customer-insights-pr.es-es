---
title: Comenzar con la función de conclusiones del público en Dynamics 365 Customer Insights
description: Una descripción general de las conclusiones del público ayuda a los recursos a comenzar rápidamente.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645285"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Comenzar con la capacidad de conclusiones del público en Dynamics 365 Customer Insights

Las conclusiones del público pueden ayudarle a crear una comprensión mayor de sus clientes. Conecte los datos de varias fuentes transaccionales, de comportamiento y de observación para crear un visión global de los clientes. Utilice esta información para impulsar experiencias y procesos centrados en el cliente. Unifique y conozca los datos de sus clientes y aprovéchelos para extraer conocimientos y acciones inteligentes.

## <a name="step-1-create-an-environment"></a>Paso 1: crear un entorno

Para empezar, primero tiene que crear un entorno en el que trabajar. Si su organización ya compró una licencia, consulte [Crear un entorno](create-environment.md). Para iniciar una prueba de conclusiones del público, consulte [Configurar un entorno de prueba](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Paso 2: explorar las conclusiones del público

La primera vez que inicie sesión en las conclusiones del público, puede configurar los ajustes y explorar el producto.

1. [Inicie sesión en conclusiones del público](https://home.ci.ai.dynamics.com) usando su cuenta de usuario de Microsoft Azure Active Directory (AAD).

1. [Cambie el entorno](manage-environments.md#switch-environments) para ver datos de demostración y [explorar las conclusiones del público](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Paso 3: ingesta, unificación y configuración de relaciones para sus datos

Los perfiles unificados son la base para obtener información y tomar medidas sobre los datos. Traiga datos de diversos orígenes y ejecute el proceso de unificación de datos para combinar perfiles unificados. Especifique relaciones entre las entidades ingeridas y use funciones de enriquecimiento para agregar información a los perfiles. 

1. Ingiera datos creando orígenes de datos a partir de múltiples opciones. Escoja entre [Conectores de Power Query](connect-power-query.md), una [carpeta de Common Data Model](connect-common-data-model.md) o [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Ejecute el [proceso de unificación de datos](data-unification.md) pasando por las fases de [mapa](map-entities.md), [coincidencia](match-entities.md) y [combinación](merge-entities.md).

1. Familiarícese con las [entidades que crea el sistema](entities.md) y cree [Relaciones entre las entidades ingeridas](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Paso 4: mejorar los perfiles unificados con predicciones, actividades y medidas

Con la configuración de perfiles unificados, puede mejorar sus datos y aumentar aún más la información que ofrecen.

1. Elija entre una biblioteca en expansión de proveedores de enriquecimiento para [enriquecer los datos de sus clientes](enrichment-hub.md).

1. Use [modelos listos para usar](predictions-overview.md) para predecir la probabilidad de abandono o los ingresos esperados.

1. [Configure actividades](activities.md) basándose en datos ingeridos y visualice las interacciones con sus clientes en una línea de tiempo cronológica. 

1. [Cree medidas](measures.md) para medir sus objetivos comerciales y los KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Paso 5: cree segmentos y active datos a través de varias opciones de exportación

Ahora que sus datos están completos y contienen una amplia gama de información sobre sus clientes, es hora de buscar formas de actuar sobre esos datos. 

1. [Cree segmentos](segments.md), subconjuntos de su base de clientes, para garantizar que sus acciones sean relevantes para los clientes objetivo.

1. Explore el catálogo en expansión de [opciones de exportacion](export-destinations.md), donde puede utilizar los datos de clientes. Por ejemplo, puede utilizar datos para gestionar promociones y contactar con marketing digital.

1. Revise las opciones de integración, por ejemplo con la [conexión directa con las conocimientos de involucración](../engagement-insights/integrate-audience-insights-engagement-insights.md) o con otras aplicaciones de Dynamics 365 con el [Complemento de tarjeta de cliente](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
