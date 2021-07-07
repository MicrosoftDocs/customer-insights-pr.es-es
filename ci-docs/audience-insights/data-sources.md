---
title: Usar orígenes de datos para ingerir datos
description: Aprenda a importar datos desde distintos orígenes.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304717"
---
# <a name="data-sources-overview"></a>Información general de los orígenes de datos

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La capacidad de información de público de Dynamics 365 Customer Insights se conecta a datos de un amplio conjunto de orígenes. Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*. Después de ingerir los datos, puede [unificar](data-unification.md) y actuar sobre ellos.

## <a name="add-a-data-source"></a>Agregar un origen de datos

Consulte los artículos detallados sobre cómo agregar un origen de datos, según la opción que elija.

Puede agregar un origen de datos de tres formas principales:

- [A través de decenas de conectores de Power Query](connect-power-query.md)
- [Desde una carpeta de Common Data Model](connect-common-data-model.md)
- [Desde su propio lago de Microsoft Dataverse](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Agregar datos de orígenes de datos locales

La ingesta de datos de orígenes de datos locales en Audience Insights se admite según los flujos de datos de Microsoft Power Platform. Los flujos de datos se pueden habilitar en Customer Insights [proporcionando la dirección URL del entorno de Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) al configurar el entorno.

Los orígenes de datos que se crean después de asociar un entorno de Dataverse con Customer Insights utilizarán [flujos de datos de Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Los flujos de datos admiten conectividad local mediante la puerta de enlace. Quite y vuelva a crear los orígenes de datos que existían antes de que un entorno de Dataverse se asociara para [utilizar las puertas de enlace de datos locales](/data-integration/gateway/service-gateway-app.md).

Las puertas de enlace de datos de un entorno de Power BI o Power Apps existente serán visibles y podrá reutilizarlas en Customer Insights. La página de orígenes de datos muestra enlaces para ir al entorno de Microsoft Power Platform donde puede ver y configurar puertas de enlace de datos locales.

## <a name="review-ingested-data"></a>Revisar datos ingeridos

Podrá ver el nombre de cada origen de datos ingeridos, su estado y la última vez que se actualizaron los datos para ese origen. Puede ordenar la lista de orígenes de datos por cada columna.

> [!div class="mx-imgBorder"]
> ![Origen de datos agregado](media/configure-data-datasource-added.png "Origen de datos agregado")

|Estado  |Descripción  |
|---------|---------|
|Operación correcta   |El origen de datos se ingirió correctamente si se menciona una hora en la columna **Actualizado**.
|Sin iniciar   |El origen de datos aún no tiene datos ingeridos o sigue en modo de borrador.         |
|Actualizando    |La ingesta de datos está en curso. Para cancelar esta operación, seleccione **Detener la actualización** en la columna **Acciones**. Al detener la actualización de un origen de datos se revertirá a su último estado de actualización.       |
|Con errores     |Se han producido errores al ingerir datos.         |

Seleccione el valor en la columna **Estado** de cualquier origen de datos para revisar más detalles. En el panel **Detalles del progreso**, expanda **Fuentes de datos**. Seleccione **Ver detalles** para obtener más información sobre el estado de actualización, incluidos los detalles del error y las actualizaciones del proceso posterior.

La carga de datos puede llevar tiempo. Una vez completada una actualización, se pueden revisar los datos ingeridos en la página **Entidades**. Para obtener más información, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Actualizar un origen de datos

Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición. 

Vaya a **Administrador** > **Sistema** > [**Programación**](system.md#schedule-tab) para configurar actualizaciones programadas de todos sus orígenes de datos ingeridos.

Para actualizar un origen de datos a petición, siga estos pasos:

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales junto al origen de datos que desea actualizar y seleccione **Actualizar** en la lista desplegable.

3. El origen de datos ahora se desencadena para una actualización manual. Al actualizar un origen de datos, se actualizará tanto el esquema de la entidad como los datos para todas las entidades especificadas en el origen de datos.

4. Seleccione **Dejar de actualizar** si desea cancelar una actualización existente y el origen de datos volverá a su último estado de actualización.

## <a name="delete-a-data-source"></a>Eliminar un origen de datos

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales junto al origen de datos que desea quitar y seleccione **Eliminar** en la lista desplegable.

3. Confirme la eliminación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
