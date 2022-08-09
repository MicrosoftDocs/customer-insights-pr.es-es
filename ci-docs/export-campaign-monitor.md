---
title: Exportar segmentos a Campaign Monitor (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196323"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos a Campaign Monitor (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Campaign Monitor y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de Campaign Monitor](https://www.campaignmonitor.com/) y las credenciales de administrador correspondientes.
- Un [Id. de lista de Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Una [Clave de API generada](https://www.campaignmonitor.com/api/getting-started/) de **Configuraciones de cuenta** de Campaign Monitor para obtener el id. de la lista de API.
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles de clientes por exportación a Campaign Monitor, lo que puede tardar hasta 20 minutos en completarse. La cantidad de perfiles de clientes que puede exportar a Campaign Monitor depende de su contrato con Campaign Monitor.
- Solo segmentos.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar una conexión a Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Campaign Monitor**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión a Campaign Monitor.

1. Seleccione **Autenticar con Campaign Monitor** y proporcione sus credenciales de administrador para Campaign Monitor.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión en la sección Campaign Monitor. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Escriba su **Id. de lista de Campaign Monitor**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a Campaign Monitor.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
