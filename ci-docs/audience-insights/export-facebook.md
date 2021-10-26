---
title: Exportar datos de Customer Insights al Administrador de anuncios de Facebook
description: Aprenda a configurar la conexión y a exportar a el administrador de anuncios de Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4403c6f535f5dc60919be3717073d52640bbe61a
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619232"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Exportar lista de segmentos al administrador de anuncios de Facebook (versión preliminar)

Exportar segmentos de perfiles de clientes unificados a Administrador de anuncios de Facebook para crear campañas en Facebook e Instagram.

## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

- Debe tener una [**Cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)que incluya una [**Cuenta empresarial de Facebook**](https://business.facebook.com/).
- Debe ser un administrador en la [**Cuenta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 10 millones de perfiles de clientes por exportación al administrador de anuncios de Facebook.
- La exportación al administrador de anuncios de Facebook está limitada a segmentos.
- Cree o actualice audiencias personalizadas en Facebook solo de tipo *lista de clientes*.
- La exportación de segmentos con un total de 10 millones de perfiles de clientes puede tardar hasta 90 minutos en completarse.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar una conexión al administrador de anuncios de Facebook

Antes de que los usuarios puedan crear una exportación, un administrador debe configurar la conexión al servicio y permitir que los colaboradores usen la conexión.

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Administrador de anuncios de Facebook** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticación con anuncios de Facebook: 

   1. Seleccione **Continuar con Facebook** para iniciar sesión en su cuenta de Facebook.

   1. Autorizar el permiso **ads_management** después de autenticarse con Facebook.

   1. Seleccione la **Cuenta de anuncios de Facebook** con la que desea trabajar.

   1. Seleccione una **Público personalizado existente** en la lista desplegable o cree un **Nuevo público personalizado**. Para más información, vea [**Audiencias en Administrador de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Solo puede crear o actualizar audiencias personalizadas en Facebook del tipo *lista de clientes* con esta exportación. En algunos casos, verá públicos personalizadas de diferentes tipos en la lista desplegable. Si selecciona un tipo diferente a la *lista de clientes*, dará como resultado una exportación fallida. 

1. Revise **Privacidad y cumplimiento de datos** y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**. 

1. En el campo **Conexión para exportación**, elija una conexión en la sección **Administrador de anuncios de Facebook**. Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.

1. En **Elija su campo de identificador de clave**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar a Administrador de anuncios de Facebook. 

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.

1. Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.
   > [!TIP]
   > Las mejores posibilidades para que se produzca una coincidencia es seleccionar **Correo electrónico** como identificador clave Agregar identificadores adicionales puede mejorar la coincidencia.

1. Seleccione **Agregar atributo** para asignar más atributos para enviar al administrador de anuncios de Facebook. Los atributos de Administrador de anuncios de Facebook se asignan a los siguientes nombres descriptivos: **FN** = **Nombre**, **LN** = **Apellidos**, **FI** = **Primera inicial**, **PHONE** = **Teléfono**, **GEN** = **Género**, **DOB** = **Fecha de nacimiento**, **ST** = **Estado**, **CT** = **Ciudad**, **ZIP** = **Código postal**, **COUNTRY** = **País / Región**

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). 

Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos al Administrador de anuncios de Facebook, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los anuncios de Facebook cumplan con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
