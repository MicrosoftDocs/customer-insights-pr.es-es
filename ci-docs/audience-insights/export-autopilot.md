---
title: Exportar datos de Customer Insights a Autopilot
description: Aprenda a configurar la conexión a Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596152"
---
# <a name="connector-for-autopilot-preview"></a>Conector para Autopilot (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Autopilot y utilícelos para marketing por correo electrónico en Autopilot. 

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de Autopilot](https://www.autopilothq.com/) y las credenciales de administrador correspondientes.
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="connect-to-autopilot"></a>Conectar a Autopilot

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **Autopilot**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Panel de configuración para la conexión de Autopilot.":::

1. Especifique su **Clave de API de Autopilot** [Clave de API de Autopilot](https://autopilot.docs.apiary.io/#).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Autopilot.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales como **Nombre de pila** o **Apellido**.

1. Seleccione los segmentos que desea exportar. Recomendamos encarecidamente **no exportar más de 100 000 perfiles de clientes en total** a Autopilot. 

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 100 000 perfiles de clientes a Autopilot.
- La exportación a Autopilot está limitada a segmentos.
- La exportación de hasta 100 000 perfiles a Autopilot puede tardar unas pocas horas en completarse. 
- La cantidad de perfiles que puede exportar a Autopilot depende y está limitada a su contrato con Autopilot.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Autopilot, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Autopilot cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]