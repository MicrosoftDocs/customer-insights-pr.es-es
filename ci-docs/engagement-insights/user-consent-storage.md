---
title: Administrar las cookies y el consentimiento del usuario para almacenar datos del usuario en Dynamics 365 Customer Insights
description: Comprenda cómo se utilizan las cookies y el consentimiento del usuario para identificar a los visitantes del sitio web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229006"
---
# <a name="manage-cookies-and-user-consent"></a>Gestionar cookies y consentimiento del usuario

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La capacidad de información sobre el compromiso Dynamics 365 Customer Insights utiliza cookies y claves (`localStorage`) para identificar a los visitantes del sitio web.

Las cookies son pequeños archivos que almacenan bits de información sobre las interacciones de un usuario con el sitio web. Se almacenan en navegadores web. Cuando los usuarios visitan un sitio web para el que sus usuarios han almacenado cookies, el navegador envía esa información al servidor, que devuelve información que es única para el usuario. Esta es la tecnología que permite, por ejemplo, que un carrito de compras en línea mantenga los artículos seleccionados en él incluso si un usuario sale del sitio web.

## <a name="user-consent"></a>Consentimiento del usuario

El [Reglamento general de protección de datos (RGPD)](/dynamics365/get-started/gdpr/) es una regulación de la Unión Europea (UE) que define cómo las organizaciones deben gestionar la privacidad y seguridad de sus usuarios. Las cookies a menudo almacenan o recopilan "datos personales", como un identificador en línea, que está cubierto por el RGPD. Si su empresa emplea o vende a sujetos de datos de la UE, el RGPD se aplica. [Obtenga más información sobre cómo Microsoft puede ayudarle a cumplir con el RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Para permitir que el SDK de conclusiones sobre la interacción almacene cookies u otra información confidencial, debe especificar si sus usuarios han dado su consentimiento. Esto ocurre en la inicialización del SDK al establecer un campo `userConsent` en la configuración.

Si indica que no hay consentimiento del usuario, el SDK no almacenará ningún dato y no enviará eventos que puedan usarse para rastrear el comportamiento del usuario. Todos los datos almacenados previamente se eliminarán del navegador.

Si no se especifica ningún valor de consentimiento del usuario, el SDK asumirá que el usuario ha dado su consentimiento. Esto significa que si usted (como nuestro cliente) no especifica un valor para el consentimiento del usuario en el SDK, se recopilarán datos. Sin embargo, si especifica que el valor del consentimiento del usuario debe ser "verdadero", los datos no se recopilarán si un usuario se niega o no brinda su consentimiento explícito.

A continuación se muestra un código fragmento de código para inicializar el SDK web con el consentimiento del usuario:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Almacenamiento de datos de visitantes en la funcionalidad de conclusiones sobre la interacción

### <a name="cookies"></a>Galletas

- _msei
    - Almacena el Id. de usuario anónimo. Esta cookie se establece en el dominio del cliente y caduca en 365 días.

### <a name="local-storage"></a>Almacenamiento local

La capacidad de información sobre el compromiso también hace uso de claves (`localStorage`) para rastrear datos no confidenciales. Estos datos se almacenan completamente en el propio navegador, sin tráfico enviado hacia o desde sus servidores.

- *EISession.Id*
    - Almacena información sobre la sesión de usuario en curso, como el Id. de la sesión, cuándo se inició y cuándo caduca.
- *EISession.Previous*
    - Almacena la URL de la página visitada anteriormente en la sesión actual.

Las claves en el almacenamiento local no caducan automáticamente y se restablecerán durante la próxima sesión del SDK.

## <a name="deleting-cookies"></a>Eliminar cookies

Sus clientes pueden eliminar manualmente las cookies y las claves de almacenamiento local en cualquier momento a través de la configuración de sus navegadores.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
