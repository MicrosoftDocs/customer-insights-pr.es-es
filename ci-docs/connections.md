---
title: Información general sobre conexiones (versión preliminar)
description: Conexiones a otros servicios de Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245532"
---
# <a name="connections-preview-overview"></a>Información general sobre conexiones (versión preliminar)

Las conexiones son la clave para permitir el intercambio de datos desde y hacia Customer Insights. Cada conexión establece el intercambio de datos con un servicio específico. Use las conexiones para [configurar enriquecimientos de terceros](enrichment-hub.md) y [configurar exportaciones](export-destinations.md). La misma conexión se puede utilizar varias veces. Por ejemplo, una conexión para Dynamics 365 Marketing funciona para varias exportaciones y una conexión Leadspace se puede usar para varios enriquecimientos.

## <a name="export-connections"></a>Exportar conexiones

Solo los administradores pueden configurar nuevas conexiones, pero pueden [otorgar acceso a los colaboradores](#allow-contributors-to-use-a-connection-for-exports) para que usen las conexiones existentes. Los administradores controlan dónde pueden ir los datos, los colaboradores definen la carga útil y la frecuencia según sus necesidades.

## <a name="enrichment-connections"></a>Conexiones de enriquecimiento

Solo los administradores pueden configurar nuevas conexiones, pero las conexiones creadas siempre están disponibles tanto para administradores como para colaboradores. Los administradores gestionan las credenciales y dan su consentimiento para las transferencias de datos. Las conexiones pueden ser utilizadas para enriquecimiento tanto por parte de administradores como por parte de colaboradores.

## <a name="add-a-new-connection"></a>Agregar una nueva conexión

### <a name="prerequisites"></a>Requisitos previos

- [Permisos de administrador](permissions.md)
- Otros servicios de Microsoft, si los hay, están en la misma organización

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija el tipo de conexión que quiere crear. O vaya a la pestaña **Descubrir** y seleccione **Configurar** en un icono de conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Especifique los detalles necesarios. Los campos exactos dependen del servicio al que te estás conectando. Para obtener detalles de un tipo de conexión específico, consulte el artículo sobre el servicio de destino.

1. Si usted [usa tu propio Key Vault](use-azure-key-vault.md) para almacenar secretos, active **Usar Key Vault** y elija el secreto de la lista.

1. Revise Privacidad y cumplimiento de datos y seleccione **Acepto**.

1. Seleccione **Guardar** para crear la conexión.

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a terceras partes o a otros productos Microsoft, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que la tercera parte cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Su administrador de Dynamics 365 Customer Insights puede quitar la conexión en cualquier momento para dejar de usar esta funcionalidad.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permitir que los contribuyentes utilicen una conexión para las exportaciones

Al configurar o editar una conexión de exportación, elige qué usuarios pueden usar esta conexión específica para definir [exportaciones](export-destinations.md). De forma predeterminada, una conexión está disponible para los usuarios con un rol de administrador. Cambie la configuración en **Elegir quién puede usar esta conexión** y permita que los usuarios con el rol colaborador utilicen esta conexión.

- Los colaboradores no podrán ver ni editar la conexión. Solo verán el nombre y su tipo al crear una exportación.
- Al compartir una conexión, permite que los colaboradores usen una conexión. Los colaboradores verán conexiones compartidas cuando configuren exportaciones. Pueden gestionar todas las exportaciones que utilizan esta conexión específica.
- Puede cambiar esta configuración manteniendo las exportaciones que ya han sido definidas por los colaboradores.

## <a name="manage-existing-connections"></a>Administrar conexiones existentes

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione las pestañas **Enriquecimiento** o **Exportaciones** para ver una lista de conexiones de exportación o enriquecimiento, el tipo de conexión, cuándo se creó y quién tiene acceso. Puede ordenar la lista de conexiones por cada columna.

1. Seleccione la conexión para ver las acciones disponibles.

   - **Edite** la conexión.
   - [**Elimine**](#remove-a-connection) una conexión.

### <a name="remove-a-connection"></a>Quitar una conexión

Si la conexión que está eliminando es utilizada por enriquecimientos o exportaciones, primero debe separarlos o eliminarlos. El cuadro de diálogo para quitar le lleva a los enriquecimientos o exportaciones relevantes.

> [!TIP]
> Los enriquecimientos y exportaciones desasociadas desactivados se vuelven inactivos. Se reactivan agregándoles otra conexión en la página [Enriquecimientos](enrichment-hub.md) o [Exportaciones](export-destinations.md).

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione las pestañas **Enriquecimiento** o **Exportaciones**.

1. Seleccione la conexión que desee quitar.

1. Seleccione **Quitar** del menú desplegable. Aparece un cuadro de diálogo de confirmación.

   1. Si hay enriquecimientos o exportaciones usando esta conexión, seleccione el botón para ver qué está usando la conexión.
      - **Exportaciones:** elija **Eliminar** la exportación o **Desasociar la conexión**. Al desasociar la conexión, se conserva la configuración de exportación, pero no se ejecutará hasta que se le agregue otra conexión.
      - **Enriquecimientos:** elija **Borrar** o **Desactivar** los enriquecimientos.
   1. Cuando la conexión no tenga más dependencias, vuelva a **Administrador** > **Conexiones** e intente quitar la conexión nuevamente.

1. Para confirmar la eliminación, seleccione **Quitar**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configure conexiones con secretos administrados por su propio Key Vault

Algunas conexiones necesitan secretos como claves API o contraseñas. Algunas conexiones admiten secretos almacenados en su propio Key Vault. Obtenga más información sobre conexiones admitidas y cómo configurar [su propio Key Vault para Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
