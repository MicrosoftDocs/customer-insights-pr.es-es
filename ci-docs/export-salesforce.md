---
title: Exportar datos a Salesforce Marketing Cloud (versión preliminar)
description: Aprenda a configurar la conexión y exportar a Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197059"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportar datos a Salesforce Marketing Cloud (versión preliminar)

Utilice los datos de sus clientes en Salesforce Marketing Cloud exportándolos a través de una ubicación de Protocolo seguro de transferencia de archivos (SFTP).

## <a name="prerequisites"></a>Requisitos previos

- Un[Host SFTP para Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) y las credenciales de administrador correspondientes.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configurar la conexión a Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Salesforce Marketing Cloud**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione un **Nombre de usuario**, una **Contraseña**,un **Nombre de host** y una **Carpeta de exportación** para su cuenta SFTP.

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

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar datos de Customer Insights desde una ubicación de SFTP a Salesforce Marketing Cloud

1. Cree [extensiones de datos en Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar el archivo de datos de Customer Insights desde la ubicación SFTP.

2. [Importar los datos de la ubicación SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) a la extensión de datos de Salesforce Marketing Cloud.

3. Configure la automatización para importar los datos a las extensiones de datos. Más información sobre [automatizaciones de colocación de archivos y automatizaciones programadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definir una [automatización de colocación de archivos](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) o una [automatización programada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

He aquí un ejemplo de [una automatización con SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
