---
title: 'Conector LiveRamp '
description: Aprenda a configurar la conexión y a exportar a LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7940db3efacad62ba16099849b3e3ca00d2a5cc1ed31e15a34209c0797e6ae13
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035666"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos a LiveRamp&reg; (versión preliminar)

Active sus datos en LiveRamp para conectarse con más de 500 plataformas en ecosistemas digitales, sociales y de televisión. Trabaje con sus datos en LiveRamp para orientar, suprimir y personalizar las campañas publicitarias.

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

- Necesita una suscripción a LiveRamp para usar este conector.
- Para obtener una suscripción, puede ponerse en [contacto con LiveRamp](https://liveramp.com/contact/) directamente. [Más información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configurar conexión a LiveRamp

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **LiveRamp** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique un **Nombre de usuario** y la **Contraseña** para su cuenta de FTP seguro (SFTP) de LiveRamp.
Estas credenciales pueden ser distintas de las credenciales de LiveRamp Onboarding.

1. Seleccione **Comprobar** para probar la conexión a LiveRamp.

1. Después de una comprobación correcta, proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección LiveRamp. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. En el campo **Elegir su identificador clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar estos datos a LiveRamp para la resolución de identidad.
   > [!div class="mx-imgBorder"]
   > ![Conector para LiveRamp con asignación de atributos.](media/export-liveramp-segments.png "Conector para LiveRamp con asignación de atributos")

1. Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.

1. Seleccione **Agregar atributo** para asignar más atributos para enviar a LiveRamp.

   > [!TIP]
   > Es probable que el envío de más atributos de identificador clave a LiveRamp le proporcione una tasa de coincidencia más alta.

1. Seleccione los segmentos que desea exportar a LiveRamp.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Liveramp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Liveramp cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
