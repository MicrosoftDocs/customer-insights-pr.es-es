---
title: Actualización incremental para Power Query y orígenes de datos de Azure Data Lake
description: Actualizar datos nuevos y actualizados para grandes fuentes de datos en función de orígenes de datos de Power Query o de Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012046"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Actualización incremental para Power Query y orígenes de datos de Azure Data Lake

Este artículo analiza cómo configurar la actualización incremental para fuentes de datos basadas en Power Query o Azure Data Lake.

La actualización incremental de las fuentes de datos ofrece las siguientes ventajas:

- **Actualizaciones más rápidas** - Solo se actualizan los datos que han cambiado. Por ejemplo, puede actualizar solo los últimos cinco días de un conjunto de datos histórico.
- **Mayor fiabilidad** - Con actualizaciones más pequeñas, no necesita mantener conexiones a sistemas de origen volátiles durante tanto tiempo, lo que reduce el riesgo de problemas de conexión.
- **Reducción del consumo de recursos** - Actualizar solo un subconjunto de sus datos totales brinda un uso más eficiente de los recursos informáticos y disminuye la huella ambiental.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configurar la actualización incremental para orígenes de datos basados en Power Query

Customer Insights permiten la actualización incremental para los orígenes de datos importados a través de Power Query que admiten la ingestión incremental. Por ejemplo, las bases de datos Azure SQL con campos de fecha y hora que indican cuándo se actualizaron por última vez los registros de datos.

1. [Crear un nuevo origen de datos basado en Power Query](connect-power-query.md).

1. Seleccione un origen de datos que admita la actualización incremental, como la [base de datos de Azure SQL](/power-query/connectors/azuresqldatabase).

1. Seleccione las entidades o tablas para ingerir.

1. Complete los pasos de transformación y seleccione **Siguiente**.

1. En el cuadro de diálogo **Configurar actualización incremental**, seleccione **Configurar** para abrir la **Configuración de actualización incremental**. Si selecciona **Omitir**, el origen de datos actualizará todo el conjunto de datos.
   > [!TIP]
   > También puede aplicar una actualización incremental más tarde editando un origen de datos existente.

1. En **Configuración de actualización incremental**, configurará la actualización incremental para todas las entidades que seleccionó al crear el origen de datos.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurar actualización incremental.":::

1. Seleccione una entidad y proporcione los siguientes detalles:

   - **Definir la clave principal**: Seleccione una clave principal para la entidad o tabla.
   - **Definir el campo "última actualización"**: Este campo solo mostrará atributos de tipo fecha u hora. Seleccione un atributo que indique cuándo se actualizaron por última vez los registros. Se utilizará para identificar los registros que se encuentran dentro del periodo de tiempo de actualización incremental.
   - **Buscar actualizaciones cada**: Especifique cuánto durará el periodo de tiempo de la actualización incremental.

1. Seleccione **Guardar** para completar la creación del origen de datos. La actualización de datos inicial será una actualización completa. Posteriormente, la actualización incremental de datos se producirá como se configuró en el paso anterior.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configurar la actualización incremental para orígenes de datos de Azure Data Lake

Customer Insights permite la actualización incremental de las fuentes de datos conectadas a Azure Data Lake Storage. Para usar la incorporación y actualización incrementales para una entidad, configure esa entidad cuando agregue Azure Data Lake origen de datos o posterior cuando edite origen de datos. La carpeta de datos de la entidad debe contener las siguientes carpetas:

- **FullData**: carpeta que debe tener archivos de datos que contengan registros iniciales
- **IncrementalData**: carpeta con carpetas de jerarquía de fecha/hora en formato **aaaa/mm/dd/hh** que contiene las actualizaciones incrementales. **hh** representa la hora UTC de las actualizaciones y contiene las carpetas **Upserts** y **Deletes** carpetas. **Upserts** contiene archivos de datos con actualizaciones de registros existentes o registros nuevos. **Deletes** contiene archivos de datos con registros que se eliminarán.

1. Al agregar o editar un origen de datos, navegue hasta el panel **Atributos** para la entidad.

1. Revisar los atributos. Asegúrese de que un atributo de fecha de creación o última actualización esté configurado con un **Formato de datos** *dateTime* y un **Tipo semántico** *Calendar.Date*. Edite el atributo si es necesario y seleccione **Hecho**.

1. En el panel **Seleccionar entidades**, edite la entidad. La casilla de verificación **Ingesta incremental** está seleccionada.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurar entidades en un origen de datos para actualización incremental.":::

   1. Busque la carpeta raíz que contiene los archivos .csv o .parquet para obtener datos completos, actualizaciones de datos incrementales y eliminaciones de datos incrementales.
   1. Introduzca la extensión para los datos completos y ambos archivos incrementales (\.csv o \.parquet).
   1. Seleccione **Guardar**.

1. Para **Última actualización**, seleccione el atributo de fecha y hora.

1. Si la **Clave principal** no está seleccionada, seleccione la clave principal. La clave principal es un atributo exclusivo de la entidad. Para que un atributo pueda ser una clave principal válida, no debe incluir valores duplicados, no deben faltar valores ni debe haber valores nulos. Los atributos de tipo de datos de cadena, entero y GUID se admiten como claves principales.

1. Seleccione **Cerrar** para guardar y cerrar el panel.

1. Continúe agregando o editando el origen de datos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
