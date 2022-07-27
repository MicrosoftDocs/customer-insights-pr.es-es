---
title: Exportar segmentos a Snapchat (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: abe04cd1464c3f7df969da3c769329382d603d7e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051934"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segmentos a Snapchat (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Snapchat y utilícelos para actividades de publicidad. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

-   Usted tiene una [cuenta comercial de Snapchat](https://business.snapchat.com/), una [cuenta de anuncios de Snapchat](https://ads.snapchat.com/) y las credenciales de administrador correspondientes. Debe ser al menos miembro de una cuenta de organización y administrador de datos de una cuenta publicitaria específica. 
-   Tienes al menos un administrador de audiencia en Snapchat audiencia del tipo SAM (Snap audiencia Match). 
-   Tiene [Segmentos configurados](segments.md) en Customer Insights.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- La exportación a Snapchat está limitada a segmentos.
- La exportación de hasta 1 millón de perfiles de clientes a Snapchat puede tardar hasta 15 minutos en completarse. 

## <a name="set-up-connection-to-snapchat"></a>Configurar conexión a Snapchat

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Snapchat** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Snapchat.

1. Seleccione **Autenticar con Snapchat** y proporcione sus credenciales de administrador para Snapchat. 

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Snapchat. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Introducir el [**Segmento de Snapchat/audiencia ID**](https://businesshelp.snapchat.com/s/article/custom-audiences). El ID de audiencia se puede encontrar en la URL después de seleccionar audiencia en Snapchat audiencia Manager. 

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a Snapchat.

1. Seleccione los segmentos que desea exportar. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Snapchat, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Snapchat cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
