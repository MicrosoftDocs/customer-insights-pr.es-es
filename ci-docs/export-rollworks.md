---
title: Exportar segmentos a RollWorks (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195633"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportar segmentos a RollWorks (versión preliminar)

Exporte segmentos de perfiles de clientes unificados a RollWorks y utilícelos para actividades de publicidad.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de RollWorks](https://www.rollworks.com/) y las credenciales de administrador correspondientes.
- Un [Id. de anunciante de RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmentos configurados](segments.md) en Customer Insights.
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 250 000 perfiles de clientes por exportación a RollWorks, lo que puede tardar hasta 10 minutos en completarse. El número de perfiles de clientes que puede exportar a RollWorks depende de su contrato con RollWorks.
- Solo segmentos.

## <a name="set-up-connection-to-rollworks"></a>Configurar conexión a RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **RollWorks**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión.  De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Autenticar con RollWorks** y proporcione sus credenciales de administrador para RollWorks.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección RollWorks. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Especifique su **Id. de anunciante de RollWorks**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
