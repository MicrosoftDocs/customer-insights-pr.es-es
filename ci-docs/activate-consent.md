---
title: Activar reglas de consentimiento para segmentos
description: Siga estos pasos para vincular los datos de consentimiento y activar las verificaciones de consentimiento en Dynamics 365 Customer Insights. Un administrador también puede deshabilitar las verificaciones de consentimiento.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647569"
---
# <a name="activate-consent-rules"></a>Activar reglas de consentimiento

El [Centro de consentimiento (vista previa)](consent-management/overview.md) le ayuda a armonizar los datos de consentimiento de diversas fuentes. Usa la entidad unificada *Consentimiento* para aplicar comprobaciones de consentimiento por defecto. Después de importar los datos de consentimiento en el Centro de consentimiento y configurar las reglas para los datos, la entidad *Consentimiento* se sincroniza automáticamente con Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Habilitar comprobaciones de consentimiento

Con los datos de consentimiento importados al Centro de consentimiento (vista previa) y las reglas configuradas, puede habilitar las verificaciones de consentimiento. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Pestaña de consentimiento en la configuración de Customer Insights con datos de consentimiento activados.":::

1. En Customer Insights, vaya a **Administración** > **Sistema**.

1. Seleccione la pestaña **Consentimiento (versión preliminar)**.

1. En la sección **Habilitar verificaciones de consentimiento**, configure el interruptor para las áreas que desea habilitar como **Activado**.

1. Seleccione la casilla **Permitir anular las reglas de consentimiento predeterminadas** para eliminar las comprobaciones de consentimiento predeterminadas que se aplican a un segmento en particular. 

1. En el menú desplegable, seleccione dónde desea permitir anulaciones.     

1. En la sección **Vincular el consentimiento a los perfiles de los clientes**, elija el atributo que se utiliza como identificador para vincular los datos de consentimiento a los datos del cliente. Probablemente sea un número de teléfono o una dirección de correo electrónico. 

1. Seleccione **Guardar** para aplicar la configuración.

## <a name="disable-consent-checks"></a>Deshabilitar comprobaciones de consentimiento

Para dejar de usar los datos de consentimiento en Customer Insights, un administrador debe actualizar la configuración del sistema en consecuencia.

1. En Customer Insights, vaya a **Administración** > **Sistema**.

1. Seleccione la pestaña **Consentimiento (versión preliminar)**.

1. En la sección **Habilite las verificaciones de consentimiento** y establezca el interruptor en **Apagado**.

> [!TIP]
> Para dejar de utilizar la función de gestión de consentimiento, consulte [Configuración del sistema en el Centro de consentimiento (vista previa)](consent-management/system-settings.md).
