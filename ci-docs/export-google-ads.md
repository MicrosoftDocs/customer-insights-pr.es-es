---
title: Exportar segmentos a Google Ads (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196599"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos a Google Ads (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a una lista de público de Google Ads y utilícelos para anunciar en la Google Search, Gmail, YouTube y la Red de Display de Google.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de Google Ads](https://ads.google.com/) y las credenciales de administrador correspondientes.
- Un [Id. de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344).
- Los requisitos de la [Directiva Customer Match](https://support.google.com/adspolicy/answer/6299717) se cumplen.
- Los requisitos de los [tamaños de listas de marketing](https://support.google.com/google-ads/answer/7558048) se cumplen.
- [Segmentos configurados](segments.md).
- Los perfiles de clientes unificados en los segmentos exportados contienen campos que representan una dirección de correo electrónico, teléfono, Id. de anunciante móvil, Id. de usuario de terceros o dirección.

## <a name="known-limitations"></a>Limitaciones conocidas

- Exporte hasta 1 millón de perfiles de clientes por exportación a Google Ads, lo que puede tardar hasta 30 minutos en completarse debido a las limitaciones del lado del proveedor.
- Solo segmentos.
- La coincidencia en Google Ads puede tardar hasta 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexión a Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Google Ads**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su id. de cliente de Google Ads.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Autenticarse con Google Ads** y proporcione sus credenciales de Google Ads.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Google Ads. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Elija si usar un púnlico existente o cree uno nuevo:
   - Para actualizar un público de Google Ads existente, escriba su [Id. de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Para crear un nuevo público, deje en blanco el campo Id. de público de Google. Customer Insights creará automáticamente un nuevo público en su cuenta de Google Ads y usará el nombre del segmento exportado.

1. En la sección **Coincidencia de Datos**, seleccione uno o más campos de datos para exportar y seleccione el campo que representa los campos de datos correspondientes en Customer Insights.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
