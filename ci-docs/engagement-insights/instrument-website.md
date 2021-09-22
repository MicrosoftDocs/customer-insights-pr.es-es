---
title: Añadir código a su sitio web
description: Cómo agregar un fragmento de código para capturar eventos en su sitio web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035115"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalar el fragmento de código en un sitio web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En este artículo se describe cómo un administrador instala el fragmento de código en un sitio web. Comenzará a ver eventos en su área de trabajo poco después de agregar el script a su sitio web. Para obtener más información, consulte [Gestionar entornos y áreas de trabajo](manage-environments-workspaces.md). Para capturar eventos en aplicaciones móviles, consulte [Descripción general de los recursos para desarrolladores](developer-resources.md).


### <a name="prerequisites"></a>Requisitos previos

* Debe tener permisos de administrador para que el área de trabajo almacene los datos.
* Su sitio web o proyecto debe estar alojado en línea para enviar datos de actividad. El servidor no aceptará los datos enviados desde un archivo local.


## <a name="add-code-to-your-website"></a>Añadir código a su sitio web
1.  Vaya a **Administración** > **Área de trabajo** y luego seleccione **Guía de instalación**.
1. Seleccione **Copiar codigo** para copiar el fragmento de código. De forma predeterminada, la clave de ingesta para su área de trabajo está incrustada en el fragmento de código.
:::image type="content" source="media/copy-code.png" alt-text="Captura de pantalla de la página del fragmento de código.":::
3. Agregue el fragmento de código copiado a su sitio web, cerca de la <head> etiqueta y antes de cualquier otro script o etiquetas CSS.
4.  Publique su sitio web actualizado y espere unos minutos para capturar el tráfico web entrante.
5.  Para ver sus datos, seleccione su área de trabajo en el selector de áreas de trabajo en el panel de navegación. Luego, seleccione uno de los informes en la sección **Descubrir**.

## <a name="configuration-options"></a>Opciones de configuración

Puede cambiar las siguientes opciones de configuración en el fragmento de código:

- **ingestionKey**: la clave de ingesta que se usa para enviar eventos a su área de trabajo. Puede cambiar la clave de ingesta para enviar eventos a un área de trabajo diferente. Una clave de ingesta es única para cada área de trabajo. 
- **autoCapture**: especifica si se capturan las visitas a la página y las interacciones con el sitio web. Tiene dos opciones:
    - **vista**: configúrelo como *Verdadero* para capturar visitas a la página. Las páginas vistas se capturan como [eventos](glossary.md#event) de *vista*, un tipo de [evento base](glossary.md#base-event).
    - **clic**: configúrelo como *Verdadero* para capturar las interacciones de los visitantes en el sitio web. Las interacciones se capturan como [eventos](glossary.md#event) de *acción*, un tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
