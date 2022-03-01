---
title: Exportar datos de Customer Insights a AdRoll
description: Aprenda a configurar la conexión a AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697095"
---
# <a name="connector-for-adroll-preview"></a>Conector para AdRoll (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a AdRoll y utilícelos para publicidad. 

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de AdRoll](https://www.adroll.com/) y las credenciales de administrador correspondientes.
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="connect-to-adroll"></a>Conectarse a AdRoll

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **AdRoll**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panel de configuración para la conexión de AdRoll.":::

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a AdRoll.

1. Seleccione **Autenticarse con AdRoll** y proporcione sus credenciales de administrador para AdRoll. 

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Introduzca su **Identificador de anunciante de AdRoll** [AdRoll anunciable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Es obligatorio para exportar segmentos a AdRoll.

1. Seleccione los segmentos que desea exportar. Seleccione un segmento con al menos 100 miembros. No puede exportar segmentos más pequeños. Además, el tamaño máximo de un segmento para exportar es de 250 000 miembros por exportación. 

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 250 000 perfiles de clientes a AdRoll por exportación.
- No puede exportar segmentos con menos de 100 perfiles a AdRoll. 
- La exportación a AdRoll está limitada a segmentos.
- La exportación de hasta 250 000 perfiles a AdRoll puede tardar hasta 10 minutos en completarse. 
- La cantidad de perfiles que puede exportar a AdRoll depende y está limitada a su contrato con AdRoll.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a AdRoll, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que AdRoll cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
