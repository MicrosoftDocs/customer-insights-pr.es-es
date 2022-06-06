---
title: Usar orígenes de datos para ingerir datos
description: Aprenda a importar datos desde distintos orígenes.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 355d52eabde90e0764817cf479821264ebb2e5eb
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800487"
---
# <a name="data-sources-overview"></a>Información general de los orígenes de datos



Dynamics 365 Customer Insights conecta los datos de una amplia gama de orígenes. Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*. Después de ingerir los datos, puede [unificar](data-unification.md) y actuar sobre ellos.

## <a name="add-a-data-source"></a>Agregar un origen de datos

Consulte los artículos detallados sobre cómo agregar un origen de datos, según la opción que elija.

Puede agregar los siguientes orígenes de datos:

- [A través de docenas de conectores de Power Query](connect-power-query.md)
- [Desde una carpeta de Common Data Model](connect-common-data-model.md)
- [Desde su propio lago de Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Desde una base de datos de Azure Synapse Analytics](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Agregar datos de orígenes de datos locales

Se admite la ingesta de datos de fuentes de datos local en función de flujos de datos de Microsoft Power Platform. Puede habilitar los flujos de datos en Customer Insights [proporcionando la URL del entorno de Microsoft Dataverse](create-environment.md) al configurar el entorno.

Los orígenes de datos que se crean después de asociar un entorno de Dataverse con Customer Insights usan [flujos de datos de Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Los flujos de datos admiten conectividad local mediante la puerta de enlace. Puede eliminar y volver a crear fuentes de datos que existían antes de asociar un entorno de Dataverse [usando pasarelas de datos locales](/data-integration/gateway/service-gateway-app).

Las puertas de enlace de datos de un entorno de Power BI o Power Apps existente serán visibles y podrá reutilizarlas en Customer Insights. La página de orígenes de datos muestra enlaces para ir al entorno de Microsoft Power Platform donde puede ver y configurar puertas de enlace de datos locales.

> [!IMPORTANT]
> Asegúrese de que sus puertas de enlace estén actualizadas a la última versión. Puede instalar una actualización y reconfigurar una puerta de enlace desde una solicitud que se muestra en la pantalla de la puerta de enlace directamente o [descargar la última versión](https://powerapps.microsoft.com/downloads/). Si no usa la última versión de la puerta de enlace, la actualización del flujo de datos falla con mensajes de error como **La palabra clave no es compatible: propiedades de configuración. Nombre del parámetro: palabra clave**.

## <a name="review-ingested-data"></a>Revisar datos ingeridos
Si su entorno contiene flujos de datos de Power Platform, la página **Orígenes de Datos** enumera tres secciones: 
- **Compartido**: orígenes de datos que pueden administrar todos los administradores de Customer Insights. Flujos de datos de Power BI, su propia cuenta de almacenamiento y la conexión a un lago de datos gestionado por Dataverse son ejemplos de orígenes de datos compartidos.
- **Administrado por mi**: flujos de datos de Power Platform creados y que solo usted puede administrar. Otros administradores de Customer Insights solo pueden ver estos flujos de datos, pero no editarlos, actualizarlos ni eliminarlos.
- **Administrados por otros**: flujos de datos de Power Platform creados por otros administradores. Usted solo puedes verlos. Enumera al propietario del flujo de datos para contactar en caso de necesitar asistencia.
> [!NOTE]
> Otros usuarios pueden ver y utilizar todas las entidades. La contextualidad del usuario se aplica solo a los orígenes de datos y no a las entidades que resultan de estos flujos de datos.

Si no se utilizan flujos de datos de Power Platform, no verá ningún grupo ni sección. La página de **Orígenes de Datos** contiene solo una lista de todos los orígenes de datos.

Podrá ver el nombre de cada origen de datos ingeridos, su estado y la última vez que se actualizaron los datos para ese origen. Puede ordenar la lista de orígenes de datos por cada columna.

> [!div class="mx-imgBorder"]
> ![Origen de datos agregado.](media/configure-data-datasource-added.png "Origen de datos agregado")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La carga de datos puede llevar tiempo. Una vez completada una actualización, se pueden revisar los datos ingeridos en la página **Entidades**. Para obtener más información, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Actualizar un origen de datos

Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición. 

Vaya a **Administrador** > **Sistema** > [**Programación**](system.md#schedule-tab) para configurar actualizaciones programadas de todos sus orígenes de datos ingeridos.

Para actualizar un origen de datos a petición, siga estos pasos:

1. Vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales (&vellip;) junto al origen de datos que desea actualizar y seleccione **Actualizar** en la lista desplegable.

3. El origen de datos ahora se desencadena para una actualización manual. Al actualizar un origen de datos, se actualizará tanto el esquema de la entidad como los datos para todas las entidades especificadas en el origen de datos.

4. Seleccione **Dejar de actualizar** si desea cancelar una actualización existente y el origen de datos volverá a su último estado de actualización.

## <a name="delete-a-data-source"></a>Eliminar un origen de datos

1. Vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales (&vellip;) junto al origen de datos que desea quitar y seleccione **Eliminar** en la lista desplegable.

3. Confirme la eliminación.


[!INCLUDE [footer-include](includes/footer-banner.md)]
