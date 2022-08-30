---
title: Crear un perfil de contacto unificado (vista previa)
description: Realice el proceso de unificación de datos para crear un único conjunto maestro de datos de contactos.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305046"
---
# <a name="create-a-unified-contact-profile-preview"></a>Crear un perfil de contacto unificado (vista previa)

Después de [unificar cuentas comerciales](map-entities.md), opcionalmente puede unificar contactos para esas cuentas y vincular los contactos unificados a las cuentas unificadas. El proceso de unificación de contactos asigna datos de contacto de múltiples fuentes de datos, elimina duplicados, compara los datos entre entidades, configura el mapeo semántico, crea Relaciones entre contactos y cuentas, y luego crea un perfil de contacto unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Los primeros pasos son idénticos a los pasos de unificación de cuentas.

## <a name="prerequisites"></a>Requisitos previos

Los registros de cuenta y contacto deben tener una clave única (llamada clave externa) que los conecte. Por ejemplo, un ID de cuenta que existe en el registro de cuenta y el registro de contacto que vincula la cuenta y el contacto.

## <a name="preview-limitations"></a>Limitaciones de la versión preliminar

- Los contactos sin un enlace a una cuenta se eliminan.
- Si se elimina la duplicación de una cuenta, se identifica un registro ganador en función de las preferencias de combinación. Los registros perdedores no se seleccionan y, por lo tanto, se eliminan. Los contactos asociados con los registros perdidos se eliminan.
- Una cuenta puede tener múltiples contactos, pero un contacto está vinculado a una sola cuenta.
- Los atributos de contacto mapeados en el paso de mapeo semántico son los únicos atributos que se pueden mostrar en la ficha del Cliente. Sin embargo, hay 17 atributos disponibles.

## <a name="select-source-fields"></a>Seleccionar campos de origen

1. Bajo **Unificar contactos (versión preliminar)**, seleccione **Empezar**.

1. [Seleccionar las entidades y campos](map-entities.md) para sus fuentes de datos de contacto, incluidas las claves principales y los tipos de atributos.

1. Seleccione **Siguiente**.

## <a name="remove-duplicate-records"></a>Quitar registros duplicados

1. Opcionalmente, [defina reglas de desduplicación](remove-duplicates.md) para sus entidades seleccionadas.

1. Seleccione **Siguiente**.

## <a name="match-conditions"></a>Condiciones coincidentes

1. [Defina el orden y las reglas](match-entities.md) para la coincidencia entre entidades.

1. Seleccione **Siguiente**.

## <a name="unify-contact-fields"></a>Unificar campos de contacto

1. [Combinar y excluir campos de contacto](merge-entities.md).

1. Seleccione **Siguiente**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definir los campos semánticos para los contactos unificados

Este paso en el proceso de unificación asigna sus campos de contacto unificados a tipos semánticos. En B-to-B, las tarjetas de clientes muestran cuentas. Cuando se selecciona la tarjeta, se muestran todos los contactos asociados con la cuenta. Los campos que asigne en este paso son los campos que se mostrarán en las tarjetas.

1. Seleccione el tipo semántico que se asigna a cada campo unificado. Seleccione **Ninguno** si un tipo semántico no está disponible.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Captura de pantalla de la página Campos semánticos para definir los tipos semánticos." lightbox="media/semantic_mapping.png":::

1. Después de mapear todos los campos unificados, seleccione **Próximo**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Establecer la relación entre contactos y cuentas

Este paso del proceso de unificación conecta los datos de contacto a sus datos de cuenta correspondiente.

1. Para cada entidad, introduzca la siguiente información:

   - **Clave externa de la entidad de contacto**: elija el atributo de su entidad de origen que conecta su entidad de contacto con la cuenta.
   - **A la entidad de la cuenta**: elija la entidad de cuenta asociada con el contacto.

   :::image type="content" source="media/contact_relationship.png" alt-text="Captura de pantalla de la página Relación para conectar las entidades de contacto y cuenta.":::

1. Seleccione **Siguiente**.

## <a name="review-contact-unification"></a>Revisar la unificación de contactos

