---
title: Límites de servicio en Dynamics 365 Customer Insights
description: Comprenda los límites y restricciones.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7792001"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Límites de servicio en capacidades de Customer Insights

En este artículo se describen los límites integrados en el servicio de Customer Insights, diseñados para garantizar la confiabilidad y la estabilidad del servicio. Las solicitudes para los cambios pueden realizarse a través del [foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Conclusiones del público

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límites de servicio de la capacidad de informaciones de público en Dynamics 365 Customer Insights

| Región  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas y predicciones | 300  | El numero total de [segmentos](audience-insights/segments.md), [medidas](audience-insights/measures.md), y [predicciones](audience-insights/predictions.md) combinadas no pueden pasar de 300.  |
| Relaciones | 20 niveles de profundidad en relaciones de rutas de entidad. | Al crear [segmentos](audience-insights/segments.md) o [medidas](audience-insights/measures.md) mediante la interfaz del generador, las rutas de las entidades pueden tener hasta 20 saltos de relación entre la entidad de inicio y la entidad de destino.  |


## <a name="engagement-insights"></a>Conclusiones sobre la involucración

### <a name="workspace-and-event-quotas"></a>Cuotas de espacios de trabajo y eventos

Conclusiones sobre la interacción es una aplicación altamente escalable que puede admitir millones de eventos por segundo. Durante la versión preliminar pública, los eventos tienen un umbral de volumen. También hay un límite para la cantidad de áreas de trabajo en una organización.

### <a name="engagement-insights-limits"></a>Límites de las conclusiones sobre la interacción

- Volumen máximo de eventos por área de trabajo = 100 eventos por segundo

- Número máximo de áreas de trabajo por organización = 100

Cuando los eventos superan el umbral, puede provocar la pérdida de datos en los informes basados en esos eventos. Puede [ponerse en contacto con el soporte técnico](https://go.microsoft.com/fwlink/?linkid=2145734) para solicitar un aumento de volumen antes de superar los límites. Trabajaremos con usted para determinar su necesidad de un aumento de volumen y para respaldar su solicitud.


[!INCLUDE[footer-include](includes/footer-banner.md)]
