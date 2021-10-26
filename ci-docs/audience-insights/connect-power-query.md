---
title: Ingerir datos a través de un conector de Power Query
description: Conectores para orígenes de datos basados en Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: ab6edc3f33ebacb81f55c0882a78c5827b4384ed
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643515"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectar un origen de datos de Power Query

Power Query ofrece un amplio conjunto de conectores para ingerir datos. La mayoría de estos conectores son compatibles con Dynamics 365 Customer Insights. Agregar orígenes de datos basados en conectores de Power Query generalmente sigue los pasos descritos en la siguiente sección. Sin embargo, según el conector que utilice, se requiere información diferente. Para obtener más información, consulte la documentación sobre conectores individuales en la [Referencia del conector de Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear un nuevo origen de datos

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

1. Seleccione **Agregar origen de datos**.

1. Elija el método **Importar datos** y seleccione **Siguiente**.

1. Proporcione un **Nombre** para el origen de datos y seleccione **Siguiente** para crear el origen de datos. Directrices de nomenclatura: 
   - Empiece con una letra.
   - Utilice solo letras y números. No se permiten caracteres especiales ni espacios.
   - Utilice entre 3 y 64 caracteres.

1. Elija uno de los [conectores disponibles](#available-power-query-data-sources). Para este ejemplo, seleccionamos el conector **Texto/CSV**.

1. Ingrese los detalles requeridos en la **Configuraciónde conexión** para el conector seleccionado y seleccione **Siguiente** para ver una vista previa de los datos.

1. Seleccione **Transformar datos**. En este paso va a agregar entidades a su origen de datos. Las entidades son conjuntos de datos. Si tiene una base de datos que incluye múltiples conjuntos de datos, cada conjunto de datos es su propia entidad.

1. El diálogo **Power Query - Editar consultas** le permite revisar y refinar los datos. Las entidades que los sistemas identificaron en el origen de datos seleccionado se muestran en el panel izquierdo.

   > [!div class="mx-imgBorder"]
   > ![Diálogo Editar consultas.](media/data-manager-configure-edit-queries.png "Diálogo Editar consultas")

1. También puede transformar los datos. Seleccione una entidad para editarla o transformarla. Utilice las opciones de la ventana Power Query para aplicar transformaciones. Cada transformación se enumera en **Pasos aplicados**. Power Query proporciona numerosas opciones de transformación prediseñadas. Para obtener más información, vea [Transformaciones de Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Puede agregar entidades adicionales a su origen de datos seleccionando **Obtener datos** en el cuadro de diálogo **Editar consultas**.

   Estas transformaciones son muy recomendables:

   - Si está ingiriendo datos de un archivo CSV, la primera fila suele contener encabezados. Vaya a **Transformar tabla** y seleccione **Usar encabezados como primera fila**.
   - Asegúrese de que el tipo de datos esté configurado correctamente.

1. Seleccione **Guardar** en la esquina inferior derecha de la ventana Power Query para guardar las transformaciones. Después de guardar, encontrará su origen de datos en **Datos** > **Orígenes de datos**.

1. En la página **Orígenes de datos** observará que el nuevo origen de datos está en estado **Actualizando**.

## <a name="available-power-query-data-sources"></a>Orígenes de datos de Power Query disponibles

Vea la [Referencia del conector de Power Query](/power-query/connectors/) para obtener una lista actualizada de conectores que puede seleccionar para importar datos a Customer Insights. 

Los conectores con una marca de verificación en la columna **Customer Insights (flujos de datos)** están disponibles para crear nuevos orígenes de datos basados en Power Query. Revise la documentación de un conector específico para obtener más información sobre sus requisitos previos, limitaciones y otros detalles.

## <a name="edit-power-query-data-sources"></a>Editar orígenes de datos de Power Query

> [!NOTE]
> Es posible que no se puedan realizar cambios en los orígenes de datos que se están utilizando actualmente en uno de los procesos de la aplicación ( *segmentación*, *coincidencia* o *combinación*, por ejemplo). 
>
> En la página **Configuración** puede realizar un seguimiento del progreso de cada uno de los procesos activos. Cuando se completa un proceso, puede volver a la página **Orígenes de datos** y hacer cambios.

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales junto al origen de datos que desea cambiar y seleccione **Editar** en la lista desplegable.

   > [!div class="mx-imgBorder"]
   > ![Editar opción.](media/edit-option-data-sources.png "Editar opción")

3. Aplique sus cambios y transformaciones en el diálogo **Power Query - Editar consultas** como se describe en la sección [Crear un origen de datos nuevo](#create-a-new-data-source).

4. Seleccione **Guardar** en Power Query después de completar sus ediciones para guardar sus cambios.


[!INCLUDE[footer-include](../includes/footer-banner.md)]