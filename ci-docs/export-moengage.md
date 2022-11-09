---
title: Exportar segmentos a MoEngage
description: Aprenda a configurar la conexión y a exportar a MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725287"
---
# <a name="export-segments-to-moengage-preview"></a>Exportar segmentos a MoEngage (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a MoEngage y utilícelos para marketing por correo electrónico en MoEngage.

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

- [Cuenta de MoEngage](https://www.moengage.com/) y las credenciales de administrador correspondientes.
- Clave API de MoEngage desde Configuración > API en MoEngage.
- [Segmentos configurados](segments.md) en Customer Insights.

## <a name="known-limitations"></a>Limitaciones conocidas

- No se admite el enlace privado en combinación con Traiga su propio almacenamiento (BYOS).
- Hasta 100 000 perfiles de clientes por exportación a MoEngage, lo que puede tardar hasta 15 minutos en completarse. La cantidad de perfiles de clientes que puede exportar a MoEngage depende de su contrato con MoEngage.
- Solo segmentos.

## <a name="set-up-connection-to-moengage"></a>Configurar conexión a MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **MoEngage** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su [Id. de API de datos de MoEngage y la clave de API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión a MoEngage.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección MoEngage. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales.

1. Seleccione los segmentos que desea exportar. Crearemos uno o más segmentos con el mismo nombre que los segmentos seleccionados en MoEngage en **Segmentos** > **Segmentos personalizados**.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
