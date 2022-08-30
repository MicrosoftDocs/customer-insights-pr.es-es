---
title: Crear una vista unificada de sus clientes
description: Realice el proceso de unificación de datos con sus datos para crear un único conjunto maestro de datos de la cuenta o perfiles de clientes.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304448"
---
# <a name="data-unification-overview"></a>Información general de la unificación de datos

Después de [configurar los orígenes de datos](data-sources.md), puede unificar los datos. La unificación de datos le permite unificar fuentes de datos que alguna vez fueron dispares en un solo maestro conjunto de datos que proporciona una vista unificada de esos datos.

Para consumidores individuales (B-to-C) donde los datos se centran en individuos, la unificación proporciona una vista unificada de sus clientes. Para cuentas empresariales (B-to-B) donde los datos se centran en las cuentas, la unificación proporciona una vista unificada de sus cuentas. [Unificación de contactos (versión preliminar)](data-unification-contacts.md) permite que los contactos de esas cuentas se unifiquen por separado y se asocien con las cuentas.

Los datos se pueden unificar en una sola entidad o en varias entidades.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

El proceso de unificación mapea datos de clientes de sus fuentes de datos, elimina duplicados, compara los datos entre entidades y crea un perfil unificado. La unificación se realiza en el siguiente orden:

1. [Campos de origen](map-entities.md) (anteriormente llamado Mapa): en el paso de campos de origen, seleccione entidades y campos para incluir en el proceso de unificación. Asigne campos a un tipo semántico común que describa el propósito del campo.

1. [Registros duplicados](remove-duplicates.md) (anteriormente parte de Match): en el paso de registros duplicados, opcionalmente defina reglas para eliminar registros de clientes duplicados dentro de cada entidad.

1. [Condiciones coincidentes](match-entities.md) (anteriormente llamado Coincidencia): en el paso de condiciones de coincidencia, defina reglas que coincidan con registros de clientes entre entidades. Cuando un cliente se encuentra en dos o más entidades, se crea un único registro consolidado con todas las columnas y datos de cada entidad.

1. [Campos de clientes unificados](merge-entities.md) (anteriormente llamado Fusionar): en el paso de campos de clientes unificados, determine qué campos de origen deben incluirse, excluirse o fusionarse en un perfil de cliente unificado.  

1. [Revisar](review-unification.md) y cree el perfil unificado.

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

El proceso de unificación mapea datos de cuenta de sus fuentes de datos, elimina duplicados, compara los datos entre entidades y crea un perfil unificado. La unificación se realiza en el siguiente orden:

1. [Campos de origen](map-entities.md) (anteriormente llamado Mapa): en el paso de campos de origen, seleccione entidades y campos para incluir en el proceso de unificación de cuenta. Asigne campos a un tipo semántico común que describa el propósito del campo.

1. [Registros duplicados](remove-duplicates.md) (anteriormente parte de Match): en el paso de registros duplicados, opcionalmente defina reglas para eliminar registros de cuentas duplicados dentro de cada entidad.

1. [Condiciones coincidentes](match-entities.md) (anteriormente llamado Coincidencia): en el paso de condiciones de coincidencia, defina reglas que coincidan con registros de cuentas entre entidades. Cuando una cuenta se encuentra en dos o más entidades, se crea un único registro consolidado con todas las columnas y datos de cada entidad.

1. [Campos de clientes unificados](merge-entities.md) (anteriormente llamado Fusionar): en el paso de campos de clientes unificados, determine qué campos de origen deben incluirse, excluirse o fusionarse en un perfil de cliente unificado.  

1. [Revisar](review-unification.md) y cree el perfil unificado.

Después de unificar las cuentas , puede [unificar los contactos (vista previa)](data-unification-contacts.md), opcionalmente, para esas cuentas y vincular los contactos unificados a las cuentas unificadas.

---

Después de completar la unificación de datos, puede opcionalmente:

- [Configurar relaciones entre entidades](relationships.md) para crear segmentos sofisticados.
- [Enriquecer sus datos](enrichment-hub.md) para obtener una gama más amplia de información sobre sus clientes.
- [Definir actividades](activities.md) de algunos de los atributos ingeridos.
- [Construir medidas](measures.md) para comprender mejor los comportamientos de los clientes y el rendimiento empresarial.

[!INCLUDE [footer-include](includes/footer-banner.md)]
