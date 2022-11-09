---
title: Exporte segmentos a Iterable (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724625"
---
# <a name="export-segments-to-iterable-preview"></a>Exporte segmentos a Iterable (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a Iterable y utilícelos para actividades de marketing.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de Iterable](https://iterable.com/) y las credenciales de Administrador correspondientes.
- Una [Clave de API de Iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- No se admite el enlace privado en combinación con Traiga su propio almacenamiento (BYOS).
- Hasta 1 millón de perfiles de clientes a Iterable, lo que puede tardar hasta 30 minutos en completarse. El número de perfiles de clientes que puede exportar a Iterable depende de su contrato con Iterable.
- Solo segmentos.

## <a name="set-up-connection-to-iterable"></a>Configure la conexión con Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Iterable**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione su Clave de API de Iterable para continuar iniciando sesión.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión desde la sección Iterable. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. La lista creada en Iterable recibirá exactamente el mismo nombre que el nombre de su segmento en Dynamics 365 Customer Insights.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
