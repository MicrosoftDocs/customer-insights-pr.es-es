---
title: Exportar segmentos a ActiveCampaign
description: Aprenda a configurar la conexión y exportar a ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: eb6f2bb69bb30c319e17390562b3f33512f33ff1
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054729"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportar segmentos a ActiveCampaign (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a ActiveCampaign y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

- Tiene una [cuenta de ActiveCampaign](https://www.activecampaign.com/) y las credenciales de administrador correspondientes.
- Tiene [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo con una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 1 millón de perfiles de clientes por exportación a ActiveCampaign y puede tardar hasta 90 minutos en completarse.
- La exportación a ActiveCampaign está limitada a segmentos.
- La cantidad de perfiles de clientes que puede exportar a ActiveCampaign depende de su contrato con ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Configurar la conexión a ActiveCampaign

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **ActiveCampaign** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique su [cave de API ActiveCampaign y nombre de host del punto de conexión de REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). El nombre de host del punto de conexión REST es solo el nombre de host, sin https://. 

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a ActiveCampaign.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar una exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección ActiveCampaign. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Indique su [**Id. de lista de ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a ActiveCampaign. Opcionalmente, puede exportar Nombre de pila, Apellido, y Teléfono para crear correos electrónicos más personalizados. Seleccione Agregar atributo para asignar estos campos.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilite Dynamics 365 Customer Insights para transmitir datos a ActiveCampaign, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que ActiveCampaign cumple las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
