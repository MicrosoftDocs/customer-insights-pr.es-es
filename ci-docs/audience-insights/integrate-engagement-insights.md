---
title: Integrar datos web a partir de información sobre la participación con las informaciones de público
description: Transmita información web sobre los clientes, desde la información sobre la participación hasta las informaciones de público.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033790"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrar datos web a partir de información sobre la participación con las informaciones de público

Los clientes suelen realizar sus transacciones diarias en línea a través de sitios web. La función de conocimientos sobre la interactuación (vista previa) en Dynamics 365 Customer Insights es una solución práctica para integrar los datos web como origen. Además de los datos transaccionales, demográficos o de comportamiento, podemos ver actividades en la web en perfiles de clientes unificados. Podemos usar estos perfiles para obtener conocimientos adicional como segmentos, medidas o predicciones para la activación de público.

En este artículo se describen los pasos para transmitir los datos de la actividad web de sus clientes de la información sobre participación a su entorno existente de informaciones de público.

En este ejemplo, partimos de la base de un entorno que contiene perfiles de clientes unificados. Los perfiles se unificaron con fuentes a partir de encuestas, ventas minoristas y un sistema de emisión de entradas. También muestra las actividades relacionadas de los clientes. 

Ahora queremos saber si un cliente visita nuestras propiedades web y comprende sus actividades. Las actividades incluyen, por ejemplo, sitios web visitados o páginas de productos visualizadas desde un enlace recibido en un correo electrónico.

## <a name="prerequisites"></a>Requisitos previos

Para integrar los datos a partir de la información sobre la participación, se deben cumplir algunos requisitos previos: 

- Integre el SDK de información sobre la participación en su sitio web. Para obtener más información, consulte [Información general para desarrolladores](../engagement-insights/developer-resources.md).
- La exportación de eventos web a partir de conocimientos sobre la interactuación requiere acceso a una cuenta de Azure Data Lake Storage que se utilizará para ingerir los datos de eventos web en Audience Insights. Para obtener más información, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurar eventos refinados en la información sobre participación

Después de que un administrador instrumente un sitio web con el SDK de estadísticas de interactuación, se recopilan *eventos base* cuando un usuario ve una página web o hace clic en algún lugar. Los eventos básicos suelen contener numerosos detalles. Dependiendo de su caso de uso, solo necesitará un subconjunto de los datos en un evento básico. Las estadísticas de participación le permiten crear *eventos refinados* que contienen solo las propiedades de un evento básico que seleccione.     

Para obtener más información, consulte [Crear y modificar eventos refinados](../engagement-insights/refined-events.md).

Consideraciones al crear eventos refinados: 

- Proporcione un nombre descriptivo para el evento refinado. Se utilizará como nombre de actividad en Audiencia Insights.
- Seleccione al menos las siguientes propiedades para crear una actividad en las informaciones de público: 
    - Signal.Action.Name: indica los detalles de la actividad.
    - Signal.User.Id: se usa para asignarse con el Id. de cliente.
    - Signal.View.Uri: se usa como dirección web como base para segmentos o medidas.
    - Signal.Export.Id: se utiliza como clave principal para eventos.
    - Signal.Timestamp: determina la fecha y hora de la actividad de la actividad.

Seleccione los filtros para centrarse en los eventos y las páginas que son importantes para su caso de uso. En este ejemplo, usaremos el nombre de la acción "Promoción por correo electrónico".

## <a name="export-the-refined-web-events"></a>Exportar los eventos web refinados 

Después de definir el evento refinado, debe configurar la exportación de los datos del evento a Azure Data Lake Storage, que se puede configurar como origen de datos para la ingesta en Audience Insights. Las exportaciones se producen constantemente a medida que los eventos fluyen desde la propiedad web.

Para obtener más información, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Ingerir datos de eventos para informaciones de público

Ahora que ha definido el evento refinado y configurado su exportación, pasamos a la ingesta de datos en informaciones de público. Debe crear un nuevo origen de datos basado en una carpeta de Common Data Model. Especifique los detalles de la cuenta de almacenamiento a la que exporta los eventos. En el archivo *default.cdm.json*, seleccione el evento refinado para ingerir y crear la entidad en las informaciones de público.

Para más información, vea [Conectarse a una carpeta de Common Data Model mediante una cuenta de Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relacionar los datos de eventos refinados como una actividad de un perfil de cliente

Después de completar la ingesta de la entidad, puede configurar la actividad para el perfil del cliente.

Para obtener más información, consulte [Actividades del cliente](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Página de actividades con el panel Editar actividad expandido y los campos completados.":::

Configure la nueva actividad con la siguiente asignación: 

- **Clave primaria**: Signal.Export.Id, un identificador único que está disponible para cada registro de eventos en la información sobre participación. Esta propiedad se genera automáticamente.

- **Marca de tiempo**: Signal.Timestamp en la propiedad del evento.

- **Evento**: Signal.Name, nombre del evento que desea rastrear.

- **Dirección web**: Signal.View.Uri se refiere a la URI de la página que creó el evento.

- **Detalles**: Signal.Action.Name para representar la información a asociar con el evento. La propiedad seleccionada en este caso indica que el evento es para promoción por correo electrónico.

- **Tipo de actividad**: en este ejemplo, elegimos el WebLog del tipo de actividad existente. Esta selección es una opción de filtro útil para ejecutar modelos de predicción o crear segmentos basados en este tipo de actividad.

- **Definir relación**: este importante parámetro vincula la actividad a los perfiles de clientes existentes. **Signal.User.Id** es el identificador configurado en el SDK que se recopilará y que se relaciona con el identificador de usuario en otras fuentes de datos que se configuran en las informaciones de público. En este ejemplo, configuramos la relación entre Signal.User.Id y RetailCustomers:CustomerRetailId, que es la clave principal que se identificó en el paso de la asignación del proceso de unificación de datos.

Después de procesar las actividades, puede revisar los registros de los clientes y abrir una tarjeta de cliente para ver las actividades a partir de la información sobre participación en la escala de tiempo. 

> [!TIP]
> Para encontrar un identificador de cliente que tenga una actividad de información sobre participación, vaya a **Entidades** y obtenga una vista previa de los datos para la entidad UnifiedActivity. ActivityTypeDisplay = WebLog contiene la actividad de los conocimientos sobre la interactuación configurada en el ejemplo anterior. Copie el identificador del cliente para uno de esos registros y para ese identificador en la página **Clientes**.

## <a name="next-steps"></a>Pasos siguientes

Ahora puede crear [segmentos](segments.md), [medidas](measures.md) y [predicciones](predictions.md) para establecer una conexión significativa con sus clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
