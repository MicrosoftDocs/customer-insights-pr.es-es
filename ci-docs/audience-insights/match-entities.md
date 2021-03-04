---
title: Asignar entidades para la unificación de datos
description: Asignar entidades para crear perfiles de cliente unificados.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267499"
---
# <a name="match-entities"></a>Coincidir entidades

Después de completar la fase de asignación, está listo para hacer coincidir sus entidades. La fase de coincidencia especifica cómo combinar sus conjuntos de datos en un conjunto de datos de perfil de cliente unificado. La fase de coincidencia requiere al menos [dos entidades asignadas](map-entities.md).

## <a name="specify-the-match-order"></a>Especifique el orden de coincidencia

Vaya a **Datos** > **Unificar** > **Establecer coincidencia** y seleccione **Establecer orden** para iniciar la fase de coincidencia.

Cada coincidencia unifica dos o más entidades en una sola entidad, mientras mantiene cada registro de cliente único. En el siguiente ejemplo, seleccionamos tres entidades: **ContactCSV: TestData** como entidad **Principal**, **WebAccountCSV: TestData** como **Entidad 2** y **CallRecordSmall: TestData** como **Entidad 3**. El diagrama sobre las selecciones ilustra cómo se ejecutará el orden de coincidencia.

> [!div class="mx-imgBorder"]
> ![Editar el orden de coincidencia de datos](media/configure-data-match-order-edit-page.png "Editar el orden de coincidencia de datos")
  
La entidad **Principal** coincide con **Entidad 2**. El conjunto de datos que resulta de la primera coincidencia se corresponde con **Entidad 3**.
En este ejemplo, solo seleccionamos dos coincidencias, pero el sistema puede admitir más.

> [!IMPORTANT]
> La entidad que elige como entidad **Principal** servirá de base para el conjunto de datos maestro unificado. Las entidades adicionales que se seleccionen durante la fase de coincidencia se agregarán a esta entidad. Al mismo tiempo, esto no significa que la entidad unificada incluirá *todos* los datos incluidos en esta entidad.
>
> Hay dos consideraciones que pueden ayudarlo a elegir la jerarquía de sus entidades:
>
> - ¿Qué entidad considera que tiene los datos más completos y fiables sobre sus clientes?
> - ¿La entidad que acaba de identificar tiene atributos que también comparten otras entidades (por ejemplo, nombre, número de teléfono o dirección de correo electrónico)? Si no, elija su segunda entidad más fiable.

Seleccione **Hecho** para guardar el orden de coincidencia.

## <a name="define-rules-for-your-first-match-pair"></a>Definir reglas para el primer par de coincidencia

Después de especificar el orden de coincidencia, verá las coincidencias definidas en la página **Coincidencia**. Las ventanas de la parte superior de la pantalla estarán vacías hasta que ejecute su orden de coincidencia.

> [!div class="mx-imgBorder"]
> ![Definir reglas](media/configure-data-match-need-rules.png "Definir reglas")

La advertencia **Reglas de necesidades** sugiere que no hay reglas de coincidencia definidas para un par de coincidencias. Las reglas de coincidencia especifican la lógica por la cual se emparejará un par específico de entidades.

1. Para definir la primera regla, abra el panel **Definición de regla** seleccionando la fila de coincidencia correspondiente en la tabla de coincidencias (1) y luego seleccionando **Crear nueva regla** (2).

   > [!div class="mx-imgBorder"]
   > ![Crear nueva regla](media/configure-data-match-new-rule2.png "Crear nueva regla")

