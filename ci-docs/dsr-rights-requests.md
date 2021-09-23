---
title: Solicitudes de interesados (DSR) en virtud del RGPD | Microsoft Docs
description: Responder a las solicitudes de los interesados en relación con la capacidad de informaciones de público para Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483710"
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

## <a name="engagement-insights"></a>Conclusiones sobre la interacción

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Eliminar y exportar datos de eventos que contienen información identificable del usuario final

Las siguientes secciones describen cómo eliminar y exportar datos de eventos que pueden contener datos personales.

Para eliminar o exportar datos:

1. Etiquete las propiedades de los eventos que contienen datos con información personal.
2. Elimine o exporte datos asociados con valores específicos (por ejemplo: un Id. de usuario específico).

#### <a name="tag-and-update-event-properties"></a>Etiquetar y actualizar propiedades de eventos

Los datos personales se etiquetan a nivel de propiedad del evento. Primero, etiquete las propiedades que se quieren eliminar o exportar.

Para etiquetar una propiedad de evento como que contiene información personal, siga estos pasos:

1. Abra el área de trabajo que contiene el evento.

1. Ir a **Datos** > **Eventos** para ver la lista de eventos en el área de trabajo seleccionado.
  
1. Seleccione el evento que desea etiquetar.

1. Seleccione **Editar propiedades** para abrir el panel que enumera todas las propiedades del evento seleccionado.
     
1. Seleccione **...** y luego **Editar** para llegar al diálogo **Actualizar la propiedad**.

   ![Editar evento.](engagement-insights/media/edit-event.png "Editar evento")

1. En la ventana **Actualizar propiedad**, elija **...** en la esquina superior derecha y luego seleccione el cuadro **Contiene IIUF**. Elija **Actualizar** para guardar los cambios.

   ![Guarda los cambios.](engagement-insights/media/update-property.png "Guarde los cambios")

   > [!NOTE]
   > Cada vez que cambia el esquema del evento o crea un nuevo evento, se recomienda que evalúe las propiedades del evento asociado y las etiquete o las desetiquete como que contienen datos personales, si es necesario.

#### <a name="delete-or-export-tagged-event-data"></a>Eliminar o exportar datos de eventos etiquetados

Si todas las propiedades del evento se han etiquetado correctamente como se describe en el paso anterior, un administrador del entorno puede emitir una solicitud de eliminación de los datos del evento etiquetado.

Para gestionar solicitudes de exportación o eliminación de IIUF

1. Vaya a **Administración** > **Entorno** > **Configuración**.

1. En la sección **Gestionar la información identificable del usuario final (IIUF)**, seleccione **Gestionar IIUF**.

##### <a name="deletion"></a>Eliminación

Para proceder con la eliminación, puede ingresar una lista de Id. de usuario separados por comas en la sección **Eliminar la información identificable del usuario final (IIUF)**. Estos Id. luego se compararán con todas las propiedades de eventos etiquetados de todos los proyectos en el entorno actual mediante la coincidencia exacta de cadenas. 

Si el valor de una propiedad coincide con uno de los Id. proporcionados, el evento asociado se eliminará de forma permanente. Debido a la irreversibilidad de esta acción, debe confirmar la eliminación después de seleccionar **Eliminar**.

##### <a name="export"></a>Export

El proceso de exportación es idéntico al proceso de eliminación cuando se trata de definir valores de propiedad de eventos en la sección **Exportar información identificable del usuario final (IIUF)**. Además, deberá proporcionar una **URL de almacenamiento de blobs de Azure** para especificar el destino de la exportación. La URL de Azure Blob debe incluir una [Firma de acceso compartido (SAS)](/azure/storage/common/storage-sas-overview).

Después de seleccionar **Exportar**, todos los eventos del equipo actual que contienen propiedades etiquetadas coincidentes se exportarán en formato CSV al destino de exportación.

### <a name="good-practices"></a>Prácticas recomendadas

* Trate de evitar enviar eventos que contengan datos personales.
* Si necesita enviar eventos que contienen datos IIUF, limite el número de eventos y propiedades de eventos que contienen datos IIUF. Idealmente, limítese a uno de esos eventos.
* Asegúrese de que el menor número posible de personas tenga acceso a los datos personales enviados.
* Para los eventos que contienen datos personales, asegúrese de establecer una propiedad para que emita un identificador único que pueda vincularse fácilmente a un usuario específico (por ejemplo, un Id. de usuario). Esto facilita la segregación de datos y la exportación o eliminación de los datos correctos.
* Solo etiquete una propiedad por evento que contenga datos personales. Idealmente, uno que solo contenga un identificador único.
* No etiquete propiedades que contengan valores detallados (por ejemplo, un cuerpo de solicitud completo). La capacidad de conclusiones sobre la interacción utiliza la coincidencia exacta de cadenas al decidir qué eventos eliminar o exportar.

[!INCLUDE[footer-include](includes/footer-banner.md)]