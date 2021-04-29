---
title: Enriquecer perfiles de cliente unificados
description: Utilice las capacidades para enriquecer los datos de sus clientes.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896026"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimiento para perfiles de clientes (vista previa)

Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página del centro de enriquecimiento":::

En la información de audiencia, vaya a **Datos** > **Enriquecimiento** para trabajar con opciones de enriquecimiento.    
Debe tener permisos de Colaborador o Administrador para crear o editar enriquecimientos. Para obtener más información, vea [Permisos](permissions.md).

En la pestaña **Descubrir** encontrará los siguientes enriquecimientos:

- [Marcas](enrichment-microsoft.md) proporcionadas por Microsoft
- [Intereses](enrichment-microsoft.md) proporcionados por Microsoft
- [Datos de empresa](enrichment-leadspace.md) proporcionados por Leadspace
- [Datos demográficos](enrichment-experian.md) proporcionados por Experian
- [Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies
- [Datos de cliente](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)

En la pestaña **Mis enriquecimientos** puede ver los enriquecimientos que ha configurado y editar sus propiedades.

## <a name="manage-existing-enrichments"></a>Administrar enriquecimientos existentes

Vaya a **Mis enriquecimientos** para ver todos los enriquecimientos configurados. Cada enriquecimiento se representa como una fila que incluye información adicional sobre el enriquecimiento.

Seleccione un enriquecimiento para ver las opciones disponibles. También puede seleccionar los puntos suspensivos (...) en un elemento de la lista para ver las opciones.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opciones para administrar enriquecimientos en la lista de enriquecimientos":::

- **Vea** los detalles de enriquecimiento con el número de perfiles de clientes enriquecidos.
- **Edite** la configuración de enriquecimiento.
- **Ejecutar** el enriquecimiento para actualizar los perfiles de los clientes con los últimos datos.
- **Desactive** un enriquecimiento existente para evitar que se actualice automáticamente con cada actualización programada. Los datos de la última actualización exitosa seguirán estando disponibles. **Active** un enriquecimiento inactivo para reiniciar la actualización automática con cada actualización programada.
- **Eliminar** un enriquecimiento.

Puede ejecutar o desactivar varios enriquecimientos a la vez seleccionándolos en la lista. Las opciones de visualización y edición no están disponibles como acción masiva y solo funcionan para un enriquecimiento a la vez.

## <a name="enrichments-and-connections"></a>Enriquecimientos y conexiones

Los enriquecimientos de terceros se configuran mediante [conexiones](connections.md), que un administrador configura con credenciales y proporciona consentimiento para transferencias de datos. La conexión puede ser utilizadas por parte de administradores y colaboradores para configurar enriquecimientos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiples enriquecimientos del mismo tipo

La entidad que se va a enriquecer se especifica durante la configuración del enriquecimiento, lo que le permite enriquecer solo un subconjunto de sus perfiles. Por ejemplo, enriquezca los datos solo para un segmento específico. Puede configurar varios enriquecimientos del mismo tipo y reutilizar la misma conexión. Algunos enriquecimientos tendrán límites en el número de enriquecimientos del mismo tipo que se pueden crear. Los límites y el uso actual se pueden ver en la página **Enriquecimiento**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
