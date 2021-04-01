---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar la conexión a un host SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598406"
---
# <a name="connector-for-sftp-preview"></a>Conector para SFTP (vista previa)

Use sus datos de clientes en aplicaciones de terceros exportándolos de forma segura a un servidor a través del protocolo seguro de transferencia de archivos (SFTP).

## <a name="prerequisites"></a>Requisitos previos

- Disponibilidad de un host SFTP y las credenciales correspondientes.

## <a name="connect-to-sftp"></a>Conectarse a SFTP

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **SFTP**, seleccione **Configurar**.

1. Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.

1. Proporcione un **Nombre de usuario**, una **Contraseña**,un **Nombre de host** y una **Carpeta de exportación** para su cuenta SFTP.

1. Seleccione **Verificar** para probar la conexión.

1. Después de una verificación exitosa, elija si desea exportar sus datos **comprimidos** o **descomprimidos** y seleccione el **delimitador de campo** para los archivos exportados.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Siguiente** para comenzar a configurar la exportación.

## <a name="configure-the-export"></a>Configurar la exportación

1. Seleccione las entidades, por ejemplo segmentos, que desea exportar.

   > [!NOTE]
   > Cada entidad seleccionada generará hasta cinco archivos de salida cuando se exporta. 

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitaciones conocidas

- El tiempo de ejecución de una exportación depende del rendimiento de su sistema. Recomendamos dos núcleos de CPU y 1 Gb de memoria como configuración mínima de su servidor. 
- Exportar entidades con hasta 100 millones de perfiles de clientes puede prolongarse durante 90 minutos cuando se utiliza la configuración mínima recomendada de dos núcleos de CPU y 1 Gb de memoria. 

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a través de SFTP, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que el destino de exportación cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]