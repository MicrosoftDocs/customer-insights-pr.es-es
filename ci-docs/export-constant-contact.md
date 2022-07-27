---
title: Exportar segmentos a Constant Contact (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fe9706a7cd0755412ee18c4b974684bb9aa3f8d3
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081794"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segmentos a Constant Contact (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Constant Contact y utilícelos para actividades de marketing. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de Constant Contact](https://www.constantcontact.com/account-home) y las credenciales de administrador correspondientes.
-   Tiene [Segmentos configurados](segments.md) en Customer Insights.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 1 millón de perfiles de clientes por exportación a Constant Contact.
- La exportación a Constant Contact está limitada a segmentos.
- La exportación de hasta 1 millón de perfiles de clientes a Constant Contact puede tardar hasta 1 hora en completarse. 
- La cantidad de perfiles de clientes que puede exportar a Constant Contact depende y está limitada por su contrato con Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Configurar la conexión a Constant Contact

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Constant Contact** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Constant Contact.

1. Seleccione **Autenticar con Constant Contact** y proporcione sus credenciales de administrador de Constant Contact. 

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión en la sección Constant Contact. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Escriba su [**identificador de la lista de Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Abra una lista en Constant Contact para encontrar el identificador de la lista en la dirección URL.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a Constant Contact.

1. Opcionalmente, puede exporta Nombre de pila y Apellido como campos adicionales para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Constant Contact, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Constant Contact cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
