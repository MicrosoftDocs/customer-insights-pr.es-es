---
title: Power Automate conector (vista preliminar) | Microsoft Docs
description: Crear flujos en Microsoft Power Automate desde Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196139"
---
# <a name="power-automate-connector-preview"></a>Conector de Power Automate (vista previa)

Desencadene eventos específicos para que se produzcan automáticamente cuando cambien los datos y administre flujos más complejos directamente en [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitaciones conocidas

- Un máximo de 100 llamadas cada 60 segundos. Use el [parámetro $skip](/connectors/customerinsights/#get-items-from-an-entity) para llamar al punto de conexión de API varias veces.

## <a name="power-automate-triggers"></a>Desencadenadores de Power Automate

Utilice desencadenadores para crear flujos de nube y automatizar tareas repetitivas, como notificaciones o acciones más avanzadas. Usar desencadenadores cuando:

- La actualización de un origen de datos falla.
- La actualización de un origen de datos es correcta.
- Un umbral se rebasa en un segmento. El desencadenador se limita a cruzar por encima del umbral.
- Un umbral se rebasa en una medida empresarial. Solo se admiten medidas empresariales sin dimensión. El desencadenador se limita a cruzar por encima del umbral.
- Se completa una actualización completamente programada. Este disparador no funciona para actualizaciones iniciadas manualmente.
- Se completa una actualización del proceso de unificación.

[Configurar los desencadenadores en Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Acciones de Power Automate

El conector Power Automate proporciona otras acciones además de los desencadenantes disponibles. Para obtener más información, vea el [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Crea un flujo de Power Automate

1. Vaya a **Administrador** > **Conexiones**.

1. En el icono de **Power Automate**, seleccione **Configuración**.

1. Se abre el conector de Customer Insights (versión preliminar) en Power Automate. **Iniciar sesión** en Power Automate.

1. Elija uno de los desencadenadores disponibles y agregue más pasos a su nuevo flujo. Para obtener más información, consulte [Crear un flujo de nube en Power Automate](/power-automate/get-started-logic-flow).

Ejemplos de cómo utilizar los flujos: 
- Publique un mensaje en un canal de Microsoft Teams si falla una actualización origen de datos. 
- Envíe un correo electrónico a los propietarios de los datos cuando se cruce un umbral en un segmento.

[!INCLUDE [footer-include](includes/footer-banner.md)]
