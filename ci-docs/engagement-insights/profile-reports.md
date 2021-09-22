---
title: Habilitar informes de perfil predefinidos
description: Cómo crear informes de perfil predefinidos agrupados por sexo, edad y condado o región de origen.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033973"
---
# <a name="out-of-box-profile-reports"></a>Informes de perfil predefinidos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe es una colección de visualizaciones que le ayudan a comprender el comportamiento de los usuarios. Al conectarse a las conclusiones del público de Customer Insights, las conclusiones sobre la interacción pueden mostrar un informe con información sobre perfiles de clientes unificados. Este informe incluye la cantidad de perfiles que tiene, agrupados por sexo, edad y ubicación geográfica.

## <a name="prerequisites"></a>Requisitos previos

El entorno de conclusiones del público debe almacenar datos en una cuenta de Azure Data Lake Storage gestionada por el cliente.

Si está utilizando una versión de prueba de la funcionalidad de las conclusiones del público o un entorno en un lago de datos administrado de Customer Insights, [póngase en contacto con nosotros](https://go.microsoft.com/fwlink/?linkid=2145734) para que le proporcionemos asistencia.  


## <a name="enable-the-customer-profile-report"></a>Habilitar el informe de perfil de cliente

Un administrador de entorno debe [crear una conexión con las conclusiones del público](configure-connections.md).

Después de especificar los detalles de la conexión, el administrador puede otorgar acceso a otras personas de la organización para que vean el informe. El administrador del entorno que configura la conexión tiene acceso automáticamente al informe. 

Después de completar la conexión, la funcionalidad **Perfiles** estará disponible en el panel de navegación izquierdo. 

- Vaya a **Descubrir** > **Perfiles** para ver el informe.

El informe **Perfiles** contiene visualizaciones sobre el sexo, la edad y la ubicación geográfica de los perfiles de clientes conectados.

:::image type="content" source="media/customer-profiles.png" alt-text="Informe del perfil del cliente.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]