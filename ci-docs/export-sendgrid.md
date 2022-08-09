---
title: Exportar segmentos a SendGrid (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197013"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos a SendGrid (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a las listas de contactos de SendGrid y utilícelos para campañas y marketing por correo electrónico en SendGrid.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de SendGrid](https://sendgrid.com/) y las credenciales de administrador correspondientes.
- [Listas de contactos existentes en SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) y los identificadores correspondientes.
- Una [Clave de API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 100 000 perfiles de clientes en total a SendGrid, lo que puede tardar varias horas en completarse. El número de perfiles de clientes que puede exportar a SendGrid depende de su contrato con SendGrid.
- Solo segmentos.

## <a name="set-up-connection-to-sendgrid"></a>Configurar conexión a SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **SendGrid**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introzuca su **Clave de API SendGrid**.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección SendGrid. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Especifique su **Id. de lista de SendGrid**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Opcionalmente, seleccione campos como **Nombre de pila**, **Apellido**, **País o región**, **Provincia**, **Ciudad** y **Código postal**.

1. Seleccione los segmentos que desea exportar, siguiendo las limitaciones conocidas.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
