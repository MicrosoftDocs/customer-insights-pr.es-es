---
title: Exportar datos de Customer Insights a HubSpot
description: Aprenda a configurar la conexión y exportar a HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588915"
---
# <a name="export-segments-to-hubspot-preview"></a>Exportar segmentos a HubSpot (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a HubSpot y utilícelos para actividades de marketing por correo electrónico.

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

- Una [cuenta de HubSpot](https://www.hubspot.com/) y las credenciales de administrador correspondientes.
- [Clave API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) de HubSpot.
- [Segmentos configurados](segments.md) en Customer Insights.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 100 000 perfiles de clientes por exportación a HubSpot, que puede tardar hasta 15 minutos en completarse. La cantidad de perfiles de clientes que puede exportar a HubSpot depende y está limitada por su contrato con HubSpot.
- Solo segmentos.

## <a name="set-up-connection-to-hubspot"></a>Configurar conexión a HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **HubSpot** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cuando se le solicite, escriba sus credenciales de HubSpot.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión a HubSpot.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección HubSpot. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
