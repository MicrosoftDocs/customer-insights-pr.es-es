---
title: Complemento de tarjeta de cliente para aplicaciones de Dynamics 365
description: Muestre datos de conclusiones del público en aplicaciones de Dynamics 365 con este complemento.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9c7cfbf9f47cca53e5543e2cda2584e25ad855d
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643469"
---
# <a name="customer-card-add-in-preview"></a>Complemento de tarjeta de cliente (versión preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obtenga una vista de 360 grados de sus clientes directamente en las aplicaciones de Dynamics 365. Con el Complemento de tarjeta de cliente instalado en una aplicación de Dynamics 365 compatible, puede optar por mostrar los campos del perfil del cliente, la información y la escala de tiempo de actividad. El complemento recuperará datos de Customer Insights sin afectar los datos en la aplicación de Dynamics 365 conectada.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Requisitos previos

- El complemento solo funciona con aplicaciones basadas en modelos de Dynamics 365, como Ventas o Servicio al cliente, versión 9.0 y posteriores.
- Para que sus datos de Dynamics 365 se asignen a los perfiles de clientes de conclusiones del público, deben [ingerirse desde la aplicación Dynamics 365, utilizando el conector Microsoft Dataverse](connect-power-query.md).
- Todos los usuarios de Dynamics 365 del complemento de tarjeta de cliente deben ser [agregados como usuarios](permissions.md) en las conclusiones del público para poder ver los datos.
- Se requieren [Capacidades de búsqueda y filtrado configuradas](search-filter-index.md) en las conclusiones del público para que funcione la búsqueda de datos.
- Cada control de complemento se basa en datos específicos de las conclusiones del público. Algunos datos y controles solo están disponibles en entornos de tipos específicos. La configuración del complemento le informará si un control no está disponible debido al tipo de entorno seleccionado. Más información sobre [casos de uso del entorno](work-with-business-accounts.md).
  - **Control de medidas**: Requiere [medidas configuradas](measures.md) de atributos de tipo de cliente.
  - **Control de inteligencia**: requiere datos generados usando [predicciones](predictions.md) o [modelos personalizados](custom-models.md).
  - **Control de detalles del cliente**: Todos los campos del perfil están disponibles en el perfil de cliente unificado.
  - **Control de enriquecimiento**: requiere [enriquecimientos](enrichment-hub.md) activos aplicados a perfiles de clientes.
  - **Control de contactos**: Requiere definición de entidad semántica de tipo contactos.
  - **Control de escala de tiempo**: requiere [actividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar el complemento de tarjeta de cliente

El complemento de tarjeta de cliente es una solución para aplicaciones Customer Engagement en Dynamics 365. Para instalar la solución, vaya a AppSource y busque **Tarjeta de cliente de Dynamics**. Seleccione el [Complemento de tarjeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) y seleccione **Obtenerlo ahora**.

Es posible que deba iniciar sesión con sus credenciales de administrador para que la aplicación Dynamics 365 instale la solución. La solución puede tardar un tiempo en instalarse en su entorno.

## <a name="configure-the-customer-card-add-in"></a>Configurar el Complemento de tarjeta de cliente

1. Como administrador, vaya a la sección **Configuración** en Dynamics 365, y seleccione **Soluciones**.

1. Seleccione el vínculo del **Nombre para mostrar** para la solución del **Complemento de la tarjeta de cliente Dynamics 365 Customer Insights (versión preliminar)**.

   > [!div class="mx-imgBorder"]
   > ![Seleccionar nombre para mostrar.](media/select-display-name.png "Seleccionar nombre para mostrar.")

1. Seleccione **iniciar sesión** y especifique las credenciales para la cuenta de administrador que usa para configurar Customer Insights.

   > [!NOTE]
   > Compruebe que el bloqueador de elementos emergentes del navegador no bloquea la ventana de autenticación cuando selecciona el botón **Iniciar sesión**.

1. Seleccione el entorno de Customer Insights del que desea capturar datos.

1. Defina la asignación de campos a registros en la aplicación Dynamics 365. Dependiendo de sus datos en Customer Insights, puede elegir asignar las siguientes opciones:
   - Para asignarse a un contacto, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de contacto.
   - Para asignarse a una cuenta, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de cuenta.

   > [!div class="mx-imgBorder"]
   > ![Campo de identificador de contacto.](media/contact-id-field.png "Campo de identificador de contacto.")

1. Seleccione **Guardar configuración** para guardar la configuración.

1. A continuación, debe asignar roles de seguridad en Dynamics 365 para que los usuarios puedan personalizar y ver la tarjeta del cliente. En Dynamics 365, vaya a **Configuración** > **Seguridad** > **Usuarios**. Seleccione los usuarios para editar los roles de usuario y seleccione **Administrar roles**.

1. Asigne el rol **Personalizador de tarjetas de Customer Insights** a los usuarios que personalizarán el contenido que se muestra en la tarjeta para toda la organización.

## <a name="add-customer-card-controls-to-forms"></a>Agregar controles de tarjeta de cliente a formularios

Dependiendo de su escenario, puede optar por agregar controles al formulario **Contacto** o al formulario **Cuenta**. Si su entorno de conclusiones del público es para cuentas de negocio, le recomendamos que agregue los controles al formulario Cuenta. En ese caso, reemplace "contacto" en los pasos siguientes por "cuenta".

1. Para agregar los controles de la tarjeta del cliente a su formulario de contacto, vaya a **Configuración** > **Personalizaciones** en Dynamics 365.

1. Seleccione **Personalizar el sistema**.

1. Busque la entidad **Contacto**, expándala y seleccione **Formularios**.

1. Seleccione el formulario de contacto que al desea agregar los controles de tarjeta de cliente.

    > [!div class="mx-imgBorder"]
    > ![Seleccionar formulario de contacto.](media/contact-active-forms.png "Seleccionar formulario de contacto.")

1. Para agregar un control demográfico, en el editor de formularios, arrastre cualquier campo desde el **Explorador de campos** hasta el lugar en el que desee que aparezca el control demográfico.

1. Seleccione el campo en el formulario que acaba de agregar y, a continuación, seleccione **Cambiar propiedades**.

1. Vaya a la pestaña **Controles** y seleccione **Agregar control**. Elija uno de los controles personalizados disponibles y seleccione **Añadir**.

1. En el cuadro de diálogo **Propiedades de campo**, desactive la casilla **Mostrar etiqueta en el formulario**.

1. Selecciona la opción **Web** para el control. Para el control de enriquecimiento, seleccione qué tipo de enriquecimiento desea mostrar configurando el campo **enrichmentType**. Agregue un control de enriquecimiento independiente para cada tipo de enriquecimiento.

1. Seleccione **Guardar** y **Publicar** para publicar el formulario de contacto actualizado.

1. Vaya al formulario de contacto publicado. Verá el control recién agregado. Es posible que tenga que iniciar sesión la primera vez que lo use.

1. Para personalizar lo que desea mostrar en el control personalizado, seleccione el botón de edición en la esquina superior derecha.

## <a name="upgrade-customer-card-add-in"></a>Actualizar el complemento de tarjeta de cliente

El complemento de tarjeta de cliente no se actualiza automáticamente. Para actualizar a la última versión, siga estos pasos en la aplicación Dynamics 365 que tiene el complemento instalado.

1. En la aplicación Dynamics 365, vaya a **Configuración** > **Personalización** y seleccione **Soluciones**.

1. En la tabla de complementos, busque **CustomerInsightsCustomerCard** y seleccione la fila.

1. Seleccione la opción **Aplicar actualización de la solución** en la barra de acciones.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualizar la solución en el área de personalización de las aplicaciones de Dynamics 365.":::

1. Después de iniciar el proceso de actualización, verá un indicador de carga hasta que se complete la actualización. Si no hay una versión más reciente, la actualización mostrará un mensaje de error.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
