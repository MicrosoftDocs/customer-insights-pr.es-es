---
title: Exportar segmentos a Constant Contact (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196507"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segmentos a Constant Contact (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Constant Contact y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de Constant Contact](https://www.constantcontact.com/account-home) y las credenciales de administrador correspondientes.
- Un [Id. de lista de Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). Abra una lista en Constant Contact para encontrar el identificador de la lista en la dirección URL.
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles de clientes por exportación a Constant Contact, lo que puede tardar hasta una hora en completarse. El número de perfiles de clientes que puede exportar a Constant Contact depende de su contrato con Constant Contact.
- Solo segmentos.

## <a name="set-up-connection-to-constant-contact"></a>Configurar la conexión a Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Constant Contact**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Autenticar con Constant Contact** y proporcione sus credenciales de administrador de Constant Contact.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión en la sección Constant Contact. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Escriba su **Id. de lista de Constant Contact**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Opcionalmente, exporte **Nombre de pila** y **Apellido** como campos adicionales para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
