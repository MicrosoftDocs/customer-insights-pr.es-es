---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar la conexión a Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598268"
---
# <a name="connector-for-google-ads-preview"></a>Conector para Google Ads (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a la lista de público de Google Ads y utilícelos para anunciar en Búsqueda de Google, Gmail, YouTube y la Red de visualización de Google. 

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de Google Ads](https://ads.google.com/) y las credenciales de administrador correspondientes.
-   Hay públicos existentes en Google Ads y los id. correspondientes. Para más información, consulte [Audiencias de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Ha [configurado los segmentos](segments.md)
-   Los perfiles de clientes unificados en los segmentos exportados contienen campos que representan una dirección de correo electrónico, un nombre de pila y los apellidos

## <a name="connect-to-google-ads"></a>Conectar a Google Ads

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **Google Ads**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

1. Introduzca su **[Id. de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduzca su **[Token de desarrollador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Introduzca su **[Id. de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** y seleccione **Conectar** para inicializar la conexión a Google Ads.

1. Seleccione **Autenticarse con Google Ads** y proporcione sus credenciales de Google Ads.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Exportar captura de pantalla para conexión de Google Ads":::

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para los campos **Nombre de pila** y **Apellido**.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a Google Ads.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab). En Google Ads, ahora puede encontrar sus segmentos en [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a Google Ads.
- La exportación a Google Ads está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 5 minutos debido a las limitaciones del lado del proveedor. 
- La coincidencia en Google Ads puede tardar hasta 48 horas.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Google Ads cumplan con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]