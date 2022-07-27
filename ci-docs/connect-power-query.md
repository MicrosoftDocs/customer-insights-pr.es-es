---
title: Conectarse a un origen de datos de Power Query (contiene vídeo)
description: Ingerir datos a través de un conector de Power Query (contiene vídeo).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081764"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectarse a un origen de datos en Power Query

Power Query ofrece un amplio conjunto de conectores para ingerir datos. La mayoría de estos conectores son compatibles con Dynamics 365 Customer Insights.

Agregar fuentes de datos basadas en conectores de Power Query generalmente sigue los pasos descritos en esta sección. Sin embargo, según el conector que utilice, se requiere información diferente. Para obtener más información, consulte la documentación sobre conectores individuales en la [Referencia del conector Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear un nuevo origen de datos

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione **Agregar origen de datos**.

1. Seleccione **Microsoft Power Query**.

1. Proporcione un **Nombre** para el origen de datos y una **Descripción** opcional y seleccione **Siguiente**.

1. Elija uno de los [conectores disponibles](#available-power-query-data-sources). En este ejemplo, seleccionamos el conector **Texto/CSV**.

1. Ingrese los detalles requeridos en la **Configuraciónde conexión** para el conector seleccionado y seleccione **Siguiente** para ver una vista previa de los datos.

1. Seleccione **Transformar datos**. En este paso va a agregar entidades a su origen de datos. Las entidades son conjuntos de datos. Si tiene una base de datos que incluye múltiples conjuntos de datos, cada conjunto de datos es su propia entidad.

1. El cuadro de diálogo **Power Query - Editar consultas** le permite revisar y refinar los datos. Las entidades que los sistemas identificaron en el origen de datos seleccionado se muestran en el panel izquierdo.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Diálogo Editar consultas":::

1. También puede transformar los datos. Seleccione una entidad para editarla o transformarla. Utilice las opciones en la ventana Power Query para aplicar transformaciones. Cada transformación se enumera en **Pasos aplicados**. Power Query proporciona numerosas opciones de transformación preconstruidas. Para obtener más información, consulte [Transformaciones de Power Query](/power-query/power-query-what-is-power-query#transformations).

   Recomendamos que use las siguientes transformaciones:

   - Si está ingiriendo datos de un archivo CSV, la primera fila suele contener encabezados. Vaya a **Transformar** y seleccione **Usar la primera fila como encabezados**.
   - Asegúrese de que el tipo de datos esté configurado correctamente. Por ejemplo, para los campos de fecha, seleccione un tipo de fecha.

1. Para agregar entidades adicionales a su origen de datos en el cuadro de diálogo **Editar consultas**, vaya a **Inicio** y seleccione **Obtener datos**. Repita los pasos 6 a 10 hasta que haya agregado todas las entidades para este origen de datos.

1. Seleccione **Guardar**. La página **Orígenes de datos** se abre y muestra el nuevo origen de datos en estado **Actualizando**.

### <a name="available-power-query-data-sources"></a>Orígenes de datos Power Query disponibles

Vea la [referencia del conector de Power Query](/power-query/connectors/) para obtener una lista de conectores que puede utilizar para importar datos a Customer Insights.

Los conectores con una marca de verificación en la columna **Customer Insights (flujos de datos)** están disponibles para crear nuevos orígenes de datos basados en Power Query. Revise la documentación de un conector específico para obtener más información sobre sus requisitos previos, [limitaciones de consulta](/power-query/power-query-online-limits), y otros detalles.

## <a name="add-data-from-on-premises-data-sources"></a>Agregar datos de orígenes de datos locales

Se admite la ingesta de datos de fuentes de datos local en función de flujos de datos de Microsoft Power Platform (PPDF). Puede habilitar los flujos de datos en Customer Insights [proporcionando la URL del entorno de Microsoft Dataverse](create-environment.md) al configurar el entorno.

Los orígenes de datos que se crean después de asociar un entorno de Dataverse con Customer Insights usan [flujos de datos de Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Los flujos de datos admiten conectividad local mediante la puerta de enlace. Puede eliminar y volver a crear fuentes de datos que existían antes de asociar un entorno de Dataverse [usando pasarelas de datos locales](/data-integration/gateway/service-gateway-app).

Las puertas de enlace de datos de un entorno de Power BI o Power Apps existente serán visibles y podrá reutilizarlas en Customer Insights. La página de orígenes de datos muestra enlaces para ir al entorno de Microsoft Power Platform donde puede ver y configurar puertas de enlace de datos locales.

> [!IMPORTANT]
> Asegúrese de que sus puertas de enlace estén actualizadas a la última versión. Puede instalar una actualización y reconfigurar una puerta de enlace desde una solicitud que se muestra en la pantalla de la puerta de enlace directamente o [descargar la última versión](https://powerapps.microsoft.com/downloads/). Si no usa la última versión de la puerta de enlace, la actualización del flujo de datos falla con mensajes de error como **La palabra clave no es compatible: propiedades de configuración. Nombre del parámetro: palabra clave**.

## <a name="edit-power-query-data-sources"></a>Editar orígenes de datos de Power Query

> [!NOTE]
> Es posible que no se puedan realizar cambios en los orígenes de datos que se están utilizando actualmente en uno de los procesos de la aplicación ( *segmentación*, *coincidencia* o *combinación*, por ejemplo).
>
> En la página **Configuración** puede realizar un seguimiento del progreso de cada uno de los procesos activos. Cuando se completa un proceso, puede volver a la página **Orígenes de datos** y hacer cambios.

1. Vaya a **Datos** > **Orígenes de datos**.

1. Junto al origen de datos que desea actualizar, seleccione **Editar**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Aplique sus cambios y transformaciones en el cuadro de diálogo **Power Query - Editar consultas** como se describe en la sección [Crear un nuevo origen de datos](#create-a-new-data-source).

1. Seleccione **Guardar** en Power Query después de completar sus ediciones para guardar sus cambios.
