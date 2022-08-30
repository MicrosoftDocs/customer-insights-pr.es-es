---
title: Eliminar duplicados antes de unificar datos
description: El segundo paso en el proceso de unificación es seleccionar qué registro guardar cuando se encuentran duplicados.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304494"
---
# <a name="remove-duplicates-before-unifying-data"></a>Eliminar duplicados antes de unificar datos

Este paso opcional en la unificación le permite configurar reglas para eliminar registros duplicados **dentro** de una entidad. La desduplicación identifica múltiples registros para un cliente y selecciona el mejor registro para conservar (según las preferencias básicas de combinación) o combina los registros en uno (según las preferencias avanzadas de combinación). Los registros de origen se vinculan al registro combinado con id. alternativos. Si no se configuran esas reglas, se aplican las reglas definidas por el sistema.

## <a name="default-deduplication"></a>Desduplicación predeterminada

Las reglas definidas por el sistema se aplican si no se han agregado reglas de desduplicación.

- La clave principal es la desduplicación.
  Para cualquier registro con la misma clave principal, el registro **Más lleno** (el que tiene menos valores nulos) es el ganador.
- Cualquier regla de coincidencia entre entidades se aplica a la entidad.
  Por ejemplo: en el paso de coincidencia, si la entidad A se compara con la entidad B en *FullName* y *DateofBirth*, entonces la entidad A también se desduplica por *FullName* y *DateofBirth*. Como *FullName* y *DateofBirth* son claves válidas para identificar un cliente en la entidad A, estas claves también son válidas para identificar clientes duplicados en la entidad A.

## <a name="include-enriched-entities-preview"></a>Incluir entidades enriquecidas (versión preliminar)

Si enriqueció entidades en el nivel origen de datos para ayudar a mejorar sus resultados de unificación, selecciónelas. Para obtener más información, consulte [Enriquecimiento de orígenes de datos](data-sources-enrichment.md).

1. En la página **Registros duplicados**, seleccione **Usar entidades enriquecidas** en la parte superior de la página.

1. Desde el panel **Usar entidades enriquecidas**, elija una o más entidades enriquecidas.

1. Seleccione **Listo**.

## <a name="define-deduplication-rules"></a>Definir reglas de desduplicación

1. En la página **Registros duplicados**, seleccione una entidad y seleccione **Agregar regla** para definir las reglas de deduplicación.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captura de pantalla de la página de registros duplicados con la entidad resaltada y se muestra Agregar regla"  lightbox="media/m3_duplicates_showmore.png":::

   1. En el panel **Agregar regla**, introduzca la siguiente información:
      - **Seleccionar campo**: elija de la lista de campos disponibles de la entidad que desea verificar si hay duplicados. Elija campos que probablemente sean únicos para cada cliente. Por ejemplo, una dirección de correo electrónico o la combinación de nombre, ciudad y número de teléfono.
      - **Normalizar**: seleccione entre las siguientes opciones de normalización para los atributos seleccionados.
        - **Números**: convierte otros sistemas numéricos, como números romanos, en números arábigos. *VIII* se convierte en *8*.
        - **Símbolos**: elimina todos los símbolos y caracteres especiales. *Cabeza&hombros* se convierte en *Cabezahombros*.
        - **Texto a minúsculas: convierte todos los caracteres a minúsculas**. *TODAS LAS MAYÚSCULAS y el título* se convierte en *todas las mayúsculas y el título*.
        - **Tipo (Teléfono, Nombre, Dirección, Organización)**: estandariza nombres, títulos, números de teléfono, direcciones, etc.
        - **Unicode a ASCII**: convierte la notación Unicode en caracteres ASCII. */u00B2* se convierte en *2*.
        - **Espacio en blanco**: elimina todos los espacios. *Hola Mundo* se convierte en *HolaMundo*.
      - **Precisión**: establece el nivel de precisión que se aplicará a esta condición.
        - **Básico**: se escoge entre *Bajo (30 %)*, *Medio (60 %)*, *Alto (80 %)* y *Exacto (100 %)*. Seleccione **Exacto** para hacer coincidir solo los registros que coincidan al 100 por ciento.
        - **Personalizado**: establezca el porcentaje con el que los registros deben coincidir. El sistema solo hará coincidir los registros que superen este umbral.
      - **Nombre**: Nombre de la regla.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Captura de pantalla del panel Agregar regla para eliminar duplicados.":::

   1. Opcionalmente, seleccione **Agregar** > **Agregar condición** para agregar más condiciones a la regla. Las condiciones están conectadas con un operador AND lógico y, por lo tanto, solo se ejecutan si se cumplen todas las condiciones.

   1. Opcionalmente, **Agregar** > **Añadir excepción** para [añadir excepciones a la regla](match-entities.md#add-exceptions-to-a-rule). Las excepciones se utilizan para abordar casos raros de falsos positivos y falsos negativos.

   1. Seleccione **Hecho** para crear la regla.

1. Opcionalmente, [agregue más reglas](#define-deduplication-rules).

1. Seleccione una entidad y luego **Editar preferencias de combinación**.

1. En el panel **Combinar preferencias**:
   1. Elija una de las tres opciones para determinar qué registro conservar si se encuentra un duplicado:
      - **Más lleno**: identifica el registro con la más campos de atributo rellenados como el registro ganador. Es la opción de combinación predeterminada.
      - **Más reciente**: identifica el registro ganador basado en el más reciente. Requiere una fecha o un campo numérico para definir la antigüedad.
      - **Menos reciente**: identifica el registro ganador basado en el menos reciente. Requiere una fecha o un campo numérico para definir la antigüedad.

      En caso de empate, el registro ganador es el que tiene el valor de clave principal MAX(PK) o mayor.

   1. Opcionalmente, para definir preferencias de combinación en atributos individuales de una entidad, seleccione **Avanzado** en la parte inferior del panel. Por ejemplo, puede optar por mantener el correo electrónico más reciente Y la dirección más completa de diferentes registros. Expanda la entidad para ver todos sus atributos y defina qué opción usar para atributos individuales. Si elige una opción basada en la antigüedad, también debe especificar un campo de fecha/hora que defina la antigüedad.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panel de preferencias de combinación avanzadas con el correo electrónico más reciente y la dirección completa":::

   1. Seleccione **Listo** para aplicar las preferencias de combinación.

1. Después de definir las reglas de deduplicación y las preferencias de combinación, seleccione **Siguiente**.
  
> [!div class="nextstepaction"]
> [Siguiente paso para una sola entidad: Unificar campos](merge-entities.md)

> [!div class="nextstepaction"]
> [Siguiente paso para varias entidades: condiciones coincidentes](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
