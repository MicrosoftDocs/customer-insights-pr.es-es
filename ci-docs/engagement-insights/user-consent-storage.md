---
title: Gestionar las cookies y el consentimiento del usuario para almacenar datos del usuario.
description: Comprenda cómo se utilizan las cookies y el consentimiento del usuario para identificar a los visitantes del sitio web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036759"
---
# <a name="manage-cookies-and-user-consent"></a>Gestionar cookies y consentimiento del usuario

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights de funcionalidades de conclusiones sobre la interacción utiliza cookies y almacenamiento local (`localStorage`) para identificar a los visitantes del sitio web.

Las cookies son pequeños archivos que almacenan bits de información sobre las interacciones de un usuario con el sitio web. Se almacenan en navegadores web. Cuando los usuarios visitan un sitio web para el que sus usuarios han almacenado cookies, el navegador envía esa información al servidor, que devuelve información que es única para el usuario. Esta es la tecnología que permite, por ejemplo, que un carrito de compras en línea mantenga los artículos seleccionados en él incluso si un usuario sale del sitio web.

## <a name="user-consent"></a>Consentimiento del usuario

El [Reglamento general de protección de datos (RGPD)](/dynamics365/get-started/gdpr/) es una regulación de la Unión Europea (UE) que define cómo las organizaciones deben gestionar la privacidad y seguridad de sus usuarios. Las cookies a menudo almacenan o recopilan "datos personales", como un identificador en línea, que está cubierto por el RGPD. Si su empresa emplea o vende a sujetos de datos de la UE, el RGPD se aplica. [Obtenga más información sobre cómo Microsoft puede ayudarle a cumplir con el RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Para permitir que el SDK de conclusiones sobre la interacción almacene cookies u otra información confidencial, debe especificar si sus usuarios han dado su consentimiento. Esto ocurre en la inicialización del SDK.

Si indica que no hay consentimiento del usuario, el SDK no almacenará ningún dato y no enviará eventos que puedan usarse para rastrear el comportamiento del usuario. Todos los datos almacenados previamente se eliminarán del navegador.

Si no se especifica ningún valor de consentimiento del usuario, el SDK asumirá que el usuario ha dado su consentimiento. Esto significa que si usted (como nuestro cliente) no especifica un valor para el consentimiento del usuario en el SDK, se recopilarán datos. Sin embargo, si especifica que el valor del consentimiento del usuario debe ser "verdadero", los datos no se recopilarán si un usuario se niega o no brinda su consentimiento explícito.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Almacenamiento de datos de visitantes en la funcionalidad de conclusiones sobre la interacción

### <a name="cookies"></a>Galletas

- _msei
    - Almacena el Id. de usuario anónimo. Esta cookie se establece en el dominio del cliente y caduca en 365 días.

### <a name="local-storage"></a>Almacenamiento local

La funcionalidad de conclusiones sobre la interacción también hace uso del almacenamiento local (`localStorage`) para rastrear datos no confidenciales. Estos datos se almacenan completamente en el propio navegador, sin tráfico enviado hacia o desde sus servidores.

- *EISession.Id* 
    - Almacena información sobre la sesión de usuario en curso, como el Id. de la sesión, cuándo se inició y cuándo caduca.
- *EISession.Previous*
    - Almacena la URL de la página visitada anteriormente en la sesión actual.
    
Las claves del almacenamiento local no caducan automáticamente. El SDK los restablecerá durante la próxima sesión.

## <a name="deleting-cookies"></a>Eliminar cookies

Sus clientes pueden eliminar manualmente las cookies y las claves de almacenamiento local en cualquier momento a través de la configuración de sus navegadores.


[!INCLUDE[footer-include](../includes/footer-banner.md)]