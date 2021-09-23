---
title: Introducción al SDK de Android
description: Aprenda a personalizar y ejecutar el SDK de Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494296"
---
# <a name="get-started-with-the-android-sdk"></a>Introducción al SDK de Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este tutorial le guiará a través del proceso de instrumentación de la aplicación del SDK de Android con el SDK de conclusiones sobre la interacción de Dynamics 365 Customer Insights. Comenzará a ver eventos en su portal en cinco minutos o antes.

## <a name="configuration-options"></a>Opciones de configuración
Las siguientes opciones de configuración se pueden pasar al SDK:

- **ingestionKey**: la clave de ingesta se utiliza para enviar eventos en su área de trabajo.

## <a name="prerequisites"></a>Requisitos previos

- Android Studio

- Nivel de API mínimo de Android: 16 (Jelly Bean)

- Una clave de ingesta (consulte a continuación las instrucciones sobre cómo obtenerla)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar el SDK en la aplicación
Comience el proceso seleccionando un espacio de trabajo, seleccionando la plataforma móvil de Androidy descargando el SDK de Android.

- Utilice el conmutador de área de trabajo en el panel de navegación izquierdo para seleccionar su área de trabajo.

- Si no tiene un espacio de trabajo existente, seleccione **Nuevo espacio de trabajo** y siga los pasos para crear un [área de trabajo nueva](create-workspace.md).

- Después de crear un área de trabajo, vaya a **Administrador** > **Espacio de trabajo** y luego seleccione **Guía de instalación**. 

## <a name="configure-the-sdk"></a>Configurar el SDK

Una vez que descargue el SDK, puede trabajar con él en Android Studio para habilitar y definir eventos. Hay dos formas de hacerlo:
### <a name="option-1-using-jitpack-recommended"></a>Opción 1: usar JitPack (recomendado)
1. Agregue el repositorio de JitPack a su raíz `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Agregue la dependencia:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Opción 2: usar el enlace de descarga
1. Descargar el [SDK de Android con las conclusiones sobre la interacción](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) y coloque el archivo `eiandroidsdk-debug.aar` en la carpeta `libs`.

1. Abra el archivo `build.gradle` de nivel de proyecto y agregue los siguientes fragmentos de código:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Agregue permiso para la red e Internet en su archivo `AndroidManifest.xml` ubicado en la carpeta `manifests`. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Configure la configuración del SDK de conocimientos sobre la interacción a través del archivo ubicado en la carpeta `AndroidManifest.xml`. 

## <a name="enable-auto-instrumentation"></a>Habilitar la instrumentación automática
1. Copie el fragmento de código de XML de la **Guía de instalación**. `Your-Ingestion-Key` deberá rellenarse automáticamente.

   > [!NOTE]
   > No es necesario sustituir la sección `${applicationId}`. Se completa automáticamente.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Habilite o deshabilite la captura automática de `View` eventos estableciendo el campo `autoCapture` anterior en `true` o `false`. En la actualidad, los eventos `Action` deben agregarse manualmente.

1. (Opcional) Otras configuraciones incluyen configurar la dirección URL del recopilador del extremo. Se pueden agregar en de los metadatos de la clave de ingesta en `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Implementar eventos personalizados

Después de inicializar el SDK, puede trabajar con eventos y sus propiedades en el entorno `MainActivity`.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Establecer propiedad para todos los eventos (opcional)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Los siguientes tipos son compatibles con las propiedades de eventos de contexto:
- String
- Fecha
- Doble
- Largo
- Booleana
- UUID

### <a name="track-an-event"></a>Realizar seguimiento de un evento

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Configurar los detalles de usuario para su evento (opcional)

El SDK le permite definir la información del usuario que se puede enviar con cada evento. Puede especificar la información del usuario llamando a la API `setUser(user: User)` en el nivel de `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

La clase de datos `User` contiene las siguientes propiedades de cadena:

- **localId**: Id. local del usuario.
- **authId**: Id. de usuario autenticado.
- **Tipo de autenticación**: el tipo de autenticación utilizado para obtener el ID de usuario autenticado.
- **nombre**: el nombre del usuario.
- **correo electrónico**: la dirección de correo electrónico del usuario.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
