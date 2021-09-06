---
title: Enriquecimiento de los perfiles de la empresa con el enriquecimiento de terceros de Leadspace
description: Información general sobre el enriquecimiento de terceros de Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031724"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecimiento de perfiles de empresa con Leadspace (vista previa)

Leadspace es una empresa de ciencia de datos que proporciona una plataforma de datos de clientes B2B. Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa. Los enriquecimientos incluyen más atributos como el tamaño de la empresa, su ubicación, su sector y mucho más.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Leadspace deben cumplirse los siguientes requisitos previos:

- Debe tener una licencia activa de Leadspace.
- Usted tiene [perfiles de clientes unificados](customer-profiles.md) para empresas.
- Una conexión de Leadspace ya ha sido configurada por un administrador o tiene permisos de [administrador](permissions.md#administrator) y la "clave perpetua" (denominada **Token de Leadspace**). Póngase en contacto directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obtener detalles sobre su producto.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. En las informaciones de público, vaya a **Datos** > **Enriquecimiento**.

1. Seleccione **Enriquecer mis datos** en la ventana de Leadspace y seleccione **Comenzar**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla del mosaico de Leadspace.":::

1. Seleccione una [conexión](connections.md) en la lista desplegable. Contacte con un administrador si no hay conexión disponible. Si es un administrador, puede crear una conexión seleccionando **Agregar conexión** y elija **Leadspace**. 

1. Seleccione **Conectarse a Leadspace** para confirmar la selección de la conexión.

1. Seleccione **Siguiente** y elija el **Conjunto de datos del cliente** que desea enriquecer con datos empresariales de Leadspace. Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. Seleccione **Siguiente** y defina qué campos de sus perfiles unificados se usan para buscar datos empresariales coincidentes de Leadspace. Se requiere el campo **Nombre de la compañía**. Para una mayor precisión de coincidencia, pueden añadirse hasta otros dos campos, **Sitio web de la compañía** y **Ubicación de la compañía**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un nombre para el enriquecimiento y seleccione **Guardar enriquecimiento** después de revisar sus opciones.


## <a name="configure-the-connection-for-leadspace"></a>Configurar la conexión para Leadspace 

Debe ser un administrador para configurar las conexiones. Seleccione **Agregar conexión** cuando configure un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Leadspace.

1. Seleccione **Comenzar**. 

1. Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.

1. Proporcionar su token de Leadspace válido.

1. Revise y proporcione su consentimiento para **Privacidad y cumplimiento de datos** seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración.

1. Después de completar la verificación, seleccione **Guardar**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuración de la conexión de Leadspace.":::

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Después de actualizar el enriquecimiento, puede revisar los datos de la empresa recién enriquecidos en [Mis enriquecimientos](enrichment-hub.md). Puede encontrar la hora de la última actualización y la cantidad de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

Para obtener más información, vea [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Crear [segmentos](segments.md) y [medidas](measures.md) e incluso [exportar los datos](export-destinations.md) para brindar experiencias personalizadas a sus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Leadspace cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
