---
title: Exportar datos de Customer Insights a hosts SFTP (vista previa) (contiene vídeo)
description: Aprenda a configurar la conexión y a exportar a una ubicación de SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207250"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exportar datos a hosts de SFTP (versión preliminar)

Utilice los datos de sus clientes en aplicaciones de terceros exportándolos a una ubicación del protocolo seguro de transferencia de archivos (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Requisitos previos

- Disponibilidad de un host SFTP y las credenciales correspondientes.

## <a name="known-limitations"></a>Limitaciones conocidas

- Los destinos SFTP detrás de firewalls no son compatibles actualmente.
- El tiempo de ejecución de una exportación depende del rendimiento de su sistema. Recomendamos dos núcleos de CPU y 1 Gb de memoria como configuración mínima de su servidor.
- Hasta 100 millones de perfiles de clientes que pueden llevar 90 minutos cuando se utiliza la configuración mínima recomendada de dos núcleos de CPU y 1 Gb de memoria.
- Si utiliza una clave SSH para la autenticación, asegúrese de [crear su clave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) con formato PEM o SSH.COM. Si está utilizando Putty, convierta su clave privada exportándola como Open SSH. Se admiten los siguientes formatos de clave privada:
  - RSA en formato OpenSSL PEM y ssh.com
  - DSA en formato OpenSSL PEM y ssh.com
  - ECDSA 256/384/521 en formato OpenSSL PEM
  - ED25519 y RSA en formato de clave OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configurar conexiones para SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **SFTP**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Elija si desea autenticarse a través de SSH o nombre de usuario/contraseña para su conexión y proporcione los detalles necesarios. Si utiliza una clave SSH para la autenticación, asegúrese de [crear su clave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) con formato PEM o SSH.COM. Si está utilizando Putty, convierta su clave privada exportándola como Open SSH. Se admiten los siguientes formatos de clave privada:
   - RSA en formato OpenSSL PEM y ssh.com
   - DSA en formato OpenSSL PEM y ssh.com
   - ECDSA 256/384/521 en formato OpenSSL PEM
   - ED25519 y RSA en formato de clave OpenSSH

1. Seleccione **Verificar** para probar la conexión.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección SFTP. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Elija si desea exportar sus datos **comprimidos** o **descomprimidos** y el **delimitador de campo** para los archivos exportados.

1. Seleccione las entidades, por ejemplo segmentos, que desea exportar.

   > [!NOTE]
   > Cada entidad seleccionada se dividirá en un máximo de cinco archivos de salida cuando se exporten.

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> La exportación de entidades que contienen una gran cantidad de datos puede generar varios archivos CSV en la misma carpeta para cada exportación. La división de las exportaciones se produce por motivos de rendimiento para minimizar el tiempo que tarda en completarse una exportación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
