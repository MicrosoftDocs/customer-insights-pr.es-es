---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar la conexión a un host SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643524"
---
# <a name="connector-for-sftp-preview"></a>Conector para SFTP (vista previa)

Use sus datos de clientes en aplicaciones de terceros exportándolos de forma segura a un servidor a través del protocolo seguro de transferencia de archivos (SFTP).

## <a name="prerequisites"></a>Requisitos previos

- Disponibilidad de un host SFTP y credenciales correspondientes.

## <a name="connect-to-sftp"></a>Conectarse a SFTP

1. Vaya a **Administración** > **Destinos de exportación**.

1. En **SFTP**, seleccione **Configurar**.

1. Asigne a su destino un nombre reconocible en el campo **Nombre para mostrar**.

1. Proporcione un **Nombre de usuario**, una **Contraseña** y un **Nombre de host** para su cuenta SFTP. Ejemplo: si la carpeta raíz de su servidor SFTP es /root/folder y desea que los datos se exporten a /root/folder/ci_export_destination_folder, el servidor debe ser sftp://<server_address>/ci_export_destination_folder".

1. Seleccione **Verificar** para probar la conexión.

1. Después de una verificación correcta, elija si desea exportar sus datos **Comprimidos** o **Descomprimidos** y seleccione el **delimitador de campo** para los archivos exportados.

1. Seleccione **Acepto** para confirmar **Privacidad y cumplimiento de datos**.

1. Seleccione **Siguiente** para comenzar a configurar la exportación.

## <a name="configure-the-connection"></a>Configurar la conexión

1. Seleccionar los **atributos de clientes** que desea exportar. Puede exportar uno o varios atributos.

1. Seleccione **Siguiente**.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**.

## <a name="export-the-data"></a>Exportar los datos

Puede [exportar datos a petición](export-destinations.md). La exportación también se ejecutará con cada [actualización programada](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a través de SFTP, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que el destino de exportación cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.
