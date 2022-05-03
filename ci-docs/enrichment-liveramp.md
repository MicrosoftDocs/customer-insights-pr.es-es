---
title: Enriquecimiento de datos de identidad de LiveRamp
description: Enriquezca los perfiles de los clientes con datos de LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647609"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquecer los perfiles de los clientes con datos de identidad de LiveRamp (versión preliminar) 

LiveRamp proporciona resolución de identidad fuera de línea determinista y consolidación de datos de clientes. Puede asignar identificadores personales en sus datos de cliente al gráfico de identidad de AbiliTec y recibir id. de AbiliTec. A continuación, puede utilizar estos id. para una mejor unificación de los datos de sus clientes. 

## <a name="prerequisites"></a>Requisitos previos 

Para configurar el enriquecimiento, deben cumplirse los siguientes requisitos previos: 

- Debe disponer de una suscripción activa de LiveRamp. Para obtener una suscripción, comuníquese con su equipo de cuenta de LiveRamp o [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para más información.   

- Una suscripción activa de AbiliTec con id. y secreto de cliente para acceder a la API. Para obtener más información, consulte [Centro de desarrollo de API AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Países/regiones admitidos 

Actualmente admitimos el enriquecimiento de perfiles de clientes con datos de LiveRamp solo en los Estados Unidos. 

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento 

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**. 

1. Seleccione **Enriquecer mis datos** en la ventana **Identidad**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Icono de identidad en la página de información general de enriquecimiento ":::

1. Seleccione una [conexión](connections.md) en la lista desplegable. Contacte con un administrador si no hay conexión disponible. Si es un Administrador, puede crear una conexión seleccionando **Añadir conexión**. Elija **LiveRamp** en la lista desplegable. 

1. Seleccione **Siguiente** y elija el **Conjunto de datos de cliente** que desea enriquecer con datos de identidad de LiveRamp. Puede seleccionar la entidad *Cliente* para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de *segmento* para enriquecer solo los perfiles de clientes contenidos en ese segmento. 

1. Seleccione **Siguiente** y defina qué tipo de campos de sus perfiles unificados deben usarse para buscar datos de identidad coincidentes de LiveRamp. Al menos uno de los campos **Nombre y dirección**, **Teléfono** o **Correo electrónico** es obligatorio. 

   > [!TIP]
   > Cuantos más identificadores y campos principales asigne, mayor será la probabilidad de una tasa de coincidencia más alta. 

1. Asigne los campos de su entidad *Cliente* unificada que se utilizará para hacer coincidir con el gráfico de id. de AbiliTec de LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opciones de asignación de datos para el enriquecimiento de LiveRamp.":::

1. Seleccione **Siguiente** para completar la asignación de campos. 

1. Proporcione un **nombre** para el enriquecimiento y la **entidad de salida**. 

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones. 

## <a name="configure-the-connection-for-liveramp"></a>Configurar la conexión para LiveRamp 

Debe ser un administrador para [configurar las conexiones](connections.md). Seleccione **Añadir conexión** al configurar el enriquecimiento o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en el icono **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Panel de configuración para configurar la conexión al servicio AbiliTec de LiveRamp ":::

1. Para **Nombre para mostrar**, introduzca el nombre de la conexión. 

1. Proporcione un id. de cliente de LiveRamp válido y un secreto. 

1. Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**. 

1. Seleccione **Verificar** para validar la configuración. 

1. Para completar la conexión, seleccione **Guardar**. 

## <a name="enrichment-results"></a>Resultados del enriquecimiento 

Para iniciar el proceso de enriquecimiento, seleccione Ejecutar desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una  [actualización programada](system.md#schedule-tab). El tiempo de procesamiento depende del tamaño de los datos de sus clientes. 

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de perfiles de clientes recientemente enriquecidos en  **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos. 

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando  **Ver datos enriquecidos**. 

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Utilice los id. de AbiliTec para consolidar los perfiles de los clientes en una vista basada en personas. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos 

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que LiveRamp cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para obtener más información, revise la [declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
