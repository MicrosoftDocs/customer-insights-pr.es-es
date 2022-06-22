---
title: Configuración de seguridad Customer Insights
description: Aprenda sobre configuración de seguridad en Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947436"
---
# <a name="security-settings-in-customer-insights"></a>Configuración de seguridad Customer Insights

La página **Seguridad** enumera opciones para configurar permisos de usuario y características que ayudan a hacer Dynamics 365 Customer Insights más seguro. Solo los administradores pueden acceder a esta página.

Vaya a **Administración** > **Seguridad** para configurar los ajustes.

La página **Seguridad** incluye las siguientes pestañas:

- [Usuarios](#users-tab)
- [API](#apis-tab)
- [Vínculos privados](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Acceder de forma segura a los datos del cliente con Caja de seguridad del cliente (versión preliminar)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Pestaña Usuarios

El acceso a Customer Insights está restringido a los usuarios de su organización que un administrador agregó a la aplicación. La pestaña **Usuarios** le permite administrar el acceso de los usuarios y sus permisos. Para obtener más información, consulte [Permisos de usuario](permissions.md).

## <a name="apis-tab"></a>Pestaña API

Ver y administrar las claves para usar la [API de Customer Insights](apis.md) con los datos de su entorno.

Puede crear nuevas claves primarias y secundarias seleccionando **Regenerar primario** o **Regenerar secundario**. 

Para bloquear el acceso de la API al entorno, seleccione **Deshabilitar**. Si las API están deshabilitadas, puede seleccionar **Habilitar** para conceder acceso de nuevo.

## <a name="private-links-tab"></a>Pestaña Private Links

[Azure Private Link](/azure/private-link/private-link-overview) permite a Customer Insights conectarse con su cuenta de Azure Data Lake Storage a través de un punto de conexión privado en su red virtual. Para los datos en una cuenta de almacenamiento, que no está expuesta a la Internet pública, Private Link permite la conexión a esa red restringida.

> [!IMPORTANT]
> Requisito mínimo de rol para configurar una conexión Private Link:
>
> - Customer Insights: Administrador
> - Rol integrado de Azure: [Cuenta de almacenamiento colaborador](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisos para el rol personalizado de Azure: [Microsoft.Storage/storageAccounts/read y Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Configurar Private Link en Customer Insights es un proceso de dos pasos. Primero, inicia la creación de un Private Link desde **Administración** > **Seguridad** > **Enlaces privados** en Customer Insights. El panel **Agregar Private Link** enumera las cuentas de almacenamiento de su arrendatario que tiene permisos para ver. Seleccione la cuenta de almacenamiento y proporcione su consentimiento para crear el Private Link.

A continuación, debe aprobar el Private Link en el lado de la cuenta de Data Lake Storage. Abra el enlace presentado en pantalla para aprobar el nuevo Private Link.

## <a name="key-vault-tab"></a>Pestaña Key Vault

La pestaña **Key Vault** le permite vincular y administrar su propia [Azure Key Vault](/azure/key-vault/general/basic-concepts) al entorno.
El almacén de claes dedicado se puede utilizar para organizar y utilizar secretos en el límite de cumplimiento de una organización. Customer Insights puede usar los secretos de Azure Key Vault para [configurar conexiones](connections.md) a sistemas de terceros.

Para obtener más información, consulte [Traer su propia Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Acceder de forma segura a los datos del cliente con Caja de seguridad del cliente (versión preliminar)

Customer Insights está utilizando la capacidad de Caja de seguridad del cliente de Power Platform. La Caja de seguridad del cliente proporciona una interfaz para revisar y aprobar (o rechazar) solicitudes de acceso a datos. Estas solicitudes ocurren cuando se necesita acceso a los datos del cliente para resolver un caso de soporte. Para utilizar esta función, Customer Insights debe tener una conexión existente a un entorno Microsoft Dataverse en su inquilino.

Para obtener más información sobre la caja de seguridad del cliente, consulte el [resumen](/power-platform/admin/about-lockbox#summary) de Caja de seguridad del cliente de Power Platform. El artículo también describe el [flujo de trabajo](/power-platform/admin/about-lockbox#workflow) y la [configuración](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) necesaria para habilitar la caja de seguridad del cliente.

> [!IMPORTANT]
> Administradores globales de Power Platform o administradores de Power Platform pueden aprobar las solicitudes de Caja de seguridad del cliente emitidas para Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
