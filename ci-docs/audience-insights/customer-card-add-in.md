---
title: Instalar y configurar el complemento de tarjeta de cliente
description: Instale y configure el complemento de tarjeta de cliente para Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644064"
---
# <a name="customer-card-add-in-preview"></a>Complemento de tarjeta de cliente (versión preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obtenga una vista de 360 grados de sus clientes directamente en las aplicaciones de Dynamics 365. Vea datos demográficos, información y cronogramas de actividades con el complemento de tarjeta de cliente.

## <a name="prerequisites"></a>Requisitos previos

- Aplicación Dynamics 365 (como Centro de ventas o Centro de Customer Service), versión 9.0 y posterior con Interfaz unificada habilitada.
- Perfiles de clientes [ingeridos desde la aplicación Dynamics 365 usando Common Data Service](connect-power-query.md).
- Los usuarios del complemento de tarjeta de cliente deben estar [agregados como usuarios](permissions.md) en la información de público.
- [Capacidades de búsqueda y filtrado configuradas](search-filter-index.md).
- Control demográfico: los campos demográficos, como la edad o el sexo, están disponibles en el perfil de cliente unificado.
- Control de enriquecimiento: requiere [enriquecimientos](enrichment-hub.md) activos aplicados a perfiles de clientes.
- Control de inteligencia: requiere datos generados con Azure Machine Learning ([Predicciones](predictions.md) o [Modelos personalizados](custom-models.md))
- Control de medidas: Requiere [medidas configuradas](measures.md).
- Control de línea de tiempo: requiere [actividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar el complemento de tarjeta de cliente

El complemento de tarjeta de cliente es una solución para aplicaciones Customer Engagement en Dynamics 365. Para instalar la solución, vaya a AppSource y busque **Tarjeta de cliente de Dynamics**. Seleccione el [Complemento de tarjeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) y seleccione **Obtenerlo ahora**.

Es posible que deba iniciar sesión con sus credenciales de administrador para que la aplicación Dynamics 365 instale la solución.

La solución puede tardar un tiempo en instalarse en su entorno.

## <a name="configure-the-customer-card-add-in"></a>Configurar el Complemento de tarjeta de cliente

1. Como administrador, vaya a la sección **Configuración** en Dynamics 365, y seleccione **Soluciones**.

1. Seleccione el vínculo del **Nombre para mostrar** para la solución del **Complemento de la tarjeta de cliente Dynamics 365 Customer Insights (versión preliminar)**.

   > [!div class="mx-imgBorder"]
   > ![Seleccionar nombre para mostrar](media/select-display-name.png "Seleccionar nombre para mostrar")

1. Seleccione **iniciar sesión** y especifique las credenciales para la cuenta de administrador que usa para configurar Customer Insights.

   > [!NOTE]
   > Compruebe que el bloqueador de elementos emergentes del navegador no bloquea la ventana de autenticación cuando selecciona el botón **Iniciar sesión**.

1. Seleccione el entorno del que desea recuperar datos.

1. Defina la asignación de campos a los registros en la aplicación Dynamics 365.
   - Para asignarse a un contacto, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de contacto.
   - Para asignarse a una cuenta, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de cuenta.

   > [!div class="mx-imgBorder"]
   > ![Campo de identificador de contacto](media/contact-id-field.png "Campo de identificador de contacto")

1. Seleccione **Guardar configuración** para guardar la configuración.

1. A continuación, debe asignar roles de seguridad en Dynamics 365 para que los usuarios puedan personalizar y ver la tarjeta del cliente. En Dynamics 365, vaya a **Configuración** > **Seguridad** > **Usuarios**. Seleccione los usuarios para editar los roles de usuario y seleccione **Administrar roles**.

1. Asigne el rol **Personalizador de tarjetas de Customer Insights** a los usuarios que personalizarán el contenido que se muestra en la tarjeta para toda la organización.

## <a name="add-customer-card-controls-to-forms"></a>Agregar controles de tarjeta de cliente a formularios
  
1. Para agregar los controles de la tarjeta del cliente a su formulario de contacto, vaya a **Configuración** > **Personalizaciones** en Dynamics 365.

1. Seleccione **Personalizar el sistema**.

1. Busque la entidad **Contacto**, expándala y seleccione **Formularios**.

1. Seleccione el formulario de contacto al que desea agregar los controles de tarjeta de cliente.

    > [!div class="mx-imgBorder"]
    > ![Seleccionar formulario de contacto](media/contact-active-forms.png "Seleccionar formulario de contacto")

1. Para agregar un control demográfico, en el editor de formularios, arrastre cualquier campo desde el **Explorador de campos** hasta el lugar en el que desee que aparezca el control demográfico.

1. Seleccione el campo en el formulario que acaba de agregar y, a continuación, seleccione **Cambiar propiedades**.

1. Vaya a la pestaña **Controles** y seleccione **Agregar control**. Elija uno de los controles personalizados disponibles y seleccione **Añadir**.

1. En el cuadro de diálogo **Propiedades de campo**, desactive la casilla **Mostrar etiqueta en el formulario**.

1. Selecciona la opción **Web** para el control. Para el control de enriquecimiento, seleccione qué tipo de enriquecimiento desea mostrar configurando el campo **enrichmentType**. Debe agregar un control de enriquecimiento separado para cada tipo de enriquecimiento.

1. Seleccione **Guardar** y **Publicar** para publicar el formulario de contacto actualizado.

1. Vaya al formulario de contacto publicado. Verá el control recién agregado. Es posible que tenga que iniciar sesión la primera vez que lo use.

1. Para personalizar lo que desea mostrar en el control personalizado, seleccione el botón de edición en la esquina superior derecha.
