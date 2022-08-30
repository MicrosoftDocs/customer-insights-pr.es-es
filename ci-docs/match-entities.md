---
title: Condiciones de coincidencia para la unificación de datos
description: Asignar entidades para crear perfiles de cliente unificados.
recommendations: false
ms.date: 07/27/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: eaa3409aaa7541dc88953336942e43afaf6511c6
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304678"
---
# <a name="match-conditions-for-data-unification"></a>Condiciones de coincidencia para la unificación de datos

Este paso en la unificación define el orden de coincidencia y las reglas para la coincidencia entre entidades. Este paso requiere al menos dos entidades.

> [!NOTE]
> Una vez que cree sus condiciones de coincidencia y seleccione **Siguiente**, no puede eliminar una entidad o atributo seleccionado. Si es necesario, seleccione **Atrás** para revisar las entidades y atributos seleccionados antes de continuar.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Incluir entidades enriquecidas (versión preliminar)

Si enriqueció entidades en el nivel origen de datos para ayudar a mejorar sus resultados de unificación, selecciónelas. Para obtener más información, consulte [Enriquecimiento de orígenes de datos](data-sources-enrichment.md). Si seleccionó entidades enriquecidas en la página **Registros duplicados**, no necesita seleccionarlos de nuevo.

1. En la página **Condiciones coincidentes**, seleccione **Usar entidades enriquecidas** en la parte superior de la página.

1. Desde el panel **Usar entidades enriquecidas**, elija una o más entidades enriquecidas.

1. Seleccione **Listo**.

## <a name="specify-the-match-order"></a>Especifique el orden de coincidencia

Cada coincidencia unifica dos o más entidades en una sola entidad consolidada. Al mismo tiempo, mantiene registros de clientes únicos. El orden de coincidencia indica el orden en que el sistema intenta hacer coincidir los registros.

> [!IMPORTANT]
> La primera entidad se llama entidad principal y sirve de base para los perfiles unificados. Las entidades adicionales que se seleccionen se agregarán a esta entidad.
>
> Consideraciones importantes:
>
> - Elija la entidad con los datos de perfil más completos y confiables sobre sus clientes como entidad principal.
> - Elija la entidad que tiene varios atributos en común con otras entidades (por ejemplo, nombre, número de teléfono o dirección de correo electrónico) como la entidad principal.

1. En la página **Condiciones coincidentes**, use las flechas hacia arriba y hacia abajo para mover las entidades en el orden que desee, o arrástrelas y suéltelas. Por ejemplo, seleccione **eCommerceCustomers** como entidad principal y **loyCustomers** como entidad secundaria.

1. Para tener cada registro en la entidad como un cliente único independientemente de si se encuentra una coincidencia, seleccione **Incluir todos los registros**. Todos los registros de esta entidad que no coincidan con los registros de otras entidades se incluyen en el perfil unificado. Los registros que no tienen una coincidencia se denominan singletons.
  
La entidad primaria *Contacts:eCommerce* se empareja con la siguiente entidad *CustomerLoyalty:Loyalty*. El conjunto de datos que resulta del primer paso de coincidencia se compara con la siguiente entidad si tiene más de dos entidades.

:::image type="content" source="media/m3_match.png" alt-text="Captura de pantalla del orden de coincidencia seleccionado para las entidades." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definir reglas para los pares de coincidencias

Las reglas de coincidencia especifican la lógica por la cual se emparejará un par específico de entidades. Una regla consta de una o más condiciones.

La advertencia junto al nombre de una entidad significa que no se ha definido ninguna regla de coincidencia para un par de coincidencias.

1. Seleccione **Agregar regla** para que un par de entidades defina reglas de coincidencia.

1. En el panel **Añadir regla**, configure las condiciones para la regla.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Captura de pantalla del panel Agregar regla.":::

   - **Seleccione Entidad/Campo (primera fila)**: elija una entidad y un atributo que probablemente sea único para un cliente. Por ejemplo, un número de teléfono o una dirección de correo electrónico. Evite las coincidencias por atributos de tipo de actividad. Por ejemplo, es probable que un identificador de compra no coincida con otros tipos de registro.

   - **Seleccione Entidad/Campo (segunda fila)**: elija un atributo que se relacione con el atributo de la entidad especificada en la primera fila.

   - **Normalizar**: seleccione entre las siguientes opciones de normalización para los atributos seleccionados.
     - **Números**: convierte otros sistemas numéricos, como números romanos, en números arábigos. *VIII* se convierte en *8*.
     - **Símbolos**: elimina todos los símbolos y caracteres especiales. *Cabeza&hombros* se convierte en *Cabezahombros*.
     - **Texto a minúsculas**: convierte todos los caracteres a minúsculas. *TODAS LAS MAYÚSCULAS y el título* se convierte en *todas las mayúsculas y el título*.
     - **Tipo (Teléfono, Nombre, Dirección, Organización)**: estandariza nombres, títulos, números de teléfono, direcciones y organizaciones.
     - **Unicode a ASCII**: convierte la notación Unicode en caracteres ASCII. */u00B2* se convierte en *2*.
     - **Espacio en blanco**: elimina todos los espacios. *Hola Mundo* se convierte en *HolaMundo*.

   - **Precisión**: establece el nivel de precisión que se aplicará a esta condición.
     - **Básico**: se escoge entre *Bajo (30 %)*, *Medio (60 %)*, *Alto (80 %)* y *Exacto (100 %)*. Seleccione **Exacto** para hacer coincidir solo los registros que coincidan al 100 por ciento.
     - **Personalizado**: establezca el porcentaje con el que los registros deben coincidir. El sistema solo hará coincidir los registros que superen este umbral.

   - **Nombre**: Nombre de la regla.

