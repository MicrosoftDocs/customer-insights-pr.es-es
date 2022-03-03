---
title: Exportar datos de Customer Insights a Adobe Campaign Standard
description: Descubra cómo usar los segmentos de conclusiones del público en Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 6b90ee53236fdd601ecdfd8e6117a15269a08084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227779"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Use segmentos de Customer Insights en Adobe Campaign Standard (versión preliminar)

Como usuario de Audience Insights en Dynamics 365 Customer Insights, es posible que haya creado segmentos para hacer que sus campañas de marketing sean más eficientes al dirigirse a audiencias relevantes. Para usar un segmento de conclusiones del público en Adobe Experience Platform y aplicaciones como Adobe Campaign Standard, debe seguir algunos pasos descritos en este artículo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso de los pasos descritos en este artículo.":::

## <a name="prerequisites"></a>Requisitos previos

-   Licencia de Dynamics 365 Customer Insights
-   Licencia de Adobe Campaign Standard
-   Cuenta de Azure Blob Storage

## <a name="campaign-overview"></a>Información general de la campaña

Para comprender mejor cómo se pueden usar los segmentos de conclusiones del público en Adobe Experience Platform, veamos una campaña de muestra ficticia.

Supongamos que su empresa ofrece un servicio mensual por suscripción a sus clientes en los Estados Unidos. Desea identificar a los clientes cuyas suscripciones deben renovarse en los próximos ocho días pero que aún no han renovado su suscripción. Para mantener a estos clientes, desea enviarles una oferta promocional por correo electrónico, usando Adobe Campaign Standard.

En este ejemplo, queremos ejecutar la campaña de correo electrónico promocional una vez. Este artículo no cubre el caso de uso de ejecutar la campaña más de una vez. Sin embargo, las conclusiones del público y Adobe Campaign Standard se pueden configurar para que funcionen para un escenario de campaña recurrente.

## <a name="identify-your-target-audience"></a>Identifique su público objetivo

En nuestro escenario, asumimos que las direcciones de correo electrónico de los clientes están disponibles en información de público y sus preferencias promocionales fueron analizadas para identificar a los miembros del segmento.

El [segmento que definió en información de público](segments.md) se llama **ChurnProneCustomers** y planea enviar a estos clientes la promoción por correo electrónico.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla de la página de segmentos con el segmento ChurnProneCustomers creado.":::

El correo electrónico de oferta que desea enviar contendrá el nombre de pila, apellido y la fecha de finalización de la suscripción del cliente. Informa a los clientes sobre el descuento que obtendrán si renuevan su suscripción antes de que finalice.

## <a name="export-your-target-audience"></a>Exporte su público objetivo

### <a name="configure-a-connection"></a>Configurar una conexión

Con nuestro público objetivo identificado, podemos configurar la exportación desde información de público a una cuenta de Azure Blob Storage.

1. En Audience Insights, vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Adobe Campaign** para configurar la conexión o seleccione **Configurar** en el mosaico **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuración para Adobe Campaign Standard.":::

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Escriba el **Nombre de la cuenta**, la **Clave de cuenta**, y el **Contenedor** de la cuenta de Azure Blob Storage a la que desea exportar el segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla de la configuración de cuenta de almacenamiento. "::: 

   - Para obtener más información sobre cómo encontrar el nombre y la clave de cuenta de almacenamiento de blobs de Azure, consulte [Administrar la configuración de la cuenta de almacenamiento en Azure Portal](/azure/storage/common/storage-account-manage).

   - Para obtener información sobre cómo crear un contenedor, consulte [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccione **Guardar** para completar la conexión.

### <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una nueva exportación, **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Adobe Campaign. Si no ve el nombre de esta sección, es porque no tiene disponibles conexiones de este tipo.

1. Elija el segmento que desea exportar. En este ejemplo, es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla de la interfaz de usuario de selección de segmento con el segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Siguiente**.

1. Ahora asignamos los campos **Origen** del segmento de conclusiones del público a los nombres del campo **Destino** en el esquema de perfil de Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campo para el conector de Adobe Campaign Standard.":::

   Si desea agregar más atributos, seleccione **Agregar atributo**. El nombre del destino puede ser diferente del nombre del campo de origen para que pueda asignar los resultados de los segmentos de conclusiones del público a Adobe Campaign Standard si los campos no tienen el mismo nombre en dos sistemas.

   > [!NOTE]
   > La dirección de correo electrónico se usa como un campo de identidad, pero puede usar cualquier otro identificador de su perfil de cliente de conclusiones del público para asignar datos a Adobe Campaign Standard.

1. Seleccione **Guardar**.

Después de guardar el destino de la exportación, lo encontrará en **Datos** > **Exportaciones**.

Ahora puede [exportar el segmento bajo demanda](export-destinations.md#run-exports-on-demand). La exportación también se ejecutará con cada [actualización programada](system.md).

> [!NOTE]
> Asegúrese de que el número de registros en el segmento exportado esté dentro del límite permitido de su licencia de Adobe Campaign Standard.

Los datos exportados se almacenan en el contenedor Azure Blob Storage que configuró anteriormente. La siguiente ruta de carpeta se crea automáticamente en su contenedor:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Ejemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar Adobe Campaign Standard

Cuando se exporta un segmento de información de público, contiene las columnas que seleccionó al definir el destino de exportación en el paso anterior. Estos datos se pueden usar para [crear perfiles en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para usar el segmento en Adobe Campaign Standard, debemos ampliar el esquema de perfil de Adobe Campaign Standard para incluir dos campos adicionales. Aprenda cómo [ampliar el recurso del perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con nuevos campos en Adobe Campaign Standard.

En nuestro ejemplo, estos campos son *Nombre del segmento y Fecha del segmento (opcional)*.

Usaremos estos campos para identificar los perfiles de Adobe Campaign Standard a los que queremos dirigirnos para esta campaña.

Si no hay otros registros en Adobe Campaign Standard, aparte de los que va a importar, puede omitir este paso.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar datos en Adobe Campaign Standard

Ahora que todo está en su sitio, tenemos que importar los datos del público preparados a partir de la información sobre el público a Adobe Campaign Standard para crear perfiles. Aprenda [cómo importar perfiles en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando un flujo de trabajo.

El flujo de trabajo de importación en la imagen a continuación se configuró para ejecutarse cada ocho horas y buscar segmentos de Audience Insights exportados (archivo .csv en Azure Blob Storage). El flujo de trabajo extrae el contenido del archivo .csv en un orden de columna específico. Este flujo de trabajo se ha creado para realizar una gestión básica de errores y garantizar que cada registro tenga una dirección de correo electrónico antes de hidratar los datos en Adobe Campaign Standard. El flujo de trabajo también extrae el nombre del segmento del nombre del archivo antes de insertarlo en los datos del perfil de Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla de un flujo de trabajo de importación en la interfaz de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperar el público en Adobe Campaign Standard

Cuando los datos se hayan importado a Adobe Campaign Standard, [podrá crear un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) y [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) los clientes basándose en el *Nombre de segmento* y la *Fecha del segmento* para seleccionar perfiles que se identificaron para nuestra campaña de muestra.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear y enviar el correo electrónico usando Adobe Campaign Standard

Cree el contenido del correo electrónico y luego [pruebe y envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) su correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ejemplo de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
