---
title: Exportar segmentos a ActiveCampaign
description: Aprenda a configurar la conexión y exportar a ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195588"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportar segmentos a ActiveCampaign (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a ActiveCampaign y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de ActiveCampaign](https://www.activecampaign.com/) y las credenciales de administrador correspondientes.
- Una [lista de ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Una [clave de API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) y nombre de host del punto de conexión de REST.
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles de clientes por exportación a ActiveCampaign, lo que puede tardar hasta 90 minutos en completarse. La cantidad de perfiles de clientes que puede exportar a ActiveCampaign depende de su contrato con ActiveCampaign.
- Solo segmentos.

## <a name="set-up-connection-to-activecampaign"></a>Configurar la conexión a ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **ActiveCampaign**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique su cave de API ActiveCampaign y nombre de host del punto de conexión de REST. El nombre de host del punto de conexión REST es solo el nombre de host, sin https://.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección ActiveCampaign. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Indique su **Id. de lista de ActiveCampaign**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Opcionalmente, puede exportar **Nombre de pila**, **Apellido** y **Teléfono** para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
