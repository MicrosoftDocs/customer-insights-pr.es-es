---
title: Roles y permisos
description: Descripción general de los roles y permisos disponibles para los miembros del área de trabajo.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645558"
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
