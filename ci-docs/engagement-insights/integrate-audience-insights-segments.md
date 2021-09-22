---
title: Usar segmentos de conclusiones del público para filtrar informes de conclusiones sobre la interacción
description: Use los segmentos de conclusiones del público en los análisis interactivos de los datos de comportamiento capturados por las conclusiones sobre la interacción en el sitio web de un cliente.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461079"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Usar segmentos de conclusiones del público para filtrar informes de conclusiones sobre la interacción

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Con conclusiones sobre la interacción puede usar los segmentos de conclusiones del público en los análisis interactivos de los datos de comportamiento capturados por las conclusiones sobre la interacción en sus sitios web.

## <a name="prerequisite"></a>Requisito previo

- Un entorno de conclusiones sobre la interacción en el que tiene datos de conclusiones del público vinculados al entorno de conclusiones del público donde se crean los segmentos y los perfiles de cliente. Para más información: [Crear un vínculo entre las conclusiones del público y las conclusiones sobre la interacción](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Crear segmentos de conclusiones del público 

> [!IMPORTANT]
> Para que los segmentos de conclusiones del público se muestren en conclusiones sobre la interacción, primero debe [ejecutar la combinación y los procesos subsiguientes](../audience-insights/merge-entities.md). Los procesos posteriores son importantes porque generan una tabla única que prepara los segmentos de iconclusiones del público para compartir con las conclusiones sobre la interacción. (Si se programa una actualización del sistema, incluirá automáticamente los procesos posteriores).

Puede usar segmentos de conclusiones del público en informes listos para usar de conclusiones sobre la interacción o en informes personalizados que haya creado. Para obtener más información, vaya a [Informes de perfiles listos para usar](profile-reports.md) y [Crear y editar informes personalizados](custom-reports.md).

**Para usar segmentos de conclusiones del público en informes de conclusiones sobre la interacción**

1. En la página **Área de trabajo**, seleccione **Datos** y, a continuación, seleccione la pestaña **Segmentos**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Seleccione la pestaña Segmentos.":::

   >[!NOTE]
   > La selección de un segmento de conclusiones del público le lleva a las conclusiones del público, donde puede averiguar cómo se creó ese segmento en términos de las reglas y la lógica. Para obtener más información sobre segmentos de conclusiones del público, vaya a [Ver y crear segmentos](../audience-insights/segments.md).

2. Seleccione un informe listo para usar o [cree un informe personalizado](custom-reports.md) y, a continuación, seleccione **Agregar condición**. (Para este ejemplo, elegimos el informe **Vistas de página**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Agrega una condición.":::

3. Seleccione **Filtrar por segmento**, expanda la lista **Tipo de segmento** y, a continuación, seleccione **Datos demográficos**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Seleccione el tipo de segmento demográfico.":::

4. Expanda la lista **Nombre de segmento** y, a continuación, elija un segmento de conclusiones del público.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Elija un segmento.":::

5. Puede aplicar uno o más segmentos, incluidos los segmentos de comportamiento (conclusiones sobre la interacción) y datos demográficos (conclusiones del público). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Informe de vistas de página restringido a los clientes de EE. UU. Y a los segmentos de la página de inicio.":::

En la imagen anterior, se han seleccionado los segmentos **Clientes de EE. UU.** y **Página de inicio**, lo que restringe el informe de **Vistas de página** para mostrar solo esos dos segmentos. 


>[!NOTE]
> Puede usar segmentos de conclusiones del público para filtrar informes listos para usar, informes personalizados y embudos en conclusiones sobre la interacción. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]