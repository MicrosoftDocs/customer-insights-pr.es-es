---
title: Asignar entidades para la unificación de datos
description: Asignar entidades para crear perfiles de cliente unificados.
ms.date: 11/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 253c1614725252eb4c794d77669a00b401f0198d
ms.sourcegitcommit: 740e41ec965cee2229592a6d2610c12def116311
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "7863832"
---
# <a name="match-entities"></a>Coincidir entidades

La fase de coincidencia especifica cómo combinar sus conjuntos de datos en un conjunto de datos de perfil de cliente unificado. Después de completar el [paso de asignación](map-entities.md) en el proceso de unificación de datos, está listo para hacer coincidir sus entidades. La fase de coincidencia requiere al menos dos entidades asignadas.

La página de coincidencias consta de tres secciones: 
- Métricas clave que resumen la cantidad de registros coincidentes
- Orden de coincidencia y reglas para la coincidencia entre entidades
- Reglas para la deduplicación de entidades coincidentes

## <a name="specify-the-match-order"></a>Especifique el orden de coincidencia

Vaya a **Datos** > **Unificar** > **Establecer coincidencia** y seleccione **Establecer orden** para iniciar la fase de coincidencia.

Cada coincidencia unifica dos o más entidades en una sola entidad consolidada. Al mismo tiempo, mantiene registros de clientes únicos. Por ejemplo, seleccionamos dos entidades: **eCommerce:eCommerceContacts** como entidad primaria y **LoyaltyScheme:loyCustomers** como segunda entidad. El orden de las entidades especifica en qué orden el sistema intentará hacer coincidir los registros.

:::image type="content" source="media/match-page.png" alt-text="Captura de pantalla de la página Coincidir en el área Unificar del proceso de unificación de datos.":::
  
La entidad primaria *eCommerce: eCommerceContacts* se hace coincidir con la siguiente entidad *LoyaltyScheme: loyCustomers*. El conjunto de datos que resulta del primer paso de coincidencia se empareja con la siguiente entidad si tiene más de dos entidades.

> [!IMPORTANT]
> La entidad que elige como entidad principal servirá de base para el conjunto de datos de perfiles unificado. Las entidades adicionales que se seleccionen durante la fase de coincidencia se agregarán a esta entidad. Esto no significa que la entidad unificada incluirá *todos* los datos incluidos en esta entidad.
>
> Hay dos consideraciones que pueden ayudarlo a elegir la jerarquía de sus entidades:
>
> - Elija la entidad con los datos de perfil más completos y fiables sobre sus clientes como entidad principal.
> - Elija la entidad que tiene varios atributos en común con otras entidades (por ejemplo, nombre, número de teléfono o dirección de correo electrónico) como entidad principal.

Después de especificar el orden de coincidencia, verá los pares de coincidencias definidos en la sección **Detalles de registros coincidentes** en **Datos** > **Unificar** > **Coincidencia**. Las métricas clave estarán vacías hasta que se complete el proceso de coincidencia.

## <a name="define-rules-for-match-pairs"></a>Definir reglas para los pares de coincidencias

Las reglas de coincidencia especifican la lógica por la cual se emparejará un par específico de entidades.

La advertencia **Necesita reglas** junto al nombre de una entidad sugiere que no se define una regla de coincidencia para un par de coincidencias. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de pantalla de la sección Detalles de registros coincidentes con control para agregar reglas resaltadas.":::

1. Seleccione **Agregar reglas** bajo una entidad en la sección **Detalles de registros coincidentes** para definir las reglas de coincidencia.

