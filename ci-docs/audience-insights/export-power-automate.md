---
title: Conector para Power Automate | Microsoft Docs
description: Cree flujos en Power Automate desde Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407004"
---
# <a name="power-automate-connector-preview"></a>Conector de Power Automate (vista previa)

Desencadene eventos específicos para que se produzcan automáticamente cuando cambien los datos y administre flujos más complejos directamente en [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Desencadenadores de Power Automate

Puede usar una variedad de desencadenadores que le permiten crear flujos para automatizar tareas repetitivas, como notificaciones o acciones más avanzadas. 

- Desencadenador cuando falla una actualización de origen de datos. 
- Desencadenador cuando una actualización de origen de datos se realiza correctamente.
- Desencadenador cuando se cruza un umbral en un segmento. El desencadenador se limita a cruzar por encima del umbral.
- Desencadenador cuando se cruza un umbral en una medida empresarial. El desencadenador se limita a cruzar por encima del umbral.
- Desencadene cuando se completa una actualización (fuentes de datos, segmentos, medidas, ...).
- Se desencadena cuando se completa una actualización del proceso de unificación (mapa, coincidencia, fusión).

[Configurar los desencadenadores en Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Acciones de Power Automate
El conector Power Automate proporciona otras acciones además de los desencadenantes disponibles. Para obtener más información, vea el [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Crear un flujo de Power Automate en informaciones de público

1. En las informaciones de público, vaya a **Administrador** > **Sistema**.

1. En la página **Sistema**, seleccione la pestaña **Estado**.

1. En la sección **Orígenes de datos**, seleccione **Flujos** y **Crear un flujo** de la lista desplegable.
   > [!div class="mx-imgBorder"]
   > ![Conector de Power Automate que muestra la acción Crear un flujo](media/power-automate-connector-create-flow.png "Conector de Power Automate que muestra la acción Crear un flujo")

1. En Power Automate, seleccione uno de los desencadenadores disponibles para crear su flujo preferido. Si está creando su primer flujo, primero deberá autenticarse con el conector de Power Automate.
