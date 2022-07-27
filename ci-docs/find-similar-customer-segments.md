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
ms.openlocfilehash: d58b2e424fd81ad691db4b2576bdf5655038ed89
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054829"
---
# <a name="find-similar-customers-with-ai-preview"></a>Encuentre clientes similares con IA (vista previa)

Esta característica le permite buscar clientes similares en su base de clientes utilizando inteligencia artificial. Debe tener al menos un segmento creado para usar esta función. Ampliar los criterios de un segmento existente ayuda a encontrar clientes que sean similares a ese segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Buscar clientes similares* utiliza medios automatizados para evaluar datos y hacer predicciones basadas en esos datos y, por lo tanto, tiene la capacidad de usarse como método de creación de perfiles, tal como lo define el Reglamento General de Protección de Datos ("RGPD"). El uso de esta función por parte del cliente para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones. Usted es responsable de garantizar que el uso de Dynamics 365 Customer Insights, incluidas las predicciones, cumple con todas las leyes y regulaciones aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.

## <a name="finding-similar-customers"></a>Buscar clientes similares

1. Vaya a **Segmentos** y seleccione el segmento en el que desea basar su nuevo segmento. Ese es su *segmento de origen*.

1. En la barra de acción, seleccione **Buscar clientes similares**.

1. Revise el nombre sugerido para su nuevo segmento y cámbielo si es necesario.

1. Opcionalmente, agregue [etiquetas](work-with-tags-columns.md#manage-tags) al nuevo segmento.

1. Revise los campos que definen su nuevo segmento. Estos campos definen la base sobre la cual el sistema intentará encontrar clientes similares a su segmento de origen. El sistema seleccionará los campos recomendados de forma predeterminada.
  Los campos que pueden reducir significativamente el rendimiento del modelo se excluyen automáticamente:
  
   - Campos con los siguientes tipos de datos: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos con una cardinalidad (el número de elementos en un campo) de menos de 2 o más de 30

1. Elija si quiere incluir **Todos los clientes** o solo clientes de un **Segmento existente específico** en su nuevo segmento.

1. Por defecto, el sistema sugiere incluir solo el 20% del tamaño audiencia objetivo en su salida. Edite este umbral según sea necesario. Aumentar el umbral reducirá la precisión.

1. Incluya clientes en su segmento de origen seleccionando la casilla **Incluir miembros del segmento de origen además de los clientes con atributos similares**.

1. Seleccione **Ejecutar** en la parte inferior de la página para iniciar una tarea de clasificación binaria (un método de aprendizaje automático) que analice el conjunto de datos.

## <a name="view-the-similar-segment"></a>Ver el segmento similar

Después de procesar el segmento similar, encontrará el nuevo segmento en la lista de la página **Segmentos**.

> [!div class="mx-imgBorder"]
> ![Segmento de clientes similares.](media/expanded-segment.png "Segmento de clientes similares")

Seleccione **Ver** en la barra de acción para abrir el detalle del segmento. Esta vista contiene información sobre la distribución de resultados en [puntuaciones de similitud](#about-similarity-scores). También encontrará los valores de puntuación de similitud en la **Vista previa de miembros del segmento**.

## <a name="use-the-output-of-a-similar-segment"></a>Use la salida de un segmento similar

Puede [trabajar con la salida de un segmento similar](segments.md) igual que con otros segmentos. Por ejemplo, exporte el segmento o cree una medida.

## <a name="refresh-and-edit-a-similar-segment"></a>Actualizar y editar un segmento similar

Para actualizar un segmento similar, selecciónelo en la página **Segmentos** y seleccione **Actualizar** en la barra de acción.

Editar un segmento similar volverá a procesar sus datos. El segmento creado anteriormente se actualiza con datos actualizados.
Para editar un segmento similar, selecciónelo en la página **Segmentos** y seleccione **Editar** en la barra de acción. Aplique los cambios y seleccione **Ejecutar** para comenzar el procesamiento.

## <a name="delete-a-similar-segment"></a>Eliminar un segmento similar

Seleccione el segmento en la página **Segmentos** y seleccione **Eliminar** en la barra de acción. A continuación, confirme la eliminación.

## <a name="about-similarity-scores"></a>Acerca de puntuaciones de similitud

El modelo de aprendizaje automático de clasificación binaria asigna una puntuación a los clientes del segmento similar. La puntuación se basa en la similitud con los clientes del segmento de origen.

- Las puntuaciones de similitud por debajo de 0,55 son clientes que el sistema clasificó como *no similares* a clientes del segmento de origen
- Las puntuaciones de similitud entre 0,55 - 0,7 se clasifican como *algo similares*
- Las puntuaciones de similitud entre 0,7 - 0,85 se clasifican como *similares*
- Las puntuaciones de similitud entre 0,85 - 1 son clientes que el sistema clasificó como *muy similares*

Los clientes con puntuaciones de similitud inferiores a 0,4 no se incluyen en el resultado del modelo. El sistema no los considera lo suficientemente similares al segmento de origen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
