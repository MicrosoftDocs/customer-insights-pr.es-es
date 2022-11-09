---
title: Exportar segmentos a DotDigital (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725007"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos a DotDigital (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a las libretas de direcciones de DotDigital y utilícelos para campañas, marketing por correo electrónico y para crear segmentos de clientes con DotDigital.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de DotDigital](https://dotdigital.com/) y un [usuario de API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Una id. de DotDigital de una libreta de direcciones [nueva](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) o existente en DotDigital. El id. se puede encontrar en la URL cuando selecciona y abre una libreta de direcciones.
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- No se admite el enlace privado en combinación con Traiga su propio almacenamiento (BYOS).
- Hasta 1 millón de perfiles de clientes por exportación a DotDigital, lo que puede tardar hasta tres horas en completarse debido a las limitaciones del lado del proveedor. La cantidad de perfiles de clientes que puede exportar a DotDigital depende de su contrato con DotDigital.
- Solo segmentos.

## <a name="set-up-connection-to-dotdigital"></a>Configurar conexión a DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **DotDigital**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su **nombre de usuario y contraseña de la API de DotDigital**.

1. Introduzca su **Id. de la libreta de direcciones de DotDigital**.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección DotDigital. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Opcionalmente, exporte el **Nombre de pila**, el **Apellido**, el **Nombre completo**, el **Género** y el **Código postal**.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

En DotDigital, busque sus segmentos en [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
