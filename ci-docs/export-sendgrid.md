---
title: Exportar segmentos a SendGrid (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 669f0fb48b095f6a9faeebf257ee9df3d1c580c7
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081965"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos a SendGrid (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a las listas de contactos de SendGrid y utilícelos para campañas y marketing por correo electrónico en SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de SendGrid](https://sendgrid.com/) y las credenciales de administrador correspondientes.
-   Hay listas de contactos existentes en SendGrid y los identificadores correspondientes. Para más información, consulte [SendGrid: Administrar contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Tiene [Segmentos configurados](segments.md) en Customer Insights.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 100.000 perfiles de clientes en total para SendGrid.
- La exportación a SendGrid está limitada a segmentos.
- La exportación de hasta 100.000 perfiles de clientes a SendGrid puede tardar varias horas en completarse. 
- La cantidad de perfiles de clientes que puede exportar a SendGrid depende y está limitada por su contrato con SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Configurar conexión a SendGrid

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **SendGrid** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique su **Clave API de SendGrid** [Clave API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a SendGrid.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección SendGrid. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Especifique su **[identificador de lista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **País o región**, **Provincia**, **Ciudad** y **Código postal**.

1. Seleccione los segmentos que desea exportar. Recomendamos encarecidamente **no exportar más de 100 000 perfiles de clientes en total** a SendGrid. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a SendGrid, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que SendGrid cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE [footer-include](includes/footer-banner.md)]
