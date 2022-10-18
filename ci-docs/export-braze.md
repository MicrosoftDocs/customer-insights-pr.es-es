---
title: Exporte segmentos a Braze (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655283"
---
# <a name="export-segments-to-braze-preview"></a>Exporte segmentos a Braze (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Braze y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta Braze](https://www.braze.com/) y las credenciales de Administrador correspondientes.
- Una [Clave de API de Braze](https://www.braze.com/docs/api/basics/)
- Su [punto de conexión Braze REST](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico y una Id. de cliente de Braze.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles de clientes de Braze, lo que puede tardar hasta 40 minutos en completarse. La cantidad de perfiles de clientes que puede exportar a Braze depende de su contrato con Braze.
- Solo segmentos.
- Azure Private Link no es compatible con la exportación de Braze.

## <a name="set-up-connection-to-braze"></a>Configure la conexión a Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Braze**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione su Clave de API de Braze para continuar iniciando sesión.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión desde la sección Braze. Contacte con un administrador si no hay conexión disponible.

1. Ingrese su punto de conexión Rest en el campo **nombre de host** en el siguiente formato: `rest.iad-03.braze.com`.

1. Escriba un nombre para la exportación.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. En el campo **Id. de cliente** seleccione el campo que representa el Id. de Braze del cliente. Los segmentos en Braze se crearán con el mismo nombre del segmento que en Dynamics 365 Customer Insights. Puede elegir más campos opcionales adicionales para datos coincidentes.

1. Seleccione las entidades o segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
