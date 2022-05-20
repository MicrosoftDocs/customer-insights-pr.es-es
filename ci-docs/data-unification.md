---
title: Crear una vista unificada de sus clientes
description: Realice el proceso de unificación de datos con sus datos para crear un único conjunto maestro de datos de perfiles de clientes unificados.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755755"
---
# <a name="data-unification-overview"></a>Información general de la unificación de datos

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Después de [configurar los orígenes de datos](data-sources.md), puede unificar los datos. La unificación de datos le permite unificar fuentes de datos que alguna vez fueron dispares en un solo maestro conjunto de datos que proporciona una vista unificada de esos datos. Para consumidores individuales (B-to-C) donde los datos se centran en individuos, la unificación proporciona una vista unificada de sus clientes. Para cuentas empresariales (B-to-B) donde los datos se centran en las cuentas, la unificación proporciona una vista unificada de sus cuentas.

Los datos se pueden unificar en una sola entidad o en varias entidades. La unificación se realiza en el siguiente orden:

1. [Campos de origen](map-entities.md) (anteriormente llamado Mapa): en el paso de campos de origen, seleccione entidades y campos para incluir en el proceso de unificación. Asigne campos a un tipo semántico común que describa el propósito del campo.

1. [Registros duplicados](remove-duplicates.md) (anteriormente parte de Match): en el paso de registros duplicados, opcionalmente defina reglas para eliminar registros de clientes duplicados dentro de cada entidad.

1. [Condiciones coincidentes](match-entities.md) (anteriormente llamado Coincidencia): en el paso de condiciones de coincidencia, defina reglas que coincidan con registros de clientes entre entidades. Cuando un cliente se encuentra en dos o más entidades, se crea un único registro consolidado con todas las columnas y datos de cada entidad.

1. [Campos de clientes unificados](merge-entities.md) (anteriormente llamado Fusionar): en el paso de campos de clientes unificados, determine qué campos de origen deben incluirse, excluirse o fusionarse en un perfil de cliente unificado.  

1. [Revisar](review-unification.md) y cree el perfil unificado.

Después de completar la unificación de datos, puede opcionalmente:

- [Configurar relaciones entre entidades](relationships.md) para crear segmentos sofisticados.
- [Enriquecer sus datos](enrichment-hub.md) para obtener una gama más amplia de información sobre sus clientes.
- [Definir actividades](activities.md) de algunos de los atributos ingeridos.
- [Construir medidas](measures.md) para comprender mejor los comportamientos de los clientes y el rendimiento empresarial.

[!INCLUDE [footer-include](includes/footer-banner.md)]
