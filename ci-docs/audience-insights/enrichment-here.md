---
title: Enriquecimiento con el enriquecimiento de terceros HERE Technologies
description: Información general sobre el enriquecimiento de terceros HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668699"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecimiento de perfiles de clientes con HERE Technologies (versión preliminar)

HERE Technologies es una empresa de plataformas de ubicación que proporciona datos y servicios centrados en la ubicación. Con los servicios de enriquecimiento de datos de HERE Technologies, puede construir una comprensión más precisa de la ubicación de sus clientes con normalización de direcciones, extracción de latitud y longitud, etc.

## <a name="prerequisites"></a>Requisitos previos

Para configurar los enriquecimientos de HERE Technologies, se deben cumplir los siguientes requisitos previos:

- Debe disponer de una suscripción activa de HERE Technologies. Para obtener una suscripción, puede [registrarse aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) o [ponerse en contacto con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente. [Obtenga más información sobre el enriquecimiento de ubicación de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Tiene la clave de API de HERE Technologies.

- Tiene permisos de [Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuración

1. Vaya a **Datos** > **Enriquecimiento**.

1. Seleccione **Enriquecer mis datos** en el mosaico de HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de HERE Technologies](media/HERE-tile.png "Mosaico de HERE Technologies")

1. Inroduzca una **Clave de API de HERE Technologies** activa. Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**. 

1. Confirme ambas entradas seleccionando **Conéctese AQUÍ**.

1. Seleccione **Agregar datos** y elija si desea asignar campos a la dirección principal y/o secundaria. Puede especificar una asignación de campo para ambas direcciones (por ejemplo, una dirección particular y una comercial) y enriquecer los perfiles para ambas direcciones por separado. Seleccione **Siguiente**.

1. Defina qué campos de sus perfiles unificados se deben utilizar para buscar datos de ubicación coincidentes en HERE Technologies. Los campos **Calle 1** y **Código postal** son obligatorios para la dirección primaria y/o secundaria seleccionadas. Para una mayor precisión de coincidencia, se pueden agregar más campos.

   > [!div class="mx-imgBorder"]
   > ![Página de configuración de enriquecimiento de HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuración de enriquecimiento de HERE Technologies")

1. Seleccione **Aplicar** para completar la asignación de campos.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y los tiempos de respuesta de la API de HERE Technologies.

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que HERE Technologies cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.
