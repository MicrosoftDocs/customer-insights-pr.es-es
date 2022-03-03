---
title: Gestionar entornos y áreas de trabajo
description: Cómo crear, renombrar y eliminar áreas de trabajo y entornos.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350658"
---
# <a name="manage-environments-and-workspaces"></a>Administrar entornos y áreas de trabajo

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Introducción

Este tema analiza cómo administrar áreas de trabajo y entornos una vez que ya se han creado. 

- Un *área de trabajo* es un espacio para almacenar y administrar eventos e informes. Es donde puede ver la actividad del usuario en tiempo real. Cuando crea un área de trabajo, usted selecciona el tipo de datos que se envían al área de trabajo. Actualmente, se admiten datos web y aplicaciones móviles. Para más información, vea [Crear un nuevo área de trabajo y agregar miembros](create-workspace.md).

- Un *entorno* es un espacio donde gestiona sus áreas de trabajo y conexiones. Para obtener más información, consulte [Crear un nuevo entorno](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Administración de un área de trabajo existente

Puede mantener varias áreas de trabajo simultáneamente en un entorno. Su [rol](user-roles.md) determina cómo puede trabajar en ellos. 

 - Debe ser un administrador de entorno o un administrador de área de trabajo para administrar el área de trabajo.
 - Como administrador de área de trabajo, puede cambiar el nombre de las áreas de trabajo existentes o eliminarlas. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centtro de administración de áreas de trabajo":::

### <a name="edit-a-workspace-name"></a>Editar un nombre del área de trabajo

1. Vaya a **Administración** > **Área de trabajo** y seleccione **Configuración**.

1. Introduzca un nuevo nombre en el cuadro **Nombre del área de trabajo**.

1. Seleccione **Guardar** para aplicar los cambios.

### <a name="delete-a-workspace"></a>Eliminar un área de trabajo

La eliminación de un área de trabajo elimina permanentemente todo su contenido, datos, configuración y permisos. Esta acción no se puede deshacer.

1. Vaya a **Administración** > **Área de trabajo** y seleccione **Configuración**.

1. Seleccione **Eliminar área de trabajo**. 

1. En el diálogo **Eliminar área de trabajo**, escriba **CONFIRMAR ELIMINACIÓN** en mayúsculas. 

1. Seleccione **Eliminar** para eliminar de forma permanente el área de trabajo.

### <a name="manage-workspace-members"></a>Gestionar miembros del área de trabajo

1. Vaya a **Administración** > **Área de trabajo** y seleccione **Miembros**.

1. Seleccione **Añadir miembros** para dar acceso y [asignar roles](user-roles.md). Actualmente, solo está disponible **Administrador del área de trabajo**.

1. Seleccione **Añadir miembros** para agregarlos a su área de trabajo.

## <a name="manage-an-existing-environment"></a>Administrar un entorno existente

Como administrador del entorno, puede acceder a un entorno desde el panel de navegación izquierdo. Puede configurar los ajustes del entorno, otros administradores del entorno y espacios de trabajo. Seleccione las pestañas para moverse entre diferentes áreas en el centro de administración.

:::image type="content" source="media/environment-edit.png" alt-text="Centro de administración del entorno.":::

### <a name="edit-an-environment-name"></a>Editar un nombre de entorno

1. Vaya a **Administración** > **Entorno** y seleccione **Configuración**.

1. Actualice el **Nombre del entorno** y seleccione **Guardar** para aplicar los cambios.

### <a name="delete-an-environment"></a>Eliminar un entorno

Los administradores de entornos pueden eliminar entornos. Para poder eliminar un entorno, debe eliminar todas las áreas de trabajo que contiene.

1. Vaya a **Administración** > **Entorno** y seleccione **Configuración**.

1. Seleccione **Eliminar entorno**. 

1. En el diálogo **Eliminar área de trabajo**, escriba **CONFIRMAR ELIMINACIÓN** en mayúsculas. 

1. Seleccione **Eliminar** para eliminar el entorno de forma irreversible.

### <a name="manage-environment-members"></a>Gestionar miembros del entorno

1. Vaya a **Administración** > **Entorno** y seleccione **Miembros**.

1. Seleccione **Añadir miembros** para actualizar miembros y [asignar roles](user-roles.md). Actualmente, solo está disponible **Administrador del entorno**.

1. Seleccione **Añadir miembros** para agregarlos a su entorno.

## <a name="manage-connections"></a>Administrar conexiones

Establecer conexiones con conclusiones del público le permite ver informes en conclusiones sobre la interacción basados en perfiles de clientes unificados. 

Para más información, consulte [Crear un vínculo entre las conclusiones del público y las conclusiones sobre la interacción](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gestionar datos personales

Para proteger los datos personales de su cliente, puede eliminar o exportar datos identificables del usuario final.

Para obtener más información, consulte [Eliminar y exportar datos de eventos que contienen información personal](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
