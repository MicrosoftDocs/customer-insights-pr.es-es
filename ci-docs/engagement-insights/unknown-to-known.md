---
title: Reconocer eventos web de visitantes previamente autenticados mediante la característica de desconocido a conocido
description: La característica de desconocido a conocido permite asociar eventos en un sitio web con visitantes que se autenticaron previamente.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230701"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Reconocer eventos web de visitantes previamente autenticados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La característica **Desconocido a conocido** de la funcionalidad de conclusiones sobre la interacción permite asociar eventos en un sitio web con visitantes que se autenticaron previamente. Si la característica está deshabilitada, los visitantes que se autenticaron durante una visita anterior y luego se fueron no se identificarán si no se vuelven a autenticar al volver. 

Por ejemplo, una persona visitó un sitio web la semana pasada, inició sesión en su cuenta de usuario en el sitio y examinó el catálogo de productos. La persona vuelve la semana siguiente para buscar más productos sin iniciar sesión en su cuenta. El propietario del sitio que utiliza la característica **Desconocido a conocido** sabría que la misma persona había vuelto y lo que había hecho en el sitio. Esto permite crear informes y análisis más precisos de las actividades del sitio web.

## <a name="enable-unknown-to-known"></a>Habilitar Desconocido a conocido

Debe ser un [administrador del área de trabajo](user-roles.md) para poder habilitar esta característica. 

1. En conclusiones sobre interacción, vaya a **Administración** > **Área de trabajo**. 
2. Seleccione la pestaña **Configuración**.
3. En la sección **Desconocido a conocido**, establezca el control de alternancia en **Habilitada**.

![Habilitar Desconocido a conocido](media/U2Ktoggle.png "Habilitar Desconocido a conocido")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Agregar código JavaScript al fragmento de código de seguimiento del sitio

Un sitio web puede capturar **user authId** con el siguiente ejemplo de JavaScript mediante el [SDK web de conclusiones sobre la interacción](advanced-SDK-implementation.md). Para que la característica **Desconocido a conocido** funcione, debe capturar authId *y* habilitar userMapping:True en el fragmento de código JavaScript, como en el ejemplo siguiente.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
