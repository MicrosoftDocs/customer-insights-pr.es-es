---
title: Exportar segmentos a Facebook Administrador de anuncios (vista previa) (contiene video)
description: Aprenda a configurar la conexión y a exportar a el administrador de anuncios de Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724637"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportar segmentos a Facebook Administrador de anuncios (vista previa)

Exportar segmentos de perfiles de clientes unificados a Administrador de anuncios de Facebook para crear campañas en Facebook e Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Requisitos previos

- Una [Cuenta de anuncios de Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que incluya una [Cuenta empresarial de Facebook](https://business.facebook.com/).
- Privilegios de administrador en la [Cuenta de Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- El usuario que configura la conexión en Customer Insights debe aceptar los términos personalizados audiencia.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 10 millones de perfiles de clientes por exportación a Facebook Ads Manager, lo que puede tardar hasta 90 minutos.
- Solo segmentos.
- La integración de Facebook Ads no admite usuarios con más de 25 cuentas de anuncios.
- Escriba *lista de clientes* de Facebook en [públicos personalizados](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) solamente.
  > [!NOTE]
  > En algunos casos, podrían aparecer públicos personalizados de diferentes tipos en la lista desplegable. Si selecciona un tipo diferente de *lista de clientes*, la exportación tendrá errores.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar una conexión al administrador de anuncios de Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Facebook Ads Manager**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. [Permitir que los contribuyentes utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticación con anuncios de Facebook:

   1. Seleccione **Continuar con Facebook** para iniciar sesión en su cuenta de Facebook.

   1. Autorizar el permiso **ads_management** después de autenticarse con Facebook.

   1. Seleccione la **Cuenta de anuncios de Facebook** con la que desea trabajar.

   1. Seleccione una **Público personalizado existente** en la lista desplegable o cree un **Nuevo público personalizado**.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Facebook Ads Manager. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. En el campo **Datos de conexión**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar a Facebook Ads Manager.

1. Asigne los atributos correspondientes de su entidad de cliente unificado para el identificador clave seleccionado.
   > [!TIP]
   > Las mejores posibilidades para que se produzca una coincidencia es seleccionar **Correo electrónico** como identificador clave Agregar identificadores adicionales puede mejorar la coincidencia.

1. Seleccione **Agregar atributo** para asignar más atributos para enviar al administrador de anuncios de Facebook. Los atributos de Administrador de anuncios de Facebook se asignan a los siguientes nombres descriptivos: **FN** = **Nombre**, **LN** = **Apellidos**, **FI** = **Primera inicial**, **PHONE** = **Teléfono**, **GEN** = **Género**, **DOB** = **Fecha de nacimiento**, **ST** = **Estado**, **CT** = **Ciudad**, **ZIP** = **Código postal**, **COUNTRY** = **País / Región**

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
