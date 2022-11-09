---
title: Exportar segmentos a Marketo (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724961"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segmentos a Marketo (versión preliminar)

Exporte segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y usar grupos específicos de clientes con Marketo.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de Marketo](https://login.marketo.com/) y las credenciales de administrador correspondientes.
- Un [Id. de cliente de Marketo, secreto de cliente y nombre de host de punto de conexión REST](https://developers.marketo.com/rest-api/authentication/).
- [Listas existentes en Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) y los id. correspondientes.
- [Segmentos configurados](segments.md).
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- No se admite el enlace privado en combinación con Traiga su propio almacenamiento (BYOS).
- Hasta 1 millón de perfiles de clientes por exportación a Marketo, lo que puede tardar hasta 3 horas. El número de perfiles de clientes que puede exportar a Marketo depende de su contrato con Marketo.
- Solo segmentos.

## <a name="set-up-connection-to-marketo"></a>Configurar conexión a Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Marketo**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su **Id. de cliente de Marketo, secreto de cliente y nombre de host de punto de conexión REST**. El nombre de host del punto de conexión REST es solo el nombre de host, sin https://. Ejemplo: xyz-abc-123.mktorest.com.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Marketo. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Introduzca su **Id. de lista de Marketo**. El id. de la lista es un valor puramente numérico. Por ejemplo, si su id. de lista de Marketo es ST12345A7, elimine el carácter de antes y después de los números e introduzca *12345*.

1. En la sección **Coincidencia de datos**, seleccione al menos un campo que represente la dirección de correo electrónico de un cliente o la Id. de Marketo de un cliente.

1. Opcionalmente, puede exportar el **Nombre de pila**, el **Apellido**, la **Ciudad**, el **Estado** y el **País o región** para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

En Marketo, busque sus segmentos en [Listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
