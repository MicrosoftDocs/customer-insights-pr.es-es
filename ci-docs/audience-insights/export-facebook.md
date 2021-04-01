---
title: Exportar datos de Customer Insights al Administrador de anuncios de Facebook
description: Aprenda a configurar la conexión al Administrador de anuncios de Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596704"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Conector para Administrador de anuncios de Facebook (vista previa)

Exportar segmentos de perfiles de clientes unificados a Administrador de anuncios de Facebook para crear campañas en Facebook e Instagram.

## <a name="prerequisites"></a>Requisitos previos

- Necesita tener una [**cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que incluya una [**cuenta de negocios de Facebook**](https://business.facebook.com/).
- Debe ser administrador en la [**Cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Conectar a Administrador de anuncios de Facebook

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **Administrador de anuncios de Facebook**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

1. Seleccione **Continuar con Facebook** para iniciar sesión en su Cuenta de anuncios de Facebook.

1. Autorizar el permiso **ads_management** después de autenticarse con Facebook.

1. Seleccione la **Cuenta de anuncios de Facebook** con la que desea trabajar.

1. Seleccione un **Audiencia personalizado existente** de la lista desplegable o cree una **Nueva audiencia personalizada**. Para más información, vea [**Audiencias en Administrador de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Siguiente** para configurar la exportación.

## <a name="configure-the-connector"></a>Configurar el conector

1. En **Elija su campo de identificador de clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar a Administrador de anuncios de Facebook.

1. Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.
   > [SUGERENCIA] Las mejores posibilidades para que se produzca una coincidencia es seleccionar **Correo electrónico** como identificador clave Agregar identificadores adicionales puede mejorar la coincidencia.

1. Seleccione **Agregar atributo** para asignar atributos adicionales para enviar a Administrador de anuncios de Facebook. Los atributos de Administrador de anuncios de Facebook se asignan a los siguientes nombres descriptivos: **FN** = **Nombre**, **LN** = **Apellidos**, **FI** = **Primera inicial**, **PHONE** = **Teléfono**, **GEN** = **Género**, **DOB** = **Fecha de nacimiento**, **ST** = **Estado**, **CT** = **Ciudad**, **ZIP** = **Código postal**, **COUNTRY** = **País / Región**

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 10 millones de perfiles de cliente por exportación al administrador de Facebook Ads 
- La exportación al administrador de Facebook Ads está limitada a segmentos.
- La exportación de segmentos con un total de 10 millón de perfiles puede tardar hasta 90 horas en completarse.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos al Administrador de anuncios de Facebook, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Facebook cumplan con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]