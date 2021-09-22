---
title: Escenarios SDK web avanzados
description: Escenarios avanzados que hay que tener en cuenta durante la instrumentación de su sitio web con un SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036349"
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
    
El siguiente ejemplo muestra un fragmento de código que envía información del usuario. Allá donde vea Functions indicadas por *, sustitúyalas por su implementación de llamada a esos valores:  

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

También puede especificar la información del usuario llamando a la API `setUser(user: IUser)` en el SDK. La telemetría enviada después de llamar a `setUser API` contendrá la información del usuario.

## <a name="adding-custom-properties-for-each-event"></a>Agregar propiedades personalizadas para cada evento

El SDK le permite especificar las propiedades personalizadas que se pueden enviar con cada evento. Puede especificar las propiedades personalizadas como un objeto que contiene pares clave-valor (el valor puede ser de tipo `string | number | boolean`). El objeto se puede agregar en una propiedad llamada `props`, similar a `src`, `name` y `cfg` en la configuración del fragmento de código. 

El siguiente ejemplo muestra un fragmento de código que envía propiedades personalizadas:

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
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

También puede especificar propiedades personalizadas individualmente llamando a la API `setProperty(name: string, value: string | number | boolean)` en el SDK.

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