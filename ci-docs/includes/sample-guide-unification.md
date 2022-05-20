---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755565"
---
Después de ingerir los datos, comience el proceso de unificación de datos para crear un perfil de cliente unificado. Para obtener más información, consulte [Unificación de datos](../data-unification.md).

### <a name="select-source-fields"></a>Seleccionar campos de origen

1. Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes. Vaya a **Datos** > **Unificar**.

1. Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**.

   ![unificar las fuentes de datos de comercio electrónico y fidelización.](../media/unify-ecommerce-loyalty.png)

1. Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.

1. Seleccione **Siguiente**. Saltar registros duplicados y seleccionar **Siguiente**.

### <a name="match-conditions"></a>Condiciones coincidentes

1. Escoja **eCommerceContacts : eCommerce** como la entidad principal e incluir todos los registros.

1. Escoja **loyCustomers : LoyaltyScheme** e incluya todos los registros.

1. Agregar una regla:
   - Seleccione **FullName** tanto para eCommerceContacts como para loyCustomers.
   - Seleccione **Tipo (Teléfono, Nombre, Dirección, ...)** para **Normalizar**.
   - Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.
   - Introduzca el nombre **FullName, Email** para el nombre.

1. Agregue una segunda condición para la dirección de correo electrónico:
   - Seleccione **Correo electrónico** tanto para eCommerceContacts como para loyCustomers.
   - Deje Normalizar en blanco.
   - Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.

   ![Unifique la regla de coincidencia para el nombre y el correo electrónico.](../media/unify-match-rule.png)

1. Seleccione **Listo**.

1. Seleccione **Siguiente**.

### <a name="unify-fields"></a>Unificar campos

1. Renombre **ContactId** para la entidad **loyCustomers** a **ContactIdLOYALTY** para diferenciarlo de los otros ID ingeridos.

1. Seleccione **Siguiente** para revisar y luego seleccione **Crear perfiles de clientes**.
