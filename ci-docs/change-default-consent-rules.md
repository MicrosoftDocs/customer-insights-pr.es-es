---
title: Administrar reglas de consentimiento predeterminadas en segmentos
description: Con la capacidad de administración de consentimiento, puede deshabilitar o cambiar las reglas de consentimiento predeterminadas si las anulaciones están habilitadas.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755237"
---
# <a name="disable-or-change-default-consent-rules"></a>Deshabilitar o cambiar las reglas de consentimiento predeterminadas

Si su organización utiliza la [capacidad de gestión de consentimiento](consent-management/overview.md) con Dynamics 365 Customer Insights, los [administradores pueden exigir reglas de consentimiento](activate-consent.md) para los segmentos. 

Con las reglas de consentimiento impuestas en el área del segmento, cada segmento informa sobre el estado de la verificación y las reglas del consentimiento. Si se permiten anulaciones, las reglas de consentimiento predeterminadas se desactivan para segmentos específicos. Cada creador de un segmento puede agregar más reglas de consentimiento sobre las reglas predeterminadas para un segmento. 

## <a name="for-administrators"></a>Para administradores

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Creador de segmentos con opciones de reglas de consentimiento.":::

**Para desactivar las reglas de consentimiento predeterminadas:**

1. En la notificación **Reglas de consentimiento**, seleccione **Ver detalles**. 

1. Establezca el conmutador **Reglas de consentimiento predeterminadas** a **Apagado**.

**Para agregar más reglas de consentimiento:**

1. En la notificación **Reglas de consentimiento**, seleccione **Ver detalles**. 

1. Seleccione **Agregar reglas de consentimiento** y elija una regla de consentimiento de la lista desplegable **Seleccione el tipo de datos de consentimiento**.

1. Seleccione **Guardar** para aplicar la nueva regla al segmento.

## <a name="for-contributors"></a>Para colaboradores

Para crear un segmento sin reglas de consentimiento forzadas, debe trabajar con su Administrador para deshabilitarlas en su segmento. Sin embargo, puede agregar sus propias reglas de consentimiento a los segmentos que posee y administra.

Es un proceso de tres pasos: 
1. [Crear el segmento](segments.md) en Customer Insights y guardarlo. 

1. Comparta el nombre del segmento con su administrador y pídale que [habilite anulaciones para su segmento](activate-consent.md). 

1. Abra sus segmentos nuevamente. En la notificación **Reglas de consentimiento**, seleccione **Ver detalles** y agregue las reglas de consentimiento que desea aplicar. Luego **guarde** y **ejecute** el segmento.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
