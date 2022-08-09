---
title: Encuentre clientes similares con IA (vista previa) (contiene vídeo)
description: Busque segmentos de clientes similares con inteligencia artificial.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170748"
---
# <a name="find-similar-customers-with-ai-preview"></a>Encuentre clientes similares con IA (vista previa)

Encuentre clientes similares en su base de clientes utilizando inteligencia artificial. Necesita al menos un segmento creado para usar esta característica. Ampliar los criterios de un segmento existente ayuda a encontrar clientes que sean similares a ese segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Encontrar clientes similares* utiliza medios automatizados para evaluar datos y hacer predicciones basadas en esos datos. Por lo tanto, tiene la capacidad de ser utilizado como un método de generación de perfiles, tal como se define ese término en el Reglamento General de Protección de Datos (“RGPD”). El uso de esta función por parte del cliente para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones. Usted es responsable de garantizar que el uso de Dynamics 365 Customer Insights, incluidas las predicciones, cumple con todas las leyes y regulaciones aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.

## <a name="find-similar-customers"></a>Buscar clientes similares

1. Vaya a **Segmentos** y seleccione el segmento en el que desea basar su nuevo segmento. Ese es su *segmento de origen*.

1. Seleccione **Buscar clientes similares**.

1. Revise el nombre sugerido para su nuevo segmento y cámbielo si es necesario.

1. Opcionalmente, agregue [etiquetas](work-with-tags-columns.md#manage-tags) al nuevo segmento.

1. Revise los campos que definen su nuevo segmento. Estos campos definen la base sobre la cual el sistema intentará encontrar clientes similares a su segmento de origen. El sistema selecciona los campos recomendados de forma predeterminada. Si es necesaro, agregue más campos.
  Los campos que pueden reducir significativamente el rendimiento del modelo se excluyen automáticamente:
  
   - Campos con los siguientes tipos de datos: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos con una cardinalidad (el número de elementos en un campo) de menos de 2 o más de 30

1. Elija si quiere incluir **Todos los clientes**, excepto el segmento de origen, o solo clientes de un **segmento diferente** de dentro de su nuevo segmento.

1. Por defecto, el sistema sugiere incluir solo el 20% del tamaño de público objetivo en su salida. Edite este umbral según sea necesario. Aumentar el umbral reducirá la precisión.

1. Incluya clientes en su segmento de origen seleccionando la casilla **Incluir miembros del segmento de origen además de los clientes con atributos similares**.

1. Seleccione **Ejecutar** en la parte inferior de la página para iniciar una [tarea de clasificación binaria](#about-similarity-scores) (un método de aprendizaje automático) que analice el conjunto de datos.

## <a name="view-the-similar-segment"></a>Ver el segmento similar

Después de procesar el segmento similar, encontrará el nuevo segmento en la página **Segmentos** con el tipo **Expansión**.

Seleccione **Vista** para ver la distribución de resultados en [puntuaciones de similitud](#about-similarity-scores) y valores de puntuaciones de similitud bajos en **Vista previa de los miembros del segmento**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmento de clientes similares.":::

## <a name="manage-a-similar-segment"></a>Administrar un segmento similar

[Trabaje con un segmento similar y adminístrelo](segments.md#manage-existing-segments) igual que con otros segmentos. Por ejemplo, exporte el segmento o cree una medida.

Edite, actualice, cambie el nombre, descargue y elimine un segmento similar. Editar un segmento similar vuelve a procesar los datos. El segmento creado anteriormente se actualiza con datos actualizados.

## <a name="about-similarity-scores"></a>Acerca de puntuaciones de similitud

El modelo de aprendizaje automático de clasificación binaria asigna una puntuación a los clientes del segmento similar. La puntuación se basa en la similitud con los clientes del segmento de origen.

- Las puntuaciones de similitud por debajo de 0,55 son clientes que el sistema clasificó como *no similares* a clientes del segmento de origen
- Las puntuaciones de similitud entre 0,55 - 0,7 se clasifican como *algo similares*
- Las puntuaciones de similitud entre 0,7 - 0,85 se clasifican como *similares*
- Las puntuaciones de similitud entre 0,85 - 1 son clientes que el sistema clasificó como *muy similares*

Los clientes con puntuaciones de similitud inferiores a 0,4 no se incluyen en el resultado del modelo. El sistema no los considera lo suficientemente similares al segmento de origen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
