---
title: Configurar ajustes de seguridad
description: Aprenda sobre configuración de seguridad en Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387279"
---
# <a name="configure-security-settings"></a>Configurar ajustes de seguridad

Administrar claves de API, acceder a datos de clientes y configurar un Azure Private Link.

## <a name="manage-api-keys"></a>Administrar claves de API

Ver y administrar las claves para usar la [API de Customer Insights](apis.md) con los datos en su entorno.

1. Vaya a **Administración** > **Seguridad** y seleccione la pestaña **API**.

1. Si no se ha configurado el acceso de API al entorno, seleccione **Habilitar**. O, para bloquear el acceso de la API al entorno, seleccione **Deshabilitar** y confirme.

1. Administre las claves API primarias y secundarias:

   1. Para mostrar la clave de API principal o secundaria, seleccione el símbolo **Mostrar**.

   1. Para copiar la clave de API principal o secundaria, seleccione el símbolo **Copiar**.

   1. Para crear nuevas claves de API primarias o secundarias, seleccione **Regenerar primario** o **Regenerar secundario**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Acceder de forma segura a los datos del cliente con Caja de seguridad del cliente (versión preliminar)

Customer Insights usa la capacidad de Caja de seguridad del cliente de Power Platform. La Caja de seguridad del cliente proporciona una interfaz para revisar y aprobar (o rechazar) solicitudes de acceso a datos. Estas solicitudes ocurren cuando se necesita acceso a los datos del cliente para resolver un caso de soporte. Para utilizar esta función, Customer Insights debe tener una conexión existente a un entorno Microsoft Dataverse en su inquilino.

Para obtener más información sobre la caja de seguridad del cliente, consulte el [resumen](/power-platform/admin/about-lockbox#summary) de Caja de seguridad del cliente de Power Platform. El artículo también describe el [flujo de trabajo](/power-platform/admin/about-lockbox#workflow) y la [configuración](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) necesaria para habilitar la caja de seguridad del cliente.

> [!IMPORTANT]
> Administradores globales de Power Platform o administradores de Power Platform pueden aprobar las solicitudes de Caja de seguridad del cliente emitidas para Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configurar un Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview) permite a Customer Insights conectarse con su cuenta de Azure Data Lake Storage a través de un punto de conexión privado en su red virtual. Para los datos en una cuenta de almacenamiento, que no está expuesta a la Internet pública, Private Link permite la conexión a esa red restringida.

> [!IMPORTANT]
> Requisito mínimo de rol para configurar una conexión Private Link:
>
> - Customer Insights: Administrador
> - Rol integrado de Azure: [Cuenta de almacenamiento colaborador](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisos para el rol personalizado de Azure: [Microsoft.Storage/storageAccounts/read y Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. En Customer Insights, vaya a **Administración** > **Seguridad** y seleccione la pestaña **Private Links**.

1. Seleccione **Agregar Private Link**.

   El panel **Agregar Private Link** enumera las cuentas de almacenamiento de su arrendatario que tiene permisos para ver.

1. Seleccione la suscripción, el grupo de recursos y la cuenta de almacenamiento.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar**.

1. Vaya a su cuenta de Data Lake Storage y abra el vínculo presentado en la pantalla.

1. Apruebe el Private Link.


[!INCLUDE [footer-include](includes/footer-banner.md)]
