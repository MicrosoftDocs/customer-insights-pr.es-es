---
title: Asignaciones semánticas (versión preliminar)
description: Descripción general de las asignaciones semánticas y cómo usarlas.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303898"
---
# <a name="semantic-mappings-preview"></a>Asignaciones semánticas (versión preliminar)

> [!NOTE]
> La página **Mapeos semánticos** está disponible solo para entornos comerciales (B-to-B) donde los perfiles de contacto ya se han creado utilizando esta página. Puede continuar creando y administrando los perfiles de contacto individuales usando la página **Mapeos semánticos**. O bien, [unifique sus datos de contacto](data-unification-contacts.md) para eliminar duplicados, identificar coincidencias entre entidades y crear un perfil de contacto unificado. Luego puede usar el perfil de contacto unificado para crear actividades a nivel de contacto.

Las asignaciones semánticas le permiten asignar sus datos de no actividad a esquemas predefinidos. Estos esquemas ayudan a Customer Insights a comprender mejor los atributos de sus datos. La asiganción semántica y los datos proporcionados permiten nuevos conocimientos y funciones en Customer Insights. Para asignar los datos de su actividad a los esquemas, revise la documentación de [actividades](activities.md).

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir una asignación de entidad semántica de ContactProfile

1. Vaya a **Datos** > **Asignaciones semánticas (versión preliminar)**.

1. Seleccione **Agregar asignación semántica** para iniciar la experiencia guiada.

1. En el paso **Datos de la entidad**, establezca los valores para los siguientes campos:

   - **Nombre de asignación de entidad semántica**: nombre para su asignación de entidad semántica.
   - **Entidad de origen**: entidad que incluye datos de contacto.
   - **Clave principal**: campo que identifica de manera única un registro de contacto. No debe contener valores duplicados, valores vacíos ni valores que faltan.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configure la asignación de entidad semántica con nombre, entidad de origen y clave principal.":::

1. Seleccione **Siguiente**.

1. En el paso **Relaciones**, configure los detalles para conectar sus datos de contacto a sus datos de cuenta correspondiente. Este paso visualiza la conexión entre entidades.  

   Hay dos tipos de rutas de relación que se pueden implementar: **Relaciones directas** y **Relaciones indirectas**. Para obtener más información, vaya a [rutas de relaciones directas e indirectas](relationships.md#relationship-paths).

   1. Seleccione **Agregar relación** para configurar la relación.
   1. Elija el atributo de su entidad de origen que conecta su entidad de contacto con otra entidad.
   1. Elija la entidad a la que conectará su entidad de contacto. Elija una entidad de la sección **Entidades de cuenta** o **Entidad intermedia**. Si selecciona una entidad intermedia, defina una segunda relación para conectarse a la entidad de su cuenta de destino.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Seleccione una entidad de cuenta o una entidad intermedia.":::

   1. Especifique un **Nombre de relación**. Si ya existe una relación entre sus entidades, el nombre de la relación es de solo lectura. Si no existe ninguna relación, se creará una nueva relación con el nombre que proporcione.
   1. Seleccione **Aplicar** para finalizar la configuración de la relación.

   > [!NOTE]
   > Puede configurar más relaciones entre la entidad de contacto y otras entidades de cuenta con entidades intermedias.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualización de varias relaciones que conectan entidades de contacto con entidades de cuenta.":::

1. Seleccione **Siguiente**.

1. En el paso **Establecer el tipo semántico**, elija un **Tipo semántico**. Actualmente, hay un **Tipo semántico** llamado *ContactProfile*.

1. Asigne su id. de contacto al **Id. de contacto** de tipo semántico *ContactProfile*. Opcionalmente, asigne otros campos como Nombre de pila, Apellido, Género o Correo electrónico.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Asigne sus atributos de datos de contacto a los campos obligatorios y opcionales proporcionados.":::

1. Seleccione **Siguiente**.

1. En el paso **Revisar**, revise la configuración de la asignación semántica. Para hacer cambios, seleccione **Editar** para la sección correspondiente.

1. Seleccione **Guardar**.

1. Para procesar la asignación semántica, seleccione **Ejecutar**. O seleccione **Cerrar** para guardar su asignación semántica sin procesarla. Para ejecutar la más tarde, seleccione la asignación semántica y seleccione **Actualizar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Administrar asignaciones semánticas existentes

Vaya a **Datos** > **Asignaciones semánticas (versión preliminar)** para ver sus asignaciones semánticas guardadas, su entidad de origen, su tipo semántico, su tipo de asignación y su estado.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opciones para gestionar asignaciones semánticas.":::

Seleccione la asignación semántica para ver las acciones disponibles.
- **Edite** la configuración actual. Seleccione **Guardar** y **Ejecutar** para procesar los cambios.
- **Actualice** la asignación semántica para incluir los últimos datos. Si actualiza cualquier asignación semántica dada se actualizarán todas las asignaciones semánticas del mismo tipo.
- **Cambie el nombre** de la asignación semántica. Seleccione **Guardar**.
- **Elimine** la asignación semántica. Para eliminar más de una asignación semántica a la vez, seleccione las asignaciones semánticas y el icono de eliminación. Seleccione **Eliminar** para confirmar la eliminación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
