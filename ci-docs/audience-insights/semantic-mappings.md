---
title: Asignaciones semánticas (versión preliminar)
description: Descripción general de las asignaciones semánticas y cómo usarlas.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731964"
---
# <a name="semantic-mappings"></a>Asignaciones semánticas

Las asignaciones semánticas le permiten asignar sus datos de no actividad a esquemas predefinidos. Estos esquemas ayudan a conclusiones del público a comprender mejor los atributos de sus datos. La asiganción semántica y los datos proporcionados permiten nuevos conocimientos y funciones en conclusiones del público. Para asignar los datos de su actividad a los esquemas, revise la documentación de [actividades](activities.md).

**Las asignaciones semánticas están actualmente habilitadas para entornos basados en cuentas comerciales**. *ContactProfile* es el único tipo de asignación semántica disponible actualmente en conclusiones del público.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir una asignación de entidad semántica de ContactProfile

1. En conclusiones del público, vaya a **Datos** > **Asignaciones semánticas (versión preliminar)**.

1. Seleccione **Agregar asignación semántica** para iniciar la experiencia guiada.

1. En el paso **Datos de la entidad**, establezca los valores para los siguientes campos:

   - **Nombre de asignación de entidad semántica**: Proporcione un nombre para su asignación de entidad semántica.
   - **Entidad de origen**: seleccione una entidad que incluya datos de contacto.
   - **Clave principal**: seleccione el campo que identifica de manera única un registro de contacto. No debe contener valores duplicados, valores vacíos ni valores que faltan.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configure la asignación de entidad semántica con nombre, entidad de origen y clave principal.":::

1. Seleccione **Siguiente** para continuar.

1. En el paso **Relaciones**, configure los detalles para conectar sus datos de contacto a sus datos de cuenta correspondiente. Este paso visualiza la conexión entre entidades.  

   Hay dos tipos de rutas de relación que se pueden implementar: **Relaciones directas** y **Relaciones indirectas**. Para obtener más información, vaya a [rutas de relaciones directas e indirectas](relationships.md#relationship-paths).

   1. Seleccione **Agregar relación** para configurar la relación.
   1. Elija el atributo de su entidad de origen que conecta su entidad de contacto con otra entidad.
   1. Elija la entidad a la que conectará su entidad de contacto. Puede elegir una entidad de la sección **Entidades de cuenta** o **Entidad intermedia**. Si selecciona una entidad intermedia, debe definir una segunda relación para conectarse a la entidad de su cuenta de destino.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Seleccione una entidad de cuenta o una entidad intermedia.":::

   1. Especifique un **Nombre de relación**. Si ya existe una relación entre sus entidades, el nombre de la relación es de solo lectura. Si no existe ninguna relación, se creará una nueva relación con el nombre que proporcione.
   1. Seleccione **Aplicar** para finalizar la configuración de la relación.

   > [!NOTE]
   > Puede configurar más relaciones entre la entidad de contacto y otras entidades de cuenta con entidades intermedias.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualización de varias relaciones que conectan entidades de contacto con entidades de cuenta.":::

1. Seleccione **Siguiente** cuando haya terminado con la configuración de la relación.

1. En el paso **Establecer el tipo semántico**, elija un **Tipo semántico**. Actualmente, hay un **Tipo semántico** llamado *ContactProfile*.

1. Asigne los datos al **Tipo semántico** *ContactProfile* para los campos mostrados.
   - Campo obligatorio: Id. de contacto
   - Campos opcionales: Nombre de pila, Apellidos, Fecha de nacimiento, Sexo, Correo electrónico principal y Teléfono principal

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Asigne sus atributos de datos de contacto a los campos obligatorios y opcionales proporcionados.":::

1. Seleccione **Siguiente** para continuar.

1. En el paso **Revisar**, eche un vistazo a la configuración de la asignación semántica. Seleccione **Editar** para la sección correspondiente para realizar cambios.

1. Seleccione **Guardar** para guardar su nueva **Asignación semántica**.

1. Después de guardar, puede seleccionar **Ejecutar** proceso de la asignación semántica o puede seleccionar **Cerrar** para guardar su asignación semántica sin procesarla.

1. Para ejecutar una asignación semántica en un punto posterior, seleccione la asignación semántica y seleccione **Actualizar**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Administrar asignaciones semánticas existentes

En **Datos** > **Asignaciones semánticas (versión preliminar)**, puede ver todas sus asignaciones semánticas guardadas y administrarlas. Cada asignación semántica está representada por una fila separada. Encontrará detalles sobre la entidad de origen, el tipo semántico, el tipo de asignación y su estado.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opciones para gestionar asignaciones semánticas.":::

- **Editar**: Abre la configuración de la asignación semántica configurada en el paso de revisión. Puede cambiar la configuración actual. Seleccione **Guardar** y **Ejecutar** para procesar los cambios.

- **Actualizar**: Actualiza la asignación semántica seleccionada con los datos más actualizados de las entidades que forman parte de su configuración. Si actualiza cualquier asignación semántica dada se actualizarán todas las asignaciones semánticas del mismo tipo.

- **Cambiar nombre**: Abre un cuadro de diálogo en el que puede introducir un nombre diferente para la asignación semántica seleccionada. Seleccione **Guardar** para aplicar los cambios.

- **Eliminar**: Abre un cuadro de diálogo para confirmar la eliminación de la asignación semántica seleccionada. También puede eliminar más de una asignación semántica a la vez seleccionando las asignaciones semánticas y el icono de eliminación. Seleccione **Eliminar** para confirmar la eliminación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]