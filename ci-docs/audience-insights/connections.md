---
title: Conexiones a otros servicios de Customer Insights.
description: Comparta datos con otros servicios.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3689c7016454ed44e22b4d4ff5a338836a8fe288
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605970"
---
# <a name="connections-preview-overview"></a>Información general sobre conexiones (versión preliminar)

Las conexiones son la clave para permitir el intercambio de datos desde y hacia Customer Insights. Cada conexión establece el intercambio de datos con un servicio específico. Las conexiones son la base para [configurar enriquecimientos de terceros](enrichment-hub.md) y [configurar exportaciones](export-destinations.md). La misma conexión se puede utilizar varias veces. Por ejemplo, una conexión para Dynamics 365 Marketing funciona para varias exportaciones y una conexión Leadspace se puede usar para varios enriquecimientos.

Vaya a **Administración** > **Conexiones** para crear y ver conexiones.

La pestaña **Conexiones** muestra todas las conexiones activas. La lista muestra una fila para cada conexión. 

Obtenga una descripción general rápida y descubra lo que puede hacer con cada opción de extensibilidad en la pestaña **Descubrir**.

### <a name="exports"></a>Exportaciones

Solo los administradores pueden configurar nuevas conexiones, pero pueden otorgar acceso a los colaboradores para que usen las conexiones existentes. Los administradores controlan dónde pueden ir los datos, los colaboradores definen la carga útil y la frecuencia según sus necesidades. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Enriquecimientos

Solo los administradores pueden configurar nuevas conexiones, pero las conexiones creadas siempre están disponibles tanto para administradores como para colaboradores. Los administradores gestionan las credenciales y dan su consentimiento para las transferencias de datos. Las conexiones pueden ser utilizadas para enriquecimiento tanto por parte de administradores como por parte de colaboradores.

## <a name="add-a-new-connection"></a>Agregar una nueva conexión

Para agregar conexiones, debe tener [permisos de administrador](permissions.md). Si se conecta a otros servicios de Microsoft, damos por hecho que ambos servicios están en la misma organización.

1. Vaya a **Administrador** > **Conexiones (versión preliminar)**.

1. Vaya a la pestaña **Conexiones**.

1. Seleccione **Agregar conexión** para crear una nueva conexión. Elija en el menú desplegable qué tipo de conexión desea crear.

1. En el panel **Configurar conexión**, proporcione los detalles requeridos. 
   1. El **Nombre para mostrar** y el tipo de conexión describe una conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de esta conexión.
   1. Los campos exactos dependen del servicio al que se esté conectando. Puede obtener información sobre los detalles de un tipo de conexión específico en el artículo sobre el servicio de destino.
   1. Si usted [usa tu propio Key Vault](use-azure-key-vault.md) para almacenar secretos, active **Usar Key Vault** y elija el secreto de la lista.

1. Para crear la conexión, seleccione **Guardar**.

También puede seleccionar **Configurar** en un icono de la pestaña **Descubrir**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permitir que los contribuyentes utilicen una conexión para las exportaciones

Al configurar o editar una conexión de exportación, usted elige qué usuarios pueden usar esta conexión específica para definir [exportaciones](export-destinations.md). De forma predeterminada, una conexión está disponible para los usuarios con un rol de administrador. Puede cambiar esta configuración en **Elegir quién puede usar esta conexión** y permitir que los usuarios con el rol colaborador utilicen esta conexión.

- Los colaboradores no podrán ver ni editar la conexión. Solo verán el nombre para mostrar y su tipo al crear una exportación.
- Al compartir una conexión, permite que los colaboradores usen una conexión. Los colaboradores verán conexiones compartidas cuando configuren exportaciones. Pueden gestionar todas las exportaciones que utilizan esta conexión específica.
- Puede cambiar esta configuración manteniendo las exportaciones que ya han sido definidas por los colaboradores.

## <a name="edit-a-connection"></a>Editar una conexión

1. Vaya a **Administrador** > **Conexiones (versión preliminar)**.

1. Vaya a la pestaña **Conexiones**.

1. Seleccione los puntos suspensivos verticales para la conexión que desea editar.

1. Seleccione **Editar**.

1. Cambie los valores que desea actualizar y seleccione **Guardar**.

## <a name="remove-a-connection"></a>Quitar una conexión

Si los enriquecimientos o exportaciones utilizan la conexión que está quitando, primero debe desconectarlos o quitarlos. El cuadro de diálogo para quitar le llevará a los enriquecimientos o exportaciones relevantes. 

Los enriquecimientos y exportaciones que se han desconectado se vuelven inactivos. Se reactivan agregándoles otra conexión en la página [Enriquecimientos](enrichment-hub.md) o [Exportaciones](export-destinations.md).

1. Vaya a **Administrador** > **Conexiones (versión preliminar)**.

1. Vaya a la pestaña **Conexiones**.

1. Seleccione los puntos suspensivos verticales para la conexión que desea quitar.

1. Seleccione **Quitar** del menú desplegable. Aparece un cuadro de diálogo de confirmación.

   1. Si hay enriquecimientos o exportaciones usando esta conexión, seleccione el botón para ver qué está usando la conexión.
      - **Exportaciones**: puede optar por quitar o desconectar las exportaciones para poder quitar la conexión. Para desconectar una exportación, los administradores pueden utilizar la acción **Desconectar**. Esta acción está disponible para exportaciones seleccionadas individuales y múltiples. Al desconectarse, conserva la configuración de exportación, pero no se ejecutará hasta que se le agregue otra conexión.
      - **Enriquecimientos**: puede optar por quitar o desactivar los enriquecimientos para poder quitar la conexión. 
   1. Cuando la conexión no tenga más dependencias, vuelva a **Administrador** > **Conexiones** e intente quitar la conexión nuevamente.

1. Para confirmar la eliminación, seleccione **Quitar**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configure conexiones con secretos administrados por su propio Key Vault

Algunas conexiones necesitan secretos como claves API o contraseñas. Algunas conexiones admiten secretos almacenados en su propio Key Vault. Obtenga más información sobre conexiones admitidas y cómo configurar [su propio Key Vault para conclusiones del público](use-azure-key-vault.md).
