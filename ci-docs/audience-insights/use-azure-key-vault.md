---
title: Traiga su propio Azure Key Vault para administrar secretos
description: Aprenda a configurar Customer Insights para usar su propio Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 5b22c1464b3f089551f485f98d6d93840ff77136
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355912"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traiga su propia Azure Key Vault (versión preliminar)

La vinculación de un [Azure key vault](/azure/key-vault/general/basic-concepts) dedicado a un entorno de conclusiones del público ayuda a las organizaciones a cumplir los requisitos de cumplimiento.
El almacén de claes dedicado se puede utilizar para organizar y utilizar secretos en el límite de cumplimiento de una organización. Conclusiones del público puede usar los secretos de Azure Key Vault para [configurar conexiones](connections.md) a sistemas de terceros.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Vincule el almacén de claves con el entorno de conclusiones del público

### <a name="prerequisites"></a>Requisitos previos

Para configurar el almacén de claves en conclusiones del público, se deben cumplir los siguientes requisitos previos:

- Debe disponer de una suscripción activa de Azure.

- Debe tener un rol de [Administrador](permissions.md#administrator) en los conocimientos del público. Más información acerca de [permisos de usuario en conclusiones del público](permissions.md#assign-roles-and-permissions).

- Tiene los roles [Colaborador](/azure/role-based-access-control/built-in-roles#contributor) y [Administrador de acceso de usuarios](/azure/role-based-access-control/built-in-roles#user-access-administrator) en el almacén de claves o en el grupo de recursos al que pertenece el almacén de claves. Para obtener más información, vaya a [Agregar o quitar asignaciones de roles de Azure mediante Azure Portal](/azure/role-based-access-control/role-assignments-portal). Si no tiene el rol Administrador de acceso de usuarios en el almacén de claves, debe configurar los permisos de control de acceso basados en roles para la entidad de servicio de Azure para Dynamics 365 Customer Insights por separado. Siga los pasos para [usar una entidad de servicio de Azure](connect-service-principal.md) para el almacén de claves que debería estar vinculada.

- El almacén de claves debe tener el cortafuegos de Key Vault **deshabilitado**.

- El almacén de claves está en la misma [ubicación de Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que el entorno de conclusiones del público. La región del entorno en conclusiones del público aparece en **Administración** > **Sistema** > **Acerca de** > **Región**.

### <a name="link-a-key-vault-to-the-environment"></a>Vincular un almacén de claves con el entorno

1. Vaya a **Administración** > **Sistema** y, a continuación, seleccione la pestaña **Seguridad**.
1. En la ventana **Key Vault**, seleccione **Configuración**.
1. Elija una **Suscripción**.
1. Elija un almacén de claves de la lista desplegable **Key Vault**. Si aparecen demasiados almacenes de claves, seleccione un grupo de recursos para limitar los resultados de la búsqueda.
1. Acepte la declaración de **Privacidad y cumplimiento de datos**.
1. Seleccione **Guardar**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Pasos para configurar un almacén de claves vinculado en conclusiones del público.":::

La ventana **Key Vault** muestra ahora el nombre del almacén de claves vinculado, el grupo de recursos y la suscripción. Está listo para usarse en la configuración de la conexión.
Para obtener detalles sobre qué permisos del almacén de claves se otorgan a conclusiones del público, vaya a [Permisos otorgados en el almacén de claves para conclusiones del público](#permissions-granted-on-the-key-vault-to-audience-insights), más adelante en este artículo.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilice el almacén de claves en la configuración de la conexión

Cuando [establezca conexiones](connections.md) con sistemas de terceros, los secretos del Key Vault vinculado se pueden utilizar para configurar las conexiones.

1. Vaya a **Administrador** > **Conexiones**.
1. Seleccione **Agregar conexión**.
1. Para los tipos de conexión admitidos, dispone de un botón de alternancia **Usar Key Vault** si vinculó un almacén de claves.
1. En lugar de ingresar el secreto manualmente, puede elegir el nombre secreto que apunta al valor secreto en el almacén de claves.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Panel de conexión con una conexión SFTP que usa un secreto de Key Vault.":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Permisos otorgados en el almacén de claves para conclusiones del público

Los siguientes permisos se otorgan a conclusiones del público en un almacén de claves vinculado si está habilitado [Directiva de acceso de Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o [Control de acceso basado en roles de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Directiva de acceso de Key Vault

| Tipo        | Permisos          |
| ----------- | -------------------- |
| Tecla         | [Obtener claves](/rest/api/keyvault/get-keys), [Obtener clave](/rest/api/keyvault/get-key)                                 |
| Secreto      | [Obtener secretos](/rest/api/keyvault/get-secrets), [Obtener secreto](/rest/api/keyvault/get-secret)                     |
| Certificado | [Obtener certificados](/rest/api/keyvault/get-certificates), [Obtener certificado](/rest/api/keyvault/get-certificate) |

Los valores anteriores son los mínimos para enumerar y leer durante la ejecución.

### <a name="azure-role-based-access-control"></a>Control de acceso basado en roles de Azure

Se agregarán los roles de usuario Lector de Key Vault y Secretos de Key Vault para conclusiones del público. Para obtener detalles sobre estos roles, vaya a [Roles integrados de Azure para operaciones del plano de datos de Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomendaciones

- Use un almacén de claves separado o dedicado que contenga solo los secretos necesarios para conclusiones del público. Leer más sobre por qué [se recomiendan almacenes de claves separados](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Siga las [prácticas recomendadas para usar Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para opciones de control de acceso, copia de seguridad, auditoría y recuperación.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>¿Puede conclusiones del público escribir secretos o sobrescribir secretos en el almacén de claves?

N.º Solo los permisos de lectura y lista establecidos en la sección [permisos concedidos](#permissions-granted-on-the-key-vault-to-audience-insights) anterior en este artículo se otorgan a conclusiones del público. El sistema no puede agregar, eliminar ni sobrescribir secretos en el almacén de claves. Esa es también la razón por la que no puede ingresar credenciales cuando una conexión usa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>¿Puedo cambiar una conexión que usa secretos de Key Vault por autenticación predeterminada?

N.º No puede volver a una conexión predeterminada después de haberla configurado utilizando un secreto de un almacén de claves vinculado. Cree una conexión aparte y elimine la anterior si ya no la necesita.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>¿Cómo puedo revocar el acceso a un almacén de claves para conclusiones del público?

Dependiendo de si está habilitada [Directiva de acceso de Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) o [Control de acceso basado en roles de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), debe eliminar los permisos de la entidad de servicio `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` con el nombre `Dynamics 365 AI for Customer Insights`. Todas las conexiones que utilizan el almacén de claves dejarán de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un secreto que se usa en una conexión se eliminó del almacén de claves. ¿Qué puedo hacer?

Aparece una notificación en conclusiones del público cuando ya no se puede acceder a un secreto configurado del almacén de claves. Habilite [eliminación temporal](/azure/key-vault/general/soft-delete-overview) en el almacén de claves para restaurar secretos si se eliminan accidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Una conexión no funciona, pero mi secreto está en el almacén de claves. ¿Cual puede ser la causa?

Aparece una notificación en conclusiones del público cuando no puede acceder al almacén de claves. La causa podría ser:

- Se eliminaron los permisos para la entidad de servicio conclusiones del público. Deben restaurarse manualmente.

- El firewall en el almacén de claves está habilitado. El firewall debe estar deshabilitado para que el almacén de claves sea accesible para conclusiones del público nuevamente.
