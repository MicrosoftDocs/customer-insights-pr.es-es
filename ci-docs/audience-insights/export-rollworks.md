---
title: Exportar datos de Customer Insights a RollWorks
description: Aprenda a configurar la conexión y a exportar a RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124110"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportar segmentos a RollWorks (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a RollWorks y utilícelos para actividades de publicidad. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de RollWorks](https://www.rollworks.com/) y las credenciales de administrador correspondientes.
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 250 000 perfiles por exportación a RollWorks.
- No puede exportar segmentos con menos de 100 perfiles a RollWorks. 
- La exportación a RollWorks está limitada a segmentos.
- La exportación de hasta 250 000 perfiles a RollWorks Monitor puede tardar hasta 10 minutos en completarse. 
- La cantidad de perfiles que puede exportar a RollWorks depende y está limitada en su contrato con RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Configurar conexión a RollWorks

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **RollWorks** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a RollWorks.

1. Seleccione **Autenticar con RollWorks** y proporcione sus credenciales de administrador para RollWorks.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección RollWorks. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Indique su **identificador de anunciante de RollWorks** [Se puede anunciar en RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a RollWorks.

1. Seleccione los segmentos que desea exportar. Seleccione un segmento con al menos 100 miembros. No puede exportar segmentos más pequeños. Además, el tamaño máximo de un segmento para exportar es de 250 000 miembros por exportación. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a RollWorks, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que RollWorks cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
