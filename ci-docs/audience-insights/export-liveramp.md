---
title: 'Conector LiveRamp '
description: Aprenda a exportar datos a LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667205"
---
# <a name="liverampreg-connector-preview"></a>Conector para LiveRamp&reg; (versión preliminar)

Active sus datos en LiveRamp para conectarse a más de 500 plataformas en ecosistemas digitales, sociales y de televisión. Trabaje con sus datos en LiveRamp para orientar, suprimir y personalizar las campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

- Necesita una suscripción a LiveRamp para usar este conector.
- Para obtener una suscripción, puede ponerse en [contacto con LiveRamp](https://liveramp.com/contact/) directamente. [Más información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Conectarse a LiveRamp

1. En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.

1. En el mosaico de **LiveRamp**, seleccione **Preparar**.

1. Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.

1. Especifique un **Nombre de usuario** y la **Contraseña** para su cuenta de FTP seguro (SFTP) de LiveRamp.
Estas credenciales pueden ser distintas de las credenciales de LiveRamp Onboarding.

1. Seleccione **Comprobar** para probar la conexión a LiveRamp.

1. Después de una comprobación correcta, proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.

1. Seleccione **Siguiente** para configurar el conector de LiveRamp.

## <a name="configure-the-connector"></a>Configurar el conector

1. En el campo **Elegir su identificador clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar estos datos a LiveRamp para la resolución de identidad.

1. Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.

1. Seleccione **Agregar atributo** para asignar atributos adicionales que se enviarán a LiveRamp.

   > [!TIP]
   > Es probable que el envío de más atributos de identificador clave a LiveRamp le proporcione una tasa de coincidencia más alta.

1. Seleccione los segmentos que desea exportar a LiveRamp.

1. Seleccione **Guardar**.

> [!div class="mx-imgBorder"]
> ![Conector para LiveRamp con asignación de atributos](media/export-liveramp-segments.png "Conector para LiveRamp con asignación de atributos")

## <a name="export-the-data"></a>Exportar los datos

Si se han completado todos los requisitos previos para la exportación, esta comenzará en breve. La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).
Una vez que la exportación se ha completado correctamente, puede iniciar sesión en LiveRamp Onboarding para activar y distribuir sus datos.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Liveramp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Liveramp cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.