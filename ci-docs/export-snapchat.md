---
title: Exportar segmentos a Snapchat (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195403"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segmentos a Snapchat (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Snapchat y utilícelos para actividades de publicidad.

## <a name="prerequisites"></a>Requisitos previos

- Una [Cuenta comercial de Snapchat](https://business.snapchat.com/), una [Cuenta de anuncios de Snapchat](https://ads.snapchat.com/) y las credenciales de administrador correspondientes. Debe ser al menos miembro de una cuenta de organización y administrador de datos de una cuenta publicitaria específica.
- Al menos un administrador de público en Snapchat público del tipo SAM (Snap público Match).
- El [Id. del segmento de Snapchat/público](https://businesshelp.snapchat.com/s/article/custom-audiences). El ID de público se puede encontrar en la URL después de seleccionar público en Snapchat público Manager.
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles de clientes, lo que puede tardar hasta 15 minutos en completarse.
- Solo segmentos.

## <a name="set-up-connection-to-snapchat"></a>Configurar conexión a Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Snapchat**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Autenticar con Snapchat** y proporcione sus credenciales de administrador para Snapchat.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Snapchat. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Introduzca el **Id. del segmento de Snapchat/público**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
