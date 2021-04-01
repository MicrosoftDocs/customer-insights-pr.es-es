---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar la conexión a DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598038"
---
# <a name="connector-for-dotdigital-preview"></a>Conector para DotDigital (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a las libretas de direcciones de DotDigital y utilícelos para campañas, marketing por correo electrónico y para crear segmentos de clientes con DotDigital. 

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [Cuenta de DotDigital](https://dotdigital.com/) y las credenciales de administrador correspondientes.
-   Hay libretas de direcciones existentes en DotDigital y los id. correspondientes. El id. se puede encontrar en la URL cuando selecciona y abre una libreta de direcciones. Para más información, consulte [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="connect-to-dotdigital"></a>Conectarse a DotDigital

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **DotDigital**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Panel de configuración para la exportación de DotDigital.":::

1. Introduzca su **nombre de usuario y contraseña de DotDigital**.

1. Introduzca su **[Id. de la libreta de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a DotDigital.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **Nombre completo**, **Género** y **Código postal**.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a DotDigital.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab). En DotDigital, ahora puede encontrar sus segmentos en [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a DotDigital.
- La exportación a DotDigital está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas, debido a las limitaciones del proveedor. 
- La cantidad de perfiles que puede exportar a DotDigital depende y está limitada a su contrato con DotDigital.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que DotDigital cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]