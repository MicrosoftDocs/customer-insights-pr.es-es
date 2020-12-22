---
title: Usar orígenes de datos para ingerir datos
description: Aprenda a importar datos desde distintos orígenes.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643974"
---
# <a name="overview-about-data-sources"></a>Descripción general sobre orígenes de datos

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

La capacidad de información de público de Dynamics 365 Customer Insights se conecta a datos de un amplio conjunto de orígenes. Conectarse a un origen de datos a menudo se conoce como el proceso de *ingesta de datos*. Después de ingerir los datos, puede [unificar](data-unification.md) y actuar sobre ellos.

## <a name="add-a-data-source"></a>Agregar un origen de datos

Consulte los artículos detallados sobre cómo agregar un origen de datos, según la opción que elija.

Puede agregar un origen de datos de tres formas principales:

- [A través de decenas de conectores de Power Query](connect-power-query.md)
- [Desde una carpeta de Common Data Model](connect-common-data-model.md)
- [Desde su propio lago de Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Todavía no puede agregar datos de orígenes de datos locales.

## <a name="review-ingested-data"></a>Revisar datos ingeridos

Podrá ver el nombre de cada origen de datos ingeridos, su estado y la última vez que se actualizaron los datos para ese origen. Puede ordenar la lista de orígenes de datos por cada columna.

> [!div class="mx-imgBorder"]
> ![Origen de datos agregado](media/configure-data-datasource-added.png "Origen de datos agregado")

|Estado  |Descripción  |
|---------|---------|
|Operación correcta   |El origen de datos se ingirió correctamente si se menciona una hora en la columna **Actualizado**.
|Sin iniciar   |El origen de datos aún no tiene datos ingeridos o sigue en modo de borrador.         |
|Actualizando    |La ingesta de datos está en curso. Para cancelar esta operación, seleccione **Detener la actualización** en la columna **Acciones**. Si se detiene la actualización de un origen de datos, se revertirá a su último estado de actualización.       |
|Con errores     |Se han producido errores al ingerir datos.         |

Seleccione **Actualizar estado** para revisar más detalles sobre el estado de actualización, incluidos los detalles del error y las actualizaciones del proceso posterior.

La carga de datos puede tardar bastante tiempo. Una vez completada una actualización, se pueden revisar los datos ingeridos en la página **Entidades**. Para obtener más información, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Actualizar un origen de datos

Los orígenes de datos se pueden actualizar de forma automática o manualmente, a petición. 

Vaya a **Administrador** > **Sistema** > [**Programación**](system.md#schedule-tab) para configurar actualizaciones programadas de todos sus orígenes de datos ingeridos.

Para actualizar un origen de datos a petición, siga estos pasos:

1. En informaciones de público, vaya a **Datos** > **Orígenes de datos**

2. Seleccione los puntos suspensivos verticales junto al origen de datos que desea actualizar y seleccione **Actualizar** en la lista desplegable.

3. El origen de datos ahora se desencadena para una actualización manual. Actualizar un origen de datos actualizará tanto el esquema de entidad como los datos de todas las entidades especificadas en el origen de datos.

4. Seleccione **Dejar de actualizar** si desea cancelar una actualización existente y el origen de datos volverá a su último estado de actualización.

## <a name="delete-a-data-source"></a>Eliminar un origen de datos

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Seleccione los puntos suspensivos verticales junto al origen de datos que desea quitar y seleccione **Eliminar** desde el menú desplegable.

3. Confirme la eliminación.
