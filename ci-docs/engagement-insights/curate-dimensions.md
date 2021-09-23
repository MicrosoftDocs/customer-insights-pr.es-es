---
title: Usar dimensiones demográficas para dividir datos de comportamiento (dimensiones mantenidas)
description: Use dimensiones mantenidas de perfil unificado para habilitar las propiedades de perfil de cliente de conclusiones del público.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466369"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Usar dimensiones demográficas para dividir datos de comportamiento

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mediante el uso de dimensiones demográficas de perfil unificado, los usuarios de conclusiones sobre la interacción pueden acceder a las propiedades del perfil de conclusiones del público. A continuación, puede usar estas propiedades en los análisis interactivos de los datos de comportamiento, incluidos los datos capturados por las perspectivas de participación en su sitio web o aplicación móvil.

>[!NOTE]
> La información sobre la participación incluye dimensiones listas para usar para las propiedades del evento. Más información: [Ver y crear dimensiones](dimensions.md)

## <a name="prerequisite"></a>Requisito previo

- Un entorno de conclusiones sobre la interacción en el que tiene datos de perfil de cliente vinculados al entorno de conclusiones del público donde se crean los perfiles de cliente. Para más información: [Crear un vínculo entre las conclusiones del público y las conclusiones sobre la interacción](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Después de crear un vínculo entre los entornos de conclusiones del público y conclusiones sobre la interacción, es posible que solo desee datos específicos de las propiedades del perfil del cliente, que pueden ser útiles como dimensiones en conclusiones sobre la interacción. Para obtener más información, vaya a [Habilitar atributos y segmentos del perfil unificado de conclusiones del público](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Crear un nuevo informe personalizado

1. En el panel izquierdo, seleccione **Personalizado** > **Nuevo informe** y luego seleccione la métrica que desee. (Para este ejemplo, elegimos **Vistas de página por hora**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Seleccione una métrica.":::

2. En el editor de visualización, seleccione **Dimensiones** y luego seleccione **Demográfico** en el menú desplegable **Tipo de dimensión**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Seleccione los datos demográficos.":::

3. Seleccione una dimensión **Signal.Customer.*xxx***. (En este ejemplo se muestra Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Seleccione una dimensión.":::
  
## <a name="limitations"></a>Limitaciones

Actualmente solo puede usar dimensiones demográficas para dividir datos de comportamiento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
