---
title: Ejecutar el ejemplo del SDK de iOS
description: Proyecto de ejemplo para conocer saber más sobre el SDK de iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036849"
---
# <a name="run-the-ios-sdk-sample"></a>Ejecutar el ejemplo del SDK de iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este proyecto ejemplo de iOS le ayuda a comprender cómo funciona el SDK en una aplicación. No tendrá que escribir código. Simplemente agregue su clave de ingesta y podrá ver los eventos en su espacio de trabajo de inmediato.

## <a name="prerequisites"></a>Requisitos previos

- [Xcode versión 9 y posteriores](https://developer.apple.com/xcode/downloads/)
- [Clave de ingesta](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Descargar el ejemplo del SDK de iOS.

1. [Descargar el ejemplo del SDK de iOS con información sobre la interactuación](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Descomprima el archivo comprimido `ei-ios-sample.zip`.
1. Abra el proyecto de la aplicación de muestra en Xcode.
1. En el archivo `EIConfig.plist`, sustituya la cadena `“YOUR-INGESTION-KEY”` en el campo `ingestionKey` con su clave de ingesta del área de trabajo de los conocimientos sobre la interactuación en **Administrador** > **Área de trabajo** > **Guía de instalación**.
1. Seleccione **Ejecutar** para iniciar el proyecto de ejemplo.
1. Vea los eventos en su área de trabajo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
