---
title: Límites de servicio
description: Comprenda los límites y restricciones.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034885"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límites de servicio de la capacidad de informaciones de público en Dynamics 365 Customer Insights

En este artículo se describen los límites integrados en el servicio de Customer Insights, diseñados para garantizar la confiabilidad y la estabilidad del servicio. Las solicitudes para los cambios pueden realizarse a través del [foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Áreas  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos y medidas | 100 segmentos o medidas. | El número total de activos [segmentos](segments.md) y [medidas](measures.md) combinados no pueden exceder de 100.  |
| Relaciones | 20 niveles de profundidad en relaciones de rutas de entidad. | Al crear [segmentos](segments.md) o [medidas](measures.md) mediante la interfaz del generador, las rutas de las entidades pueden tener hasta 20 saltos de relación entre la entidad de inicio y la entidad de destino.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]