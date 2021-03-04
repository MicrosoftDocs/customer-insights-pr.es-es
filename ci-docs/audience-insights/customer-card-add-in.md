---
title: Instalar y configurar el complemento de tarjeta de cliente
description: Instale y configure el complemento de tarjeta de cliente para Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268065"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="a767b-103">Complemento de tarjeta de cliente (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a767b-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a767b-104">Obtenga una vista de 360 grados de sus clientes directamente en las aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a767b-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="a767b-105">Vea datos demográficos, información y cronogramas de actividades con el complemento de tarjeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="a767b-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a767b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a767b-106">Prerequisites</span></span>

- <span data-ttu-id="a767b-107">Aplicación Dynamics 365 (como Centro de ventas o Centro de Customer Service), versión 9.0 y posterior con Interfaz unificada habilitada.</span><span class="sxs-lookup"><span data-stu-id="a767b-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="a767b-108">Perfiles de clientes [ingeridos desde la aplicación Dynamics 365 usando Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="a767b-109">Los usuarios del complemento de tarjeta de cliente deben estar [agregados como usuarios](permissions.md) en la información de público.</span><span class="sxs-lookup"><span data-stu-id="a767b-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="a767b-110">[Capacidades de búsqueda y filtrado configuradas](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="a767b-111">Control demográfico: los campos demográficos, como la edad o el sexo, están disponibles en el perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="a767b-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="a767b-112">Control de enriquecimiento: requiere [enriquecimientos](enrichment-hub.md) activos aplicados a perfiles de clientes.</span><span class="sxs-lookup"><span data-stu-id="a767b-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="a767b-113">Control de inteligencia: requiere datos generados con Azure Machine Learning ([Predicciones](predictions.md) o [Modelos personalizados](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="a767b-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="a767b-114">Control de medidas: Requiere [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="a767b-115">Control de línea de tiempo: requiere [actividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="a767b-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="a767b-116">Instalar el complemento de tarjeta de cliente</span><span class="sxs-lookup"><span data-stu-id="a767b-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="a767b-117">El complemento de tarjeta de cliente es una solución para aplicaciones Customer Engagement en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a767b-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="a767b-118">Para instalar la solución, vaya a AppSource y busque **Tarjeta de cliente de Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="a767b-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="a767b-119">Seleccione el [Complemento de tarjeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) y seleccione **Obtenerlo ahora**.</span><span class="sxs-lookup"><span data-stu-id="a767b-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="a767b-120">Es posible que deba iniciar sesión con sus credenciales de administrador para que la aplicación Dynamics 365 instale la solución.</span><span class="sxs-lookup"><span data-stu-id="a767b-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="a767b-121">La solución puede tardar un tiempo en instalarse en su entorno.</span><span class="sxs-lookup"><span data-stu-id="a767b-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="a767b-122">Configurar el Complemento de tarjeta de cliente</span><span class="sxs-lookup"><span data-stu-id="a767b-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="a767b-123">Como administrador, vaya a la sección **Configuración** en Dynamics 365, y seleccione **Soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a767b-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="a767b-124">Seleccione el vínculo del **Nombre para mostrar** para la solución del **Complemento de la tarjeta de cliente Dynamics 365 Customer Insights (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="a767b-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a767b-125">![Seleccionar nombre para mostrar](media/select-display-name.png "Seleccionar nombre para mostrar")</span><span class="sxs-lookup"><span data-stu-id="a767b-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="a767b-126">Seleccione **iniciar sesión** y especifique las credenciales para la cuenta de administrador que usa para configurar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a767b-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a767b-127">Compruebe que el bloqueador de elementos emergentes del navegador no bloquea la ventana de autenticación cuando selecciona el botón **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="a767b-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="a767b-128">Seleccione el entorno del que desea recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="a767b-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="a767b-129">Defina la asignación de campos a los registros en la aplicación Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a767b-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="a767b-130">Para asignarse a un contacto, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de contacto.</span><span class="sxs-lookup"><span data-stu-id="a767b-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="a767b-131">Para asignarse a una cuenta, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de cuenta.</span><span class="sxs-lookup"><span data-stu-id="a767b-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a767b-132">![Campo de identificador de contacto](media/contact-id-field.png "Campo de identificador de contacto")</span><span class="sxs-lookup"><span data-stu-id="a767b-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="a767b-133">Seleccione **Guardar configuración** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a767b-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="a767b-134">A continuación, debe asignar roles de seguridad en Dynamics 365 para que los usuarios puedan personalizar y ver la tarjeta del cliente.</span><span class="sxs-lookup"><span data-stu-id="a767b-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="a767b-135">En Dynamics 365, vaya a **Configuración** > **Seguridad** > **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="a767b-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="a767b-136">Seleccione los usuarios para editar los roles de usuario y seleccione **Administrar roles**.</span><span class="sxs-lookup"><span data-stu-id="a767b-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="a767b-137">Asigne el rol **Personalizador de tarjetas de Customer Insights** a los usuarios que personalizarán el contenido que se muestra en la tarjeta para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="a767b-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="a767b-138">Agregar controles de tarjeta de cliente a formularios</span><span class="sxs-lookup"><span data-stu-id="a767b-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="a767b-139">Para agregar los controles de la tarjeta del cliente a su formulario de contacto, vaya a **Configuración** > **Personalizaciones** en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a767b-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="a767b-140">Seleccione **Personalizar el sistema**.</span><span class="sxs-lookup"><span data-stu-id="a767b-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="a767b-141">Busque la entidad **Contacto**, expándala y seleccione **Formularios**.</span><span class="sxs-lookup"><span data-stu-id="a767b-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="a767b-142">Seleccione el formulario de contacto al que desea agregar los controles de tarjeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="a767b-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a767b-143">![Seleccionar formulario de contacto](media/contact-active-forms.png "Seleccionar formulario de contacto")</span><span class="sxs-lookup"><span data-stu-id="a767b-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="a767b-144">Para agregar un control demográfico, en el editor de formularios, arrastre cualquier campo desde el **Explorador de campos** hasta el lugar en el que desee que aparezca el control demográfico.</span><span class="sxs-lookup"><span data-stu-id="a767b-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="a767b-145">Seleccione el campo en el formulario que acaba de agregar y, a continuación, seleccione **Cambiar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a767b-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="a767b-146">Vaya a la pestaña **Controles** y seleccione **Agregar control**.</span><span class="sxs-lookup"><span data-stu-id="a767b-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="a767b-147">Elija uno de los controles personalizados disponibles y seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="a767b-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="a767b-148">En el cuadro de diálogo **Propiedades de campo**, desactive la casilla **Mostrar etiqueta en el formulario**.</span><span class="sxs-lookup"><span data-stu-id="a767b-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="a767b-149">Selecciona la opción **Web** para el control.</span><span class="sxs-lookup"><span data-stu-id="a767b-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="a767b-150">Para el control de enriquecimiento, seleccione qué tipo de enriquecimiento desea mostrar configurando el campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="a767b-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="a767b-151">Agregue un control de enriquecimiento independiente para cada tipo de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="a767b-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="a767b-152">Seleccione **Guardar** y **Publicar** para publicar el formulario de contacto actualizado.</span><span class="sxs-lookup"><span data-stu-id="a767b-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="a767b-153">Vaya al formulario de contacto publicado.</span><span class="sxs-lookup"><span data-stu-id="a767b-153">Go to the published contact form.</span></span> <span data-ttu-id="a767b-154">Verá el control recién agregado.</span><span class="sxs-lookup"><span data-stu-id="a767b-154">You'll see the newly added control.</span></span> <span data-ttu-id="a767b-155">Es posible que tenga que iniciar sesión la primera vez que lo use.</span><span class="sxs-lookup"><span data-stu-id="a767b-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="a767b-156">Para personalizar lo que desea mostrar en el control personalizado, seleccione el botón de edición en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="a767b-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="a767b-157">Actualizar el complemento de tarjeta de cliente</span><span class="sxs-lookup"><span data-stu-id="a767b-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="a767b-158">El complemento de tarjeta de cliente no se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a767b-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="a767b-159">Para actualizar a la última versión, siga este procedimiento en la aplicación Dynamics 365 que tiene instalado el complemento.</span><span class="sxs-lookup"><span data-stu-id="a767b-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="a767b-160">En la aplicación Dynamics 365, vaya a **Configuración** > **Personalización** y seleccione **Soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a767b-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="a767b-161">En la tabla de complementos, busque **CustomerInsightsCustomerCard** y seleccione la fila.</span><span class="sxs-lookup"><span data-stu-id="a767b-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="a767b-162">Seleccione la opción **Aplicar actualización de la solución** en la barra de acciones.</span><span class="sxs-lookup"><span data-stu-id="a767b-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualizar la solución en el área de personalización de las aplicaciones de Dynamics 365":::

1. <span data-ttu-id="a767b-164">Después de iniciar el proceso de actualización, verá un indicador de carga hasta que se complete la actualización.</span><span class="sxs-lookup"><span data-stu-id="a767b-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="a767b-165">Si no hay una versión más reciente, la actualización mostrará un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="a767b-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]