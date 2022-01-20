---
title: Crear una vista unificada de sus clientes
description: Realice el proceso de unificación de datos con sus datos para crear un único conjunto maestro de datos de perfiles de clientes.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-unify
ms.openlocfilehash: c5422c9b60c21923caf4d9dc9baeec575cba093f
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977480"
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