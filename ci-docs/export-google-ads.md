---
title: Exportar segmentos a Google Ads (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081955"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos a Google Ads (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a una lista de público de Google Ads y utilícelos para anunciar en la Google Search, Gmail, YouTube y la Red de Display de Google. 


## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de Google Ads](https://ads.google.com/) y las credenciales de administrador correspondientes.
-   Cumple los requisitos de la [Directiva de asignación de clientes](https://support.google.com/adspolicy/answer/6299717).
-   Cumple los requisitos de los [tamaños de listas de marketing](https://support.google.com/google-ads/answer/7558048).
-   Ha [configurado los segmentos](segments.md).
-   Los perfiles de clientes unificados en los segmentos exportados contienen campos que representan una dirección de correo electrónico, teléfono, Id. de anunciante móvil, Id. de usuario de terceros o dirección.

## <a name="known-limitations"></a>Limitaciones conocidas

- La exportación a Google Ads está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles de clientes puede tardar hasta 30 minutos debido a las limitaciones del lado del proveedor. 
- La coincidencia en Google Ads puede tardar hasta 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexión a Google Ads

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Google Ads** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su **[Id. de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Autenticarse con Google Ads** y proporcione sus credenciales de Google Ads.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Google Ads. Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.

1. Si desea crear un nuevo público, deje en blanco el campo de Id. de público de Google. Crearemos automáticamente un nuevo público en su cuenta de Google Ads y usaremos el nombre del segmento exportado. Si desea actualizar un público de Google Ads existente, escriba su [Id. de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. En la sección **Coincidencia de Datos**, seleccione uno o más campos de datos para exportar y seleccione el campo que representa los campos de datos correspondientes en Customer Insights.

1. Seleccione los segmentos que desea exportar. 

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). 

Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Google Ads cumplan con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE [footer-include](includes/footer-banner.md)]
