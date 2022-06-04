---
title: Exporte datos de Customer Insights a Braze
description: Aprenda a configurar la conexión y a exportar a Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647589"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exporte listas de segmentos a Braze (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Braze y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

-   Usted tiene una [cuenta Braze](https://www.braze.com/) y las credenciales de Administrador correspondientes.
-   Tiene [Segmentos configurados](segments.md) en Customer Insights.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico y una Id. de cliente de Braze. 

## <a name="known-limitations"></a>Limitaciones conocidas

- La exportación a Braze está limitada a segmentos.
- La exportación de hasta 1 millón de perfiles de clientes a Braze puede tardar hasta 40 minutos en completarse. 
- La cantidad de perfiles de clientes que puede exportar a Braze depende y está limitada por su contrato con Braze.

## <a name="set-up-connection-to-braze"></a>Configure la conexión a Braze

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Braze** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione su [Clave de API de Braze](https://www.braze.com/docs/api/basics/) para continuar iniciando sesión. 

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Braze.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión desde la sección Braze. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.  

3. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente, en el campo "Id. de cliente", seleccione el campo que representa la Id. de Braze del cliente. Se requiere para exportar segmentos a Braze. Los segmentos en Braze se crearán con el mismo nombre del segmento que en Dynamics 365 Customer Insights. Puede elegir campos opcionales adicionales para datos coincidentes. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Braze, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Braze cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.