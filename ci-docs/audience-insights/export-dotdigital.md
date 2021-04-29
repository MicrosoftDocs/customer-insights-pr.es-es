---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar la conexión y a exportar a DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759980"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a>Exportar listas de segmentos a DotDigital (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a las libretas de direcciones de DotDigital y utilícelos para campañas, marketing por correo electrónico y para crear segmentos de clientes con DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

-   Tiene una [Cuenta de DotDigital](https://dotdigital.com/) y las credenciales de administrador correspondientes.
-   Hay libretas de direcciones existentes en DotDigital y los id. correspondientes. El id. se puede encontrar en la URL cuando selecciona y abre una libreta de direcciones. Para más información, consulte [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a DotDigital.
- La exportación a DotDigital está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas, debido a las limitaciones del proveedor. 
- La cantidad de perfiles que puede exportar a DotDigital depende y está limitada a su contrato con DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurar conexión a DotDigital

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **DotDigital** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su **nombre de usuario y contraseña de DotDigital**.

1. Introduzca su **[Id. de la libreta de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a DotDigital.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección DotDigital. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.


1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Repita los mismos pasos para otros campos opcionales como **Nombre de pila**, **Apellido**, **Nombre completo**, **Género** y **Código postal**.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a DotDigital.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 
 
En DotDigital, ahora puede encontrar sus segmentos en [Libretas de direcciones de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que DotDigital cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
