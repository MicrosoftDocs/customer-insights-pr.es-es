---
title: Exportar datos de Customer Insights a AdRoll
description: Aprenda a configurar la conexión y a exportar a AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a318750077c71a17e5a47c40722f6153e6640f3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227641"
---
# <a name="export-segments-to-adroll-preview"></a>Exportar segmentos a AdRoll (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a AdRoll y utilícelos para publicidad. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de AdRoll](https://www.adroll.com/) y las credenciales de administrador correspondientes.
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 250.000 perfiles de clientes a la vez a AdRoll.
- No puede exportar segmentos con menos de 100 perfiles de clientes a AdRoll. 
- La exportación a AdRoll está limitada a segmentos.
- La exportación de hasta 250.000 perfiles de clientes a AdRoll puede tardar hasta 10 minutos en completarse. 
- La cantidad de perfiles de clientes que puede exportar a AdRoll depende de su contrato con AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configurar la conexión a AdRoll

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **AdRoll** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a AdRoll.

1. Seleccione **Autenticarse con AdRoll** y proporcione sus credenciales de administrador para AdRoll. 

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección AdRoll. Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.

1. Especifique su **Id. de anunciante de AdRoll**. Para obtener más información, consulte [Perfiles de anunciante de AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio para exportar segmentos a AdRoll.

1. Seleccione los segmentos que desea exportar. Seleccione un segmento con al menos 100 miembros. No puede exportar segmentos más pequeños. Además, el tamaño máximo de un segmento para exportar es de 250 000 miembros por exportación. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). 

Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a AdRoll, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que AdRoll cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
