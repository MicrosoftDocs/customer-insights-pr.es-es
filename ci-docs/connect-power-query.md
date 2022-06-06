---
title: Ingesta datos a través de un conector Power Query (contiene vídeo)
description: Conectores para orígenes de datos basados en Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800210"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectarse a un origen de datos en Power Query

Power Query ofrece un amplio conjunto de conectores para ingerir datos. La mayoría de estos conectores son compatibles con Dynamics 365 Customer Insights. 

Agregar fuentes de datos basadas en conectores de Power Query generalmente sigue los pasos descritos en esta sección. Sin embargo, según el conector que utilice, se requiere información diferente. Para obtener más información, consulte la documentación sobre conectores individuales en la [Referencia del conector Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear un nuevo origen de datos

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione **Agregar origen de datos**.

1. Seleccione **Microsoft Power Query**.

1. Proporcione un **Nombre** para el origen de datos y seleccione **Siguiente** para crear el origen de datos.

1. Elija uno de los [conectores disponibles](#available-power-query-data-sources). En este ejemplo, seleccionamos el conector **Texto/CSV**.

1. Ingrese los detalles requeridos en la **Configuraciónde conexión** para el conector seleccionado y seleccione **Siguiente** para ver una vista previa de los datos.

1. Seleccione **Transformar datos**. En este paso va a agregar entidades a su origen de datos. Las entidades son conjuntos de datos. Si tiene una base de datos que incluye múltiples conjuntos de datos, cada conjunto de datos es su propia entidad.

1. El cuadro de diálogo **Power Query - Editar consultas** le permite revisar y refinar los datos. Las entidades que los sistemas identificaron en el origen de datos seleccionado se muestran en el panel izquierdo.

   > [!div class="mx-imgBorder"]
   > ![Diálogo Editar consultas.](media/data-manager-configure-edit-queries.png "Diálogo Editar consultas")

1. También puede transformar los datos. Seleccione una entidad para editarla o transformarla. Utilice las opciones en la ventana Power Query para aplicar transformaciones. Cada transformación se enumera en **Pasos aplicados**. Power Query proporciona numerosas opciones de transformación preconstruidas. Para obtener más información, consulte [Transformaciones de Power Query](/power-query/power-query-what-is-power-query#transformations).

   Recomendamos que use las siguientes transformaciones:

   - Si está ingiriendo datos de un archivo CSV, la primera fila suele contener encabezados. Vaya a **Transformar** y seleccione **Usar la primera fila como encabezados**.
   - Asegúrese de que el tipo de datos esté configurado correctamente. Por ejemplo, para los campos de fecha, seleccione un tipo de fecha.

1. Para agregar entidades adicionales a su origen de datos en el cuadro de diálogo **Editar consultas**, vaya a **Inicio** y seleccione **Obtener datos**.

1. Seleccione **Guardar** en la parte inferior de la ventana Power Query para guardar las transformaciones. Después de guardar, encontrará su origen de datos en **Datos** > **Orígenes de datos**.

1. En la página **Orígenes de datos** observará que el nuevo origen de datos está en estado **Actualizando**.

## <a name="available-power-query-data-sources"></a>Orígenes de datos Power Query disponibles

Vea la [referencia del conector de Power Query](/power-query/connectors/) para obtener una lista de conectores que puede utilizar para importar datos a Customer Insights. 

Los conectores con una marca de verificación en la columna **Customer Insights (flujos de datos)** están disponibles para crear nuevos orígenes de datos basados en Power Query. Revise la documentación de un conector específico para obtener más información sobre sus requisitos previos, limitaciones y otros detalles.

## <a name="edit-power-query-data-sources"></a>Editar orígenes de datos de Power Query

> [!NOTE]
> Es posible que no se puedan realizar cambios en los orígenes de datos que se están utilizando actualmente en uno de los procesos de la aplicación ( *segmentación*, *coincidencia* o *combinación*, por ejemplo). 
>
> En la página **Configuración** puede realizar un seguimiento del progreso de cada uno de los procesos activos. Cuando se completa un proceso, puede volver a la página **Orígenes de datos** y hacer cambios.

1. Vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales (&vellip;) junto al origen de datos que desea cambiar y seleccione **Editar** en el menú desplegable.

   > [!div class="mx-imgBorder"]
   > ![Editar opción.](media/edit-option-data-sources.png "Editar opción")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Aplique sus cambios y transformaciones en el cuadro de diálogo **Power Query - Editar consultas** como se describe en la sección [Crear un nuevo origen de datos](#create-a-new-data-source).

4. Seleccione **Guardar** en Power Query después de completar sus ediciones para guardar sus cambios.


[!INCLUDE [footer-include](includes/footer-banner.md)]
