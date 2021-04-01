---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar la conexión a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598222"
---
# <a name="connector-for-mailchimp-preview"></a>Conector para Mailchimp (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Mailchimp para crear boletines y campañas de correo electrónico.

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de Mailchimp](https://mailchimp.com/) y las credenciales de administrador correspondientes.
-   Hay públicos existentes en Mailchimp y los id. correspondientes. Para más información, consulte [Audiencias de Mailchimp](https://mailchimp.com/help/create-audience/).
-   Ha [configurado los segmentos](segments.md)
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="connect-to-mailchimp"></a>Conectarse a Mailchimp

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **Mailchimp**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Introduzca su **[Id. de público de Mailchimp](https://mailchimp.com/help/find-audience-id/)** y seleccione **Conectar** para inicializar la conexión a Mailchimp.

1. Seleccione **Autenticarse con Mailchimp** y proporcione sus credenciales de Mailchimp.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Exportar la captura de pantalla para conexión de Mailchimp":::

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. 

1. Opcionalmente, puede exporta **Nombre de pila** y **Apellido** como campos adicionales para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Seleccionar campos y segmentos para exportar a Mailchimp":::

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab). En Mailchimp, ahora puede encontrar sus segmentos en [Públicos de Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a Mailchimp.
- La exportación a Mailchimp está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta tres horas, debido a las limitaciones del proveedor. 
- La cantidad de perfiles que puede exportar a Mailchimp depende y está limitada a su contrato con Mailchimp.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Mailchimp cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]