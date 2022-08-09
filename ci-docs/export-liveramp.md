---
title: Exportar segmentos a LiveRamp (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196737"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos a LiveRamp&reg; (versión preliminar)

Active sus datos en LiveRamp para conectarse con más de 500 plataformas en ecosistemas digitales, sociales y de televisión. Trabaje con sus datos en LiveRamp para orientar, suprimir y personalizar las campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

- Una suscripción a LiveRamp para usar este conector. Para obtener una suscripción, puede ponerse en [contacto con LiveRamp](https://liveramp.com/contact/) directamente. [Más información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitaciones conocidas

- La exportación de LiveRamp utiliza una exportación SFTP. Los destinos SFTP detrás de firewalls no son compatibles actualmente.
- Si utiliza una clave SSH para la autenticación, asegúrese de [crear su clave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) con formato PEM o SSH.COM. Si está utilizando Putty, convierta su clave privada exportándola como Open SSH. Se admiten los siguientes formatos de clave privada:
  - RSA en formato OpenSSL PEM y ssh.com
  - DSA en formato OpenSSL PEM y ssh.com
  - ECDSA 256/384/521 en formato OpenSSL PEM
  - ED25519 y RSA en formato de clave OpenSSH
- El tiempo de ejecución de una exportación depende del rendimiento de su sistema. Recomendamos dos núcleos de CPU y 1 Gb de memoria como configuración mínima de su servidor.
- Exportar entidades con hasta 100 millones de perfiles de clientes puede prolongarse durante 90 minutos cuando se utiliza la configuración mínima recomendada de dos núcleos de CPU y 1 Gb de memoria.
- El número real de perfiles de clientes (o datos) que puede exportar a LiveRamp depende de su suscripción a LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configurar conexión a LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **LiveRamp**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Elija si desea autenticarse a través de SSH o nombre de usuario/contraseña para su conexión y proporcione los detalles necesarios.

1. Seleccione **Comprobar** para probar la conexión a LiveRamp.

1. Tras la verificación correcta, revise la [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección LiveRamp. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. En el campo **Conectar datos**, seleccione **Correo electrónico**, **Nombre y dirección** o **Teléfono** para enviar estos datos a LiveRamp para la resolución de identidad.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Conector para LiveRamp con asignación de atributos.":::

1. Asigne los atributos correspondientes de su entidad *Cliente* para el identificador de clave seleccionado.

1. Seleccione **Agregar atributo** para asignar más atributos para enviar a LiveRamp.

   > [!TIP]
   > Es probable que el envío de más atributos de identificador clave a LiveRamp le proporcione una tasa de coincidencia más alta.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
