---
title: Administrar permisos de usuario
description: Más información sobre permisos y roles de usuario.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760394"
---
# <a name="user-permissions"></a>Permisos de usuario

La página **Permisos** es donde configurará los roles y permisos para usar las informaciones de público.

Debe tener permisos de administrador para ver la página. Para acceder a la página de permisos en las informaciones de público, vaya a **Administración** > **Permisos**.

Hay tres tipos de roles:

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
- Complete las secciones *Unificación de datos* (**Asignar**, **Coincidir** y **Combinar**) que dan como resultado la entidad de perfil de cliente unificado.
- Defina **Relaciones** y **Actividades**.
- Cree segmentos mediante la página **Segmentos**.
- Cree medidas mediante la página **Medidas**.
- Administre la configuración y enriquezca los perfiles de clientes desde la página **Enriquecimiento** (solo para enriquecimientos de primera parte).
- Administre y cree exportaciones basadas en conexiones compartidas con colaboradores. [Obtenga más información sobre cómo los administradores permiten que los colaboradores utilicen una conexión para las exportaciones.](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Administrador

- Todos los permisos disponibles para el colaborador.
- Cambie la configuración de la página **Sistema**, incluido el idioma de trabajo y las programaciones de actualización de los procesos del sistema.
- Vea y agregue permisos mediante la página **Permisos**.
- Establezca definiciones de buscar y filtrar para la página Clientes mediante la página **Índice de búsqueda y filtros** (accesible a través de la página **Clientes**).
- Administre las conexiones y permítalas para otros roles de usuario en la página **Conexiones**.
- Administre la configuración y enriquezca los perfiles de clientes desde la página **Enriquecimiento** (para todos los enriquecimientos).
- Gestione y cree exportaciones en la página **Exportaciones**.
- Instale y utilice el **Complemento de tarjeta de cliente**.
- Agregue y use el conector de **Power Apps**.
- Habilitar el uso de las [API de Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Asignar roles y permisos

1. En informaciones de público, vaya a **Administración** > **Permisos**.

1. Seleccione **Agregar usuarios** para abrir el panel **Agregar/editar permisos**.

1. Utilice el campo **Buscar** para encontrar el usuario o grupo de Azure Active Directory cuyos permisos desea ajustar. Seleccione un **Rol** para asignar a ese usuario o grupo.

1. Seleccione **Guardar**. El entorno actual se compartirá automáticamente con el usuario o los miembros del grupo cuyos permisos ha cambiado. Los usuarios pueden acceder a la aplicación Customer Insights y trabajar de acuerdo con su rol específico.

## <a name="view-current-permissions"></a>Ver permisos actuales

En las informaciones de públicos, vaya a **Administrador** > **Permisos** para ver qué asignaciones de roles están activas actualmente.

- La columna **Tipo** especifica un único usuario, grupo o aplicación. El sistema admite usuarios individuales y grupos.
- Los roles se especifican en la columna **Rol**.
- Seleccione cualquier título de columna para ordenar los resultados por el valor de esa columna.
- Utilice el campo **Buscar** en la parte superior de la página para localizar usuarios específicos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
