---
title: Exportar segmentos a LinkedIn Ads (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304724"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos a LinkedIn Ads (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a LinkedIn Ads para crear Matched Audiences. Utilice las Matched Audiences para la segmentación de empresas y la segmentación de contactos.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) y las credenciales de administrador correspondientes.
- Un [Id. de cuenta de LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmentos configurados](segments.md) en Customer Insights.
- Los segmentos exportados necesitan al menos un campo específico dependiendo de si elige [segmentación de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [orientación de la empresa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en LinkedIn. Los campos posibles se enumeran en el paso **Coincidencia de datos** al [configurar la exportación](#configure-an-export).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 100 000 perfiles de clientes por exportación a LinkedIn Ads, lo que puede tardar hasta 10 minutos en completarse.
- Solo segmentos. Un segmento debe contener al menos 300 perfiles exclusivos.

## <a name="set-up-connection-to-linkedin-ads"></a>Configurar la conexión a LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **LinkedIn Ads**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione su id. de cuenta de LinkedIn Campaign Manager.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Autenticar con LinkedIn** y proporcione sus credenciales de administrador para LinkedIn Campaign Manager.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección LinkedIn Ads. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Elija si desea exportar datos para hacer [segmentación de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) o [segmentación de la empresa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en Linkedin.

1. En la sección **Coincidencia de datos**, para la segmentación de contactos, seleccione al menos un campo que represente la dirección de correo electrónico de un cliente, Id. de anuncio de Apple, Id. de anuncio de Google, ID de usuario de Google o nombre y apellidos. Si elige la segmentación por empresa, seleccione al menos un campo que represente un nombre de empresa, dominio de correo electrónico, URL de página de LinkedIn, símbolo de bolsa o sitio web.

1. Opcionalmente, puede seleccionar campos adicionales para definir mejor su exportación. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar. Las Matched Audiences en LinkedIn Campaign Manager se crearán automáticamente con el nombre de los segmentos que seleccionó para exportar. Cada segmento dará como resultado una Matched Audience diferente.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
