---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar la conexión a Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269029"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector para Dynamics 365 Sales (versión preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use sus datos de clientes para crear listas de marketing, realizar un seguimiento de los flujos de trabajo y enviar promociones con Dynamics 365 Sales.

## <a name="prerequisite"></a>Requisito previo

1. Los registros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales. Más información sobre cómo ingerir contactos en [Dynamics 365 Sales usando Common Data Services](connect-power-query.md).

   > [!NOTE]
   > La exportación de segmentos de las informaciones de público a Sales no creará nuevos registros de contactos en las instancias de Sales. Los registros de contacto de Sales deben ingerirse en las informaciones de público y usarse como origen de datos. También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]