---
title: Exportar segmentos a Sendinblue (versión preliminar)
description: Aprenda a configurar la conexión y exportar a Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724915"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segmentos a Sendinblue (versión preliminar)

Exportar segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y aprovechar grupos específicos de clientes con Sendinblue.

## <a name="prerequisites"></a>Requisitos previos

- Una [cuenta de Sendinblue](https://www.sendinblue.com/) y las credenciales de administrador correspondientes.
- Una [Clave de API de SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Listas existentes en Sendinblue y los id. correspondientes.
- [Segmentos configurados](segments.md).
- Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- No se admite el enlace privado en combinación con Traiga su propio almacenamiento (BYOS).
- Hasta 1 millón de perfiles de clientes por exportación a Sendinblue, lo que puede tardar hasta 90 minutos en completarse. El número de perfiles de clientes que puede exportar a Sendinblue depende de su contrato con Sendinblue.
- Solo segmentos.

## <a name="set-up-connection-to-sendinblue"></a>Configurar la conexión a Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Sendinblue**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique su **Clave de API de SendinBlue**.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectar** para inicializar la conexión.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Sendinblue. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Indique su **Id. de lista de Sendinblue**.

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente.

1. Opcionalmente, puede exportar **Nombre de pila**, **Apellido** y **Teléfono** para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
