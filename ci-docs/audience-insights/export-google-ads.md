---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar la conexión y a exportar a Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c958f58c927b76364f305dad8f524dde29b2a638
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558993"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos a Google Ads (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a una lista de público de Google Ads y utilícelos para anunciar en la Google Search, Gmail, YouTube y la Red de Display de Google. 

> [!IMPORTANT]
> Actualmente, solo puede crear una nueva conexión y exportar datos a Google Ads si ya tiene un token de desarrollador de Google Ads aprobado. Debido a cambios en la política, actualizaremos la exportación de Google Ads en breve y brindaremos una opción de exportación que no requerirá un token de desarrollador para garantizar la continuidad de su experiencia y simplificar la exportación a Google Ads. Recomendamos no configurar más conexiones a Google Ads para facilitar el cambio a la nueva opción de exportación.

## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de Google Ads](https://ads.google.com/) y las credenciales de administrador correspondientes.
-   Tiene un [símbolo (token) de desarrollador de Google Ads aprobado](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Cumple los requisitos de la [Directiva de asignación de clientes](https://support.google.com/adspolicy/answer/6299717).
-   Cumple los requisitos de los [tamaños de listas de marketing](https://support.google.com/google-ads/answer/7558048).
-   Hay públicos existentes en Google Ads y los id. correspondientes. Para más información, consulte [Audiencias de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Ha [configurado los segmentos](segments.md).
-   Los perfiles de clientes unificados en los segmentos exportados contienen campos que representan una dirección de correo electrónico, un nombre de pila y los apellidos.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a Google Ads.
- La exportación a Google Ads está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 5 minutos debido a las limitaciones del lado del proveedor. 
- La coincidencia en Google Ads puede tardar hasta 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexión a Google Ads

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Google Ads** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su **[Id. de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduzca su **[Token de desarrollador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Autenticarse con Google Ads** y proporcione sus credenciales de Google Ads.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Google Ads. Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.

1. Introduzca su **[Id. de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** y seleccione **Conectar** para inicializar la conexión a Google Ads.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a Google Ads.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). 

Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Google Ads cumplan con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
