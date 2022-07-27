---
title: Exportar segmentos a Adobe Experience Platform (vista previa)
description: Aprenda a usar segmentos de Customer Insights en Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052532"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportar segmentos a Adobe Experience Platform (vista previa)

Como usuario de Dynamics 365 Customer Insights, es posible que haya creado segmentos para hacer que sus campañas de marketing sean más eficientes al dirigirse a audiencias relevantes. Para utilizar un segmento de Customer Insights en Adobe Experience Platform y aplicaciones como Adobe Campaign Standard, debe seguir algunos pasos descritos en este artículo.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso de los pasos descritos en este artículo.":::

## <a name="prerequisites"></a>Requisitos previos

-   Licencia de Dynamics 365 Customer Insights
-   Licencia de Adobe Experience Platform
-   Licencia de Adobe Campaign Standard
-   Cuenta de Azure Blob Storage

## <a name="campaign-overview"></a>Información general de la campaña

Para comprender mejor cómo puede usar segmentos de Customer Insights en Adobe Experience Platform, veamos una campaña de muestra ficticia.

Supongamos que su empresa ofrece un servicio mensual por suscripción a sus clientes en los Estados Unidos. Desea identificar a los clientes cuyas suscripciones deben renovarse en los próximos ocho días pero que aún no han renovado su suscripción. Para mantener a estos clientes, desea enviarles una oferta promocional por correo electrónico, usando Adobe Experience Platform.

En este ejemplo, queremos ejecutar la campaña de correo electrónico promocional una vez. Este artículo no cubre el caso de uso de ejecutar la campaña más de una vez.

## <a name="identify-your-target-audience"></a>Identifique su público objetivo

En nuestro escenario, asumimos que las direcciones de correo electrónico de los clientes están disponibles en Customer Insights y sus preferencias promocionales se analizaron para identificar a los miembros del segmento.

Él [segmento que definió en Customer Insights](segments.md) se llama **ChurnProneCustomers** y planea enviar a estos clientes la promoción por correo electrónico.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la página de segmentos con el segmento ChurnProneCustomers creado.":::

El correo electrónico de oferta que desea enviar contendrá el nombre de pila, apellido y la fecha de finalización de la suscripción del cliente. Informa a los clientes sobre el descuento que obtendrán si renuevan su suscripción antes de que finalice.

## <a name="export-your-target-audience"></a>Exporte su público objetivo

Con nuestro objetivo audiencia identificado, podemos configurar la exportación de Customer Insights a una cuenta de Azure Blob Storage.

### <a name="configure-a-connection"></a>Configurar una conexión

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Azure Blob Storage** para configurar la conexión o seleccione **Configurar** en la ventana **Azure Blob Storage** para configurar la conexión.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuración para Azure Blob Storage."::: 

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escriba el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para la cuenta de Blob Storage a la que desea exportar el segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuración de cuenta de almacenamiento. "::: 
   
    - Para obtener más información sobre cómo encontrar el nombre y la clave de la cuenta de Blob Storage, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).
    - Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccione **Guardar** para completar la conexión. 

### <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Azure Blob Storage. Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.

1. Elija el segmento que desea exportar. En este ejemplo, es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfaz de usuario de selección de segmento con el segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Guardar**.

Después de guardar el destino de la exportación, lo encontrará en **Datos** > **Exportaciones**.

Ahora puede [exportar el segmento bajo demanda](export-destinations.md#run-exports-on-demand). La exportación también se ejecutará con cada [actualización programada](system.md).

> [!NOTE]
> Asegúrese de que el número de registros en el segmento exportado esté dentro del límite permitido de su licencia de Adobe Campaign Standard.

Los datos exportados se almacenan en el contenedor Azure Blob Storage que configuró anteriormente. La siguiente ruta de carpeta se crea automáticamente en su contenedor:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

El *model.json* para las entidades exportadas reside en el nivel *%ExportDestinationName%*.

Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir el modelo de datos de experiencia (XDM) en Adobe Experience Platform

Antes de que los datos exportados de Customer Insights se puedan usar en Adobe Experience Platform, necesitamos definir el esquema del modelo de datos de experiencia y [configurar los datos para el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Más información sobre [qué es XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) y entender los [conceptos básicos de la composición del esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar datos a Adobe Experience Platform

Ahora que todo está en su lugar, necesitamos importar los datos audiencia preparados de Customer Insights a Adobe Experience Platform.

Primero, [cree una conexión de origen de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Después de definir la conexión de origen, [configure un flujo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para una conexión por lotes de almacenamiento en la nube para importar la salida del segmento de Customer Insights a Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crear un público en Adobe Campaign Standard

Para enviar el correo electrónico de esta campaña, usaremos Adobe Campaign Standard. Después de importar los datos a Adobe Experience Platform, debemos [crear un público](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaign Standard usando los datos de Adobe Experience Platform.


Aprenda cómo [usar el generador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) en Adobe Campaign Standard para definir un público basándose en los datos de Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear y enviar el correo electrónico usando Adobe Campaign Standard

Cree el contenido del correo electrónico y luego [pruebe y envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) su correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ejemplo de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
