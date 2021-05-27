---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar la conexión y a exportar a Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059337"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segmentos a Marketo (versión preliminar)

Exporte segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y usar grupos específicos de clientes con Marketo.

## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de Marketo](https://login.marketo.com/) y las credenciales de administrador correspondientes.
-   Hay listas existentes en Marketo y los id. correspondientes. Para obtener más información, consulte las [listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Ha [configurado los segmentos](segments.md).
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a Marketo.
- La exportación a Marketo está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas. 
- La cantidad de perfiles que puede exportar a Marketo depende y está limitada a su contrato con Marketo.

## <a name="set-up-connection-to-marketo"></a>Configurar conexión a Marketo

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Marketo** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca su **[Id. de cliente de Marketo, secreto de cliente y nombre de host de punto de conexión REST](https://developers.marketo.com/rest-api/authentication/)**. El nombre de host del punto de conexión REST es solo el nombre de host, sin `https://`. Ejemplo: `xyz-abc-123.mktorest.com`. 

1. Seleccione **Estoy de acuerdo** para confirmar la **Privacidad y cumplimiento de datos** y seleccione **Conectar** para inicializar la conexión a Marketo.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Marketo. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. introduzca su **[Id. de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. El id. de la lista es un valor puramente numérico. Por ejemplo, si su id. de lista de Marketo es ST12345A7, elimine el carácter de antes y después de los números e introduzca `12345`. 

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. 

1. Opcionalmente, puede exportar el **Nombre de pila**, el **Apellido**, la **Ciudad**, el **Estado** y el **País** para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a Marketo.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). En Marketo, ahora puede encontrar sus segmentos en [Listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Marketo cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
