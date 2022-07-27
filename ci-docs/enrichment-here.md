---
title: Enriquezca los perfiles de los clientes TECNOLOGÍAS HERE (vista previa)
description: Información general sobre el enriquecimiento de terceros HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052072"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Enriquezca los perfiles de los clientes TECNOLOGÍAS HERE (vista previa)

HERE Technologies es una empresa de plataformas de ubicación que proporciona datos y servicios centrados en la ubicación. Los servicios de enriquecimiento de datos de HERE Technologies mejoran la precisión de la información de ubicación de sus clientes. Proporciona normalización de direcciones, extracción de latitud y longitud, y más.

## <a name="prerequisites"></a>Requisitos previos

- Debe disponer de una suscripción activa de HERE Technologies. Para obtener una suscripción, [regístrese aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [contacte con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente. [Obtenga más información sobre el enriquecimiento de ubicación de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- La [conexión](connections.md) HERE está [configurada](#configure-the-connection-for-here-technologies) por un Administrador.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar la conexión para HERE Technologies

Debe ser un [Administrador](permissions.md#admin) en Customer Insights y tener una clave de API de HERE Technologies activa.

1. Seleccione **Agregar conexión** cuando configure un enriquecimiento o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de HERE Technologies.

1. Introduzca un nombre para la conexión y una clave de API de HERE Technologies válida.

1. Revise y proporcione su consentimiento para [Privacidad y cumplimiento de datos](#data-privacy-and-compliance) seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración y luego seleccionar **Guardar**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Página de configuración de la conexión de HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que HERE Technologies cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en el mosaico **Ubicación** de HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Icono de HERE Technologies.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione la conexión. Contacte con un Administrador si no hay uno disponible.

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos de cliente** y elija el perfil o segmento que desea enriquecer con datos de HERE Technologies. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

1. Defina qué tipo de campos de sus perfiles unificados usar para la coincidencia: la dirección principal y/o secundaria. Puede especificar una asignación de campo para ambas direcciones y enriquecer los perfiles para ambas direcciones por separado. Por ejemplo, para una dirección particular y una dirección comercial. Seleccione **Siguiente**.

1. Asigne sus campos a los datos de identificación de HERE Technologies. Los campos **Calle 1** y **Código postal** son obligatorios para la dirección primaria y/o secundaria seleccionadas. Para una mayor precisión de coincidencia, agregue más campos.

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un **nombre** para el enriquecimiento y la **Nombre de entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="view-enrichment-results"></a>Ver los resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **Número de clientes enriquecidos por campo** proporciona un desglose de la cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
