---
title: Exportar segmentos a AdRoll (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724733"
---
# <a name="export-segments-to-adroll-preview"></a>Exportar segmentos a AdRoll (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a AdRoll y utilícelos para publicidad.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de AdRoll](https://www.adroll.com/) y las credenciales de administrador correspondientes.
- Un [Id. de anunciante de AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- No se admite el enlace privado en combinación con Traiga su propio almacenamiento (BYOS).
- Hasta 250 000 perfiles de clientes por exportación a AdRoll, lo que puede tardar hasta 10 minutos en completarse. La cantidad de perfiles de clientes que puede exportar a AdRoll depende de su contrato con AdRoll.
- Solo segmentos. Un segmento debe contener al menos 100 perfiles de clientes.

## <a name="set-up-connection-to-adroll"></a>Configurar la conexión a AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **AdRoll**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Autenticarse con AdRoll** y proporcione sus credenciales de administrador para AdRoll.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección AdRoll. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Especifique su **Id. de anunciante de AdRoll**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
