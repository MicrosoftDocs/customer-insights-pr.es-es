---
title: Usar orígenes de datos para ingerir datos
description: Aprenda a importar datos desde distintos orígenes.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011770"
---
# <a name="data-sources-overview"></a>Información general de los orígenes de datos

Dynamics 365 Customer Insights proporciona conexiones para traer datos de una amplia gama de orígenes. Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*. Después de ingerir los datos, puede [unificar](data-unification.md), generar conocimientos y activar los datos para crear experiencias personalizadas.

## <a name="add-data-sources"></a>Agregar orígenes de datos

Puede adjuntar o importar fuentes de datos en Customer Insights. Los enlaces a continuación proporcionan instrucciones sobre cómo agregar orígenes de datos.

**Adjuntar un origen de datos**

Si tiene datos preparados en uno de los servicios de datos de Azure de Microsoft, Customer Insights puede conectarse fácilmente a origen de datos sin tener que volver a ingerir los datos. Seleccione una de las siguientes opciones:
- [Azure Data Lake Storage (archivos csv o parquet en una carpeta de Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (Con bases de datos Lake)](connect-synapse.md)
- [Lago de datos Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importar y transformar**

Si usa orígenes de datos locales, Microsoft o datos de terceros, importe y transforme los datos usando conectores Power Query.
- [Conectores de Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Revisar orígenes de datos

Si su entorno se configuró para utilizar el almacenamiento de Customer Insights y utiliza orígenes de datos locales, puede usar flujos de datos de Power Platform. Con flujos de datos de Power Platform, puede ver las fuentes de datos compartidas y las fuentes de datos administradas por otros. La página **Orígenes de datos** enumera las fuentes de datos en tres secciones:
- **Compartido**: orígenes de datos que pueden administrar todos los administradores de Customer Insights. Flujos de datos de Power Platform, su propia cuenta de almacenamiento y la conexión a un lago de datos gestionado por Dataverse son ejemplos de orígenes de datos compartidos.
- **Administrado por mi**: flujos de datos de Power Platform creados y que solo usted puede administrar. Otros administradores de Customer Insights solo pueden ver estos flujos de datos, pero no editarlos, actualizarlos ni eliminarlos.
- **Administrados por otros**: flujos de datos de Power Platform creados por otros administradores. Usted solo puedes verlos. Enumera al propietario del flujo de datos para contactar en caso de necesitar asistencia.
> [!NOTE]
> Otros usuarios pueden ver y utilizar todas las entidades. Si bien las fuentes de datos son propiedad del usuario que las creó, las entidades resultantes de la ingesta de datos pueden ser utilizadas por todos los usuarios de Customer Insights.

Si su entorno no utiliza flujos de datos Power Platform, la página **Orígenes de datos** contiene solo una lista de todas las fuentes de datos. No se muestran secciones.

Vaya a **Datos** > **Orígenes de datos** para ver el nombre de cada origen de datos ingestado, su estado y la última vez que se actualizaron datos para esa fuente. Puede ordenar la lista de orígenes de datos por cada columna.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Origen de datos agregado.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La carga de datos puede llevar tiempo. Una vez completada una actualización, se pueden revisar los datos ingeridos en la página **Entidades**. Para obtener más información, consulte [Entidades](entities.md).

## <a name="refresh-data-sources"></a>Actualizar orígenes de datos

Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición. [Orígenes de datos locales](connect-power-query.md#add-data-from-on-premises-data-sources) actualice en sus propios horarios que se configuran durante la ingesta de datos. Para las fuentes de datos adjuntas, la ingestión de datos consume los últimos datos disponibles de ese origen de datos.

Vaya a **Administración** > **Sistema** > [**Calendario**](system.md#schedule-tab) para configurar actualizaciones programadas por el sistema de sus fuentes de datos ingeridas.

Para actualizar un origen de datos a petición, siga estos pasos:

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione los puntos suspensivos verticales (&vellip;) junto al origen de datos que desea actualizar y seleccione **Actualizar** en la lista desplegable. El origen de datos ahora se desencadena para una actualización manual. Al actualizar un origen de datos, se actualizará tanto el esquema de la entidad como los datos para todas las entidades especificadas en el origen de datos.

1. Seleccione **Dejar de actualizar** si desea cancelar una actualización existente y el origen de datos volverá a su último estado de actualización.

## <a name="delete-a-data-source"></a>Eliminar un origen de datos

Un origen de datos se puede eliminar solo si los datos no se usan en ningún procesamiento, como unificación, información, activaciones o exportaciones.

1. Vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales (&vellip;) junto al origen de datos que desea quitar y seleccione **Eliminar** en la lista desplegable.

3. Confirme la eliminación.


[!INCLUDE [footer-include](includes/footer-banner.md)]
