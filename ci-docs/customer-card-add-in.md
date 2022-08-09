---
title: Complemento de tarjeta de cliente para aplicaciones de Dynamics 365 (versión preliminar) (contiene vídeo)
description: Muestre datos de perfil de cliente de Customer Insights en aplicaciones de Dynamics 365 con este complemento.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8b3b6a0d54b80d7df454e9dc925f14cc3c39684c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194944"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Complemento de tarjeta de cliente para aplicaciones de Dynamics 365 (versión preliminar)

Obtenga una vista de 360 grados de sus clientes directamente en las aplicaciones de Dynamics 365. Con el Complemento de tarjeta de cliente instalado en una aplicación de Dynamics 365 compatible, puede optar por mostrar los campos del perfil del cliente, la información y la escala de tiempo de actividad. El complemento recuperará datos de Customer Insights sin afectar los datos en la aplicación de Dynamics 365 conectada.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Requisitos previos

- Las aplicaciones basadas en modelos de Dynamics 365, como Ventas o Servicio al cliente, versión 9.0 y posteriores.
- Para que sus datos de Dynamics 365 se asignen a los perfiles de clientes de Customer Insights, recomendamos que deben [ingerirse desde la aplicación Dynamics 365, utilizando el conector Microsoft Dataverse](connect-power-query.md). Si usa un método diferente para ingerir contactos (o cuentas) de Dynamics 365, debe asegurarse de que el campo `contactid` (o `accountid`) se establece como [clave principal para ese origen de datos durante el proceso de unificación de datos](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Todos los usuarios de Dynamics 365 del complemento de tarjeta de cliente deben ser [agregados como usuarios](permissions.md) en Customer Insights para ver los datos.
- [Funciones configuradas de búsqueda y de filtro ](search-filter-index.md) en Customer Insights.
- Cada control de complemento se basa en datos específicos en Customer Insights. Algunos datos y controles solo están disponibles en entornos de tipos específicos. La configuración del complemento le informará si un control no está disponible debido al tipo de entorno seleccionado. Más información sobre [casos de uso del entorno](work-with-business-accounts.md).
  - **Control de medidas**: requiere [medidas de atributos de cliente configuradas](measures.md).
  - **Control de inteligencia**: requiere datos generados usando [predicciones o modelos personalizados](predictions-overview.md).
  - **Control de detalles del cliente**: muestra todos los campos del perfil disponibles en el perfil de cliente unificado.
  - **Control de enriquecimiento**: requiere [enriquecimientos](enrichment-hub.md) activos aplicados a perfiles de clientes. El complemento de la tarjeta admite estos enriquecimientos: [Marcas](enrichment-microsoft.md) proporcionadas por Microsoft, [Intereses](enrichment-microsoft.md) proporcionadas por Microsoft y [Datos de interacción con la oficina](enrichment-office.md) proporcionados por Microsoft.
  - **Control de contactos**: requiere un tipo de entidad semántica de contacto.
  - **Control de escala de tiempo**: requiere [actividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar el complemento de tarjeta de cliente

El complemento de tarjeta de cliente es una solución para aplicaciones Customer Engagement en Dynamics 365. Para instalar la solución:

1. Vaya a AppSource y busque **Tarjeta de cliente de Dynamics**.

1. Seleccione el [Complemento de tarjeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) y seleccione **Obtenerlo ahora**.

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

Dependiendo de su escenario, puede optar por agregar controles al formulario **Contacto** o al formulario **Cuenta**. Si su entorno de Customer Insights es para cuentas de negocio, le recomendamos que agregue los controles al formulario Cuenta. En ese caso, reemplace "contacto" en los pasos siguientes por "cuenta".

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

## <a name="troubleshooting"></a>Solución de problemas

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Los controles del complemento de tarjeta de cliente no encuentran datos

**Problema:**

Incluso con campos de id. configurados correctamente, los controles no pueden encontrar datos para ningún cliente.  

**Resolución**

1. Asegúrese de haber configurado el complemento de la tarjeta de acuerdo con las instrucciones: [Configurar el complemento de tarjeta de cliente](#configure-the-customer-card-add-in)

1. Revise la configuración de ingesta de datos. Edite el origen de datos para el sistema Dynamics 365 que contiene el GUID de id. de contacto. Si el GUID del id. de contacto se muestra con caracteres en mayúsculas en el editor de Power Query, intente los pasos siguientes:
    1. Edite el origen de datos para abrir el origen de datos en el editor de Power Query.
    1. Seleccione la columna Id. de contacto.
    1. Seleccione **Transformar** en la barra de encabezado para ver las acciones disponibles.
    1. Seleccione **minúscula**. Valide si los GUID de la tabla ahora están en minúsculas.
    1. Guarde el origen de datos.
    1. Ejecute la ingesta de datos, la unificación y los procesos posteriores para propagar los cambios en el GUID.

Después de que el sistema ha completado la actualización completa, los controles del complemento de tarjeta de cliente deberían mostrar los datos esperados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
