---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar la conexión a Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570424"
---
# <a name="connector-for-marketo-preview"></a>Conector para Marketo (versión preliminar)

Exporte segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y usar grupos específicos de clientes con Marketo.

## <a name="prerequisites"></a>Requisitos previos

-   Tiene una [cuenta de Marketo](https://login.marketo.com/) y las credenciales de administrador correspondientes.
-   Hay listas existentes en Marketo y los id. correspondientes. Para obtener más información, consulte las [listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Ha [configurado los segmentos](segments.md).
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="connect-to-marketo"></a>Conectar a Marketo

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **Marketo**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

1. Introduzca su **[Id. de cliente de Marketo, secreto de cliente y nombre de host de punto de conexión REST](https://developers.marketo.com/rest-api/authentication/)**.

1. introduzca su **[ID de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Seleccione **Estoy de acuerdo** para confirmar la **Privacidad y cumplimiento de datos** y seleccione **Conectar** para inicializar la conexión a Marketo.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Exportar la captura de pantalla para conexión de Marketo":::

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo en su perfil de cliente unificado que representa la dirección de correo electrónico de un cliente. 

1. Opcionalmente, puede exportar **Nombre de pila**, **Apellido**, **Ciudad**, **Estado** y **País/Región** como campos adicionales para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar. Puede exportar hasta 1 millón de perfiles de clientes en total a Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Seleccionar campos y segmentos para exportar a Marketo":::

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab). En Marketo, ahora puede encontrar sus segmentos en [Listas de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles por exportación a Marketo.
- La exportación a Marketo está limitada a segmentos.
- La exportación de segmentos con un total de 1 millón de perfiles puede tardar hasta 3 horas. 
- La cantidad de perfiles que puede exportar a Marketo depende y está limitada a su contrato con Marketo.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Marketo cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
