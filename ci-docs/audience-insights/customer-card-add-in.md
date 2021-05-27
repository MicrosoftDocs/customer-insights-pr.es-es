---
title: Complemento de tarjeta de cliente para aplicaciones de Dynamics 365
description: Muestre datos de conclusiones del público en aplicaciones de Dynamics 365 con este complemento.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059609"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="c7f43-103">Complemento de tarjeta de cliente (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c7f43-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c7f43-104">Obtenga una vista de 360 grados de sus clientes directamente en las aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c7f43-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="c7f43-105">Con el complemento de tarjeta de cliente instalado en una aplicación de Dynamics 365 compatible, puede elegir mostrar datos demográficos, conocimientos y cronogramas de actividad.</span><span class="sxs-lookup"><span data-stu-id="c7f43-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="c7f43-106">El complemento recuperará datos de Customer Insights sin afectar los datos en la aplicación de Dynamics 365 conectada.</span><span class="sxs-lookup"><span data-stu-id="c7f43-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c7f43-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c7f43-107">Prerequisites</span></span>

- <span data-ttu-id="c7f43-108">El complemento solo funciona con aplicaciones basadas en modelos de Dynamics 365, como Ventas o Servicio al cliente, versión 9.0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="c7f43-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="c7f43-109">Para que sus datos de Dynamics 365 se asignen a los perfiles de clientes de conclusiones del público, deben [ingerirse desde la aplicación Dynamics 365, utilizando el conector Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c7f43-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="c7f43-110">Todos los usuarios de Dynamics 365 del complemento de tarjeta de cliente deben ser [agregados como usuarios](permissions.md) en las conclusiones del público para poder ver los datos.</span><span class="sxs-lookup"><span data-stu-id="c7f43-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="c7f43-111">Se requieren [Capacidades de búsqueda y filtrado configuradas](search-filter-index.md) en las conclusiones del público para que funcione la búsqueda de datos.</span><span class="sxs-lookup"><span data-stu-id="c7f43-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="c7f43-112">Cada control de complemento se basa en datos específicos de las conclusiones del público:</span><span class="sxs-lookup"><span data-stu-id="c7f43-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="c7f43-113">Control de medidas: Requiere [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="c7f43-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="c7f43-114">Control de inteligencia: requiere datos generados usando [predicciones](predictions.md) o [modelos personalizados](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="c7f43-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="c7f43-115">Control demográfico: los campos demográficos, como la edad o el sexo, están disponibles en el perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="c7f43-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="c7f43-116">Control de enriquecimiento: requiere [enriquecimientos](enrichment-hub.md) activos aplicados a perfiles de clientes.</span><span class="sxs-lookup"><span data-stu-id="c7f43-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="c7f43-117">Control de línea de tiempo: requiere [actividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="c7f43-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="c7f43-118">Instalar el complemento de tarjeta de cliente</span><span class="sxs-lookup"><span data-stu-id="c7f43-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="c7f43-119">El complemento de tarjeta de cliente es una solución para aplicaciones Customer Engagement en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c7f43-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="c7f43-120">Para instalar la solución, vaya a AppSource y busque **Tarjeta de cliente de Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="c7f43-121">Seleccione el [Complemento de tarjeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) y seleccione **Obtenerlo ahora**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="c7f43-122">Es posible que deba iniciar sesión con sus credenciales de administrador para que la aplicación Dynamics 365 instale la solución.</span><span class="sxs-lookup"><span data-stu-id="c7f43-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="c7f43-123">La solución puede tardar un tiempo en instalarse en su entorno.</span><span class="sxs-lookup"><span data-stu-id="c7f43-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="c7f43-124">Configurar el Complemento de tarjeta de cliente</span><span class="sxs-lookup"><span data-stu-id="c7f43-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="c7f43-125">Como administrador, vaya a la sección **Configuración** en Dynamics 365, y seleccione **Soluciones**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="c7f43-126">Seleccione el vínculo del **Nombre para mostrar** para la solución del **Complemento de la tarjeta de cliente Dynamics 365 Customer Insights (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7f43-127">![Seleccionar nombre para mostrar](media/select-display-name.png "Seleccionar nombre para mostrar")</span><span class="sxs-lookup"><span data-stu-id="c7f43-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="c7f43-128">Seleccione **iniciar sesión** y especifique las credenciales para la cuenta de administrador que usa para configurar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c7f43-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c7f43-129">Compruebe que el bloqueador de elementos emergentes del navegador no bloquea la ventana de autenticación cuando selecciona el botón **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="c7f43-130">Seleccione el entorno de Customer Insights del que desea capturar datos.</span><span class="sxs-lookup"><span data-stu-id="c7f43-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="c7f43-131">Defina la asignación de campos a registros en la aplicación Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c7f43-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="c7f43-132">Dependiendo de sus datos en Customer Insights, puede elegir asignar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c7f43-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="c7f43-133">Para asignarse a un contacto, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de contacto.</span><span class="sxs-lookup"><span data-stu-id="c7f43-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="c7f43-134">Para asignarse a una cuenta, seleccione el campo en la entidad cliente que coincida con el id. de su entidad de cuenta.</span><span class="sxs-lookup"><span data-stu-id="c7f43-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7f43-135">![Campo de identificador de contacto](media/contact-id-field.png "Campo de identificador de contacto")</span><span class="sxs-lookup"><span data-stu-id="c7f43-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="c7f43-136">Seleccione **Guardar configuración** para guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c7f43-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="c7f43-137">A continuación, debe asignar roles de seguridad en Dynamics 365 para que los usuarios puedan personalizar y ver la tarjeta del cliente.</span><span class="sxs-lookup"><span data-stu-id="c7f43-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="c7f43-138">En Dynamics 365, vaya a **Configuración** > **Seguridad** > **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="c7f43-139">Seleccione los usuarios para editar los roles de usuario y seleccione **Administrar roles**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="c7f43-140">Asigne el rol **Personalizador de tarjetas de Customer Insights** a los usuarios que personalizarán el contenido que se muestra en la tarjeta para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="c7f43-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="c7f43-141">Agregar controles de tarjeta de cliente a formularios</span><span class="sxs-lookup"><span data-stu-id="c7f43-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="c7f43-142">Para agregar los controles de la tarjeta del cliente a su formulario de contacto, vaya a **Configuración** > **Personalizaciones** en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c7f43-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="c7f43-143">Seleccione **Personalizar el sistema**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="c7f43-144">Busque la entidad **Contacto**, expándala y seleccione **Formularios**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="c7f43-145">Seleccione el formulario de contacto al que desea agregar los controles de tarjeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="c7f43-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c7f43-146">![Seleccionar formulario de contacto](media/contact-active-forms.png "Seleccionar formulario de contacto")</span><span class="sxs-lookup"><span data-stu-id="c7f43-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="c7f43-147">Para agregar un control demográfico, en el editor de formularios, arrastre cualquier campo desde el **Explorador de campos** hasta el lugar en el que desee que aparezca el control demográfico.</span><span class="sxs-lookup"><span data-stu-id="c7f43-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="c7f43-148">Seleccione el campo en el formulario que acaba de agregar y, a continuación, seleccione **Cambiar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="c7f43-149">Vaya a la pestaña **Controles** y seleccione **Agregar control**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="c7f43-150">Elija uno de los controles personalizados disponibles y seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="c7f43-151">En el cuadro de diálogo **Propiedades de campo**, desactive la casilla **Mostrar etiqueta en el formulario**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="c7f43-152">Selecciona la opción **Web** para el control.</span><span class="sxs-lookup"><span data-stu-id="c7f43-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="c7f43-153">Para el control de enriquecimiento, seleccione qué tipo de enriquecimiento desea mostrar configurando el campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="c7f43-154">Agregue un control de enriquecimiento independiente para cada tipo de enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="c7f43-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="c7f43-155">Seleccione **Guardar** y **Publicar** para publicar el formulario de contacto actualizado.</span><span class="sxs-lookup"><span data-stu-id="c7f43-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="c7f43-156">Vaya al formulario de contacto publicado.</span><span class="sxs-lookup"><span data-stu-id="c7f43-156">Go to the published contact form.</span></span> <span data-ttu-id="c7f43-157">Verá el control recién agregado.</span><span class="sxs-lookup"><span data-stu-id="c7f43-157">You'll see the newly added control.</span></span> <span data-ttu-id="c7f43-158">Es posible que tenga que iniciar sesión la primera vez que lo use.</span><span class="sxs-lookup"><span data-stu-id="c7f43-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="c7f43-159">Para personalizar lo que desea mostrar en el control personalizado, seleccione el botón de edición en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="c7f43-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="c7f43-160">Actualizar el complemento de tarjeta de cliente</span><span class="sxs-lookup"><span data-stu-id="c7f43-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="c7f43-161">El complemento de tarjeta de cliente no se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c7f43-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="c7f43-162">Para actualizar a la última versión, siga este procedimiento en la aplicación Dynamics 365 que tiene instalado el complemento.</span><span class="sxs-lookup"><span data-stu-id="c7f43-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="c7f43-163">En la aplicación Dynamics 365, vaya a **Configuración** > **Personalización** y seleccione **Soluciones**.</span><span class="sxs-lookup"><span data-stu-id="c7f43-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="c7f43-164">En la tabla de complementos, busque **CustomerInsightsCustomerCard** y seleccione la fila.</span><span class="sxs-lookup"><span data-stu-id="c7f43-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="c7f43-165">Seleccione la opción **Aplicar actualización de la solución** en la barra de acciones.</span><span class="sxs-lookup"><span data-stu-id="c7f43-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualizar la solución en el área de personalización de las aplicaciones de Dynamics 365":::

1. <span data-ttu-id="c7f43-167">Después de iniciar el proceso de actualización, verá un indicador de carga hasta que se complete la actualización.</span><span class="sxs-lookup"><span data-stu-id="c7f43-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="c7f43-168">Si no hay una versión más reciente, la actualización mostrará un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="c7f43-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
