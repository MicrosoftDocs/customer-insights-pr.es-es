---
title: Configuración de seguridad en Dynamics 365 Customer Insights
description: Aprenda sobre configuración de seguridad en Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653733"
---
# <a name="security-overview-page"></a>Página de información general sobre seguridad

La página **Seguridad** enumera opciones para configurar permisos de usuario y características que ayudan a hacer Dynamics 365 Customer Insights más seguro. Solo los administradores pueden acceder a esta página. 

Vaya a **Administración** > **Seguridad** para configurar los ajustes.

La página **Seguridad** incluye las siguientes pestañas:
- [Usuarios](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Pestaña Usuarios

El acceso a Customer Insights está restringido a los usuarios de su organización que un administrador agregó a la aplicación. La pestaña **Usuarios** le permite administrar el acceso de los usuarios y sus permisos. Para obtener más información, consulte [Permisos de usuario](permissions.md).

## <a name="apis-tab"></a>Pestaña API

Ver y administrar las claves para usar la [API de Customer Insights](apis.md) con los datos de su entorno.

Puede crear nuevas claves primarias y secundarias seleccionando **Regenerar primario** o **Regenerar secundario**. 

Para bloquear el acceso de la API al entorno, seleccione **Deshabilitar**. Si las API están deshabilitadas, puede seleccionar **Habilitar** para conceder acceso de nuevo.

## <a name="key-vault-tab"></a>Pestaña Key Vault

La pestaña **Key Vault** le permite vincular y administrar su propia [Azure Key Vault](/azure/key-vault/general/basic-concepts) al entorno.
El almacén de claes dedicado se puede utilizar para organizar y utilizar secretos en el límite de cumplimiento de una organización. Customer Insights puede usar los secretos de Azure Key Vault para [configurar conexiones](connections.md) a sistemas de terceros.

Para obtener más información, consulte [Traer su propia Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
