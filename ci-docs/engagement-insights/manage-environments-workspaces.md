---
title: Gestionar entornos y áreas de trabajo
description: Cómo crear, renombrar y eliminar áreas de trabajo y entornos.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486056"
---
# <a name="manage-environments-and-workspaces"></a>Administrar entornos y áreas de trabajo

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Introducción

Un área de trabajo es un espacio para almacenar y administrar eventos e informes. Es donde puede ver la actividad del usuario en tiempo real. Cuando crea un área de trabajo, usted selecciona el tipo de datos que se envían al área de trabajo. Actualmente, se admiten datos web y aplicaciones móviles.

Un entorno es un espacio donde gestiona sus áreas de trabajo y conexiones. La forma en que usa los entornos depende de su organización y su caso de uso. Por ejemplo, puede crear:

-   Un solo entorno.
-   Entornos separados de prueba y de producción.
-   Entornos separados para equipos o departamentos específicos de su organización que contienen eventos relevantes para cada público.
-   Entornos separados para diferentes ramas del mundo de su empresa.
-   Conexiones a las funcionalidades de las conclusiones del público de Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Elija un entorno y cree un área de trabajo 

Cada área de trabajo debe estar en un entorno. Puede seleccionar un entorno preexistente o crear uno nuevo cuando cree un área de trabajo. Luego, puede optar por agregar miembros al área de trabajo y comenzar a recopilar datos.

**Para crear su primera área de trabajo**

1. En conclusiones sobre la interacción, seleccione **Nuevo** desde el selector de área de trabajo. 

   :::image type="content" source="media/New-workspace.png" alt-text="Selector de área de trabajo de la página Customer Insights.":::

1. Elija un entorno de la lista o seleccione **Crear un nuevo entorno**.

1. Introduzca un nombre en **Nombre del área de trabajo**. 

1. Seleccione el tipo de entorno que desea crear, dependiendo de si desea medir lo que sucede en un sitio web o en una aplicación móvil. 

1. Puede agregar miembros y asignar su nivel de permiso desde la lista **Rol**. Luego seleccione **Terminar** para crear el área de trabajo o **Siguiente** para instalar código. 

1. Instale el fragmento de código para comenzar a recibir datos y luego seleccione **Listo**. 

## <a name="manage-a-workspace"></a>Gestionar un área de trabajo

Puede mantener varias áreas de trabajo simultáneamente en un entorno. Su [rol](user-roles.md) determina cómo puede trabajar en ellos. 

 - Debe ser un administrador de entorno o un administrador de área de trabajo para administrar el área de trabajo.
 - Como administrador de área de trabajo, puede cambiar el nombre de las áreas de trabajo existentes o eliminarlas. 

### <a name="edit-a-workspace-name"></a>Editar un nombre del área de trabajo

1. Vaya a **Administración** > **Área de trabajo** y seleccione **Configuración**.

1. Introduzca un nuevo nombre en el cuadro **Nombre del área de trabajo**.

1. Seleccione **Guardar** para aplicar los cambios.

### <a name="delete-a-workspace"></a>Eliminar un área de trabajo

La eliminación de un área de trabajo eliminará permanentemente todo su contenido, datos, configuración y permisos. Esta acción no se puede deshacer.

1. Vaya a **Administración** > **Área de trabajo** y seleccione **Configuración**.

1. Seleccione **Eliminar área de trabajo**. 

1. En el cuadro de diálogo **Eliminar área de trabajo**, introduzca **CONFIRMAR ELIMINACIÓN**. 

1. Seleccione **Eliminar** para eliminar de forma permanente el área de trabajo.

### <a name="manage-workspace-members"></a>Gestionar miembros del área de trabajo

1. Vaya a **Administración** > **Área de trabajo** y seleccione **Miembros**.

1. Seleccione **Añadir miembros** para dar acceso y [asignar roles](user-roles.md). Actualmente, solo está disponible **Administrador del área de trabajo**.

1. Seleccione **Añadir miembros** para agregarlos a su área de trabajo.

## <a name="manage-an-environment"></a>Administrar un entorno

Como administrador del entorno, puede acceder a un entorno desde el panel de navegación izquierdo. Puede configurar los ajustes del entorno, otros administradores del entorno y espacios de trabajo. Seleccione las pestañas para moverse entre diferentes áreas en el centro de administración.

:::image type="content" source="media/New-environment.png" alt-text="Centro de administración del entorno.":::

### <a name="create-an-environment"></a>Crear un entorno

1. En el selector de área de trabajo, seleccione **+Nuevo**.

1. En la experiencia guiada, abra el menú desplegable **Entorno** y seleccione **Crear nuevo entorno**. 

1. Especifique un **Nombre del entorno**.

   :::image type="content" source="media/create-environment.png" alt-text="Entre en la experiencia guiada para especificar los detalles del entorno.":::

1. Elija la **Región** y seleccione **Siguiente**. 

1. Proporcione un nombre de área de trabajo y elija el tipo de área de trabajo que desea crear. 

1.  Opcionalmente, agregue miembros y copie el fragmento de código para completar el proceso de creación.

### <a name="rename-an-environment"></a>Cambiar nombre a un entorno

1. Vaya a **Administración** > **Entorno** y seleccione **Configuración**.

1. Actualice el **Nombre del entorno** y seleccione **Guardar** para aplicar los cambios.

### <a name="manage-environment-members"></a>Gestionar miembros del entorno

1. Vaya a **Administración** > **Entorno** y seleccione **Miembros**.

1. Seleccione **Añadir miembros** para actualizar miembros y [asignar roles](user-roles.md). Actualmente, solo está disponible **Administrador del entorno**.

1. Seleccione **Añadir miembros** para agregarlos a su entorno.

### <a name="delete-an-environment"></a>Eliminar un entorno

Los administradores de entornos pueden eliminar entornos. Para poder eliminar un entorno, debe eliminar todas las áreas de trabajo que contiene.

1. Vaya a **Administración** > **Entorno** y seleccione **Configuración**.

1. Seleccione **Eliminar entorno**. 

1. En el cuadro de diálogo **Eliminar área de trabajo**, introduzca **CONFIRMAR ELIMINACIÓN**. 

1. Seleccione **Eliminar** para eliminar el entorno de forma irreversible.

## <a name="manage-connections"></a>Administrar conexiones

Establecer conexiones con conclusiones del público le permite ver informes en conclusiones sobre la interacción basados en perfiles de clientes unificados. 

Para más información, consulte [Crear un vínculo entre las conclusiones del público y las conclusiones sobre la interacción](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gestionar datos personales

Para proteger los datos personales de su cliente, puede eliminar o exportar datos identificables del usuario final.

Para obtener más información, consulte [Eliminar y exportar datos de eventos que contienen información personal](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
