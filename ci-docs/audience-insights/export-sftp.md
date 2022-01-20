---
title: Exportar datos de Customer Insights a hosts SFTP (contiene vídeo)
description: Aprenda a configurar la conexión y a exportar a una ubicación de SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 542bd908010cf0a8ccc12f15d54e0a3d5b72f189
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934952"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Exportar segmentos y otros datos a SFTP (versión preliminar)

Utilice los datos de sus clientes en aplicaciones de terceros exportándolos a una ubicación del protocolo seguro de transferencia de archivos (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

- Disponibilidad de un host SFTP y las credenciales correspondientes.

## <a name="known-limitations"></a>Limitaciones conocidas

- Los destinos SFTP detrás de firewalls no son compatibles actualmente. 
- El tiempo de ejecución de una exportación depende del rendimiento de su sistema. Recomendamos dos núcleos de CPU y 1 Gb de memoria como configuración mínima de su servidor. 
- Exportar entidades con hasta 100 millones de perfiles de clientes puede prolongarse durante 90 minutos cuando se utiliza la configuración mínima recomendada de dos núcleos de CPU y 1 Gb de memoria. 

## <a name="set-up-connection-to-sftp"></a>Configurar conexiones para SFTP

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **SFTP** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione un **Nombre de usuario**, una **Contraseña**,un **Nombre de host** y una **Carpeta de exportación** para su cuenta SFTP.

1. Seleccione **Verificar** para probar la conexión.

1. Elija si desea exportar sus datos **comprimidos** o **descomprimidos** y el **delimitador de campo** para los archivos exportados.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección SFTP. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Seleccione las entidades, por ejemplo segmentos, que desea exportar.

   > [!NOTE]
   > Cada entidad seleccionada se dividirá en hasta cinco archivos de salida cuando se exporten. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a través de SFTP, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que el destino de exportación cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
