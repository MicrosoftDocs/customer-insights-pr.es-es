---
title: Límites de servicio en Customer Insights
description: Comprenda los límites y las restricciones en el servicio Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411761"
---
# <a name="service-limits-in-customer-insights"></a>Límites de servicio en Customer Insights

 Customer Insights tiene límites integrados diseñados para garantizar la fiabilidad y la estabilidad del servicio. Las solicitudes para los cambios pueden realizarse a través del [foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Región  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas y predicciones | 300  | El numero total de [segmentos](segments.md), [medidas](measures.md), y [predicciones](predictions-overview.md) combinadas no pueden pasar de 300.  |
| Relaciones | 20 niveles de profundidad en relaciones de rutas de entidad. | Al crear [segmentos](segments.md) o [medidas](measures.md) mediante la interfaz del generador, las rutas de las entidades pueden tener hasta 20 saltos de relación entre la entidad de inicio y la entidad de destino.  |

## <a name="fair-scheduling-of-jobs"></a>Programación justa de trabajos

Customer Insights es un servicio SaaS que usa recursos compartidos de Azure. Los clientes tienden a tener cargas de trabajo de intensidad variable y en diferentes horarios. Para garantizar un acceso justo a los recursos subyacentes, nos aseguramos de que los procesos del sistema se ejecuten en el orden justo. Ejemplos de procesos del sistema son trabajos relacionados con la unificación de datos, actualizaciones de segmentos o cálculo de medidas. La programación justa lo protege de hacer cola para obtener recursos si hay un pico de trabajos solicitados. Al mismo tiempo, Customer Insights no garantiza que todos los trabajos que pone en cola se procesen en paralelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