2. En el panel **Editar regla**, configure las condiciones para esa regla. Cada condición está representada por dos filas que incluyen selecciones obligatorias.

   > [!div class="mx-imgBorder"]
   > ![Panel Nueva regla](media/configure-data-match-new-rule-condition.png "Panel Nueva regla")

   Entidad/campo (primero): un atributo que se utilizará para la coincidencia de la primera entidad de par de coincidencia. Los ejemplos podrían incluir un número de teléfono o una dirección de correo electrónico. Elija un atributo que pueda ser exclusivo del cliente.

   > [!TIP]
   > Evite la coincidencia en función de los atributos de tipo de actividad. En otras palabras, si un atributo parece ser una actividad, puede ser un criterio pobre para establecer coincidencia.  

   Entidad/campo (segundo): un atributo que se utilizará para la coincidencia de la segunda entidad de par de coincidencia.

   Normalizar - **Método de normalización**: Varias opciones de normalización están disponibles para los atributos seleccionados. Por ejemplo, eliminar puntuación o espacios

   Para la normalización del nombre de la organización (Vista previa), también puede seleccionar **Tipo (teléfono, nombre, organización)**

   > [!div class="mx-imgBorder"]
   > ![Normalización-B2B](media/match-normalization-b2b.png "Normalización-B2B")

   Nivel de precisión: el nivel de precisión que se utilizará para esta condición. Establecer un nivel de precisión para una condición de coincidencia puede tener dos tipos: **Básico** y **Personalizado**.  
   - Básico: le brinda cuatro opciones para seleccionar: Bajo, Medio, Alto y Exacto. Seleccione **Exacto** para hacer coincidir solo los registros que coinciden al 100 por ciento. Seleccione uno de los otros niveles para que coincidan los registros que no son 100 por ciento idénticos.
   - Personalizado: utilice el control deslizante para definir el porcentaje personalizado que los registros deben coincidir o introduzca un valor en el campo **Personalizado**. El sistema solo hará coincidir los registros que pasen este umbral como pares de coincidencia de combinación. Los valores en el control deslizante están entre 0 y 1. Por tanto, 0,64 representa el 64 por ciento.

3. Seleccione **Listo** para guardar la regla.

### <a name="add-multiple-conditions"></a>Agregar múltiples condiciones

Para hacer coincidir sus entidades solo si se cumplen varias condiciones, agregue más condiciones que estén vinculadas a través de un operador AND.

1. En el panel **Editar regla**, seleccione **Agregar condición**. También puede eliminar condiciones seleccionando el botón Eliminar junto a una condición existente.

2. Seleccione **Listo** para guardar la regla.

## <a name="add-multiple-rules"></a>Agregar varias reglas

Cada condición se aplica a un solo par de atributos, mientras que las reglas representan conjuntos de condiciones. Para que sus entidades coincidan con diferentes conjuntos de atributos, puede agregar más reglas.

1. En las informaciones de público, vaya a **Datos** > **Unificar** > **Coincidir**.

2. Seleccione la entidad que desea actualizar y seleccione **Agregar reglas**.

3. Siga el procedimiento como se describe en [Definir reglas para el primer par de coincidencia](#define-rules-for-your-first-match-pair).

> [!NOTE]
> El orden de las reglas importa. El algoritmo de coincidencia intenta hacer coincidir en función de la primera regla y continúa hasta la segunda regla solo si no se identificaron coincidencias según la primera regla.

## <a name="define-deduplication-on-a-match-entity"></a>Definir la desduplicación en una entidad de coincidencia

Además de especificar las reglas de coincidencia entre entidades como se describe en las secciones anteriores, también puede especificar reglas de desduplicación. *Desduplicación* es un proceso. Identifica registros duplicados, los fusiona en un registro y vincula todos los registros de origen a este registro combinado con id. alternativos al registro combinado.

Una vez que se identifica un registro desduplicado, ese registro se utilizará en el proceso de comparación entre entidades. La desduplicación se implementa en el nivel de entidad y se puede aplicar a todas las entidades utilizadas en el proceso de coincidencia.

### <a name="add-deduplication-rules"></a>Agregar reglas de desduplicación

1. En las informaciones de público, vaya a **Datos** > **Unificar** > **Coincidir**.

1. En la sección **Duplicados fusionados**, seleccione **Establecer entidades**.

1. En la sección **Preferencias de fusión**, seleccione las entidades a las que desea aplicar la desduplicación.

1. Especifique cómo combinar los registros duplicados y elija una de las tres opciones de combinación:
   - *Más lleno*: identifica el registro con la mayoría de los atributos rellenados como registro ganador. Esta es la opción de configuración predeterminada.
   - *Más reciente*: identifica el registro ganador basado en el más reciente. Requiere una fecha o un campo numérico para definir la antigüedad.
   - *Menos reciente*: identifica el registro ganador basado en el menos reciente. Requiere una fecha o un campo numérico para definir la antigüedad.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 1 de reglas de desduplicación](media/match-selfconflation.png "Paso 1 de reglas de desduplicación")
 
