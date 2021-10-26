---
title: Exportar datos de Customer Insights a Klaviyo
description: Aprenda a configurar la conexión y exportar a Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5f7c91afed8eeb1f767f1efc58dceb7782c37bb4
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619094"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Exportar listas de segmentos a Klaviyo (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Klaviyo y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de Klaviyo](https://www.klaviyo.com/) y las credenciales de administrador correspondientes.
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 100.000 perfiles de clientes por exportación a Klaviyo.
- La exportación a Klaviyo está limitada a segmentos.
- La exportación de hasta 1 millón de perfiles de clientes a Klaviyo puede tardar hasta 20 minutos en completarse. 
- La cantidad de perfiles de clientes que puede exportar a Klaviyo depende y está limitada por su contrato con Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Configurar la conexión con Klaviyo

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Klaviyo** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. PRoporcione su [Clave de API de Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) para continuar iniciando sesión. 

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Klaviyo.

1. Seleccione **Autenticar con Klaviyo** y proporcione sus credenciales de administrador de Klaviyo.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Klaviyo. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Indique su [**Id. de lista de Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a Klaviyo.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilite Dynamics 365 Customer Insights para transmitir datos a Klaviyo, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Klaviyo cumple las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
