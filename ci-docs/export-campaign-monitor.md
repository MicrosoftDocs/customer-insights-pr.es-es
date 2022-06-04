---
title: Exportar datos de Customer Insights a Campaign Monitor
description: Aprenda a configurar la conexión y a exportar a Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647588"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos a Campaign Monitor (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Campaign Monitor y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de Campaign Monitor](https://www.campaignmonitor.com/) y las credenciales de administrador correspondientes.
-   Tiene [Segmentos configurados](segments.md) en Customer Insights.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 1 millón de perfiles de clientes por exportación a Campaign Monitor.
- La exportación a Campaign Monitor está limitada a segmentos.
- La exportación de hasta 1 millón de perfiles de clientes a Campaign Monitor puede tardar hasta 20 minutos en completarse. 
- La cantidad de perfiles de clientes que puede exportar a Campaign Monitor depende y está limitada por su contrato con Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar una conexión a Campaign Monitor

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Campaign Monitor** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Campaign Monitor.

1. Seleccione **Autenticar con Campaign Monitor** y proporcione sus credenciales de administrador para Campaign Monitor.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión en la sección Campaign Monitor. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Escriba su [**Identificador de Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Genere la clave API](https://www.campaignmonitor.com/api/getting-started/) en **Configuraciones de la cuenta** de Campaign Monitor primero para ver el identificador de la lista de API.  

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a Campaign Monitor.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Campaign Monitor, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Campaign Monitor cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.