Revise el resumen de cambios, cree el perfil unificado y revise los resultados.

### <a name="review-and-create-contact-profiles"></a>Revisar y crear perfiles de cuenta

Este último paso en el proceso de unificación muestra un resumen de los pasos del proceso y brinda la oportunidad de realizar cambios antes de crear el perfil de contacto unificado.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Captura de pantalla de Revisar y crear perfiles de contacto.":::

1. Seleccione **Editar** en cualquiera de los pasos de unificación de contactos para revisar y realizar cambios.

1. Si está satisfecho con sus selecciones, seleccione **Crear perfiles de contactos**. La página **Unificar** se muestra mientras se crea el perfil de contacto unificado.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Captura de pantalla de la página de Unificar contactos con mosaicos que muestran En cola o Actualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

El algoritmo de unificación tarda un tiempo en completarse y no puede cambiar la configuración hasta que se complete.

### <a name="view-the-results-of-contact-unification"></a>Ver los resultados de la unificación de contactos

Después de que la unificación se completa, la página **Datos** > **Unificar** muestra el número de perfiles de contacto unificados. Los resultados de cada paso en el proceso de unificación se muestran en cada mosaico. Por ejemplo, **Campos de origen** muestra el número de atributos mapeados (campos) y **Registros duplicados** muestra el número de registros duplicados encontrados.

:::image type="content" source="media/unified_contacts.png" alt-text="Captura de pantalla de la página Unificar datos después de unificar los contactos.":::

> [!TIP]
> El icono **Condiciones coincidentes** se muestra solo si se seleccionaron varias entidades.

Le recomendamos que revise los resultados, particularmente la calidad de sus [reglas de coincidencia](data-unification-update.md#manage-match-rules) y refinarlas si es necesario.

Cuando sea necesario, [realice cambios en la configuración de unificación de contactos](data-unification-update.md) y vuelva a ejecutar el perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verificar entidades de salida de la unificación de datos

Vaya a **Datos** > **Entidades** para verificar las entidades de salida.

La entidad de perfil de contacto unificado, llamada *ContactProfile*, se muestra en la sección **Entidades semánticas**. La primera ejecución de unificación exitosa crea la entidad *ContactProfile* unificada. Todas las ejecuciones posteriores expanden esa entidad.

La entidad *ContactsCustomer* (vista previa) se crea y se muestra en la sección **Perfiles**. Esta entidad contiene los datos de contacto sin los enlaces a las cuentas. Esta entidad se utiliza como entrada en el mapeo semántico y los pasos de relación de la unificación de contactos.

Las entidades de deduplicación y combinación se crean y se muestran en la sección **Sistema**. Se crea una entidad de desduplicación para cada una de las entidades de origen con el nombre **Deduplication_DataSource_Entity**. La entidad **ContactsConflationMatchPairs** contiene información sobre coincidencias entre entidades.

Una entidad de resultado de la desduplicación contiene la siguiente información:
- Identificadores y claves
  - Campos de clave principal e ID alternativa. El campo ID alternativo consta de todos los ID alternativos identificados para un registro.
  - El campo Deduplication_GroupId muestra el grupo o clúster identificado dentro de una entidad que agrupa todos los registros similares según los campos de desduplicación especificados. Se utiliza para fines de procesamiento del sistema. Si no hay reglas de desduplicación manual especificadas y se aplican reglas de desduplicación definidas por el sistema, es posible que no encuentre este campo en la entidad de resultados de la desduplicación.
  - Deduplication_WinnerId: este campo contiene el identificador del elemento elegido en los grupos o clústeres identificados. Si Deduplication_WinnerId es el mismo que el valor de la clave principal para un registro, significa que el registro es el elegido.
- Campos utilizados para definir las reglas de desduplicación.
- Los campos Regla y Puntuación indican cuál de las reglas de desduplicación se aplicó y la puntuación devuelta por el algoritmo de coincidencia.

## <a name="next-step"></a>Paso siguiente

Configure las [actividades](activities.md), el [enriquecimiento](enrichment-hub.md) o las [relaciones](relationships.md) para obtener más información sobre sus contactos.
