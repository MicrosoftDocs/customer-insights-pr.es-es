---
title: Enriquecer de perfiles de empresa con Leadspace (vista previa)
description: Información general sobre el enriquecimiento de terceros de Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081805"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Enriquecer de perfiles de empresa con Leadspace (vista previa)

Leadspace es una empresa de ciencia de datos que proporciona una plataforma de datos del cliente B2B. Permite entornos con perfiles de clientes unificados basados en cuentas para enriquecer sus datos. Enriquezca *Perfiles de clientes* con atributos como tamaño de la empresa, ubicación o sector. Enriquezca *Perfiles de contacto* con atributos como título, persona o verificación de correo electrónico.

## <a name="prerequisites"></a>Requisitos previos

- Una licencia activa de Leadspace.
- [Perfiles de clientes unificados](customer-profiles.md) basados en cuentas.
- La [conexión](connections.md) Leadspace está [configurada](#configure-the-connection-for-leadspace) por un Administrador. Póngase en contacto directamente con [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) para obtener detalles sobre su producto.

## <a name="configure-the-connection-for-leadspace"></a>Configurar la conexión para Leadspace

Debes ser un [Administrador](permissions.md#admin) en Customer Insights y tener la "clave perpetua" (denominada **Token de espacio de ventaja**).

1. Seleccione **Agregar conexión** cuando configure un enriquecimiento o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuración de la conexión de Leadspace.":::

1. Introduzca un nombre para la conexión y un token de Leadspace válido.

1. Revise y proporcione su consentimiento para [Privacidad y cumplimiento de datos](#data-privacy-and-compliance) seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración y luego seleccionar **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Leadspace cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana **Datos de la empresa** de Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla del mosaico de Leadspace.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione la conexión. Contacte con un Administrador si no hay uno disponible.

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos de cliente** y elija el perfil o segmento que desea enriquecer con datos de la empresa de Leadspace. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. Defina qué tipo de campos de sus perfiles unificados usar para la coincidencia: la dirección principal y/o secundaria. Puede especificar una asignación de campo para ambas direcciones y enriquecer los perfiles para ambas direcciones por separado. Por ejemplo, para una dirección particular y una dirección comercial. Seleccione **Siguiente**.

1. Asigne sus campos a los datos de empresa de Leadspace. Se requiere el campo **Nombre de la compañía**. Para una mayor precisión de coincidencia, pueden añadirse hasta otros dos campos, **Sitio web de la compañía** y **Ubicación de la compañía**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Seleccione la casilla de verificación si tiene *Perfiles de contacto* que le gustaría enriquecer. Customer Insights asignará automáticamente los campos obligatorios.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enriquecimiento de registros de contacto de Leadspace.":::

1. Seleccione **Siguiente**.

1. Proporcione un **nombre** para el enriquecimiento y la **Nombre de entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="view-enrichment-results"></a>Ver los resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Para obtener más información, vea [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
