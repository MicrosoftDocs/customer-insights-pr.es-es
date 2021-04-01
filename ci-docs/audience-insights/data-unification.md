---
title: Unificación de datos
description: Aprenda a unificar datos ingeridos.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597900"
---
# <a name="data-unification-overview"></a>Información general de la unificación de datos

Después de [configurar los orígenes de datos](data-sources.md), puede unificar los datos. La unificación de datos incluye tres pasos: **Asignación**, **Coincidencia** y **Combinación**.

El proceso de unificación de datos le permite unificar fuentes de datos que alguna vez fueron dispares en un solo conjunto de datos maestro que proporciona una vista unificada de sus clientes. Las etapas de unificación son obligatorias y se realizan en el siguiente orden:

1. [Asignación](map-entities.md)
2. [Coincidencia](match-entities.md)
3. [Combinar](merge-entities.md)

Después de completar la unificación de datos, puede opcionalmente

- [configurar relaciones entre entidades](relationships.md) para crear segmentos sofisticados
- [enriquecer sus datos](enrichment-hub.md) para obtener una gama más amplia de información sobre sus clientes
- [definir actividades](activities.md) de algunos de los atributos ingeridos


[!INCLUDE[footer-include](../includes/footer-banner.md)]