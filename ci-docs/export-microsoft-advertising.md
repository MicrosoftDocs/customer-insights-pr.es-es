---
title: Exportar datos de Customer Insights a Microsoft Advertising
description: Aprenda a configurar la conexión y a exportar a Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14479e915dd6ae76e018b59bee5980a600bb222d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647989"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos a Microsoft Advertising (versión preliminar)

Exporte segmentos de Customer Insights a Microsoft Advertising para crear audiencias de Customer Match. Utilice estas audiencias para sus campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

-   Una [cuenta de Microsoft Advertising](https://ads.microsoft.com/) y las credenciales de administrador correspondientes.
-   Ha aceptado las condiciones de uso de Customer Match. 
-   [Segmentos configurados](segments.md) en Customer Insights.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo con una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 500.000 perfiles de clientes por exportación a Microsoft Advertising.
- La exportación a Microsoft Advertising está limitada a segmentos.
- La exportación de hasta 500.000 perfiles de clientes a Microsoft Advertising puede tardar hasta 10 minutos en completarse. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configurar la conexión a Microsoft Advertising

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Microsoft Advertising** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. El valor predeterminado es administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Microsoft Advertising.

1. Seleccione **Autenticar con Microsoft Advertising** y proporcione sus credenciales de administrador para Microsoft Advertising.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Microsoft Advertising. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Seleccione los segmentos que desea exportar. Las audiencias de Customer Match en Microsoft Advertising se crean automáticamente con el nombre de los segmentos seleccionados para exportar. Cada segmento dará como resultado una audiencia diferente de Customer Match. 

1. Introduzca su **Id. de cliente e Id. de cuenta de Microsoft Advertising**. Puede encontrar el Id. de cliente (`cid`) e Id. de cuenta (`aid`) en los parámetros de la URL cuando inicie sesión en Microsoft Advertising.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo con la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a Microsoft Advertising.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Microsoft Advertising, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Microsoft Advertising cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para detener esta funcionalidad.
