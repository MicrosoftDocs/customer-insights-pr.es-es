---
title: Actualizar la configuración de unificación
description: Actualice reglas duplicadas, reglas de coincidencia o campos unificados en la configuración de unificación.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755611"
---
# <a name="update-the-unification-settings"></a>Actualizar la configuración de unificación

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Para revisar o cambiar cualquier configuración de unificación una vez que se haya creado un perfil unificado, realice los siguientes pasos.

1. Vaya a **Datos** > **Unificar**.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la página Unificar datos después de unificar los datos.":::

   > [!TIP]
   > El icono **Condiciones coincidentes** se muestra solo si se seleccionaron varias entidades.

1. Elija lo que desea actualizar:
   - [Campos de origen](#edit-source-fields) para agregar entidades o atributos o cambiar los tipos de atributos.
   - [Registros duplicados](#manage-deduplication-rules) para administrar reglas de deduplicación o fusionar preferencias.
   - [Condiciones coincidentes](#manage-match-rules) para actualizar las reglas de coincidencia entre dos o más entidades.
   - [Campos de clientes unificados](#manage-unified-fields) para combinar o excluir campos. También puede agrupar perfiles relacionados en clústeres.

1. Después de hacer sus cambios, elija su siguiente opción:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Captura de pantalla de la página Unificar datos con las opciones de Unificar resaltadas.":::

   - Para actualizar el perfil de cliente unificado (con o sin dependencias), consulte [Ejecutar actualizaciones en el perfil del cliente](#run-updates-to-the-unified-customer-profile).
   - Para evaluar la calidad de sus condiciones coincidentes sin actualizar el perfil unificado, consulte [Ejecutar condiciones coincidentes](#run-matching-conditions). La opción **Ejecutar solo condiciones coincidentes** no se muestra para una sola entidad.

## <a name="edit-source-fields"></a>Editar campos de origen

No puede eliminar un atributo o una entidad si ya se han unificado.

1. Seleccione **Editar** en el icono **Campos de origen**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de pantalla de la página de campos de origen que muestra el número de claves principales, campos asignados y no asignados":::

   Se muestra el número de campos asignados y no asignados.

1. Seleccione **Seleccionar entidades y campos** para agregar otros atributos o entidades. Utilice la búsqueda o desplácese para buscar y seleccionar sus atributos y entidades de interés. Seleccione **Aplicar**.

1. Opcionalmente, puede cambiar la clave principal de una entidad, los tipos de atributos y alternar entre **Mapeo inteligente** activado o desactivado. Para más información, vea [Seleccionar la clave principal y el tipo semántico para los atributos](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Seleccione **Siguiente** para realizar cambios en las reglas de deduplicación, o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Administrar reglas de desduplicación

1. Seleccione **Editar** en el icono **Registros duplicados**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de pantalla de la página de registros duplicados que muestra el número de registros duplicados" lightbox="media/m3_duplicates_edit.png":::

   El número de registros duplicados encontrados se muestra bajo **Duplicados**. La columna **Registros deduplicados** muestra qué entidades tenían registros duplicados y el porcentaje de registros duplicados.

1. Si agregó una entidad enriquecida, seleccione **Usar entidades enriquecidas**. Para obtener más información, consulte [Enriquecimiento de orígenes de datos](data-sources-enrichment.md).

1. Para administrar las reglas de deduplicación, elija cualquiera de las siguientes opciones:
   - **Crear una nueva regla**: seleccione **Agregar regla** bajo la entidad correspondiente. Para más información, consulte [Definir reglas de deduplicación](remove-duplicates.md#define-deduplication-rules).
   - **Cambiar las condiciones de la regla**: seleccione la regla y luego **Editar**. Cambie campos, agregue o elimine condiciones, o agregue o elimine excepciones.
   - **Avance**: Seleccione la regla y luego **Avance** para ver los resultados de la última ejecución de esta regla.
   - **Desactivar una regla**: seleccione la regla y luego **Desactivar** para retener una regla de deduplicación y excluirla del proceso de coincidencia.
   - **Duplicar una regla**: seleccione la regla y luego **Duplicar** para crear una regla similar con modificaciones.
   - **Eliminar una regla**: seleccione la regla y luego **Borrar**.

1. Para cambiar las preferencias de combinación, seleccione la entidad. Solo puede cambiar las preferencias si se crea una regla.
   1. Seleccione **Editar preferencias de fusión** y cambie la opción **Registro para mantener**.
   1. Para cambiar las preferencias de fusión en atributos individuales de una entidad, seleccione **Avanzado** y hacer los cambios necesarios.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Captura de pantalla de las preferencias de combinación avanzadas que muestran el correo electrónico más reciente y la dirección más completa":::

   1. Seleccione **Listo**.

1. Seleccione **Siguiente** para realizar cambios en las condiciones de coincidencia , o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Administrar reglas de coincidencia

Puede reconfigurar y ajustar la mayoría de los parámetros de coincidencia. No puede agregar o eliminar entidades. Las reglas de coincidencia no se aplican a una sola entidad.

1. Seleccione **Editar** en el icono **Condiciones coincidentes**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de pantalla de la página de reglas y condiciones del partido con estadísticas." lightbox="media/m3_match_edit.png":::

   La página muestra el orden de los partidos y las reglas definidas y las siguientes estadísticas:
   - **Registros de origen únicos** muestra el número de registros de origen individuales que se procesaron en la última ejecución de coincidencia.
   - **Registros coincidentes y no coincidentes** resalta cuántos registros únicos quedan después de procesar las reglas de coincidencia.
   - **Solo registros coincidentes** muestra el número de coincidencias en todos sus pares de coincidencias.

1. Para ver los resultados de todas las reglas y sus puntajes, seleccione **Ver última ejecución**. Se muestran los resultados, incluidos los ID de contacto alternativos. Puedes descargar los resultados.

1. Para ver los resultados y puntajes de una regla en particular, seleccione la regla y luego **Vista previa**. Se muestran los resultados. Puedes descargar los resultados.

1. Para ver los resultados de una condición en particular, seleccione la regla y luego **Editar**. En el panel Editar, seleccione **Vista previa** bajo la condición. Puedes descargar los resultados.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representación gráfica de registros coincidentes y no coincidentes, incluida una lista de los datos.":::

1. Si agregó una entidad enriquecida, seleccione **Usar entidades enriquecidas**. Para obtener más información, consulte [Enriquecimiento de orígenes de datos](data-sources-enrichment.md).

1. Para administrar las reglas, elija cualquiera de las siguientes opciones:
   - **Crear una nueva regla**: seleccione **Agregar regla** bajo la entidad correspondiente. Para más información, vea [Definir reglas para emparejar pares](match-entities.md#define-rules-for-match-pairs).
   - **Cambie el orden de las reglas** si definió varias reglas: arrastre y suelte las reglas en el orden que desee. Para más información, vea [Especificar el orden de coincidencia](match-entities.md#specify-the-match-order).
   - **Cambiar las condiciones de la regla**: seleccione la regla y luego **Editar**. Cambie campos, agregue o elimine condiciones, o agregue o elimine excepciones.
   - **Desactivar una regla**: seleccione la regla y luego **Desactivar** para retener una regla de coincidencia y excluirla del proceso de coincidencia.
   - **Duplicar una regla**: seleccione la regla y luego **Duplicar** para crear una regla similar con modificaciones.
   - **Eliminar una regla**: seleccione la regla y luego **Borrar**.

1. Seleccione **Siguiente** para realizar cambios en los campos unificados, o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Administrar campos unificados

1. Seleccione **Editar** en el icono **Campos de cliente unificados**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de pantalla de los campos de cliente unificados":::

1. Revise los campos combinados y excluidos y realice los cambios necesarios. Agregue o edite la clave de CustomerID o los perfiles de grupo en clústeres. Para obtener más información, consulte [Unificar campos de cliente](merge-entities.md).

1. Seleccione **Siguiente** para revisar la configuración de unificación y [actualizar el perfil unificado y las dependencias](#run-updates-to-the-unified-customer-profile), o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-the-unification-settings) para hacer más cambios.

## <a name="run-matching-conditions"></a>Ejecutar condiciones coincidentes

1. En la página **Datos** > **Unificar**, seleccione **Ejecutar solo condiciones coincidentes**.

   Los iconos **Registros duplicados** y **Condiciones coincidentes** muestran **Puesto en cola** o **En actualización**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Cuando finalice el proceso de coincidencia, seleccione **Editar** en el icono **Condiciones coincidentes**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla recortada de las métricas clave en la página Coincidencia con números y detalles.":::

1. Para realizar cambios, consulte [Administrar reglas de deduplicación](#manage-deduplication-rules) o [Administrar reglas de coincidencia](#manage-match-rules).

1. Vuelva a ejecutar el proceso de emparejamiento o [ejecutar actualizaciones en el perfil del cliente](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Ejecutar actualizaciones en el perfil de cliente unificado

1. En la página **Datos** > **Unificar**, seleccione:

   - **Unificar perfiles de clientes**: actualiza la entidad de perfil de cliente unificado sin afectar las dependencias (como enriquecimientos, segmentos o medidas). Los procesos dependientes no se ejecutan, pero se actualizarán a medida que [se definan en el programa de actualización](system.md#schedule-tab).

   - **Unificar los perfiles y las dependencias de los clientes**: actualiza el perfil unificado y todas las dependencias. Todos los procesos se vuelven a ejecutar automáticamente. Una vez que se han completado todos los procesos posteriores, el perfil del cliente refleja los datos actualizados.

   Los iconos **Registros duplicados**, **Condiciones coincidentes** y **Campos de cliente unificados** muestran **Puesto en cola** o **En actualización**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
