---
title: Límites de servicio en Dynamics 365 Customer Insights
description: Comprenda los límites y restricciones.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350428"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Límites de servicio en capacidades de Customer Insights

En este artículo se describen los límites integrados en el servicio de Customer Insights, diseñados para garantizar la confiabilidad y la estabilidad del servicio. Las solicitudes para los cambios pueden realizarse a través del [foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Conclusiones del público

| Región  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas y predicciones | 300  | El numero total de [segmentos](audience-insights/segments.md), [medidas](audience-insights/measures.md), y [predicciones](audience-insights/predictions.md) combinadas no pueden pasar de 300.  |
| Relaciones | 20 niveles de profundidad en relaciones de rutas de entidad. | Al crear [segmentos](audience-insights/segments.md) o [medidas](audience-insights/measures.md) mediante la interfaz del generador, las rutas de las entidades pueden tener hasta 20 saltos de relación entre la entidad de inicio y la entidad de destino.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