1. Para hacer coincidir entidades solo si los atributos cumplen varias condiciones, seleccione **Agregar** > **Agregar condición** para agregar más condiciones a una regla de coincidencia. Las condiciones están conectadas con un operador AND lógico y, por lo tanto, solo se ejecutan si se cumplen todas las condiciones.

1. Opcionalmente, considere opciones avanzadas como [excepciones](#add-exceptions-to-a-rule) o [condiciones de coincidencia personalizadas](#specify-custom-match-conditions).

1. Seleccione **Hecho** para finalizar la regla.

1. Opcionalmente, [agregue más reglas](#add-rules-to-a-match-pair).

1. Haga clic en **Siguiente**.

> [!div class="nextstepaction"]
> [Siguiente paso: unificar campos](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Agregar reglas a un par de coincidencias

Las reglas de coincidencia representan conjuntos de condiciones. Para hacer coincidir entidades mediante condiciones basadas en varios atributos, agregue más reglas.

1. Seleccione **Añadir regla** en la entidad a la que desea agregar reglas.

1. Siga los pasos en [Definir reglas para parejas coincidentes](#define-rules-for-match-pairs).

> [!NOTE]
> El orden de las reglas importa. El algoritmo de coincidencia intenta coincidir un regitro de cliente dado en función de la primera regla y continuará con la segunda regla solo si no se identificaron coincidencias con la primera regla.

## <a name="advanced-options"></a>Opciones avanzadas

### <a name="add-exceptions-to-a-rule"></a>Agregar excepciones a una regla

En la mayoría de los casos, la coincidencia de entidades conduce a perfiles de cliente únicos con datos consolidados. Para abordar los casos excepcionales de falsos positivos y falsos negativos, puede definir excepciones para una regla de coincidencia. Las excepciones se aplican después de procesar las reglas de coincidencia y evitan la coincidencia de todos los registros que cumplen los criterios de excepción.

Por ejemplo, si su regla de coincidencia combina apellido, ciudad y fecha de nacimiento, el sistema identificaría a los gemelos con el mismo apellido que viven en la misma ciudad que el mismo perfil. Puede especificar una excepción que no coincida con los perfiles si nombre de pila en las entidades que combina no son iguales.

1. En el panel **Editar regla**, seleccione **Añadir** > **Añadir excepción**.

1. Especifique los criterios de excepción.

1. Seleccione **Listo** para guardar la regla.

### <a name="specify-custom-match-conditions"></a>Especificar condiciones de coincidencia personalizadas

Puede especificar condiciones que anulen la lógica de coincidencia predeterminada. Existen cuatro opciones disponibles:

|Opción  |Description |Ejemplo  |
|---------|---------|---------|
|Coincidir siempre     | Define valores que siempre coinciden.         |  Siempre coincidir *Mike* y *MikeR*.       |
|No coincidir nunca     | Define valores que nunca coinciden.        | Nunca coincidir *John* y *Jonathan*.        |
|Omitir            | Define valores que el sistema siempre debe ignorar en la fase de coincidencia. |  Ignora los valores *11111* y *Desconocido* durante la coincidencia.        |
|Asignación de alias    | Definición de valores que el sistema debe considerar como un mismo valor.         | Considerar *Joe* igual a *Joseph*.        |

1. Seleccione **Personalizada**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Botón personalizado":::

1. Elija el **Tipo personalizado** y seleccione **Descargar plantilla**. Necesita una plantilla separada para cada opción de coincidencia.

1. Abra el archivo de plantilla descargado y complete los detalles. La plantilla contiene campos para especificar los valores de entidad y clave principal de la entidad que se utilizarán en la coincidencia personalizada. Por ejemplo, si desea una clave principal *12345* de la entidad *Ventas* para que siempre coincida con la clave principal *34567* de la entidad *Contacto*, complete la plantilla:
    - Entidad 1: Ventas
    - Entity1Key: 12345
    - Entity2: Contacto
    - Entity2Key: 34567

   El mismo archivo de plantilla puede especificar registros de coincidencia personalizados de múltiples entidades.

   Si desea especificar una coincidencia personalizada para la desduplicación en una entidad, proporcione la misma entidad como Entity1 y Entity2 y configure los diferentes valores de clave principal.

1. Después de agregar todas las modificaciones, guarde el archivo de plantilla.

1. Vaya a **Datos** > **Orígenes de datos** e ingiera los archivos de plantilla como nuevas entidades.

1. Después de cargar los archivos, seleccione la opción **Personalizado** de nuevo. Seleccione las entidades requeridas del menú desplegable y seleccione **Hecho**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla del cuadro de diálogo para elegir anulaciones para un escenario de partido personalizado.":::

1. La aplicación de la coincidencia personalizada depende de la opción de coincidencia que desee utilizar.

   - Para **Siempre coincidir** o **Nunca coincidir**, continúe con el siguiente paso.
   - Para **Omitir** o **Asignación de alias**, seleccione **Editar** en una regla de coincidencia existente o cree una nueva regla. En el menú desplegable Normalizaciones, elija la opción **Bypass personalizado** o **Asignación de alias** y seleccione **Hecho**.

1. Seleccione **Hecho** en el panel **Personalizado** para aplicar la configuración de coincidencia personalizada.

> [!div class="nextstepaction"]
> [Siguiente paso: unificar campos](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
