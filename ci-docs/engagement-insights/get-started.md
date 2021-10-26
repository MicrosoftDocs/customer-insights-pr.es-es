---
title: Comenzar con la funcionalidad de conclusiones sobre la interacción
description: Una descripción general de los recursos de ayuda para comenzar rápidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623698"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Comenzar con la funcionalidad de conclusiones sobre la interacción (versión preliminar) de Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La funcionalidad conclusiones sobre la interacción le permite recopilar y medir el comportamiento de los clientes en su sitio web. Se integra con la funcionalidad de conclusiones del público para que pueda ver análisis de comportamiento enriquecidos en tiempo real junto con informes de perfil de cliente. Los enlaces de este artículo le ayudarán a configurar rápidamente su entorno.

## <a name="step-1-review-prerequisites"></a>Paso 1: Revisar requisitos previos

Primero, debe tener una cuenta de usuario de Microsoft Azure Active Directory (AAD) activa. Luego, lea los siguientes artículos antes de configurar un área de trabajo de conclusiones sobre la interacción.

- Revise y acepte los [Términos del servicio](terms-of-service.md) con Microsoft.  
- Lea el artículo [Gestionar cookies y consentimiento del usuario](user-consent-storage.md). Luego, evalúe si necesita actualizar su notificación de consentimiento de usuario. Si anteriormente no tenía cookies "no esenciales", es probable que deba actualizar la política de su sitio.
- Revise el [glosario](glossary.md) para obtener una introducción rápida a los términos y conceptos clave.

## <a name="step-2-explore-engagement-insights"></a>Paso 2: explorar las conclusiones sobre la interacción

La primera vez que visite las conclusiones de involucración, puede configurar los ajustes, revisar las directivas y explorar la capacidad.

1. Inicie sesión en el [portal de capacidad de información sobre involucración](https://home.ci.ai.dynamics.com/app/engagement-insights) utilizando su cuenta de usuario de Microsoft AAD (escuela o trabajo).

1. Seleccione su región y marque la casilla si desea optar por recibir actualizaciones y ofertas por correo electrónico.

1. Revise las **Condiciones de uso** de conclusiones sobre la interacción(versión preliminar) y la **Declaracion de privacidad** y luego seleccione **Explorar la demostración** para aceptar estos ajustes.

1. Explore el producto utilizando un conjunto de datos de muestra.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Paso 3: configure un área de trabajo y cree informes

Un espacio de trabajo es donde puede ver la actividad del usuario en tiempo real y almacenar y administrar informes. Agregue código a su sitio web para comenzar a recopilar *eventos*, los datos de actividad que provienen de los usuarios.

1. [Cree un área de trabajo](create-workspace.md) y añada miembros.

1. Agregue código a su [sitio web](instrument-website.md) o [aplicación móvil](developer-resources.md#capture-events-from-mobile-apps) para ver la actividad del usuario que llega a su área de trabajo.

1. Vea un [informe en tiempo real](view-reports.md) que muestra a los usuarios activos por navegador, dispositivo, sistema operativo, ubicación e idioma. También puede crear [informes personalizados](custom-reports.md) para crear sus propias visualizaciones.

1. Cree [dimensiones](dimensions.md) para clasificar a los visitantes por usuarios nuevos y recurrentes, [métrica](metrics.md) para ayudar a comprender mejor el comportamiento de los usuarios, y [segmentos](segments.md) para identificar subconjuntos de visitantes en función de las características o interacciones del sitio web.
    
## <a name="step-4-export-data-to-other-channels"></a>Paso 4: exportar datos a otros canales

Puede crear *eventos refinados* (una vista virtual) de sus datos de análisis web. Luego filtre y exporte los datos a Azure Data Lake Storage. Puede ingerir los datos exportados como origen de datos.

1. [Cree eventos refinados](refined-events.md) para exportar.

1. [Exportar los datos](export-events.md) a Azure Data Lake Storage.

1. [Cree un vínculo entre las conclusiones de audiencia y de participación](integrate-audience-insights-engagement-insights.md) para compartir datos entre las dos capacidades.

1. [Reconozca eventos web de usuarios previamente autenticados](unknown-to-known.md) con la característica **desconocido a conocido**.

1. Aprenda a [eliminar y exportar datos de eventos que contienen información personal](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Paso 5: cree y administre informes de embudo

En un informe de embudo, se recopila información sobre los pasos que tienen lugar durante un recorrido del cliente a través de su sitio web o aplicación móvil. Además de crear informes de perfil predefinidos e informes personalizados, puede crear un informe de embudo para identificar las rutas que toman sus clientes antes de realizar una compra. 

1. [Cree un informe de embudo](funnel-reports.md) para informar decisiones e identificar áreas de optimización y mejora de procesos.

1. Cree informes de embudo multicanal, una vez que haya instrumentado su aplicación móvil con el [Android SDK](get-started-android.md) o el [iOS SDK](get-started-ios.md) de conclusiones sobre la interacción.

1. Utilice [la información del embudo](funnel-reports.md#funnel-insights) para obtener una visión más profunda del comportamiento del cliente en los pasos del informe del embudo.
 
## <a name="step-6-stay-connected"></a>Paso 6: mantenerse conectado

Agradecemos su participación activa y consideramos todos los comentarios relevantes en el desarrollo de versiones futuras. Comparta sus comentarios y notifique las incidencias a través de uno de estos canales:
- [Comunidad](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Proporcionar comentarios](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitud de soporte técnico](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