1. Una vez que se seleccionan las entidades y se establece su preferencia de fusión, seleccione **Crear nueva regla** para definir las reglas de desduplicación a nivel de entidad.
   - **Seleccionar campo** enumera todos los campos disponibles de esa entidad en la que desea desduplicar los datos de origen.
   - Especifique la configuración de normalización y precisión de manera similar a como se especifica en la coincidencia entre entidades.
   - Puede definir condiciones adicionales seleccionando **Agregar condición**.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 2 de reglas de desduplicación](media/match-selfconflation-rules.png "Paso 2 de reglas de desduplicación")

  Puede crear varias reglas de desduplicación para una entidad. 

1. La ejecución del proceso de coincidencia ahora agrupa los registros según las condiciones definidas en las reglas de desduplicación. Después de agrupar los registros, se aplica la política de combinación para identificar el registro ganador.

1. Este registro elegido se pasa luego a la correspondencia entre entidades, junto con los registros no elegidos (por ejemplo, identificadores alternativos) para mejorar la calidad de la coincidencia.

1. Las reglas de coincidencia personalizadas definidas para coincidir siempre y no coincidir nunca anulan las reglas de desduplicación. Si una regla de desduplicación identifica registros coincidentes y se establece una regla de coincidencia personalizada para no hacer coincidir nunca esos registros, estos dos registros no coincidirán.

1. Después de ejecutar el proceso de coincidencia, verá las estadísticas de desduplicación.
   
> [!NOTE]
> No es obligatorio especificar reglas de desduplicación. Si no se configuran tales reglas, se aplican las reglas definidas por el sistema. Contraen todos los registros que comparten la misma combinación de valores (coincidencia exacta) de la clave principal y los campos de las reglas de coincidencia en un solo registro antes de pasar los datos de la entidad a la coincidencia entre entidades para mejorar el rendimiento y el estado del sistema.

## <a name="run-your-match-order"></a>Ejecute el orden de coincidencia

Después de definir las reglas de coincidencia, incluidas las reglas de desduplicación y coincidencia entre entidades, puede ejecutar el orden de coincidencia. En la página **Coincidencia**, seleccione **Ejecutar** para iniciar el proceso. El algoritmo de coincidencia puede tardar un tiempo en completarse. No puede cambiar las propiedades en la página **Coincidencia** hasta que se complete el proceso de coincidencia. Encontrará la entidad de perfil de cliente unificada que se creó en la página **Entidades**. Su entidad de cliente unificada se llama **ConflationMatchPairs : CustomerInsights**.

Para realizar cambios adicionales y volver a ejecutar el paso, puede cancelar una asignación en curso. Seleccione el texto **Actualizando...** y seleccione **Cancelar trabajo** en la parte inferior del panel lateral que aparece.

Cuando se completa el proceso de coincidencia, el texto **Actualizando ...** cambiará a **Correcto** y podrá usar toda la funcionalidad de la página nuevamente.

El primer proceso de coincidencia da como resultado la creación de una entidad maestra unificada. Todas las ejecuciones de coincidencia posteriores producen la expansión de esa entidad.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="deduplication-output-as-an-entity"></a>Resultado de la desduplicación como entidad
Además de la entidad maestra unificada creada como parte de la correspondencia entre entidades, el proceso de desduplicación también genera una nueva entidad para cada entidad a partir del orden de coincidencia para identificar los registros desduplicados. Estas entidades se pueden encontrar junto con **ConflationMatchPairs: CustomerInsights** en la sección **Sistema** en la página **Entidades**, con el nombre **Deduplication_Datasource_Entity**.

