---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar la conexión a Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643794"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Conector para Dynamics 365 Marketing (versión preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use los [segmentos](segments.md) creados para generar campañas y contactar con grupos específicos de clientes con Dynamics 365 Marketing. Para obtener más información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Requisito previo

Registros de contactos [de Common Data Service ingeridos en Dynamics 365 Marketing](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>Configurar el conector para Marketing

1. En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.

1. En **Dynamics 365 Marketing**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

1. Introduzca la dirección URL de Marketing de su organización en el campo **Dirección del servidor**.

1. En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Marketing.

1. Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.

1. Seleccione **Siguiente**.

1. Elija uno o más segmentos.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).
