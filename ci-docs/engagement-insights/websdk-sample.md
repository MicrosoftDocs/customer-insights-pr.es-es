---
title: Ejecutar una muestra de SDK web
description: Aprenda a personalizar y ejecutar una muestra de SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225352"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Ejecute la muestra de SDK web para Dynamics 365 Customer Insights de funcionalidad de conclusiones sobre la interacción

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La biblioteca de SDK web de funcionalidad de conclusiones sobre la interacción es una biblioteca de JavaScript con código de muestra que puede utilizar en su sitio web.

## <a name="prerequisites"></a>Requisitos previos

- Instale [Visual Studio Code](https://code.visualstudio.com/).
- [Instale la extensión Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) en Visual Studio Code y familiarícese con cómo ejecutar Live Server.
- Debe tener un [área de trabajo de conclusiones sobre la interacción](create-workspace.md).

## <a name="run-sample"></a>Ejecutar muestra

1. [Descargar la muestra de SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descomprima el archivo comprimido `ei_websdk_sample.zip`.

1. Abra la carpeta descomprimida en Visual Studio Code.

1. Vaya al portal de conclusiones sobre la interacción de su área de trabajo. Seleccione **Administración** > **Área de trabajo** y luego **Guía de instalación**. Siga la primera opción y seleccione **Copiar código** para copiar el fragmento de código JavaScript.

1. En el archivo `ei_websdk_sample.html`, pegue el fragmento de código que acaba de copiar debajo de esta línea:

   - <- PEGUE EL FRAGMENTO DE CÓDIGO JAVASCRIPT DEL PORTAL DE CONCLUSIONES SOBRE LA INTERACCIÓN AQUÍ DEBAJO DE ESTA LÍNEA ->

1. Abre el archivo `ei_websdk_sample.html` usando Live Server en Visual Studio Code seleccionando **Poner en marcha** desde la barra de estado.

1. Al abrir la página, se debe enviar automáticamente un evento de visualización. Al hacer clic en cualquiera de los botones de la página, se enviarán eventos de acción. El botón de **Rastreo de eventos** también enviará eventos personalizados. Al seleccionar el botón **Ir a Bing**, se enviará un evento de acción antes de navegar al sitio web de Bing.

1. Observe los eventos que fluyen cuando navega a su área de trabajo. Esta área de trabajo está asociada con la clave de ingesta introducida en el paso 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
