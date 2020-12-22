---
title: Actualización incremental para fuentes de datos basadas en Power Query
description: Actualice los datos nuevos y actualizados para grandes fuentes de datos basados en Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407039"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Actualización incremental para fuentes de datos basadas en Power Query

La actualización incremental de las fuentes de datos ofrece las siguientes ventajas:

- **Actualizaciones más rápidas** - Solo se actualizan los datos que han cambiado. Por ejemplo, puede actualizar solo los últimos cinco días de un conjunto de datos histórico.
- **Mayor fiabilidad** - Con actualizaciones más pequeñas, no necesita mantener conexiones a sistemas de origen volátiles durante tanto tiempo, lo que reduce el riesgo de problemas de conexión.
- **Reducción del consumo de recursos** - Actualizar solo un subconjunto de sus datos totales brinda un uso más eficiente de los recursos informáticos y disminuye la huella ambiental.

## <a name="configure-incremental-refresh"></a>Configurar actualización incremental

Las informaciones de público permiten la actualización incremental de las fuentes de datos importadas a través de Power Query que admiten la ingestión incremental. Por ejemplo, las bases de datos Azure SQL con campos de fecha y hora que indican cuándo se actualizaron por última vez los registros de datos.

1. [Crea un nuevo origen de datos basado en Power Query](connect-power-query.md).

1. Proporcione un nombre para el origen de datos.

1. Seleccione un origen de datos que admita la actualización incremental, como la base de datos de Azure SQL.

1. Seleccione las entidades o tablas para ingerir.

1. Complete los pasos de transformación y seleccione **Siguiente**.

1. En el cuadro de diálogo **Configurar actualización incremental**, seleccione **Configurar** para abrir la **Configuración de actualización incremental**. Si selecciona **Omitir**, el origen de datos actualizará todo el conjunto de datos.
   > [!TIP]
   > También puede aplicar una actualización incremental más tarde editando un origen de datos existente.

1. En **Configuración de actualización incremental**, configurará la actualización incremental para todas las entidades que seleccionó al crear el origen de datos.

   > [!div class="mx-imgBorder"]
   > ![Configurar entidades en un origen de datos para actualización incremental](media/incremental-refresh-settings.png "Configurar entidades en un origen de datos para actualización incremental")

1. Seleccione una entidad y proporcione los siguientes detalles:

   - **Definir la clave principal**: Seleccione una clave principal para la entidad o tabla.
   - **Definir el campo "última actualización"**: Este campo solo mostrará atributos de tipo fecha u hora. Seleccione un atributo que indique cuándo se actualizaron por última vez los registros. Se utilizará para identificar los registros que se encuentran dentro del periodo de tiempo de actualización incremental.
   - **Buscar actualizaciones cada**: Especifique cuánto durará el periodo de tiempo de la actualización incremental.

1. Seleccione **Guardar** para completar la creación del origen de datos. La actualización de datos inicial será una actualización completa. Posteriormente, la actualización incremental de datos se producirá como se configuró en el paso anterior.