Una entidad de resultado de la desduplicación contiene la siguiente información:
- Identificadores y claves
  - Campo de clave principal y su campo de identificadores alternativos. El campo de identificadores alternativos consta de todos los identificadores alternativos identificados para un registro.
  - El campo Deduplication_GroupId muestra el grupo o clúster identificado dentro de una entidad que agrupa todos los registros similares según los campos de desduplicación especificados. Esto se utiliza para fines de procesamiento del sistema. Si no hay reglas de desduplicación manual especificadas y se aplican reglas de desduplicación definidas por el sistema, es posible que no encuentre este campo en la entidad de resultados de la desduplicación.
  - Deduplication_WinnerId: este campo contiene el identificador del elemento elegido en los grupos o clústeres identificados. Si Deduplication_WinnerId es el mismo que el valor de la clave principal para un registro, significa que el registro es el elegido.
- Campos utilizados para definir las reglas de desduplicación.
- Los campos Regla y Puntuación indican cuál de las reglas de desduplicación se aplicó y la puntuación devuelta por el algoritmo de coincidencia.

## <a name="review-and-validate-your-matches"></a>Revisar y validar las coincidencias

Evalúe la calidad de los pares de coincidencia y ajústela:

- En la página **Coincidencia** encontrará dos ventanas que muestran información inicial sobre sus datos.

  - **Clientes únicos**: muestra el número de perfiles únicos que identificó el sistema.
  - **Registros coincidentes**: muestra el número de coincidencias en todos sus pares de coincidencia.

- En la tabla **Orden de coincidencia** puede evaluar los resultados de cada par de coincidencias comparando el número de registros que provienen de esta entidad de par de coincidencia con el porcentaje de registros que coinciden correctamente.

- En la sección **Reglas** de una entidad en la tabla **Orden de coincidencia** encontrará el porcentaje de registros que coinciden correctamente a nivel de regla. Al seleccionar el símbolo de tabla junto a una regla, puede ver todos estos registros en el nivel de regla. Recomendamos que revise un subconjunto de los registros para validar que coinciden correctamente.

- Experimente con diferentes umbrales de precisión en torno a sus condiciones para identificar el valor óptimo.

  1. Seleccione los puntos suspensivos (...) para la regla de par de coincidencia con la que desea experimentar y seleccione **Editar**.

  2. Seleccione la condición con la que desea experimentar. Cada criterio está representado por una fila en el panel **Regla de coincidencia**.

  3. Lo que verá en la página **Vista previa de criterios** depende del nivel de precisión que haya seleccionado para una condición. Encuentre el número de registros coincidentes y no coincidentes para la condición seleccionada.

     Obtenga una rica comprensión de los efectos de los diferentes niveles de umbral. Puede comparar cuántos registros se compararán en cada uno de los niveles de umbral y ver los registros en cada opción. Seleccione cada una de las ventanas y revise los datos en la sección de tabla.

## <a name="optimize-your-matches"></a>Optimice las coincidencias

Aumente la calidad reconfigurando algunos de sus parámetros de coincidencia:

- **Cambie el orden de coincidencia** seleccionando **Editar** y cambie los campos de orden de coincidencia.

  > [!div class="mx-imgBorder"]
  > ![Editar orden de coincidencia de datos](media/configure-data-match-order-edit.png "Editar orden de coincidencia de datos")

- **Cambia el orden de las reglas** si definió múltiples reglas. Puede reordenar las reglas de coincidencia seleccionando las opciones **Subir** y **Bajar** en la cuadrícula de reglas de coincidencia.

  > [!div class="mx-imgBorder"]
  > ![Cambiar orden de reglas](media/configure-data-change-rule-order.png "Cambiar orden de reglas")

- **Duplique las reglas** si ha definido una regla de coincidencia y desea crear una regla similar con modificaciones. Hágalo seleccionando **Duplicar**.

  > [!div class="mx-imgBorder"]
  > ![Duplicar una regla](media/configure-data-duplicate-rule.png "Duplicar una regla")

