---
title: Solicitudes de interesados (DSR) en virtud del RGPD | Microsoft Docs
description: Responder a las solicitudes de interesados para Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387132"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes del interesado (DSR) en el contexto del RGPD

El Reglamento General de Protección de Datos (RGPD) de la Unión Europea está en vigor desde el 25 de mayo de 2018. Otorga derechos importantes a las personas con respecto a sus datos. El RGPD versa sobre la protección y habilitación de los derechos de privacidad de las personas. Lea más sobre el compromiso de Microsoft con la seguridad y el cumplimiento en el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Nos comprometemos a ayudar a que nuestros clientes cumplan sus requisitos del RGPD. Incluye el derecho a eliminar o exportar datos que incluyen información personal, como el Id. de usuario, los números de teléfono y las direcciones de correo electrónico. Los administradores pueden implementar las solicitudes de los usuarios para eliminar o exportar datos personales.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Respuesta a las solicitudes de eliminación de datos del RGPD para Customer Insights

El "derecho a la eliminación" de datos personales de los datos de los clientes de una organización es una protección clave en el Reglamento general de protección de datos (RGPD). La eliminación de los datos personales incluye la eliminación de todos los datos personales y registros generados por el sistema, excepto la información del registro de auditoría.

### <a name="manage-data-subject-delete-requests"></a>Administrar solicitudes de eliminación de interesados

Customer Insights ofrece las siguientes experiencias del producto para eliminar datos personales para un cliente específico o un usuario:

- **Administrar solicitudes de eliminación de datos de clientes**: los datos de clientes de Customer Insights se procesan de orígenes de datos originales externos a Customer Insights. Primero ejecute las solicitudes de eliminación del RGPD en el origen de datos.
- **Gestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Customer Insights crea los datos de los usuarios. Resuelva todas las solicitudes de eliminación del RGPD en Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Administrar solicitudes de eliminación de datos de clientes

Como administrador de Customer Insights, quite los datos del cliente de Customer Insights que se eliminaron en el origen de datos. Verifique que las solicitudes de eliminación del RGPD se hayan hecho en el origen de datos original.

1. Inicie sesión en Dynamics 365 Customer Insights.

1. Vaya a **Datos** > **Orígenes de datos**.

1. Para cada origen de datos de la lista que contiene datos de clientes eliminados:
   1. Seleccione el origen de datos y, luego, seleccione **Actualizar**.
   1. Compruebe el estado del origen de datos en **Estado**. Una marca de verificación significa que la actualización se realizó correctamente. Un triángulo de advertencia significa que algo salió mal. Si se muestra un triángulo de advertencia, póngase en contacto con D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Administrar solicitudes de eliminación de datos de clientes del RGPD.":::

1. Después de una actualización correcta de los orígenes de datos, ejecute también las actualizaciones posteriores. Especialmente, si no tiene programada una actualización completa periódica de Customer Insights.

   > [!IMPORTANT]
   > Los segmentos estáticos no se incluyen en una actualización completa ni en la ejecución de actualizaciones posteriores después de una solicitud de eliminación. Para asegurarse de que los datos del cliente también se eliminen de los segmentos estáticos, vuelva a crear los segmentos estáticos con los datos de origen actualizados.

#### <a name="manage-delete-requests-for-user-data"></a>Administrar solicitudes de eliminación de datos de usuarios

Como administrador de Customer Insights, elimine los datos de usuario de Customer Insights.

1. Inicie sesión en Dynamics 365 Customer Insights.

1. Vaya a **Administración** > **Seguridad** > y seleccione la pestaña **Usuarios**.

1. Active la casilla de los usuarios que desee eliminar.

1. Seleccione **Quitar**.

1. Confirme la eliminación.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a las solicitudes de exportación del interesado de acuerdo con el RGPD

El derecho de la portabilidad de datos no permite a los interesados solicitar una copia de sus datos personales en formato electrónico (definido como “formato estructurado, de uso frecuente, de lectura mecánica e interoperable") que se puede transmitir a otro responsable de los datos.

### <a name="manage-export-and-view-requests"></a>Administrar solicitudes de exportación y visualización

Administre las solicitudes para exportar clientes o datos de usuario.

#### <a name="export-customer-data-tenant-admin"></a>Exportar datos de clientes (administración de inquilinos)

Como administrador del inquilino, exporte datos de cliente.

1. Envíe un correo electrónico de D365CI@microsoft.com especificando la dirección de correo electrónico del cliente en la solicitud. El equipo de Customer Insights enviará un correo electrónico a la dirección de correo electrónico del administrador del inquilino registrado, solicitando confirmación para exportar los datos.
2. Acepte la confirmación para exportar los datos del cliente solicitado.
3. Reciba los datos exportados a través de la dirección de correo electrónico del administrador del inquilino.

#### <a name="export-user-data-tenant-admin"></a>Exportar datos de usuarios (administrador de inquilinos)

Como administrador del inquilino, exporte datos de usuario.

1. Envíe un correo a D365CI@microsoft.com especificando la dirección de correo electrónico del usuario en la solicitud. El equipo de Customer Insights envía un correo electrónico a la dirección de correo electrónico del administrador del inquilino registrado, solicitando confirmación para exportar los datos.
1. Acepte la confirmación para exportar los datos del usuario solicitado.
1. Reciba los datos exportados a través de la dirección de correo electrónico del administrador del inquilino.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Manejo de eliminación de datos en Dynamics 365 Customer Insights

Los datos se eliminan (particiones de datos e instantáneas de datos) si las particiones de datos y las instantáneas de datos están inactivas durante más de 30 días, lo que significa que han sido reemplazadas por una nueva partición de datos e instantáneas a través de una actualización de los orígenes de datos.

No se eliminan todos los datos y las instantáneas. La partición de datos y la instantánea de datos más recientes están activas porque se usan en Customer Insights. Para los datos más recientes, no importa si los orígenes de datos no se actualizaron en los últimos 30 días.

[!INCLUDE [footer-include](includes/footer-banner.md)]
