---
title: Exportar datos de Customer Insights a Autopilot
description: Aprenda a configurar la conexión y a exportar a Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9ada8a6f4e4546990a1360567b400033050119c4c4c9a3df1af8fcaab75e157
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032046"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segmentos a Autopilot (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Autopilot y utilícelos para marketing por correo electrónico en Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de Autopilot](https://www.autopilothq.com/) y las credenciales de administrador correspondientes.
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 100 000 perfiles de clientes a Autopilot.
- La exportación a Autopilot está limitada a segmentos.
- La exportación de hasta 100 000 perfiles a Autopilot puede tardar unas pocas horas en completarse. 
- La cantidad de perfiles que puede exportar a Autopilot depende y está limitada a su contrato con Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Configurar conexión a Autopilot

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Autopilot** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

3. Escriba su [clave API de Autopilot](https://autopilot.docs.apiary.io/#).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Autopilot.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Autopilot. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

3. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales como **Nombre de pila** o **Apellido**.

1. Seleccione los segmentos que desea exportar. Recomendamos encarecidamente **no exportar más de 100 000 perfiles de clientes en total** a Autopilot. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Autopilot, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Autopilot cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
