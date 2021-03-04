---
title: Enriquecer perfiles de cliente unificados
description: Utilice las capacidades para enriquecer los datos de sus clientes.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269489"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimiento para perfiles de clientes (vista previa)

Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página del centro de enriquecimiento":::

En la información de audiencia, vaya a **Datos** > **Enriquecimiento** para trabajar con opciones de enriquecimiento.    
Debe tener permisos de Colaborador o Administrador para crear o editar enriquecimientos. Para obtener más información, vea [Permisos](permissions.md).

En la pestaña **Descubrir** encontrará los siguientes enriquecimientos:

- [Marcas](enrichment-microsoft-graph.md) proporcionadas por Microsoft Graph
- [Intereses](enrichment-microsoft-graph.md) proporcionados por Microsoft Graph
- [Datos de empresa](enrichment-leadspace.md) proporcionados por Leadspace
- [Datos demográficos](enrichment-experian.md) proporcionados por Experian
- [Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies
- [Datos de cliente](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)

En la pestaña **Mis enriquecimientos** puede ver los enriquecimientos que ha configurado y editar sus propiedades.

## <a name="manage-existing-enrichments"></a>Administrar enriquecimientos existentes

Vaya a **Mis enriquecimientos** para ver todos los enriquecimientos configurados. Cada enriquecimiento se representa como una fila que incluye información adicional sobre el enriquecimiento.

Seleccione un enriquecimiento para ver las opciones disponibles. Alternativamente, puede seleccionar los puntos suspensivos (...) en un elemento de la lista para ver las opciones.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opciones para administrar enriquecimientos en la lista de enriquecimientos":::

- **Vea** los detalles de enriquecimiento con el número de perfiles de clientes enriquecidos.
- **Edite** la configuración de enriquecimiento.
- **Ejecutar** el enriquecimiento para actualizar los perfiles de los clientes con los últimos datos.
- **Desactive** un enriquecimiento existente para evitar que se actualice automáticamente con cada actualización programada. Los datos de la última actualización exitosa seguirán estando disponibles. **Active** un enriquecimiento inactivo para reiniciar la actualización automática con cada actualización programada.
- **Eliminar** un enriquecimiento.

Puede ejecutar o desactivar varios enriquecimientos a la vez seleccionándolos en la lista. Las opciones de visualización y edición no están disponibles como acción masiva y solo funcionan para un enriquecimiento a la vez.


[!INCLUDE[footer-include](../includes/footer-banner.md)]