1. En el panel **Crear regla**, configure las condiciones para la regla.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de pantalla de una regla de coincidencia abierta con condiciones agregadas.":::

   - **Entidad / Campo (primera fila)**: elija una entidad relacionada y un atributo para especificar una propiedad de registro que probablemente sea exclusiva de un cliente. Por ejemplo, un número de teléfono o una dirección de correo electrónico. Evite las coincidencias por atributos de tipo de actividad. Por ejemplo, es probable que un identificador de compra no coincida con otros tipos de registro.

   - **Entidad / Campo (segunda fila)**: elija un atributo que se relacione con el atributo de la entidad especificada en la primera fila.

   - **Normalizar**: seleccione entre las siguientes opciones de normalización para los atributos seleccionados. 
     - Espacio en blanco: elimina todos los espacios. *Hola Mundo* se convierte en *HolaMundo*.
     - Símbolos: elimina todos los símbolos y caracteres especiales. *Cabeza&hombros* se convierte en *Cabezahombros*.
     - Texto a minúsculas: convierte todos los caracteres a minúsculas. *TODAS LAS MAYÚSCULAS y el título* se convierte en *todas las mayúsculas y el título*.
     - Unicode a ASCII: convierte la notación Unicode en caracteres ASCII. */u00B2* se convierte en *2*.
     - Números: convierte otros sistemas numéricos, como números romanos, en números arábigos. *VIII* se convierte en *8*.
     - Tipos semánticos: estandariza nombres, títulos, números de teléfono, direcciones, etc. 

   - **Precisión**: establece el nivel de precisión que se aplicará a esta condición. 
     - **Básico**: se escoge entre *Bajo*, *Medio*, *Alto*, y *Exacto*. Seleccione **Exacto** para hacer coincidir solo los registros que coinciden al 100 por ciento. Seleccione uno de los otros niveles para que coincidan los registros que no son 100 por ciento idénticos.
     - **Personalizado**: establezca el porcentaje con el que los registros deben coincidir. El sistema solo hará coincidir los registros que superen este umbral.

1. Especifique un **Nombre** para la regla.

