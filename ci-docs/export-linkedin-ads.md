---
title: Exportar datos de Customer Insights a LinkedIn Ads
description: Aprenda a configurar la conexión y a exportar a LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647998"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos a LinkedIn Ads (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a LinkedIn Ads para crear Matched Audiences. Utilice las Matched Audiences para la segmentación de empresas y la segmentación de contactos.

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) y las credenciales de administrador correspondientes.
-   Tiene [Segmentos configurados](segments.md) en Customer Insights.
-   Los perfiles de clientes en los segmentos exportados contienen un campo con una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Su segmento en Customer Insights debe contener al menos 300 perfiles únicos. 
- Puede exportar hasta 100.000 perfiles de clientes por exportación a LinkedIn Ads.
- La exportación a LinkedIn Ads está limitada a segmentos.
- La exportación de hasta 100.000 perfiles de clientes a LinkedIn Ads puede tardar hasta 10 minutos en completarse. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configurar la conexión a LinkedIn Ads

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **LinkedIn Ads** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado es Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione su [Id. de cuenta de LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Campaign Monitor.

1. Seleccione **Autenticar con LinkedIn** y proporcione sus credenciales de administrador para LinkedIn Campaign Manager.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar una exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección LinkedIn Ads. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Elija si desea exportar datos para hacer [segmentación de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [segmentación de la empresa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en Linkedin. 

1. En la sección **Coincidencia de datos**, para la segmentación de contactos, seleccione al menos un campo que represente la dirección de correo electrónico de un cliente, Id. de anuncio de Apple, Id. de anuncio de Google, ID de usuario de Google o nombre y apellidos. Si elige la segmentación por empresa, seleccione al menos un campo que represente un nombre de empresa, dominio de correo electrónico, URL de página de LinkedIn, símbolo de bolsa o sitio web. Se pueden seleccionar campos adicionales para definir mejor su exportación. 

1. Seleccione los segmentos que desea exportar. Las Matched Audiences en LinkedIn Campaign Manager se crearán automáticamente con el nombre de los segmentos que seleccionó para exportar. Cada segmento dará como resultado una Matched Audience diferente. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a LinkedIn Ads, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que LinkedIn Ads cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para detener el uso de esta funcionalidad.