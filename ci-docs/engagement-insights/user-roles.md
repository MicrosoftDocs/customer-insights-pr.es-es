---
title: Roles y permisos
description: Descripción general de los roles y permisos disponibles para los miembros del área de trabajo.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227560"
---
# <a name="roles-and-permissions"></a>Roles y permisos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un área de trabajo es donde almacena y administra eventos e informes. Para más información, vea [Crear un área de trabajo y agregar miembros](create-workspace.md). 

Un área de trabajo puede incluir los siguientes roles y permisos:

- Los roles de *miembro* son usuarios que pueden acceder a un área de trabajo. Puede asignar miembros a su área de trabajo y definir sus roles y permisos. 
- Los roles de *administrador* administran las áreas de trabajo y los entornos, y configuran las conclusiones sobre la interacción para otros usuarios. 
- Los roles de *colaborador* están dirigidos a analistas que no necesitan configurar conclusiones sobre la interacción, pero desean crear sus propios informes, embudos o segmentos.

## <a name="permissions"></a>Permisos
  
La siguiente tabla identifica los permisos para cada rol. 

| Permiso | Administrador de entorno | Administrador del área de trabajo | Colaborador del entorno | Colaborador del área de trabajo | 
|--|--|--|--|--|
| Crear entornos (el creador se convierte automáticamente en administrador del entorno) | X* | X* | X* | X* |  
| Configurar el entorno (miembros del entorno, eliminar el entorno) | X |  |  |  |  
| Crear áreas de trabajo | X |  |  |  |  
| Configurar áreas de trabajo (miembros del área de trabajo, eliminar área de trabajo) | X | X |  |  |  
| Configurar eventos y eventos refinados | X | X | |  |  
| Ver eventos del área de trabajo y eventos refinados | X | X | |  |  
| Ver recursos del área de trabajo (informes, segmentos y métricas)| X | X | X | X |  
| Crear informes y embudos personalizados | X | X | X | X |  
| Crear métricas y dimensiones base| X | X |  |  |  
| Crear segmentos| X | X | X | X |  

*Solo se pueden crear entornos de prueba en la vista previa. 

## <a name="add-members"></a>Agregar miembros

Puede agregar y eliminar miembros de áreas de trabajo y entornos. Para obtener más información, consulte [Entornos y áreas de trabajo](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
