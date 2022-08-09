---
title: Asignaciones semánticas (versión preliminar)
description: Descripción general de las asignaciones semánticas y cómo usarlas.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183652"
---
# <a name="semantic-mappings-preview"></a>Asignaciones semánticas (versión preliminar)

Las asignaciones semánticas le permiten asignar sus datos de no actividad a esquemas predefinidos. Estos esquemas ayudan a Customer Insights a comprender mejor los atributos de sus datos. La asiganción semántica y los datos proporcionados permiten nuevos conocimientos y funciones en Customer Insights. Para asignar los datos de su actividad a los esquemas, revise la documentación de [actividades](activities.md).

**Las asignaciones semánticas están actualmente habilitadas para entornos basados en cuentas comerciales**. *ContactProfile* es el único tipo de asignación semántica disponible actualmente en Customer Insights.

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Utilice una asignación de entidad semántica de ContactProfile para crear actividades a nivel de contacto

Después de crear un mapeo de entidades semánticas *ContactProfile*, puede capturar actividades de contactos. Le permite ver en el cronograma de actividad de una cuenta qué contacto fue responsable de cada actividad. La mayoría de los pasos siguen la configuración típica de mapeo de actividades.

   > [!NOTE]
   > Para que las actividades a nivel de contacto funcionen, debe tener los atributos **AccountID** y **ContactID** para cada registro dentro de los datos de su actividad.

1. [Defina una asignación de entidades semánticas *ContactProfile*](#define-a-contactprofile-semantic-entity-mapping) y ejecute la asignación semántica.

1. Vaya a **Datos** > **Actividades**.

1. Seleccione **Agregar actividad** para crear una nueva actividad.

1. Nombre la actividad, seleccione la entidad de actividad de origen y seleccione la clave principal de la entidad de actividad.

1. En el paso **Relaciones**, cree una relación indirecta entre los datos de la fuente de su actividad y las cuentas, utilizando sus datos de contacto como una entidad intermediaria. Para obtener más información, vea [rutas de relaciones directas e indirectas](relationships.md#relationship-paths).
   - Relación de ejemplo para una actividad llamada *Compras*:
      - **Datos de actividad de origen de compras** > **Datos de contacto** en el atributo **ContactID**
      - **Datos de contacto** > **Datos de cuenta** en el atributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Ejemplo de configuración de relaciones.":::

1. Después de configurar Relaciones, seleccione **Siguiente** y complete la configuración de su mapeo de actividades. Para conocer los pasos detallados sobre la creación de actividades, consulte [definir una actividad](activities.md).

1. Ejecute sus asignaciones de actividad.

1. Después de ejecutar unaasignación en el nivel de contacto, seleccione **Clientes**. Las actividades en el nivel de contacto se muestran en la escala de tiempo de su cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final después de configurar las actividades de contacto":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrado de línea de tiempo de actividad a nivel de contacto

La escala de tiempo de actividad para sus clientes incluye sus id. o nombres, según su configuración de *ContactProfile*, para las actividades en las que actuaron. Filtre actividades por contactos en la escala de tiempo para ver contactos específicos que le interesan. Para ver todas las actividades que no están asignadas a un contacto específico, seleccione **Actividades no asignadas a un contacto**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opciones de filtrado disponibles para actividades a nivel de contacto.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
