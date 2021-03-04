---
title: Conector para Power Automate | Microsoft Docs
description: Cree flujos en Power Automate desde Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268845"
---
# <a name="power-automate-connector-preview"></a>Conector de Power Automate (vista previa)

Desencadene eventos específicos para que se produzcan automáticamente cuando cambien los datos y administre flujos más complejos directamente en [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Desencadenadores de Power Automate

Utilice desencadenadores para crear flujos de nube y automatizar tareas repetitivas, como notificaciones o acciones más avanzadas. 

- Desencadenador cuando falla una actualización de origen de datos. 
- Desencadenador cuando una actualización de origen de datos se realiza correctamente.
- Desencadenador cuando se cruza un umbral en un segmento. El desencadenador se limita a cruzar por encima del umbral.
- Desencadenador cuando se cruza un umbral en una medida empresarial. El desencadenador se limita a cruzar por encima del umbral.
- Desencadene cuando se completa una actualización (fuentes de datos, segmentos, medidas, ...).
- Se desencadena cuando se completa una actualización del proceso de unificación (mapa, coincidencia, fusión).

[Configurar los desencadenadores en Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Acciones de Power Automate
El conector Power Automate proporciona otras acciones además de los desencadenantes disponibles. Para obtener más información, vea el [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Crea un flujo de Power Automate

1. En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.

1. En el icono de **Power Automate**, seleccione **Configuración**.

1. Se abre el conector de Customer Insights (versión preliminar) en Power Automate. **Iniciar sesión** en Power Automate.

1. Elija uno de los desencadenadores disponibles y agregue más pasos a su nuevo flujo. Para obtener más información, consulte [Crear un flujo de nube en Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Ejemplos de cómo utilizar los flujos: 
- Publique un mensaje en un canal de Microsoft Teams si falla una actualización origen de datos. 
- Envíe un correo electrónico a los propietarios de los datos cuando se cruce un umbral en un segmento.



[!INCLUDE[footer-include](../includes/footer-banner.md)]