- **Desactivar una regla** es para conservar una regla de coincidencia y excluirla del proceso de coincidencia.

  > [!div class="mx-imgBorder"]
  > ![Desactivar una regla](media/configure-data-deactivate-rule.png "Desactivar una regla")

- **Edite las reglas** seleccionando el símbolo **Editar**. Puede aplicar los cambios siguientes:

  - Cambiar atributos para una condición: seleccione nuevos atributos en la fila de condición específica.
  - Cambiar el umbral para una condición: ajuste el control deslizante de precisión.
  - Cambiar el método de normalización para una condición: actualice el método de normalización.

## <a name="specify-your-custom-match-records"></a>Especifique los registros de coincidencia personalizados

Puede especificar condiciones que determinados registros siempre o nunca deben coincidir. Estas reglas se pueden cargar de forma masiva en el proceso de coincidencia.

1. Seleccione la opción **Coincidencia personalizada** en la pantalla **Orden de coincidencia**.

   > [!div class="mx-imgBorder"]
   > ![Crear una coincidencia personalizada](media/custom-match-create.png "Crear una coincidencia personalizada")

2. Si no tiene entidades cargadas, verá un nuevo cuadro de diálogo **Coincidencia personalizada** que requiere que complete algunos detalles. Si ha proporcionado estos detalles anteriormente, vaya al paso 8.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo de nueva coincidencia personalizada](media/custom-match-new-dialog-box.png "Cuadro de diálogo de nueva coincidencia personalizada")

3. Seleccione **Rellene la plantilla** para obtener un archivo de plantilla que puede especificar qué registros de qué entidades siempre o nunca deben coincidir. Deberá rellenar por separado los registros de "coincidir siempre" y "coincidir nunca" en dos archivos diferentes.

4. La plantilla contiene campos para especificar los valores de entidad y clave principal de la entidad que se utilizarán en la coincidencia personalizada. Por ejemplo, si desea que la clave principal 12345 de la entidad de ventas coincida siempre con la clave principal 34567 de la entidad de contacto, deberá especificar lo siguiente:
    - Entidad 1: Ventas
    - Entity1Key: 12345
    - Entity2: Contacto
    - Entity2Key: 34567

   El mismo archivo de plantilla puede especificar registros de coincidencia personalizados de múltiples entidades.
   
   Si desea especificar una coincidencia personalizada para la desduplicación en una entidad, proporcione la misma entidad como Entity1 y Entity2 y configure los diferentes valores de clave principal.

5. Después de agregar todas las anulaciones que desea aplicar, guarde el archivo de plantilla.

6. Vaya a **Datos** > **Orígenes de datos** e ingiera los archivos de plantilla como nuevas entidades. Una vez procesados, puede usarlos para especificar la configuración de coincidencia.

7. Después de cargar los archivos y de que las entidades estén disponibles, seleccione la opción **Coincidencia personalizada** de nuevo. Verá opciones para especificar las entidades que desea incluir. Seleccione las entidades requeridas en el menú desplegable.

   > [!div class="mx-imgBorder"]
   > ![Invalidaciones de coincidencias personalizadas](media/custom-match-overrides.png "Invalidaciones de coincidencias personalizadas")

8. Seleccione las entidades que desea usar para **Coincidir siempre** y **No coincidir nunca**, seleccione **Listo**.

9. Seleccione **Guardar** en la página **Coincidencia** para la configuración de coincidencia personalizada que acaba de configurar.

10. Seleccione **Ejecutar** en la página **Coincidencia** para iniciar el proceso de coincidencia, y se aplicará la configuración de coincidencia personalizada. El conjunto de configuración anula las reglas coincidentes del sistema.

11. Una vez que se completa la coincidencia, puede verificar la entidad **ConflationMatchPair** para confirmar que las anulaciones se aplican en las coincidencias de combinación.

## <a name="next-step"></a>Paso siguiente

Después de completar el proceso de coincidencia para al menos un par de coincidencias, puede resolver posibles contradicciones en sus datos en el tema [**Combinación**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]