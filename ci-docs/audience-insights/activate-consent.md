---
title: Activar reglas de consentimiento para segmentos en audiencia insights
description: Pasos para vincular los datos de consentimiento y activar las verificaciones de consentimiento en audiencia insights.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753082"
---
# <a name="activate-consent-rules"></a>Activar reglas de consentimiento

[Centro de consentimiento (vista previa)](../consent-management/overview.md) le ayuda a armonizar los datos de consentimiento de diversas fuentes. Usa la entidad unificada *Consentimiento* para aplicar comprobaciones de consentimiento por defecto. Después de importar los datos de consentimiento en el Centro de consentimiento y configurar las reglas para los datos de consentimiento importados, la entidad *Consentimiento* se sincroniza automáticamente con audiencia insights.

## <a name="enable-consent-checks"></a>Habilitar comprobaciones de consentimiento

Con los datos de consentimiento importados al Centro de consentimiento (vista previa) y las reglas configuradas, puede habilitar las verificaciones de consentimiento en audiencia insights. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Pestaña de consentimiento en la configuración de audiencia insights con datos de consentimiento activados.":::

1. En las informaciones de público, vaya a **Administrador** > **Sistema**.

1. Seleccione la pestaña **Consentimiento (versión preliminar)**.

1. En la sección **Habilitar verificaciones de consentimiento**, configure el interruptor para el área que desea habilitar como **Activado**.

1. Seleccione la casilla **Permitir anular las reglas de consentimiento predeterminadas** para eliminar las comprobaciones de consentimiento predeterminadas que se aplican a un segmento en particular. 

1. En el menú desplegable, seleccione dónde desea permitir anulaciones.     

1. En la sección **Vincular el consentimiento a los perfiles de los clientes**, elija el atributo que se utiliza como identificador para vincular los datos de consentimiento a los datos del cliente. Probablemente sea un número de teléfono o una dirección de correo electrónico. 

1. Seleccione **Guardar** para aplicar la configuración.

## <a name="disable-consent-checks"></a>Deshabilitar comprobaciones de consentimiento

Para dejar de usar los datos de consentimiento en audiencia insights, un administrador debe actualizar la configuración del sistema en consecuencia.

1. En las informaciones de público, vaya a **Administrador** > **Sistema**.

1. Seleccione la pestaña **Consentimiento (versión preliminar)**.

1. En la sección **Habilite las verificaciones de consentimiento** y establezca el interruptor en **Apagado**.
