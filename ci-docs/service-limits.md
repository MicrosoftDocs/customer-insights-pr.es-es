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
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641783"
---
# <a name="service-limits-in-customer-insights"></a>Límites de servicio en Customer Insights

En este artículo se describen los límites integrados en el servicio de Customer Insights, diseñados para garantizar la confiabilidad y la estabilidad del servicio. Las solicitudes para los cambios pueden realizarse a través del [foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Región  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas y predicciones | 300  | El numero total de [segmentos](segments.md), [medidas](measures.md), y [predicciones](predictions.md) combinadas no pueden pasar de 300.  |
| Relaciones | 20 niveles de profundidad en relaciones de rutas de entidad. | Al crear [segmentos](segments.md) o [medidas](measures.md) mediante la interfaz del generador, las rutas de las entidades pueden tener hasta 20 saltos de relación entre la entidad de inicio y la entidad de destino.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
