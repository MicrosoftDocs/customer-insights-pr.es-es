---
title: Enriquecer perfiles de cliente unificados
description: Utilice las capacidades para enriquecer los datos de sus clientes.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 992c45e30e2dff00f5207290940b56b2fe1c08ad
ms.sourcegitcommit: b9a81c2acd42d774669d2db3d0430c7d81de991c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2021
ms.locfileid: "7470039"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimiento para perfiles de clientes (vista previa)

Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página del centro de enriquecimiento.":::

En la información de audiencia, vaya a **Datos** > **Enriquecimiento** para trabajar con opciones de enriquecimiento.  

Debe tener permisos de Colaborador o Administrador para crear o editar enriquecimientos. Para obtener más información, vea [Permisos](permissions.md).

En la pestaña **Descubrir** encontrará los siguientes enriquecimientos:

- [Azure Maps](enrichment-azure-maps.md) proporcionado por Microsoft
- [Marcas](enrichment-microsoft.md) proporcionadas por Microsoft
- [Intereses](enrichment-microsoft.md) proporcionados por Microsoft
- [Direcciones mejoradas](enrichment-enhanced-addresses.md) proporcionadas por Microsoft
- [Datos de empresa](enrichment-leadspace.md) proporcionados por Leadspace
- [Datos demográficos](enrichment-experian.md) proporcionados por Experian
- [Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies
- [Datos de cliente](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)

En la pestaña **Mis enriquecimientos** puede ver los enriquecimientos que ha configurado y editar sus propiedades.

## <a name="manage-existing-enrichments"></a>Administrar enriquecimientos existentes

Vaya a la pestaña **Mis enriquecimientos** para ver todos los enriquecimientos configurados. Cada enriquecimiento se representa como una fila que incluye información adicional sobre el enriquecimiento.

Seleccione el enriquecimiento para ver las opciones disponibles. También puede seleccionar los puntos suspensivos (...) en un elemento de la lista para ver las opciones. Si configuró varios enriquecimientos, puede usar el cuadro de búsqueda para encontrarlos rápidamente.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opciones para administrar enriquecimientos en la lista de enriquecimientos.":::

- **Vea** los detalles de enriquecimiento con el número de perfiles de clientes enriquecidos.
- **Edite** la configuración de enriquecimiento.
- **Ejecutar** el enriquecimiento para actualizar los perfiles de los clientes con los últimos datos.
- **Desactive** un enriquecimiento existente para evitar que se actualice automáticamente con cada actualización programada. Los datos de la última actualización exitosa seguirán estando disponibles. **Active** un enriquecimiento inactivo para reiniciar la actualización automática con cada actualización programada.
- **Eliminar** el enriquecimiento.

Ejecute o desactive varios enriquecimientos a la vez seleccionándolos en la lista. Las opciones de visualización y edición no están disponibles como acción masiva. Solo funcionan para un enriquecimiento a la vez.

## <a name="enrichments-and-connections"></a>Enriquecimientos y conexiones

Los enriquecimientos de terceros se configuran mediante [conexiones](connections.md), que un administrador configura con credenciales y proporciona consentimiento para transferencias de datos. La conexión puede ser utilizadas por parte de administradores y colaboradores para configurar enriquecimientos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiples enriquecimientos del mismo tipo

La entidad que se va a enriquecer se especifica durante la configuración del enriquecimiento, lo que le permite enriquecer solo un subconjunto de sus perfiles. Por ejemplo, enriquezca los datos solo para un segmento específico. Puede configurar varios enriquecimientos del mismo tipo y reutilizar la misma conexión. Algunos enriquecimientos tendrán límites en el número de enriquecimientos del mismo tipo que se pueden crear. Los límites y el uso actual se pueden ver en la página **Enriquecimiento**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Ver el progreso del proceso de enriquecimiento

Puede encontrar detalles sobre el procesamiento de un enriquecimiento, incluido su estado y posibles problemas mientras se actualiza o después de que se completa una actualización. Comprenda qué procesos están involucrados para actualizar un enriquecimiento y cuánto tiempo tomó ejecutar los procesos. El estado de enriquecimiento es compatible con Experian, Leadspace, HERE Technologies, SFTP Import y Azure Maps.

Para ver el estado de un enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento**. 
1. En la pestaña **Mis enriquecimientos**, seleccione el estado de un enriquecimiento para abrir un panel lateral. 
1. En el panel **Detalles de progreso**, expanda la sección **Enriquecimientos**. 
1. En el enriquecimiento cuyo progreso desea ver, seleccione **Ver detalles**. 
1. En el panel **Detalles de la tarea**, seleccione **Mostrar detalles** para ver los procesos que intervienen en la actualización del enriquecimiento y su estado. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
