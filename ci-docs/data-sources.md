---
title: Información general de los orígenes de datos
description: Aprenda a importar o ingerir datos de varias fuentes.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245670"
---
# <a name="data-sources-overview"></a>Información general de los orígenes de datos

Dynamics 365 Customer Insights proporciona conexiones para traer datos de una amplia gama de orígenes. Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*. Después de ingerir los datos, puede [unificar](data-unification.md), generar conocimientos y activar los datos para crear experiencias personalizadas.

## <a name="add-or-edit-data-sources"></a>Agregar o editar orígenes de datos

Puede adjuntar o importar orígenes de datos en Customer Insights. Los enlaces a continuación proporcionan instrucciones sobre cómo agregar y editar orígenes de datos.

**Adjuntar un origen de datos**

Si tiene datos preparados en uno de los servicios de datos de Azure de Microsoft, Customer Insights puede conectarse fácilmente a origen de datos sin tener que volver a ingerir los datos. Seleccione una de las siguientes opciones:
- [Azure Data Lake Storage (archivos csv o parquet en una carpeta de Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (Con bases de datos Lake)](connect-synapse.md)
- [Lago de datos Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importar y transformar**

Si usa orígenes de datos locales, Microsoft o datos de terceros, importe y transforme los datos usando conectores Power Query.
- [Conectores de Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Revisar orígenes de datos

Si su entorno se configuró para utilizar el almacenamiento de Customer Insights y utiliza orígenes de datos locales, puede usar flujos de datos de Power Platform. Con flujos de datos de Power Platform, puede ver los orígenes de datos compartidos y los orígenes de datos administrados por otros. La página **Orígenes de datos** enumera los orígenes de datos en tres secciones:
- **Compartido**: orígenes de datos que pueden administrar todos los administradores de Customer Insights. Flujos de datos de Power Platform, su propia cuenta de almacenamiento y la conexión a un lago de datos gestionado por Dataverse son ejemplos de orígenes de datos compartidos.
- **Administrado por mi**: flujos de datos de Power Platform creados y que solo usted puede administrar. Otros administradores de Customer Insights solo pueden ver estos flujos de datos, pero no editarlos, actualizarlos ni eliminarlos.
- **Administrados por otros**: flujos de datos de Power Platform creados por otros administradores. Usted solo puedes verlos. Enumera al propietario del flujo de datos para contactar en caso de necesitar asistencia.
> [!NOTE]
> Otros usuarios pueden ver y utilizar todas las entidades. Si bien los orígenes de datos son propiedad del usuario que los creó, las entidades resultantes de la ingesta de datos pueden ser utilizadas por todos los usuarios de Customer Insights.

Si su entorno no utiliza flujos de datos Power Platform, la página **Orígenes de datos** contiene solo una lista de todos los orígenes de datos. No se muestran secciones.

## <a name="manage-existing-data-sources"></a>Administrar orígenes de datos existentes

Vaya a **Datos** > **Orígenes de datos** para ver el nombre de cada origen de datos ingestado, su estado y la última vez que se actualizaron datos para esa fuente. Puede ordenar la lista de orígenes de datos por cualquier columna o usar el cuadro de búsqueda para encontrar el origen de datos que desea administrar.

Seleccione un origen de datos para ver las acciones disponibles.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Origen de datos agregado.":::

- [**Edite**](#add-or-edit-data-sources) el origen de datos para cambiar sus propiedades.
- [**Actualice**](#refresh-data-sources) el origen de datos para incluir los últimos datos.
- [**Enriquezca**](data-sources-enrichment.md) el origen de datos antes de la unificación.
- **Elimine** el origen de datos. Un origen de datos se puede eliminar solo si los datos no se usan en ningún procesamiento, como unificación, información, activaciones o exportaciones.

## <a name="refresh-data-sources"></a>Actualizar orígenes de datos

Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición. [Orígenes de datos locales](connect-power-query.md#add-data-from-on-premises-data-sources) actualice en sus propios horarios que se configuran durante la ingesta de datos. Para los orígenes de datos adjuntos, la ingestión de datos consume los últimos datos disponibles de ese origen de datos.

Vaya a **Administración** > **Sistema** > [**Calendario**](schedule-refresh.md) para configurar actualizaciones programadas por el sistema de sus orígenes de datos ingeridos.

Para actualizar un origen de datos a petición:

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione el origen de datos que desea actualizar y seleccione **Actualizar**. El origen de datos ahora se desencadena para una actualización manual. Al actualizar un origen de datos, se actualizará tanto el esquema de la entidad como los datos para todas las entidades especificadas en el origen de datos.

1. Seleccione el estado para abrir el panel **Detalles de progreso** y vea el progreso. Para cancelar el trabajo, seleccione **Cancelar trabajo** en la parte inferior del panel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
