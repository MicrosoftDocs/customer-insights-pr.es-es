---
title: Ejemplo de SDK de Android
description: Proyecto de ejemplo para conocer saber más sobre el SDK de Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035847"
---
# <a name="run-the-android-sdk-sample"></a>Ejecutar el ejemplo del SDK de Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este proyecto ejemplo de Android le ayuda a comprender cómo funciona el SDK en una aplicación. No tendrá que escribir código. Simplemente agregue su clave de ingesta y podrá ver los eventos en su espacio de trabajo de inmediato.

## <a name="prerequisites"></a>Requisitos previos

- [Android Studio](https://developer.android.com/studio)
- [Clave de ingesta](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Descargar el ejemplo del SDK de Android.

1. [Descargar el ejemplo del SDK de Android con información sobre la interactuación](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Descomprima el archivo comprimido `ei-android-sample.zip`.
1. Abra la carpeta sin comprimir en Android Studio.
1. En el archivo `AndroidManifest.xml`, sustituya la cadena `"Your-Ingestion-Key"` con su clave de ingesta del área de trabajo de la información de interactuación en **Administrador** > **Área de trabajo** > **Guía de instalación**. 

   > [!NOTE]
   > No es necesario sustituir la sección `${applicationId}`. Se completa automáticamente.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Seleccione **Ejecutar** para iniciar el proyecto de ejemplo.
1. Vea los eventos en su área de trabajo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
