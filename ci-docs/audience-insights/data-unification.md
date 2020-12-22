---
title: Unificación de datos
description: Aprenda a unificar datos ingeridos.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407012"
---
# <a name="data-unification"></a>Unificación de datos

Después de [configurar los orígenes de datos](data-sources.md), puede unificar los datos. La unificación de datos incluye tres pasos: **Asignación**, **Coincidencia** y **Combinación**.

El proceso de unificación de datos le permite unificar fuentes de datos que alguna vez fueron dispares en un solo conjunto de datos maestro que proporciona una vista unificada de sus clientes. Las etapas de unificación son obligatorias y se realizan en el siguiente orden:

1. [Asignación](map-entities.md)
2. [Coincidencia](match-entities.md)
3. [Combinar](merge-entities.md)

Después de completar la unificación de datos, puede opcionalmente

- [configurar relaciones entre entidades](relationships.md) para crear segmentos sofisticados
- [enriquecer sus datos](enrichment-hub.md) para obtener una gama más amplia de información sobre sus clientes
- [definir actividades](activities.md) de algunos de los atributos ingeridos
