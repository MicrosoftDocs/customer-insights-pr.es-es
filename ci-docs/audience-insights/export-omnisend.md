---
title: Exportar datos de Customer Insights a Omnisend
description: Aprenda a configurar la conexión y a exportar a Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5496efa075fa3474c579366d143ea55e86ec3995
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619049"
---
# <a name="export-segments-to-omnisend-preview"></a>Exportar segmentos a Omnisend (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Omnisend y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de Omnisend](https://www.omnisend.com/) y las credenciales de administrador correspondientes.
-   Tiene [segmentos configurados](segments.md) en la información de público.
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Puede exportar hasta 1 millón de perfiles de clientes por exportación a Omnisend y puede tardar hasta 4 horas en completarse.
- La exportación a Omnisend está limitada a segmentos.
- La cantidad de perfiles de clientes que puede exportar a Omnisend depende de su contrato con Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Configurar conexión a Omnisend

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Omnisend** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introzuca su [Clave de API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectar** para inicializar la conexión a Omnisend.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Omnisend. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. Es obligatorio exportar segmentos a Omnisend. Opcionalmente, puede exportar el Nombre de pila, el Apellido, Dirección la Ciudad, el Estado, Código postal y el País para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Omnisend, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Omnisend cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
