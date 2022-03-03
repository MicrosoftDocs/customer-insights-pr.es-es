---
title: Crear una nueva área de trabajo
description: El propósito de un área de trabajo y cómo crear una nueva.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 76b3466afd84aa439ea55afe90ae037825884f2d
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229098"
---
# <a name="create-a-new-workspace-and-add-members"></a>Creación de una nueva área de trabajo de la aplicación y adición de miembros

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un área de trabajo es un modo para ver la actividad de usuario en tiempo real para comprender mejor su público. Es donde almacena y administra eventos e informes.

Cuando crea un área de trabajo, selecciona el tipo de datos en el que desea centrarse. Puede agregar otros usuarios o miembros a un área de trabajo existente en cualquier momento. 

## <a name="create-a-new-workspace"></a>Crear una nueva área de trabajo

El proceso de creación de un área de trabajo incluye la configuración del *entorno* para organizar su área de trabajo. Un entorno es un espacio que puede contener una o más áreas de trabajo. Puede utilizar un entorno para administrar sus espacios de trabajo y conexiones a la capacidad de información audiencia.

1. Seleccione **+Nuevo** desde el selector de área de trabajo.

   :::image type="content" source="media/new-workspace.png" alt-text="Página de Customer Insights con una llamada en el panel de navegación y una descripción.":::

1. En el panel **Área de trabajo**, ingrese un **Nombre del área de trabajo**.

   :::image type="content" source="media/workspace-name.png" alt-text="Escriba un nombre de área de trabajo.":::

1. Elija el tipo de plataforma (web o móvil) que desea medir.

1. Seleccione **Mostrar configuración avanzada** para habilitar o deshabilitar estas configuraciones opcionales:

   - Active **Desconocido a conocido** para asociar eventos web con usuarios que se autenticaron previamente. Para más información, vea [Reconocer eventos web de visitantes previamente autenticados](unknown-to-known.md)
   - Active **Filtrar tráfico de bots** para quitar el tráfico web de los bots para esta área de trabajo. 

1. Seleccione **Completo** cuando haya terminado. 

1. Instale el fragmento de código para comenzar a recibir datos y luego seleccione **Finalizar** para crear el área de trabajo. Para obtener más información, consulte [Información general para desarrolladores](developer-resources.md).

> [!NOTE]
> Ahora puede agregar miembros y asignar su nivel de permiso desde la lista **Rol**. Para obtener más información, consulte [Roles y permisos](user-roles.md). 

Para obtener más información, consulte [Gestionar entornos y áreas de trabajo](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
