---
title: Exportar segmentos a Microsoft Advertising (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196553"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos a Microsoft Advertising (versión preliminar)

Exporte segmentos de Customer Insights a Microsoft Advertising para crear públicos de Customer Match. Utilice estos públicos para sus campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de Microsoft Advertising](https://ads.microsoft.com/) y las credenciales de administrador correspondientes.
- Id. de cliente e Id. de cuenta de Microsoft Advertising. Puede encontrar el Id. de cliente (`cid`) e Id. de cuenta (`aid`) en los parámetros de la URL cuando inicie sesión en Microsoft Advertising.
- Se aceptan las condiciones de uso de Customer Match.
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 500 000 perfiles de clientes por exportación a Microsoft Advertising, lo que puede tardar hasta 10 minutos.
- Solo segmentos.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configurar la conexión a Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Microsoft Advertising**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. El valor predeterminado es administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca el **Id. de cliente de Microsoft Advertising**.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Autenticar con Microsoft Advertising** y proporcione sus credenciales de administrador para Microsoft Advertising.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Microsoft Advertising. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Seleccione los segmentos que desea exportar. Los públicos de Customer Match en Microsoft Advertising se crean automáticamente con el nombre de los segmentos seleccionados para exportar. Cada segmento dará como resultado un público diferente de Customer Match.

1. Introduzca su **Id. de cliente e Id. de cuenta de Microsoft Advertising**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo con la dirección de correo electrónico de un cliente.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
