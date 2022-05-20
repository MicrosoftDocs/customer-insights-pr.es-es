---
title: Introducción a Dynamics 365 Customer Insights
description: Una descripción general de los recursos de ayuda de Customer Insights para comenzar rápidamente.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741154"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Introducción a Dynamics 365 Customer Insights

Customer Insights puede ayudarlo a comprender mejor a sus clientes. Conecte los datos de varias fuentes transaccionales, de comportamiento y de observación para crear un visión global de los clientes. Utilice esta información para impulsar experiencias y procesos centrados en el cliente. Unifique y conozca los datos de sus clientes y aprovéchelos para extraer conocimientos y acciones inteligentes.

## <a name="step-1-create-an-environment"></a>Paso 1: crear un entorno

Para empezar, primero tiene que crear un entorno en el que trabajar. Si su organización ya compró una licencia, consulte [Crear un entorno](create-environment.md). Para iniciar una prueba de Customer Insights, consulte [Configurar un entorno de prueba](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Paso 2: Explore Customer Insights

La primera vez que inicia sesión en Customer Insights, puede configurar los ajustes y explorar el producto.

1. [Inicie sesión en Customer Insights](https://home.ci.ai.dynamics.com) usando su cuenta de usuario de Microsoft Azure Active Directory (AAD).

1. [Cambie el entorno](manage-environments.md#switch-environments) para ver datos de demostración y [explorar Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Paso 3: ingesta, unificación y configuración de relaciones para sus datos

Los perfiles unificados son la base para obtener información y tomar medidas sobre los datos. Traiga datos de diversos orígenes y ejecute el proceso de unificación de datos para combinar perfiles unificados. Especifique relaciones entre las entidades ingeridas y use funciones de enriquecimiento para agregar información a los perfiles.

1. Ingiera datos creando orígenes de datos a partir de múltiples opciones. Elija entre [Conectores de Power Query](connect-power-query.md), una [carpeta de Common Data Model](connect-common-data-model.md) o [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Ejecute el [proceso de unificación de datos](data-unification.md) al identificar los [campos fuente](map-entities.md), quitando [duplicados](remove-duplicates.md) , [condiciones coincidentes](match-entities.md) y [campos unificadores](merge-entities.md).

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

1. Revise las opciones de integración, por ejemplo, con otras aplicaciones de Dynamics 365 con el [Complemento de tarjeta de cliente](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
