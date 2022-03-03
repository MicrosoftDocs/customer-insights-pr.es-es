---
title: Solicitudes de interesados (DSR) en virtud del RGPD | Microsoft Docs
description: Responder a las solicitudes de los interesados en relación con la capacidad de informaciones de público para Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350290"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes del interesado (DSR) en el contexto del RGPD

El Reglamento General de Protección de Datos (RGPD) de la Unión Europea está en vigor desde el 25 de mayo de 2018. Otorga derechos importantes a las personas con respecto a sus datos. El RGPD versa sobre la protección y habilitación de los derechos de privacidad de las personas. Puede leer más sobre el compromiso de Microsoft con la seguridad y el cumplimiento en el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Nos comprometemos a ayudar a que nuestros clientes cumplan sus requisitos del RGPD. Incluye el derecho a eliminar y exportar datos que incluyen información personal, como el Id. de usuario, los números de teléfono y las direcciones de correo electrónico. Los administradores pueden implementar las solicitudes de los usuarios para eliminar o exportar datos personales.

## <a name="audience-insights"></a>Conclusiones del público

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Respuesta a las solicitudes de eliminación de los interesados del RGPD en relación con la capacidad de informaciones de público para Dynamics 365 Customer Insights

El "derecho a la eliminación" de datos personales de los datos de los clientes de una organización es una protección clave en el Reglamento general de protección de datos (RGPD). La eliminación de los datos personales incluye la eliminación de todos los datos personales y registros generados por el sistema, excepto la información del registro de auditoría.

#### <a name="manage-data-subject-delete-requests"></a>Administrar solicitudes de eliminación de interesados

Las informaciones de público ofrecen las siguientes experiencias en el producto para eliminar datos personales de un cliente o usuario específico:

- **Administrar solicitudes de eliminación de datos de clientes**: los datos de clientes de Customer Insights se procesan de orígenes de datos originales externos a Customer Insights. Todas las solicitudes de eliminación del RGPD deben realizarse en el origen de datos original.
- **Gestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Customer Insights crea los datos de los usuarios. Todas las solicitudes de eliminación del RGPD deben realizarse en Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrar solicitudes de eliminación de datos de clientes

Un administrador de Customer Insights puede seguir estos pasos para quitar datos del cliente que se eliminaron en el origen de datos:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. En informaciones de público, vaya a **Datos** > **Orígenes de datos**
3. Para cada origen de datos de la lista que contiene datos de clientes eliminados:
   1. Seleccione (...) y después **Actualizar**.
   2. Compruebe el estado del origen de datos en **Estado**. Una marca de verificación significa que la actualización se realizó correctamente. Un triángulo de advertencia significa que algo salió mal. Si se muestra un triángulo de advertencia, póngase en contacto con D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Administrar solicitudes de eliminación de datos de clientes del RGPD.](audience-insights/media/gdpr-data-sources.png "Administrar solicitudes de eliminación de datos de clientes del RGPD")

##### <a name="manage-delete-requests-for-user-data"></a>Administrar solicitudes de eliminación de datos de usuarios

Un administrador de Customer Insights puede seguir estos pasos para eliminar los datos de clientes de Customer Insights:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. En informaciones de público, vaya a **Administración** > **Permisos**.
3. Active la casilla del usuario que desee eliminar.
4. Seleccione **Quitar**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a las solicitudes de exportación del interesado de acuerdo con el RGPD

Como parte de nuestro compromiso de colaborar con usted en su viaje hacia el Reglamento General de Protección de Datos (RGPD), hemos desarrollado documentación para ayudarle a prepararse. Esta documentación describe los pasos que puede seguir hoy para respaldar el cumplimiento del RGPD al usar las informaciones de público.

#### <a name="manage-export-and-view-requests"></a>Administrar solicitudes de exportación y visualización

El derecho de la portabilidad de datos no permite a los interesados solicitar una copia de sus datos personales en formato electrónico (definido como “formato estructurado, de uso frecuente, de lectura mecánica e interoperable") que se puede transmitir a otro responsable de los datos.

##### <a name="export-customer-data-tenant-admin"></a>Exportar datos de clientes (administración de inquilinos)

Un administrador de inquilinos puede seguir estos pasos para exportar datos:

1. Envíe un correo electrónico de D365CI@microsoft.com especificando la dirección de correo electrónico del cliente en la solicitud. El equipo de Customer Insights enviará un correo electrónico a la dirección de correo electrónico del administrador del inquilino registrado, solicitando confirmación para exportar los datos.
2. Acepte la confirmación para exportar los datos del cliente solicitado.
3. Reciba los datos exportados a través de la dirección de correo electrónico del administrador del inquilino.

##### <a name="export-user-data-tenant-admin"></a>Exportar datos de usuarios (administrador de inquilinos)

1. Envíe un correo a D365CI@microsoft.com especificando la dirección de correo electrónico del usuario en la solicitud. El equipo de Customer Insights enviará un correo electrónico a la dirección de correo electrónico del administrador del inquilino registrado, solicitando confirmación para exportar los datos.
2. Acepte la confirmación para exportar los datos del usuario solicitado.
3. Reciba los datos exportados a través de la dirección de correo electrónico del administrador del inquilino.

## <a name="consent-management-preview"></a>Administración de consentimientos (vista previa)

La capacidad de gestión del consentimiento no recopila datos del usuario directamente. Solo importa y procesa los datos de consentimiento proporcionados por los usuarios en otras aplicaciones.

Para eliminar datos de consentimiento sobre usuarios específicos, elimínelos en las fuentes de datos ingeridas a la capacidad de gestión de consentimiento. Después de actualizar el origen de datos, los datos eliminados también se eliminarán en el Centro de consentimiento. Las aplicaciones que utilizan la entidad de consentimiento también eliminarán los datos que se eliminaron en la fuente después de una [actualización](audience-insights/system.md#refresh-processes). Recomendamos actualizar las fuentes de datos rápidamente después de responder a una solicitud del interesado para eliminar los datos del usuario de todos los demás procesos y aplicaciones.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]