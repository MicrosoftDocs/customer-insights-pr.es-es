---
title: Exportar datos de Customer Insights a SendGrid
description: Aprenda a configurar la conexión a SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597302"
---
# <a name="connector-for-sendgrid-preview"></a>Conector para SendGrid (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a las listas de contactos de SendGrid y utilícelos para campañas y marketing por correo electrónico en SendGrid. 

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de SendGrid](https://sendgrid.com/) y las credenciales de administrador correspondientes.
-   Hay listas de contactos existentes en SendGrid y los identificadores correspondientes. Para más información, consulte [SendGrid: Administrar contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="connect-to-sendgrid"></a>Conectarse a SendGrid

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **SendGrid**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Panel de configuración de exportación de SendGrid.":::

1. Especifique su **Clave API de SendGrid** [Clave API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Especifique su **[identificador de lista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a SendGrid.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **País o región**, **Provincia**, **Ciudad** y **Código postal**.

1. Seleccione los segmentos que desea exportar. Recomendamos encarecidamente **no exportar más de 100 000 perfiles de clientes en total** a SendGrid. 

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 100 000 perfiles en total para SendGrid.
- La exportación a SendGrid está limitada a segmentos.
- La exportación de hasta 100 000 perfiles a SendGrid puede tardar unas pocas horas en completarse. 
- La cantidad de perfiles que puede exportar a SendGrid depende y está limitada a su contrato con SendGrid.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a SendGrid, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que SendGrid cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]