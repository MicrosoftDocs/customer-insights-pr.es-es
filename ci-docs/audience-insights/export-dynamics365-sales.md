---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar la conexión a Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643839"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector para Dynamics 365 Sales (versión preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use sus datos de clientes para crear listas de marketing, realizar un seguimiento de los flujos de trabajo y enviar promociones con Dynamics 365 Sales.

## <a name="prerequisite"></a>Requisito previo

Registros de contactos [de Common Data Service ingeridos en Dynamics 365 Sales](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>Configurar el conector para Sales

1. En las informaciones del público, vaya a **Administrador** > **Destinos de exportación**.

1. En **Dynamics 365 Sales**, seleccione **Configurar**.

1. Asigne a su destino de exportación un nombre reconocible en el campo **Nombre para mostrar**.

1. Introduzca la dirección URL de Sales de su organización en el campo **Dirección del servidor**.

1. En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Sales.

1. Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.

1. Seleccione **Siguiente**.

1. Elija uno o más segmentos.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).
