---
title: Añadir código a su sitio web
description: Cómo agregar un fragmento de código para capturar eventos de Dynamics 365 Customer Insights en su sitio web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231055"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instalar el SDK web en un sitio web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artículo describe cómo un Administrador instala el kit de herramientas de desarrollo de software web (SDK) en un sitio web. Comenzará a ver eventos en su espacio de trabajo poco después de configurar su sitio web. Para obtener más información, consulte [Gestionar entornos y áreas de trabajo](manage-environments-workspaces.md). Para capturar eventos en aplicaciones móviles, consulte [Descripción general de los recursos para desarrolladores](developer-resources.md).


### <a name="prerequisites"></a>Requisitos previos

* Debe tener permisos de administrador para que el área de trabajo almacene los datos.
* Su sitio web o proyecto debe estar alojado en línea para enviar datos de actividad. El servidor no aceptará los datos enviados desde un archivo local.


## <a name="add-web-sdk-to-your-website"></a>Agregar el SDK web a su sitio web

Vaya a **Administración** > **Área de trabajo** y luego seleccione **Guía de instalación**. Hay dos opciones para instalar el SDK web. El primero es utilizar un enlace de descarga y el segundo es instalar un paquete de administrador de paquetes de nodos (NPM).

### <a name="option-1-using-the-download-link"></a>Opción 1. Usando el vínculo de descarga

1. Seleccione **Copiar codigo** para copiar el fragmento de código. De forma predeterminada, la clave de ingesta para su área de trabajo está incrustada en el fragmento de código.
  :::image type="content" source="media/copy-code.png" alt-text="Captura de pantalla de la página del fragmento de código.":::

1. Agregue el código copiado a su sitio web, cerca del <head> etiqueta y antes de cualquier otro script o etiquetas CSS.
1. Publique su sitio web actualizado y espere unos minutos para capturar el tráfico web entrante.
1. Para ver sus datos, seleccione su área de trabajo en el selector de áreas de trabajo en el panel de navegación. Luego, seleccione uno de los informes en la sección **Descubrir**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opción 2: usar el paquete NPM (recomendado para aplicaciones web basadas en JavaScript)

1. Ir a nuestra [Página web de NPM](https://www.npmjs.com/package/engagementinsights-web) y siga las instrucciones para instalar y configurar el paquete web SDK NPM.
1. Publique su sitio web actualizado y espere unos minutos para capturar el tráfico web entrante.
1. Para ver sus datos, seleccione su área de trabajo en el selector de áreas de trabajo en el panel de navegación. Luego, seleccione uno de los informes en la sección **Descubrir**.

## <a name="configuration-options"></a>Opciones de configuración

Puede cambiar las siguientes opciones de configuración en el fragmento de código:

- **ingestionKey**: la clave de ingesta que se usa para enviar eventos a su área de trabajo. Puede cambiar la clave de ingesta para enviar eventos a un área de trabajo diferente. Una clave de ingesta es única para cada área de trabajo.
- **autoCapture**: especifica si se capturan las visitas a la página y las interacciones con el sitio web. Tiene dos opciones:
    - **vista**: configúrelo como *Verdadero* para capturar visitas a la página. Las páginas vistas se capturan como [eventos](glossary.md#event) de *vista*, un tipo de [evento base](glossary.md#base-event).
    - **clic**: configúrelo como *Verdadero* para capturar las interacciones de los visitantes en el sitio web. Las interacciones se capturan como [eventos](glossary.md#event) de *acción*, un tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
