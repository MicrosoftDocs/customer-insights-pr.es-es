---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611111"
---
- **Rendimiento del modelo de entrenamiento**: los grados A, B o C indican el rendimiento de la predicción y puede ayudarlo a tomar la decisión de utilizar los resultados almacenados en la entidad de salida.

  Las puntuaciones se determinan según las siguientes reglas:
  - **A** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es mayor que la tasa de referencia en al menos un 10 %.
  - **B** cuando el modelo predijo con precisión al menos el 50 % de las predicciones totales, y cuando el porcentaje de predicciones precisas para los clientes que abandonaron es hasta un 10 % mayor que la referencia.
  - **C** cuando el modelo predijo con precisión menos del 50 % de las predicciones totales, o cuando el porcentaje de predicciones precisas para los clientes que abandonaron es inferior a la referencia.
  - **Referencia** toma la entrada de ventana de tiempo predicción para el modelo (por ejemplo, un año) y crea diferentes fracciones de tiempo dividiendo por 2 hasta que llega a un mes o menos. Utiliza estas fracciones para crear una regla de negocio para los clientes que no han comprado en este plazo de tiempo. Estos clientes se consideran abandonados. La regla de negocio basada en el tiempo con la mayor capacidad para predecir quién es probable que abandone se elige como modelo de referencia.

- **Probabilidad de pérdida (número de clientes)**: Grupos de clientes según su riesgo de pérdida previsto. Opcionalmente, [cree segmentos de clientes](../prediction-based-segment.md) con alto riesgo de abandono. Dichos segmentos ayudan a comprender dónde debe estar el corte para la pertenencia del segmento.

- **Factores más influyentes**: Hay muchos factores que se tienen en cuenta al crear su predicción. Cada uno de los factores tiene su importancia calculada para las predicciones agregadas que crea un modelo. Use estos factores para ayudar a validar los resultados de la predicción. O use esta información más tarde para [crear segmentos](../prediction-based-segment.md) que puedan ayudar a influir en el riesgo de pérdida de clientes.