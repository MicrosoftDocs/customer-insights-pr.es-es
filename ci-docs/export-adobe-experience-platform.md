---
title: Exportar segmentos a Adobe Experience Platform (vista previa)
description: Aprenda a usar segmentos de Customer Insights en Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195311"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportar segmentos a Adobe Experience Platform (vista previa)

Exporte segmentos dirigidos a públicos relevantes para Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso de los pasos descritos en este artículo.":::

## <a name="prerequisites"></a>Requisitos previos

- Una licencia de Adobe Experience Platform.
- Una licencia de Adobe Campaign Standard.
- Un nombre y clave de [cuenta de Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar el nombre y la clave, consulte [Gestionar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).
- Un [contenedor de Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Configuraremos la exportación de Customer Insights a una cuenta de Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Configurar la conexión a Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Azure Blob Storage**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escriba el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** para la cuenta de Blob Storage a la que desea exportar el segmento.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuración de cuenta de almacenamiento. ":::

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

### <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Azure Blob Storage. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Elija el segmento que desea exportar. En este ejemplo, es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfaz de usuario de selección de segmento con el segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Guardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Asegúrese de que el número de registros en el segmento exportado esté dentro del límite permitido de su licencia de Adobe Campaign Standard.

Los datos exportados se almacenan en el contenedor de Azure Blob Storage que configuró. Las siguientes rutas de acceso a carpetas se crean automáticamente en el contenedor:

- Para entidades fuente y entidades generadas por el sistema:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- El *model.json* para las entidades exportadas reside en el nivel *%ExportDestinationName%*.

  Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir el modelo de datos de experiencia (XDM) en Adobe Experience Platform

Antes de que los datos exportados de Customer Insights se puedan usar en Adobe Experience Platform, defina el esquema del modelo de datos de experiencia y [configure los datos para el perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Más información sobre [qué es XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) y entender los [conceptos básicos de la composición del esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar datos a Adobe Experience Platform

Importe los datos de público preparados de Customer Insights a Adobe Experience Platform.

1. [Cree una conexión de origen de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Configure un flujo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para una conexión por lotes de almacenamiento en la nube para importar la salida del segmento de Customer Insights a Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crear un público en Adobe Campaign Standard

Para enviar el correo electrónico de esta campaña, usaremos Adobe Campaign Standard.

1. [Cree un público](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaign Standard usando los datos de Adobe Experience Platform.

1. [Use el generador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) de Adobe Campaign Standard para definir un público basándose en los datos de Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear y enviar el correo electrónico usando Adobe Campaign Standard

Cree el contenido del correo electrónico y luego [pruebe y envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) su correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ejemplo de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
