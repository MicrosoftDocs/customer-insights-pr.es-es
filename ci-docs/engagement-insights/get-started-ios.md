---
title: Introducción al SDK de iOS
description: Aprenda a personalizar y ejecutar el SDK de iOS
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226236"
---
# <a name="get-started-with-the-ios-sdk"></a>Introducción al SDK de iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este tutorial le guiará a través del proceso de instrumentación de la aplicación del SDK de iOS con el SDK de conclusiones sobre la interacción de Dynamics 365 Customer Insights. Comenzará a ver eventos en su portal en cinco minutos o antes.

## <a name="configuration-options"></a>Opciones de configuración

Las siguientes opciones de configuración se pueden pasar al SDK a través de el archivo `EIConfig.plist`:

- **ingestionKey**: la clave de ingesta se utiliza para enviar eventos en su proyecto.
- **autocollectAction**: un valor booleano para habilitar o deshabilitar la instrumentación automática del evento de acción.
- **autocollectView**: un valor booleano para habilitar o deshabilitar la instrumentación automática del evento de vista.
- **endpointUrl**: la dirección URL del extremo donde se dirigirán los eventos.

## <a name="prerequisites"></a>Requisitos previos

- Xcode versión 9 y posteriores
- iOS versión 8.2 y posteriores
- Una clave de ingesta (consulte a continuación las instrucciones sobre cómo obtenerla)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar el SDK en la aplicación

Comience el proceso seleccionando un área de trabajo donde trabajar, seleccionando la plataforma móvil de iOS y descargando el SDK.

- Utilice el conmutador de área de trabajo en el panel de navegación izquierdo para seleccionar su área de trabajo.

- Si no tiene un espacio de trabajo existente, seleccione **Nuevo espacio de trabajo** y siga los pasos para crear un [área de trabajo nueva](create-workspace.md).

- Después de crear un área de trabajo, vaya a **Administrador** > **Espacio de trabajo** y luego seleccione **Guía de instalación**.

## <a name="configure-the-sdk"></a>Configurar el SDK

Una vez que descargue el SDK, puede trabajar con él en Xcode para habilitar y definir eventos. Hay dos formas de hacerlo

### <a name="option-1-using-cocoapods-recommended"></a>Opción 1: usar CocoaPods (recomendado)
CocoaPods es un administrador de dependencias para proyectos Swift y Objective-C Cocoa. Su uso facilita la integración del SDK de conocimientos de interacción para iOS. CocoaPods también le permite actualizar a la última versión del SDK de información sobre la involucración. He aquí cómo usar CocoaPods para integrar el SDK de conocimientos de involucración en su proyecto de Xcode. 

1. Instale CocoaPods. 

1. Cree un nuevo archivo llamado Podfile dentro del directorio raíz de su proyecto y agregue las siguientes declaraciones. Reemplace YOUR_TARGET_PROJECT_NAME con el nombre de su proyecto de Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
La configuración de pod anterior contiene las versiones de depuración y de lanzamiento del SDK. Elija el que sea mejor para su proyecto.

1. Instale el pod ejecutando el siguiente comando: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Opción 2: usar el enlace de descarga

1. Descargue el [SDK de iOS con las conclusiones sobre la interacción ](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) y coloque el archivo `EIObjC.xcframework` en la carpeta `Frameworks`.

1. Si una carpeta de `Frameworks` no existe, cree una en la carpeta del proyecto.

## <a name="enable-auto-instrumentation"></a>Habilitar la instrumentación automática
 
Puede habilitar fácilmente la instrumentación automática sin codificación. Cuando el proyecto se ejecuta, rastreará automáticamente los eventos `view` y `action` usando la clave de ingesta configurada. 

1. Actualice e incluya el archivo `EIConfig.plist` proporcionado en la carpeta del directorio del proyecto para los siguientes campos:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = SÍ
    - autocollectAction = SÍ

2. Luego agregue el archivo `EIConfig.plist` a su proyecto en Xcode. 



Para deshabilitar la instrumentación automática, actualice los siguientes campos en el archivo `EIConfig.plist` en la carpeta del directorio del proyecto. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementar eventos personalizados

1. Abra el proyecto en Xcode y vaya a configuración **General**. 
1. Agregue `EIObjC.xcframework` al proyecto en la sección "Marcos de trabajo, bibliotecas y contenido incrustado".

1. Importe el archivo de encabezado del marco de trabajo en AppDelegate.m con el siguiente fragmento de código:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicializar el SDK con los conocimientos sobre la interactuación desde la aplicación: didFinishLaunchingWithOptions.
1. Copie el fragmento de código de XML de la **Guía de instalación**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Realizar seguimiento de un evento:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Configurar los detalles de usuario para su evento

El SDK le permite definir la información del usuario que se puede enviar con cada evento. Puede especificar la información del usuario llamando a la API `setUser:(nonnull EIUser *)user` en el SDK.

Especificar los detalles del usuario en el nivel `Analytics` significa que todas las telemetrías tendrán esta información. Sin embargo, si especifica en el nivel de evento llamando a la API `setUser:(nonnull EIUser *)user` en el objeto EIEvent, solo ese evento específico contendrá la información.

La clase de datos `EIUser` contiene las siguientes propiedades de NSString:

- **localId**: Id. local del usuario.
- **authId**: Id. de usuario autenticado.
- **authType**: el tipo de autenticación utilizado para obtener el Id. de usuario autenticado.
- **nombre**: el nombre del usuario.
- **correo electrónico**: la dirección de correo electrónico del usuario.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
