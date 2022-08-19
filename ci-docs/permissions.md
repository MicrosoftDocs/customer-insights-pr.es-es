---
title: Asignar permisos de usuario
description: Más información sobre permisos y roles de usuario.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245440"
---
# <a name="assign-user-permissions"></a>Asignar permisos de usuario

El acceso a Customer Insights está restringido a los usuarios de su organización que un administrador agregó a la aplicación. Un administrador puede agregar, editar o eliminar usuarios. Un usuario puede ser un solo usuario, grupo o aplicación. Hay tres tipos de roles que un usuario puede tener:

## <a name="viewer"></a>Espectador

- Explore la información y los segmentos en las páginas **Inicio** y **Segmentos**.
- Busque y filtre perfiles de clientes mediante la página **Clientes**. Los campos deben ser de búsqueda.
- Ver y explorar página **Enriquecimiento**.
- Explore y exporte entidades mediante la página **Entidades**.
- Vea el estado de los procesos del sistema mediante la página **Sistema**.
- Vea las exportaciones en la página **Exportaciones**.
- Instale y use el panel **Power BI Customer Insights**.

## <a name="contributor"></a>Colaborador

- Todos los permisos disponibles para el visor.
- Cargue y transforme datos mediante la página **Orígenes de datos**.
- Complete la **Unificación de datos** que da como resultado la entidad de perfil de cliente unificado.
- Defina **Relaciones** y **Actividades**.
- Cree segmentos mediante la página **Segmentos**.
- Cree medidas mediante la página **Medidas**.
- Administre la configuración y enriquezca los perfiles de clientes desde la página **Enriquecimiento** (solo para enriquecimientos de primera parte).
- Administre y cree exportaciones basadas en [conexiones compartidas con colaboradores.](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Todos los permisos disponibles para el colaborador.
- Cambie la configuración de la página **Sistema**, incluido el idioma de trabajo, las actualizaciones de las programaciones de los procesos del sistema y la exportación de registros de diagnóstico.
- Cambie la configuración en la página **Seguridad**, incluidos los usuarios, las claves de API, los enlaces privados y el almacén de claves.
- Establezca definiciones de buscar y filtrar para la página Clientes mediante la página **Índice de búsqueda y filtros** (accesible a través de la página **Clientes**).
- Administre las conexiones y permítalas para otros roles de usuario en la página **Conexiones**.
- Administre la configuración y enriquezca los perfiles de clientes desde la página **Enriquecimiento** (para todos los enriquecimientos).
- Gestione y cree exportaciones en la página **Exportaciones**.
- Instale y utilice el **Complemento de tarjeta de cliente**.
- Agregue y use el conector de **Power Apps**.
- Habilitar el uso de las [API de Customer Insights](apis.md).
- [Asignar propiedad del entorno](manage-environments.md#change-the-owner-of-an-environment) a otro administrador.

## <a name="admin-owner"></a>Administrador (propietario)

- Todos los permisos disponibles para el administrador.
- [Restablecer y eliminar](manage-environments.md#reset-an-existing-environment-preview) el entorno.

## <a name="add-users"></a>Agregar usuarios

1. Vaya a **Administración** > **Seguridad** y seleccione la pestaña **Usuarios**.

1. Seleccione **Agregar usuarios** para abrir el panel **Agregar/editar permisos**.

1. Utilice el campo **Buscar** para encontrar el usuario o grupo de Azure Active Directory que quiere agregar. Seleccione un **Rol** para asignar a ese usuario o grupo.

1. Seleccione **Guardar**. El entorno actual se comparte automáticamente con el usuario o los miembros del grupo. Los usuarios pueden acceder a la aplicación Customer Insights y trabajar de acuerdo con su rol específico.

## <a name="view-current-permissions"></a>Ver permisos actuales

Vaya a **Administración** > **Seguridad** y seleccione la pestaña **Usuarios** para ver la lista de usuarios activos y sus asignaciones de roles. Puede ordenar la lista de usuarios por cualquier columna o usar el cuadro de búsqueda para encontrar un usuario en particular.

## <a name="manage-current-users"></a>Administrar usuarios actuales

Vaya a **Administrador** > **Seguridad** y seleccione la pestaña **Usuarios**. Puede ordenar la lista de usuarios por cualquier columna o usar el cuadro de búsqueda para encontrar el usuario que desea administrar.

Seleccione un usuario para ver las acciones disponibles.

- **Editar** para editar el rol del usuario en Customer Insights. Seleccione **Guardar** para confirmar el cambio.
- **Eliminar** para impedir que el usuario tenga acceso a Customer Insights. Seleccione **Eliminar** para confirmar la eliminación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
