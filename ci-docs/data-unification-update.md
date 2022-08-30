---
title: Actualizar la configuración de unificación de clientes, cuentas o contactos
description: Actualice reglas duplicadas, reglas de coincidencia o campos unificados en la configuración de unificación de clientes o cuentas.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304356"
---
# <a name="update-unification-settings"></a>Actualizar la configuración de unificación

Para revisar o cambiar cualquier configuración de unificación una vez que se haya creado un perfil unificado, realice los siguientes pasos.

1. Vaya a **Datos** > **Unificar**.

   Para clientes individuales (B a C), la página **Unificar** muestra la cantidad de mosaicos y perfiles de clientes unificados para cada uno de los pasos de unificación.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla de la página Unificar datos después de unificar los datos." lightbox="media/m3_unified.png":::

   Para las cuentas empresariales (B a B), la página **Unificar** muestra la cantidad de mosaicos y perfiles de cuentas unificados para cada uno de los pasos de unificación de cuenta. Si se unificaron los contactos, se muestra la cantidad de mosaicos y perfiles de contactos unificados para cada uno de los pasos de unificación de contactos. Elija el mosaico apropiado debajo de **Unificar cuentas** o **Unificar contactos (versión preliminar)**, dependiendo de lo que quiera actualizar.

   :::image type="content" source="media/b2b_unified.png" alt-text="Captura de pantalla de la página Unificar datos después de unificar los datos de cuentas y contactos." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > El icono **Condiciones coincidentes** se muestra solo si se seleccionaron varias entidades.

