---
title: Enriquecimiento con el enriquecimiento de terceros HERE Technologies
description: Información general sobre el enriquecimiento de terceros HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896072"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecimiento de perfiles de clientes con HERE Technologies (versión preliminar)

HERE Technologies es una empresa de plataformas de ubicación que proporciona datos y servicios centrados en la ubicación. Con los servicios de enriquecimiento de datos de HERE Technologies, puede construir una comprensión más precisa de la ubicación de sus clientes con normalización de direcciones, extracción de latitud y longitud, etc.

## <a name="prerequisites"></a>Requisitos previos

Para configurar los enriquecimientos de HERE Technologies, se deben cumplir los siguientes requisitos previos:

- Debe disponer de una suscripción activa de HERE Technologies. Para obtener una suscripción, puede [registrarse aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [ponerse en contacto con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente. [Obtenga más información sobre el enriquecimiento de ubicación de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Hay una [conexión](connections.md) a HERE disponible *o* tiene permisos de [administrador](permissions.md#administrator) y la clave API de HERE Technologies.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento**. 

1. Seleccione **Enriquecer mis datos** en la ventana de HERE Technologies y seleccione **Comenzar**.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de HERE Technologies](media/HERE-tile.png "Mosaico de HERE Technologies")

1. Seleccione una [conexión](connections.md) en la lista desplegable. Contacte con un administrador si no hay conexión disponible. Si es un administrador, puede crear una conexión seleccionando **Agregar conexión**. Elija **HERE Technologies** desde el menú desplegable. 

1. Seleccione **Conectarse a HERE Technologies** para confirmar la selección.

1.  Seleccione **Siguiente** y elija el **Conjunto de datos del cliente** que desea enriquecer con datos de ubicación de HERE Technologies. Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. Elija si desea asignar campos a la dirección principal y/o secundaria. Puede especificar una asignación de campo para ambas direcciones y enriquecer los perfiles para ambas direcciones por separado. Por ejemplo, si hay una casa y una dirección comercial. Seleccione **Siguiente**.

1. Defina qué campos de sus perfiles unificados se deben utilizar para buscar datos de ubicación coincidentes en HERE Technologies. Los campos **Calle 1** y **Código postal** son obligatorios para la dirección primaria y/o secundaria seleccionadas. Para una mayor precisión de coincidencia, se pueden agregar más campos.

   > [!div class="mx-imgBorder"]
   > ![Página de configuración de enriquecimiento de HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuración de enriquecimiento de HERE Technologies")

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Escriba un nombre para el enriquecimiento. 

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar la conexión para HERE Technologies 

Debe ser un administrador para configurar las conexiones. Seleccione **Agregar conexión** cuando configure un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de HERE Technologies.

1. Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.

1. Proporcione una clave API de HERE Technologies válida.

1. Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.

1. Seleccione **Verificar** para validar la configuración.

1. Después de completar la verificación, seleccione **Guardar**.

> [!div class="mx-imgBorder"]
   > ![Página de configuración de la conexión de HERE Technologies](media/enrichment-HERE-connection.png "Página de configuración de la conexión de HERE Technologies")

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y los tiempos de respuesta de la API de HERE Technologies.

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que HERE Technologies cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
