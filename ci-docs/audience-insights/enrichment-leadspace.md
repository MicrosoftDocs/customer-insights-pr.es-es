---
title: Enriquecimiento de los perfiles de la empresa con el enriquecimiento de terceros de Leadspace
description: Información general sobre el enriquecimiento de terceros de Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597670"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecimiento de perfiles de empresa con Leadspace (vista previa)

Leadspace es una empresa de ciencia de datos que proporciona una plataforma de datos de clientes B2B. Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa. Los enriquecimientos incluyen atributos adicionales, como el tamaño de la compañía, la ubicación, el sector y mucho más.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Leadspace deben cumplirse los siguientes requisitos previos:

- Tiene una licencia Leadspace activa y la “clave perpetua” (denominada **Token de Leadspace**). Contacte directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para detalles sobre su producto.
- Tiene permisos de [Administrador](permissions.md#administrator).
- Usted tiene [perfiles de clientes unificados](customer-profiles.md) para empresas.

## <a name="configuration"></a>Configuración

1. En las informaciones de público, vaya a **Datos** > **Enriquecimiento**.

1. Seleccione **Enriquecer mis datos** en la ventana Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla del mosaico de Leadspace.":::

1. Seleccione **Comenzar** y luego introduzca un **Token de Leadspace** activo (clave perpetua). Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**. Confirme ambas entradas seleccionando **Conectarse a Leadspace**.

1. Seleccione **Agregar datos** y elija el conjunto de datos de cliente que desee enriquecer con datos empresariales de Leadspace. Puede seleccionar la entidad *Cliente* para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Elija entre el perfil del cliente y el enriquecimiento del segmento.":::

1. Haga clic en **Siguiente** y defina qué campos de sus perfiles unificados se deben utilizar para buscar datos de empresa coincidentes en Leadspace. Se requiere el campo **Nombre de la compañía**. Para una mayor precisión de coincidencia, pueden añadirse hasta otros dos campos, **Sitio web de la compañía** y **Ubicación de la compañía**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::
   
1. Seleccione **Aplicar** para completar la asignación de campos.

1. Seleccione **Ejecutar** para enriquecer los perfiles de la empresa. La duración de un enriquecimiento depende de la cantidad de perfiles de clientes unificados.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Después de actualizar el enriquecimiento, puede revisar los datos de la empresa recién enriquecidos en [Mis enriquecimientos](enrichment-hub.md). Puede encontrar la hora de la última actualización y la cantidad de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

Para obtener más información, vea [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Leadspace cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]