1. [Agregue más condiciones](#add-conditions-to-a-rule) o seleccione **Hecho** para finalizar la regla.

1. Opcionalmente, [agregue más reglas](#add-rules-to-a-match-pair).

1. Seleccione **Guardar** para aplicar los cambios.

### <a name="add-conditions-to-a-rule"></a>Agregar condiciones a una regla

Para hacer coincidir entidades solo si los atributos cumplen varias condiciones, agregue más condiciones a una regla de coincidencia. Las condiciones están conectadas con un operador AND lógico y, por lo tanto, solo se ejecutan si se cumplen todas las condiciones.

1. Vaya a **Datos** > **Unificar** > **Coincidencia** y seleccione **Editar** en la regla a la que desea agregar condiciones.

1. En el panel **Editar regla**, seleccione **Agregar condición**.

1. Seleccione **Listo** para guardar la regla.

### <a name="add-rules-to-a-match-pair"></a>Agregar reglas a un par de coincidencias

Las reglas de coincidencia representan conjuntos de condiciones. Para hacer coincidir entidades mediante condiciones basadas en varios atributos, agregue más reglas

1.  Vaya a **Datos** > **Unificar** > **Coincidencia** y seleccione **Agregar regla** en la entidad a la que desea agregar reglas.

2. Siga los pasos en [Definir reglas para parejas coincidentes](#define-rules-for-match-pairs).

> [!NOTE]
> El orden de las reglas importa. El algoritmo de coincidencia intenta coincidir en función de la primera regla y continuará con la segunda regla solo si no se identificaron coincidencias con la primera regla.

### <a name="change-the-entity-order-in-match-rules"></a>Cambiar el orden de las entidades en las reglas de coincidencia

Puede reordenar las entidades para que las reglas de coincidencia cambien el orden en que se procesan. Se eliminarán las reglas que entren en conflicto debido a un cambio de orden. Tiene que volver a crear las reglas eliminadas con una configuración actualizada.

1. Vaya a **Datos** > **Unificar** > **Coincidencia** y seleccione **Editar**.

1. En el panel **Editar regla** panel, seleccione el control **Mover hacia arriba/abajo** o arrastre y suelte entidades para cambiar el orden.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opciones para cambiar el orden en que se procesan las entidades en la fase de coincidencia.":::

1. Seleccione **Listo** para guardar la regla.

## <a name="define-deduplication-on-a-match-entity"></a>Definir la desduplicación en una entidad de coincidencia

Además de [reglas de coincidencia entre entidades](#define-rules-for-match-pairs), también puede especificar reglas de deduplicación. *Deduplicación* es otro proceso al comparar registros. Identifica registros duplicados y los combina en un solo registro. Los registros de origen se vinculan al registro combinado con id. alternativos.

Los registros desduplicados se utilizarán en el proceso de coincidencia entre entidades. La desduplicación tiene lugar en entidades individuales y se puede configurar cada entidad utilizada en pares de coincidencias.

No es obligatorio especificar reglas de desduplicación. Si no se configuran esas reglas, se aplican las reglas definidas por el sistema. Combinan todos los registros en un solo registro antes de pasar los datos de la entidad a la comparación entre entidades para mejorar el rendimiento.

### <a name="add-deduplication-rules"></a>Agregar reglas de desduplicación

1. Vaya a **Datos** > **Unificar** > **Coincidencia**.

1. En la sección **Duplicados fusionados**, seleccione **Establecer entidades**. En caso de que ya se hayan creado reglas de deduplicación, seleccione **Editar**.

1. En el panel **Preferencias de fusión**, elija las entidades en las que desea ejecutar la deduplicación.

1. Especifique cómo combinar los registros duplicados y elija una de las tres opciones:
   - **Más lleno**: identifica el registro con la más campos de atributo rellenados como el registro ganador. Es la opción de combinación predeterminada.
   - **Más reciente**: identifica el registro ganador basado en el más reciente. Requiere una fecha o un campo numérico para definir la antigüedad.
   - **Menos reciente**: identifica el registro ganador basado en el menos reciente. Requiere una fecha o un campo numérico para definir la antigüedad.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 1 de reglas de desduplicación.](media/match-selfconflation.png "Paso 1 de reglas de desduplicación")
 
1. Una vez que se seleccionan las entidades y se establece su preferencia de fusión, seleccione **Agregar regla** para definir las reglas de deduplicación a nivel de entidad.
   - **Seleccionar campo** enumera todos los campos disponibles de esa entidad. Elija el campo en el que desea verificar si hay duplicados. Elija campos que probablemente sean únicos para cada cliente. Por ejemplo, una dirección de correo electrónico o la combinación de nombre, ciudad y número de teléfono.
   - Especifique la configuración de normalización y precisión.
   - Defina más condiciones adicionales seleccionando **Agregar condición**.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 2 de reglas de desduplicación.](media/match-selfconflation-rules.png "Paso 2 de reglas de desduplicación")

  Puede crear varias reglas de desduplicación para una entidad. 

1. La ejecución del proceso de coincidencia ahora agrupa los registros según las condiciones definidas en las reglas de desduplicación. Después de agrupar los registros, se aplica la política de combinación para identificar el registro ganador.

1. Este registro elegido se pasa luego a la correspondencia entre entidades, junto con los registros no elegidos (por ejemplo, identificadores alternativos) para mejorar la calidad de la coincidencia.

1. Cualquier regla de coincidencia personalizada definida sobrescribe las reglas de deduplicación. Si una regla de desduplicación identifica registros coincidentes y se establece una regla de coincidencia personalizada para no hacer coincidir nunca esos registros, estos dos registros no coincidirán.

1. Después de [ejecutar el proceso de coincidencia](#run-the-match-process), verá las estadísticas de deduplicación en el mosaico de métricas clave.

### <a name="deduplication-output-as-an-entity"></a>Resultado de la desduplicación como entidad

El proceso de deduplicación crea una nueva entidad para cada entidad de los pares coincidentes para identificar los registros deduplicados. Estas entidades se pueden encontrar junto con **ConflationMatchPairs:CustomerInsights** en la sección **Sistema** en la página **Entidades**, con el nombre **Deduplication_DataSource_Entity**.

Una entidad de resultado de la desduplicación contiene la siguiente información:
- Identificadores y claves
  - Campo de clave principal y su campo de identificadores alternativos. El campo de identificadores alternativos consta de todos los identificadores alternativos identificados para un registro.
  - El campo Deduplication_GroupId muestra el grupo o clúster identificado dentro de una entidad que agrupa todos los registros similares según los campos de desduplicación especificados. Se utiliza para fines de procesamiento del sistema. Si no hay reglas de desduplicación manual especificadas y se aplican reglas de desduplicación definidas por el sistema, es posible que no encuentre este campo en la entidad de resultados de la desduplicación.
  - Deduplication_WinnerId: este campo contiene el identificador del elemento elegido en los grupos o clústeres identificados. Si Deduplication_WinnerId es el mismo que el valor de la clave principal para un registro, significa que el registro es el elegido.
- Campos utilizados para definir las reglas de desduplicación.
- Los campos Regla y Puntuación indican cuál de las reglas de desduplicación se aplicó y la puntuación devuelta por el algoritmo de coincidencia.
   
## <a name="run-the-match-process"></a>Ejecutar el proceso de comparación

Con las reglas de coincidencia configuradas, incluidas las reglas de desduplicación y coincidencia entre entidades, puede ejecutar el proceso de coincidencia. 

Vaya a **Datos** > **Unificar** > **Coincidencia** y seleccione **Ejecutar** para iniciar el proceso. El algoritmo de coincidencia tarda algún tiempo en completarse y no puede cambiar la configuración hasta que se complete. Para hacer cambios puede cancelar la ejecución. Seleccione el estado del trabajo y seleccione **Cancelar trabajo** en el panel **Detalles de progreso**.

Encontrará el resultado de una ejecución exitosa, la entidad de perfil de cliente unificado, en la página **Entidades**. Su entidad cliente unificada se llama **Clientes** en la sección **Perfiles**. La primera ejecución de coincidencia exitosa crea la entidad unificada *Cliente*. Todas las ejecuciones de coincidencias posteriores expanden esa entidad.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Revisar y validar las coincidencias

Vaya a **Datos** > **Unificar** > **Coincidencia** para evaluar la calidad de sus pares de coincidencias y refinarlos si es necesario.

Los mosaicos en la parte superior de la página muestran métricas clave, que resumen el número de registros coincidentes y duplicados.

:::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla recortada de las métricas clave en la página Coincidencia con números y detalles.":::

- **Registros de origen únicos** muestra el número de registros de origen individuales que se procesaron en la última ejecución de coincidencia.
- **Registros coincidentes y no coincidentes** resalta cuántos registros únicos quedan después de procesar las reglas de coincidencia.
- **Solo registros coincidentes** muestra el número de coincidencias en todos sus pares de coincidencias.

Puede evaluar los resultados de cada par de coincidencias y sus reglas en la tabla **Detalles de registros coincidentes**. Compare el número de registros que provienen de un par coincidente con el porcentaje de registros coincidentes correctamente.

Revise las reglas de un par de coincidencias para ver el porcentaje de registros que coinciden correctamente en el nivel de la regla. Seleccione los puntos suspensivos (...) y luego seleccione **Vista previa de la coincidencia** para ver todos estos registros en el nivel de la regla. Le recomendamos que eche un vistazo a algunos registros para validar que se emparejaron correctamente.

Pruebe diferentes umbrales de precisión en las condiciones para encontrar el valor óptimo.

  1. Seleccione los puntos suspensivos (...) de la regla con la que desea experimentar y seleccione **Editar**.

  2. Cambie los valores de precisión en las condiciones que quiera revisar.

  3. Seleccione **Vista previa** para ver el número de registros coincidentes y no coincidentes para la condición seleccionada.

## <a name="manage-match-rules"></a>Administrar reglas de coincidencia

Puede reconfigurar y ajustar la mayoría de los parámetros de coincidencia.

:::image type="content" source="media/match-rules-management.png" alt-text="Captura de pantalla del menú desplegable con opciones de regla coincidentes.":::

- **Cambia el orden de las reglas** si definió múltiples reglas. Puede reordenar las reglas de partido seleccionando las opciones **Subir** y **Bajar** o arrastrando y soltando.

- **Cambie las condiciones de la regla** seleccionando **Editar** y elija diferentes campos.

- **Desactivar una regla** es para conservar una regla de coincidencia y excluirla del proceso de coincidencia.

- **Duplique sus reglas** si ha definido una regla de coincidencia y le gustaría crear una regla similar con modificaciones, seleccione **Duplicar**.

- **Elimine una regla** seleccionando el símbolo **Eliminar**.

## <a name="specify-custom-match-conditions"></a>Especificar condiciones de coincidencia personalizadas

Puede especificar condiciones que anulen la lógica de coincidencia predeterminada. Existen cuatro opciones disponibles: 

|Opción  |Description |Ejemplo  |
|---------|---------|---------|
|Coincidir siempre     | Define valores que siempre coinciden.         |  Siempre coincidir *Mike* y *MikeR*.       |
|No coincidir nunca     | Define valores que nunca coinciden.        | Nunca coincidir *John* y *Jonathan*.        |
|Omisión personalizada     | Define valores que el sistema siempre debe ignorar en la fase de coincidencia. |  Ignora los valores *11111* y *Desconocido* durante la coincidencia.        |
|Asignación de alias    | Definición de valores que el sistema debe considerar como un mismo valor.         | Considerar *Joe* igual a *Joseph*.        |

1. Vaya a **Datos** > **Unificar** > **Coincidencia** y seleccione **Coincidencia personalizada** en la sección **Detalles de registros coincidentes**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Captura de pantalla de la sección reglas de coincidencia con el control de personalizar coincidencia resaltado.":::

1. En el panel **Personalizado**, vaya a la pestaña **Registros**.

1. Elija la opción de coincidencia personalizada del menú desplegable **Tipo personalizado** y seleccione **Descargar plantilla**. Necesita una plantilla separada para cada opción de coincidencia.

1. Un archivo de plantilla se descarga. Ábralo y complete los detalles. La plantilla contiene campos para especificar los valores de entidad y clave principal de la entidad que se utilizarán en la coincidencia personalizada. Por ejemplo, si desea una clave principal *12345* de la entidad *Ventas* para que siempre coincida con la clave principal *34567* de la entidad *Contacto*, complete la plantilla:
    - Entidad 1: Ventas
    - Entity1Key: 12345
    - Entity2: Contacto
    - Entity2Key: 34567

   El mismo archivo de plantilla puede especificar registros de coincidencia personalizados de múltiples entidades.
   
   Si desea especificar una coincidencia personalizada para la desduplicación en una entidad, proporcione la misma entidad como Entity1 y Entity2 y configure los diferentes valores de clave principal.

1. Después de agregar todas las modificaciones, guarde el archivo de plantilla.

1. Vaya a **Datos** > **Orígenes de datos** e ingiera los archivos de plantilla como nuevas entidades.

1. Después de cargar los archivos y de que las entidades estén disponibles, seleccione la opción **Coincidencia personalizada** de nuevo. Verá opciones para especificar las entidades que desea incluir. Seleccione las entidades requeridas del menú desplegable y seleccione **Hecho**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla del cuadro de diálogo para elegir anulaciones para un escenario de partido personalizado.":::

1. La aplicación de la coincidencia personalizada depende de la opción de coincidencia que desee utilizar. 

   - Para **Siempre coincidir** o **Nunca coincidir**, continúe con el siguiente paso.
   - Para **Bypass personalizado** o **Asignación de alias**, seleccione **Editar** en una regla de coincidencia existente o cree una nueva regla. En el menú desplegable Normalizaciones, elija la opción **Bypass personalizado** o **Asignación de alias** y seleccione **Hecho**.

1. Seleccione **Guardar** en la página **Coincidencia** para aplicar la configuración de coincidencia personalizada.

1. Seleccione **Ejecutar** en la página **Coincidencia** para iniciar el proceso de coincidencia. Otras reglas de coincidencia especificadas se anulan mediante la configuración de coincidencia personalizada.

### <a name="known-issues"></a>Problemas conocidos

- La autoconflación no muestra los datos normalizados en las entidades de deduplicación. Sin embargo, aplica la normalización internamente durante la deduplicación. Está diseñado para todas las normalizaciones. 
- Si la configuración de tipo semántico se elimina en la fase **Asignar** cuando una regla de coincidencia utiliza la asignación de alias o la omisión personalizada, la normalización no se aplicará. Solo sucede si borra el tipo semántico después de configurar la normalización en la regla de coincidencia porque el tipo semántico será desconocido.


## <a name="next-step"></a>Siguiente paso

Después de completar el proceso de emparejamiento para al menos un par de emparejamientos, continúe con el paso [**Unir**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
