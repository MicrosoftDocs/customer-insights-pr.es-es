---
title: Exportar segmentos a Criteo (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081905"
---
# <a name="export-segments-to-criteo-preview"></a>Exportar segmentos a Criteo (versión preliminar)

Exporte segmentos de perfiles de clientes unificados para generar campañas, proporcionar marketing por correo electrónico y utilizar grupos específicos de clientes con Criteo.

## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

-   Usted tiene una cuenta de [Criteo Dynamic Retargeting](https://www.criteo.com/login/) y las credenciales de Administrador correspondientes.
-   Ha [configurado los segmentos](segments.md).
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles de clientes por exportación a Criteo.
- La exportación a Criteo está limitada a segmentos.
- La exportación de segmentos con un total de 1 millones de perfiles de clientes puede tardar hasta 30 minutos. 
- La cantidad de perfiles de clientes que puede exportar a Criteo depende y está limitada por su contrato con Criteo.

## <a name="set-up-connection-to-criteo"></a>Configure la conexión a Criteo

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Criteo** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar la **Privacidad y cumplimiento de datos** y seleccione **Conectar** para inicializar la conexión a Criteo.

1. Seleccione **Autenticar con Criteo** y proporcione su nombre de usuario y credenciales de administrador para Criteo. 

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión desde la sección Criteo. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted. 

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. 

1. Opcionalmente, puede exportar el **Id. de anunciante** y **Nombre**

1. Seleccione los segmentos que desea exportar. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Criteo, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Criteo cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](includes/footer-banner.md)]
