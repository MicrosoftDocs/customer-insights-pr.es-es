---
title: Comenzar con la funcionalidad de conclusiones sobre la interacción
description: Una descripción general de los recursos de ayuda para comenzar rápidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405379"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Comenzar con la funcionalidad de conclusiones sobre la interacción (versión preliminar) de Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La funcionalidad conclusiones sobre la interacción le permite recopilar y medir el comportamiento de los clientes en su sitio web. Se integra con la funcionalidad de conclusiones del público para que pueda ver análisis de comportamiento enriquecidos en tiempo real junto con informes de perfil de cliente. Los enlaces de este artículo le ayudarán a configurar rápidamente su entorno.

## <a name="step-1-review-prerequisites"></a>Paso 1: Revisar requisitos previos

Primero, debe tener una cuenta de usuario Azure Active Directory de Microsoft activa. Luego, lea los siguientes artículos antes de configurar un área de trabajo de conclusiones sobre la interacción.

- Revise y acepte los [Términos del servicio](terms-of-service.md) con Microsoft.  
- Lea el artículo [Gestionar cookies y consentimiento del usuario](user-consent-storage.md). Después de revisar este artículo, evalúe si necesita actualizar su notificación de consentimiento de usuario. Si anteriormente no tenía cookies "no esenciales", es probable que deba actualizar la política de su sitio.
- Revise el [glosario](glossary.md) para obtener una introducción rápida a los términos y conceptos clave.

## <a name="step-2-explore-engagement-insights"></a>Paso 2: explorar las conclusiones sobre la interacción

La primera vez que visita las conclusiones sobre la interacción, puede configurar las opciones, revisar las políticas y explorar el producto.

1. Inicie sesión en el [portal de la funcionalidad de conclusiones sobre la interacción](https://pi.dynamics.com) usando su cuenta de usuario Azure Active Directory de Microsoft. (Puede ser su cuenta profesional o educativa).

1. Seleccione su región y use la casilla de verificación para indicar si desea optar por recibir actualizaciones y ofertas por correo electrónico.

1. Revise las **Condiciones de uso de conclusiones sobre la interacción (versión preliminar)** y la **Declaracion de privacidad** y luego seleccione **Explorar la demostración** para aceptarlas.

1. Explore el producto utilizando un conjunto de datos de muestra.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Paso 3: configurar un área de trabajo y agregar código a su sitio web

El área de trabajo es donde puede ver la actividad del usuario en tiempo real y almacenar y administrar informes. Agregue código a su sitio web para comenzar a recopilar *eventos*, los datos de actividad que provienen de los usuarios.

1. [Cree un área de trabajo](create-workspace.md) y añada miembros.

1. [Agregue código a su sitio web](instrument-website.md) o [aplicación móvil](developer-resources.md#capture-events-from-mobile-apps) para ver la actividad del usuario que llega a su área de trabajo.

1. Consulte un [informe en tiempo real](view-reports.md) mostrando los usuarios activos por navegador, dispositivo, sistema operativo, ubicación e idioma. También puede crear [informes personalizados](custom-reports.md) para crear sus propias visualizaciones.
    
## <a name="step-4-export-data-to-other-channels"></a>Paso 4: exportar datos a otros canales

Puede crear *eventos refinados* (una vista virtual) de sus datos de análisis web. Luego filtre y exporte los datos a Azure Data Lake Storage. Puede ingerir los datos exportados como origen de datos. Para más información, consulte [Crear un vínculo entre las conclusiones del público y las conclusiones sobre la interacción](integrate-audience-insights-engagement-insights.md).

1. [Cree eventos refinados](refined-events.md) para exportar.

1. [Exporte los datos](export-events.md) a Data Lake Storage.

1. Aprenda a [eliminar y exportar datos de eventos que contienen información personal](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Paso 5: mantenerse conectado

Agradecemos su participación activa y planeamos considerar todos los comentarios relevantes en el desarrollo de versiones futuras. Comparta sus comentarios y notifique las incidencias a través de uno de estos canales:
- [Comunidad](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Proporcionar comentarios](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitud de soporte técnico](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