1. Elija lo que desea actualizar:
   - [Campos de origen](#edit-source-fields) para agregar entidades o atributos o cambiar los tipos de atributos.
   - [Registros duplicados](#manage-deduplication-rules) para administrar reglas de deduplicación o fusionar preferencias.
   - [Condiciones coincidentes](#manage-match-rules) para actualizar las reglas de coincidencia entre dos o más entidades.
   - [Campos de clientes unificados](#manage-unified-fields) para combinar o excluir campos. También puede agrupar perfiles relacionados en clústeres.
   - [Campos semánticos](#manage-semantic-fields-for-unified-contacts) para administrar tipos semánticos para campos de contacto unificados.
   - [Relaciones](#manage-contact-and-account-relationships) para administrar la relación entre el contacto y la cuenta.

1. Después de hacer sus cambios, elija su siguiente opción:

   - [Ejecute condiciones coincidentes](#run-matching-conditions) para evaluar rápidamente la calidad de sus condiciones coincidentes (deduplicación y reglas de coincidencia) sin actualizar el perfil unificado. La opción **Ejecutar solo condiciones coincidentes** no se muestra para una sola entidad.
   - [Unificar perfiles](#run-updates-to-the-unified-profile) para ejecutar condiciones de coincidencia y actualizar la entidad de perfil unificado sin afectar las dependencias (como enriquecimientos, segmentos o medidas). Los procesos dependientes no se ejecutan, pero se actualizarán a medida que [se definan en el programa de actualización](schedule-refresh.md).
   - [Unifique perfiles y dependencias](#run-updates-to-the-unified-profile) para ejecutar condiciones de coincidencia, actualice la entidad de perfil unificado y actualice todas las dependencias (como enriquecimientos, segmentos o medidas). Todos los procesos se vuelven a ejecutar automáticamente. En B a B, la unificación se ejecuta tanto en la cuenta como en las entidades de contacto, actualizando los perfiles unificados.

## <a name="edit-source-fields"></a>Editar campos de origen

No puede eliminar un atributo o una entidad si ya se han unificado.

1. Seleccione **Editar** en el icono **Campos de origen**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de pantalla de la página de campos de origen que muestra el número de claves principales, campos asignados y no asignados":::

   Se muestra el número de campos asignados y no asignados.

1. Para añadir otros atributos o entidades, seleccione **Seleccionar entidades y campos**.

1. Opcionalmente, puede cambiar la clave principal de una entidad, los tipos de atributos y alternar entre **Mapeo inteligente** activado o desactivado. Para obtener más información, consulte [Unificar campos de origen](map-entities.md).

1. Seleccione **Siguiente** para realizar cambios en las reglas de deduplicación, o seleccione **Guardar y cerrar**, y vuelva a [Actualizar la configuración de unificación](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Administrar reglas de desduplicación

1. Seleccione **Editar** en el icono **Registros duplicados**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de pantalla de la página de registros duplicados que muestra el número de registros duplicados" lightbox="media/m3_duplicates_edit.png":::

   El número de registros duplicados encontrados se muestra bajo **Duplicados**. La columna **Registros deduplicados** muestra qué entidades tenían registros duplicados y el porcentaje de registros duplicados.

1. Para usar una entidad enriquecida, seleccione **Usar entidades enriquecidas**. Para obtener más información, consulte [Enriquecimiento de orígenes de datos](data-sources-enrichment.md).

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

   1. Seleccione **Listo**.

1. Seleccione **Siguiente** para realizar cambios en las condiciones de coincidencia , o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-unification-settings).

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

1. Seleccione **Siguiente** para realizar cambios en los campos unificados, o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-unification-settings).

## <a name="manage-unified-fields"></a>Administrar campos unificados

1. Seleccione **Editar** en el icono **Campos de cliente unificados**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de pantalla de los campos de cliente unificados":::

1. Revise los campos combinados y excluidos y realice los cambios necesarios. Agregue o edite la clave de CustomerID o los perfiles de grupo en clústeres. Para obtener más información, consulte [Unificar campos de cliente](merge-entities.md).

1. Para clientes o cuentas, seleccione **Siguiente** para revisar y [actualizar el perfil unificado y las dependencias](#run-updates-to-the-unified-profile). O bien, seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-unification-settings).

   Para contactos, seleccione **Siguiente** para gestionar campos semánticos. O bien, seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-unification-settings).

## <a name="manage-semantic-fields-for-unified-contacts"></a>Administrar los campos semánticos para los contactos unificados

1. Seleccione **Editar** en el icono **Campos semánticos**.

1. Para cambiar el tipo semántico de un campo unificado, seleccione un nuevo tipo. Para obtener información, vea [Definir los campos semánticos para los contactos unificados](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Seleccione **Siguiente** para administrar la relación de cuenta y contacto, o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-unification-settings) para realizar más cambios.

## <a name="manage-contact-and-account-relationships"></a>Administrar relaciones de contacto y cuenta

1. Seleccione **Editar** en el icono **Relaciones**.

1. Para cambiar la relación de contacto y cuenta, cambie cualquiera de la siguiente información:

   - **Clave externa de la entidad de contacto**: elija el atributo de su entidad de origen que conecta su entidad de contacto con la cuenta.
   - **A la entidad de la cuenta**: elija la entidad de cuenta asociada con el contacto.

1. Seleccione **Siguiente** para revisar la configuración de unificación y [actualizar el perfil unificado y las dependencias](#run-updates-to-the-unified-profile), o seleccione **Guardar y cerrar** y vuelva a [Actualizar la configuración de unificación](#update-unification-settings) para hacer más cambios.

## <a name="run-matching-conditions"></a>Ejecutar condiciones coincidentes

Ejecutar condiciones coincidentes ejecuta la deduplicación y las reglas coincidentes únicamente y actualiza las entidades *Deduplication_* y *ConflationMatchPair*.

1. En la página **Datos** > **Unificar**, seleccione **Ejecutar solo condiciones coincidentes**.

   Los iconos **Registros duplicados** y **Condiciones coincidentes** muestran el estado **Puesto en cola** o **En actualización**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Cuando finalice el proceso de coincidencia, seleccione **Editar** en el icono **Condiciones coincidentes**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla recortada de las métricas clave en la página Coincidencia con números y detalles.":::

1. Para realizar cambios, consulte [Administrar reglas de deduplicación](#manage-deduplication-rules) o [Administrar reglas de coincidencia](#manage-match-rules).

1. Vuelva a ejecutar el proceso de emparejamiento o [ejecutar actualizaciones en el perfil](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Ejecutar actualizaciones en el perfil unificado

- Para ejecutar condiciones de coincidencia y actualizar la entidad Unified Customer Profile *sin* afectar las dependencias (como tarjetas de cliente, enriquecimientos, segmentos o medidas), seleccione **Unificar perfiles de cliente**. Para cuentas, seleccione **Unificar cuentas** > **Unificar perfiles**. Para contactos, seleccione **Unificar contactos (versión preliminar)** > **Unificar perfiles**. Los procesos dependientes no se ejecutan, pero se actualizarán a medida que [se definan en el programa de actualización](schedule-refresh.md).
- Para ejecutar condiciones de coincidencia y actualiza el perfil unificado para ejecutar todas las dependencias, seleccione **Unificar perfiles de clientes y dependencias**. Todos los procesos se vuelven a ejecutar automáticamente. Para cuentas y contactos, seleccione **Unificar cuentas** > **Unificar perfiles y dependencias**. Las condiciones coincidentes se ejecutan tanto para las cuentas como para los contactos, actualizando ambos perfiles unificados y se ejecutan todas las demás dependencias.

Todos los mosaicos excepto **Campos de origen** muestran **Puesto en cola** o **Actualizando**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Los resultados de una ejecución exitosa se muestran en la página **Unificar** que muestra el número de perfiles unificados.
