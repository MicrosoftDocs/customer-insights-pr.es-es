---
title: Traiga su propia Azure Key Vault (versión preliminar)
description: Aprenda a configurar Customer Insights para usar su propio Azure Key Vault para gestionar secretos.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246176"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traiga su propia Azure Key Vault (versión preliminar)

La vinculación de una [Azure Key Vault](/azure/key-vault/general/basic-concepts) dedicada a un entorno de Customer Insights ayuda a las organizaciones a cumplir los requisitos de cumplimiento.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Vincule el almacén de claves con el entorno de Customer Insights

Configure el almacén de claves dedicado para organizar y utilizar secretos en el límite de cumplimiento de una organización.

### <a name="prerequisites"></a>Requisitos previos

- Una suscripción de Azure activa.

- Un rol de [Administrador](permissions.md#admin) [asignado](permissions.md#add-users) en Customer Insights.

- Los roles [Colaborador](/azure/role-based-access-control/built-in-roles#contributor) y [Administrador de acceso de usuarios](/azure/role-based-access-control/built-in-roles#user-access-administrator) en el almacén de claves o en el grupo de recursos al que pertenece el almacén de claves. Para obtener más información, vaya a [Agregar o quitar asignaciones de roles de Azure mediante Azure Portal](/azure/role-based-access-control/role-assignments-portal). Si no tiene el rol Administrador de acceso de usuarios en el almacén de claves, configure los permisos de control de acceso basados en roles para la entidad de servicio de Azure para Dynamics 365 Customer Insights por separado. Siga los pasos para [usar una entidad de servicio de Azure](connect-service-principal.md) para el almacén de claves que debería estar vinculada.

- El almacén de claves debe tener el cortafuegos de Key Vault **deshabilitado**.

- El almacén de claves está en la misma [ubicación de Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que el entorno de Customer Insights. En Customer Insights, vaya a **Administrador** > **Sistema** y a la pestaña **Acerca de** para ver la región del entorno.

### <a name="recommendations"></a>Recomendaciones

- [Use un almacén de claves separado o dedicado](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) que contenga solo los secretos necesarios para Customer Insights.

- Siga las [prácticas recomendadas para usar Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para opciones de control de acceso, copia de seguridad, auditoría y recuperación.

### <a name="link-a-key-vault-to-the-environment"></a>Vincular un almacén de claves con el entorno

1. Vaya a **Administración** > **Seguridad** y, a continuación, seleccione la pestaña **Key Vault**.
1. En la ventana **Key Vault**, seleccione **Configuración**.
1. Elija una **Suscripción**.
1. Elija un almacén de claves de la lista desplegable **Key Vault**. Si hay demasiados almacenes de claves disponibles, seleccione un grupo de recursos para limitar los resultados de la búsqueda.
1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.
1. Seleccione **Guardar**.

La ventana **Key Vault** muestra el nombre del almacén de claves vinculado, la suscripción y el grupo de recursos. Está listo para usarse en la configuración de la conexión.
Para obtener detalles sobre qué permisos del almacén de claves se otorgan a Customer Insights, vaya a [Permisos otorgados en Key Vault](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilice el almacén de claves en la configuración de la conexión

Cuando [establezca conexiones](connections.md) con [sistemas de terceros compatibles](#supported-connection-types), use los secretos del Key Vault vinculado para configurar las conexiones.

1. Vaya a **Administrador** > **Conexiones**.
1. Seleccione **Agregar conexión**.
1. Para los tipos de conexión admitidos, dispone de un botón de alternancia **Usar Key Vault** si vinculó un almacén de claves.
1. En lugar de ingresar el secreto manualmente, elija el nombre secreto que apunta al valor secreto en el almacén de claves.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Panel de conexión con una conexión SFTP que usa un secreto de Key Vault.":::

1. Seleccione **Guardar** para crear la conexión.

## <a name="supported-connection-types"></a>Tipos de conexión admitidos

Se admiten las siguientes conexiones de [exportación](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Permisos concedidos en el almacén de claves

Los siguientes permisos se otorgan a Customer Insights en un almacén de claves vinculado si está habilitado [Directiva de acceso de Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o [Control de acceso basado en roles de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Directiva de acceso de Key Vault

| Tipo        | Permisos          |
| ----------- | -------------------- |
| Tecla         | [Obtener claves](/rest/api/keyvault/keys/get-keys/get-keys), [Obtener clave](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Secreto      | [Obtener secretos](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Obtener secreto](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificado | [Obtener certificados](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Obtener certificado](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Los valores anteriores son los mínimos para enumerar y leer durante la ejecución.

### <a name="azure-role-based-access-control"></a>Control de acceso basado en roles de Azure

Se agregarán los [roles de usuario Lector de Key Vault y Secretos de Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) para Customer Insights.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>¿Puede Customer Insights escribir secretos o sobrescribir secretos en el almacén de claves?

No. Solo los permisos de lectura y lista establecidos en la sección [permisos concedidos](#permissions-granted-on-the-key-vault) se otorgan a Customer Insights. El sistema no puede agregar, eliminar ni sobrescribir secretos en el almacén de claves. Esa es también la razón por la que no puede ingresar credenciales cuando una conexión usa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>¿Puedo cambiar una conexión que usa secretos de Key Vault por autenticación predeterminada?

N.º No puede volver a una conexión predeterminada después de haberla configurado utilizando un secreto de un almacén de claves vinculado. Cree una conexión aparte y elimine la anterior si ya no la necesita.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>¿Cómo puedo revocar el acceso a un almacén de claves para Customer Insights?

Si se ha habilitado [Directiva de acceso de Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o [Control de acceso basado en roles de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), elimine los permisos de la entidad de servicio `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` con el nombre `Dynamics 365 AI for Customer Insights`. Todas las conexiones que utilizan el almacén de claves dejarán de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un secreto que se usa en una conexión se eliminó del almacén de claves. ¿Qué puedo hacer?

Aparece una notificación en Customer Insights cuando ya no se puede acceder a un secreto configurado del almacén de claves. Habilite [eliminación temporal](/azure/key-vault/general/soft-delete-overview) en el almacén de claves para restaurar secretos si se eliminan accidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Una conexión no funciona, pero mi secreto está en el almacén de claves. ¿Cual puede ser la causa?

Aparece una notificación en Customer Insights cuando no puede acceder al almacén de claves. La causa podría ser:

- Se eliminaron los permisos para la entidad de servicio Customer Insights. Deben restaurarse manualmente.

- El firewall en el almacén de claves está habilitado. El firewall debe estar deshabilitado para que el almacén de claves sea accesible para Customer Insights nuevamente.
