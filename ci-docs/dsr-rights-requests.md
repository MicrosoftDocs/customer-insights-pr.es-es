---
title: Solicitudes de interesados (DSR) en virtud del RGPD | Microsoft Docs
description: Responder a las solicitudes de interesados para Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 5b39452d7a4612242739e8000e57217954c71289
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641537"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes del interesado (DSR) en el contexto del RGPD

El Reglamento General de Protección de Datos (RGPD) de la Unión Europea está en vigor desde el 25 de mayo de 2018. Otorga derechos importantes a las personas con respecto a sus datos. El RGPD versa sobre la protección y habilitación de los derechos de privacidad de las personas. Puede leer más sobre el compromiso de Microsoft con la seguridad y el cumplimiento en el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Nos comprometemos a ayudar a que nuestros clientes cumplan sus requisitos del RGPD. Incluye el derecho a eliminar y exportar datos que incluyen información personal, como el Id. de usuario, los números de teléfono y las direcciones de correo electrónico. Los administradores pueden implementar las solicitudes de los usuarios para eliminar o exportar datos personales.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Responder a las solicitudes de eliminación de interesados del RGPD para Dynamics 365 Customer Insights.

El "derecho a la eliminación" de datos personales de los datos de los clientes de una organización es una protección clave en el Reglamento general de protección de datos (RGPD). La eliminación de los datos personales incluye la eliminación de todos los datos personales y registros generados por el sistema, excepto la información del registro de auditoría.

#### <a name="manage-data-subject-delete-requests"></a>Administrar solicitudes de eliminación de interesados

Customer Insights ofrece las siguientes experiencias del producto para eliminar datos personales para un cliente específico o un usuario:

- **Administrar solicitudes de eliminación de datos de clientes**: los datos de clientes de Customer Insights se procesan de orígenes de datos originales externos a Customer Insights. Todas las solicitudes de eliminación del RGPD deben realizarse en el origen de datos original.
- **Gestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Customer Insights crea los datos de los usuarios. Todas las solicitudes de eliminación del RGPD deben realizarse en Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrar solicitudes de eliminación de datos de clientes

Un administrador de Customer Insights puede seguir estos pasos para quitar datos del cliente que se eliminaron en el origen de datos:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Vaya a **Datos** > **Orígenes de datos**
3. Para cada origen de datos de la lista que contiene datos de clientes eliminados:
   1. Seleccione (...) y después **Actualizar**.
   2. Compruebe el estado del origen de datos en **Estado**. Una marca de verificación significa que la actualización se realizó correctamente. Un triángulo de advertencia significa que algo salió mal. Si se muestra un triángulo de advertencia, póngase en contacto con D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Administrar solicitudes de eliminación de datos de clientes del RGPD.](media/gdpr-data-sources.png "Administrar solicitudes de eliminación de datos de clientes del RGPD")

##### <a name="manage-delete-requests-for-user-data"></a>Administrar solicitudes de eliminación de datos de usuarios

Un administrador de Customer Insights puede seguir estos pasos para eliminar los datos de clientes de Customer Insights:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Vaya a **Administrador** > **Permisos**.
3. Active la casilla del usuario que desee eliminar.
4. Seleccione **Quitar**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a las solicitudes de exportación del interesado de acuerdo con el RGPD

Como parte de nuestro compromiso de colaborar con usted en su viaje hacia el Reglamento General de Protección de Datos (RGPD), hemos desarrollado documentación para ayudarle a responder a las solicitudes de sujetos de datos.

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

Para eliminar datos de consentimiento sobre usuarios específicos, elimínelos en las fuentes de datos ingeridas a la capacidad de gestión de consentimiento. Después de actualizar el origen de datos, los datos eliminados también se eliminarán en el Centro de consentimiento. Las aplicaciones que utilizan la entidad de consentimiento también eliminarán los datos que se eliminaron en la fuente después de una [actualización](system.md#refresh-processes). Recomendamos actualizar las fuentes de datos rápidamente después de responder a una solicitud del interesado para eliminar los datos del usuario de todos los demás procesos y aplicaciones.

[!INCLUDE [footer-include](includes/footer-banner.md)]