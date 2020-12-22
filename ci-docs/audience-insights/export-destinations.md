---
title: Destinos de exportación
description: Exporte datos y administre destinos de exportación.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643884"
---
# <a name="export-destinations-preview"></a>Destinos de exportación (vista previa)

La página **Destinos de exportación** muestra todas las ubicaciones que ha configurado como destino de exportación de datos. También puede agregar nuevos destinos para exportación. Además, muestra las opciones de exportación disponibles actualmente. Obtenga información general rápida, una descripción y descubra lo que puede hacer con cada opción de extensibilidad. Exporte perfiles, medidas y segmentos unificados a aplicaciones compatibles relevantes para su negocio.

Vaya a **Administración** > **Exportar destinos** para encontrar las siguientes opciones de extensibilidad:

- [Complemento de tarjeta de cliente de Dynamics 365](customer-card-add-in.md)
- [Conector de administrador de anuncios de Facebook](export-facebook.md)
- [Power Automateconector](export-power-automate.md)
- [Power Appsconector](export-power-apps.md)
- [Power BIconector](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 for Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Conector LiveRamp &reg;](export-liveramp.md)
- [Bot para Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Agregar un nuevo destino de exportación

Para agregar destinos de exportación, tiene [permisos de administrador](permissions.md). Si exporta a servicios de Microsoft, suponemos que ambos servicios están en la misma organización.

1. Vaya a **Administración** > **Destinos de exportación**.

1. Pase a la pestaña **Mis destinos de exportación**.

1. Seleccione **Agregar destino** para crear un nuevo destino de exportación.

1. En el panel **Agregar destino**, seleccione el **Tipo** de destino de exportación en el menú desplegable.

1. Proporcione los detalles necesarios y seleccione **Siguiente** para crear el destino de exportación.

También puede seleccionar **Configurar** en un icono de la pestaña **Descubrir**.

## <a name="view-export-destinations"></a>Ver destinos de exportación

Una vez creados los destinos de exportación, los verá en una tabla de la pestaña **Mis destinos de exportación**. Esta tabla tiene tres columnas:

- **Nombre para mostrar**: el nombre que ha introducido al crear el destino.
- **Tipo**: el tipo de destino de exportación que estableció al crear el destino.
- **Creado**: la fecha en la que creó el destino.

## <a name="edit-an-export-destination"></a>Editar un destino de exportación

1. Seleccione los puntos suspensivos verticales del destino de exportación que desea editar.

   > [!div class="mx-imgBorder"]
   > ![Puntos suspensivos verticales](media/export-destinations-page-ellipsis.png "Puntos suspensivos verticales")

1. Seleccione **Editar** en el menú desplegable.

1. Cambie los valores que requieren actualización y seleccione **Guardar**.

## <a name="export-data-on-demand"></a>Exportar datos a petición

Tras configurar un conector para un destino de exportación, las exportaciones se ejecutarán en cada [actualización programada](system.md#schedule-tab).

Para exportar datos sin esperar una actualización programada, vaya a la pestaña **Mis destinos de exportación** en **Administración** > **Destinos de exportación**.

> [!div class="mx-imgBorder"]
> ![Puntos suspensivos verticales](media/export-destinations-page-ellipsis.png "Puntos suspensivos verticales")

- Seleccione **Exportar** encima de la lista para ejecutar simultáneamente la exportación a todos los destinos de exportación.
- Seleccione los puntos suspensivos (...) que se muestran a continuación de un elemento de la lista y después elija la opción **Exportar** para ejecutar la exportación para un solo destino de exportación.

## <a name="remove-an-export-destination"></a>Quitar un destino de exportación

Para quitar un destino de exportación, empiece desde la página principal **Exportar destinos**.

1. Seleccione los puntos suspensivos verticales para el destino de exportación que desea quitar.

   > [!div class="mx-imgBorder"]
   > ![Puntos suspensivos verticales](media/export-destinations-page-ellipsis.png "Puntos suspensivos verticales")

2. Seleccione **Quitar** del menú desplegable.

3. Confirme la eliminación seleccionando **Quitar** en la pantalla de confirmación.
