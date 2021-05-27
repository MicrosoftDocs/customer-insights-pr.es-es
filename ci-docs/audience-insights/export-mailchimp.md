---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar la conexión y a exportar a Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976176"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>Exportar listas de segmentos a Mailchimp (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Mailchimp para crear boletines y campañas de correo electrónico.

## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de Mailchimp](https://mailchimp.com/) y las credenciales de administrador correspondientes.
-   Hay públicos existentes en Mailchimp y los id. correspondientes. Para más información, consulte [Audiencias de Mailchimp](https://mailchimp.com/help/create-audience/).
-   Ha [configurado los segmentos](segments.md)
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a Mailchimp.
- La exportación a Mailchimp está limitada a segmentos.
- La exportación de segmentos con un millón de perfiles puede tardar hasta tres horas. 
- La cantidad de perfiles que puede exportar a Mailchimp depende y está limitada a su contrato con Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Configurar conexión a Mailchimp

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Autopilot** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Mailchimp.

1. Seleccione **Autenticarse con Mailchimp** y proporcione sus credenciales de Mailchimp.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-the-connector"></a>Configurar el conector

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos**> **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Mailchimp. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Escriba su **[identificador de audiencia de Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. 

1. Opcionalmente, puede exportar el **Nombre de pila** y el **Apellido** para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a Mailchimp.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Mailchimp cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
