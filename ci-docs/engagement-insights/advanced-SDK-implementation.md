---
title: Escenarios SDK web avanzados
description: Escenarios avanzados que hay que tener en cuenta durante la instrumentación de su sitio web con un SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227219"
---
# <a name="advanced-web-sdk-instrumentation"></a>Instrumentación avanzada web SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artículo le guiará a través de los escenarios avanzados que debe tener en cuenta a la hora de [instrumentar su sitio web](instrument-website.md) con un SDK Dynamics 365 Customer Insights de funcionalidad de conclusiones sobre la interacción.

## <a name="setting-user-details-for-your-event"></a>Configurar los detalles de usuario para su evento

El SDK le permite definir la información del usuario que se puede enviar con cada evento. Puede especificar los detalles del usuario en una propiedad llamada `user` (los datos esperados para esta propiedad son el objeto `IUser`), similar a `src`, `name` y `cfg` en la configuración del fragmento de código.

El objeto `IUser` contiene las siguientes propiedades de cadena:

- **localId**: Id. local del usuario.
- **authId**: Id. de usuario autenticado.
- **authType**: el tipo de autenticación utilizado para obtener el Id. de usuario autenticado.
- **nombre**: el nombre del usuario.
- **correo electrónico**: la dirección de correo electrónico del usuario.

El siguiente ejemplo muestra un fragmento de código que envía información del usuario. Cuando vea funciones precedidas por un símbolo de asterisco *, reemplace la función con su implementación personalizada:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

También puede especificar la información del usuario llamando a la API `setUser(user: IUser)`. La telemetría enviada después de llamar a la API `setUser` contendrá la información del usuario.

## <a name="adding-custom-properties-for-each-event"></a>Agregar propiedades personalizadas para cada evento

El SDK le permite especificar las propiedades personalizadas que se pueden enviar con cada evento. Puede especificar las propiedades personalizadas como un objeto que contiene pares clave-valor (el valor puede ser de tipo `string | number | boolean`). Puede agregar el objeto en una propiedad llamada `props`, similar a `src`, `name`, y `cfg` en la configuración del código fragmento de código.

El siguiente ejemplo muestra un fragmento de código que envía propiedades personalizadas:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

También puede especificar propiedades personalizadas individualmente llamando a la API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Enviar eventos personalizados

Puede utilizar el SDK para enviar eventos personalizados. Debe especificar un nombre para el evento y las propiedades que se enviarán con el evento.

El siguiente ejemplo muestra un fragmento de código que realiza un seguimiento del evento personalizado. "NAME" es el valor en la clave `name` en la configuración del fragmento de código. También es el nombre de la variable en el objeto de la ventana donde se carga el SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
