---
title: Trabajar con API
description: Utilice las API y conozca las limitaciones.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710481"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="d0c8b-103">Trabajar con las API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d0c8b-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="d0c8b-104">Dynamics 365 Customer Insights proporciona las API para crear sus propias aplicaciones basadas en sus datos en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0c8b-105">Los detalles de estas API se enumeran en la [Referencia de las API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="d0c8b-106">Incluyen información adicional sobre operaciones, parámetros y respuestas.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="d0c8b-107">Este artículo le guía para acceder a las API de Customer Insights, crear un registro de la aplicación de Azure y ayudarle a comenzar con las bibliotecas de cliente disponibles.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="d0c8b-108">Comenzar a probar las API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d0c8b-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="d0c8b-109">[Inicie sesión](https://home.ci.ai.dynamics.com) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="d0c8b-110">Si aún no tiene una suscripción, [Regístrese para obtener una versión de prueba de Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="d0c8b-111">Para habilitar las API en su entorno de Customer Insights, vaya a **Administración** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="d0c8b-112">Necesitará permisos de administrador para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="d0c8b-113">Vaya a la pestaña **API** y seleccione el botón **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="d0c8b-114">La habilitación de las API crea una clave de suscripción primaria y secundaria para su instancia que se usa en las solicitudes de API.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="d0c8b-115">Puede regenerar las claves seleccionando **Regenerar primaria** o **Regenerar secundaria** en **Administración** > **Permisos** > **API**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Habilitar las API de Customer Insights":::

1. <span data-ttu-id="d0c8b-117">Seleccione **Explorar nuestras API** para [probar las API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="d0c8b-118">Elija una operación de API y seleccione **Intentarlo**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="d0c8b-119">En el panel lateral, establezca el valor en el menú desplegable **Autorización** en **Implícito**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="d0c8b-120">El encabezado `Authorization` viene con un token de portador agregado.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="d0c8b-121">Su clave de suscripción se completará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="d0c8b-122">Opcionalmente, agregue todos los parámetros de consulta necesarios.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="d0c8b-123">Desplácese hacia la parte inferior del panel lateral y seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="d0c8b-124">La respuesta HTTP pronto aparecerá a continuación.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Gif animado que muestra cómo seleccionar y probar las API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="d0c8b-126">Crear un registro de nueva aplicación en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="d0c8b-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="d0c8b-127">Estos pasos le ayudarán a comenzar a usar las API de Customer Insights en una aplicación de Azure con permisos delegados.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="d0c8b-128">Asegúrese de haber completado antes la [sección Comenzar](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="d0c8b-129">Inicie sesión en [Azure Portal](https://portal.azure.com) con la cuenta que puede acceder a los datos de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="d0c8b-130">A la izquierda, seleccione **Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="d0c8b-131">Seleccione **Nuevo registro**, facilite un nombre de aplicación y elija el tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="d0c8b-132">Opcioonalmente, agregue una URL de redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="d0c8b-133">http://localhost es suficiente para desarrollar una aplicación en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="d0c8b-134">En el registro de su nueva aplicación, vaya a **Permisos de API**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="GIF animado para establecer el permiso de la API en el registro de la aplicación.":::

1. <span data-ttu-id="d0c8b-136">Seleccione **Agregar permiso** y seleccione **Customer Insights** en el panel lateral.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="d0c8b-137">En **Tipo de permiso**, seleccione **Permisos delegados** y seleccione el permiso **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="d0c8b-138">Seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-138">Select **Add permissions**.</span></span> <span data-ttu-id="d0c8b-139">Si necesita acceder a la API sin que un usuario inicie sesión, revise la sección [Permisos de aplicaciones de servidor a servidor](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="d0c8b-140">Seleccione **Otorgar consentimiento de administrador para...** para completar el registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="d0c8b-141">Puede utilizar la aplicación/id. de cliente para el registro de esta aplicación con la biblioteca de autenticación de Microsoft (MSAL) para obtener un token de portador para enviar con su solicitud a la API.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animado para otorgar el consentimiento del administrador.":::

<span data-ttu-id="d0c8b-143">Para obtener más información sobre MSAL, consulte [Descripción general de la biblioteca de autenticación de Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="d0c8b-144">Para obtener más información sobre el registro de aplicaciones en Azure, consulte [La nueva experiencia de registro de aplicaciones de Azure Portal](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="d0c8b-145">Para obtener información sobre el uso de las API de nuestras bibliotecas cliente, consulte [Bibliotecas de cliente de Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="d0c8b-146">Permisos de aplicaciones de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="d0c8b-146">Server-to-server application permissions</span></span>

<span data-ttu-id="d0c8b-147">La [sección de registro de aplicaciones](#create-a-new-app-registration-in-the-azure-portal) describe cómo registrar una aplicación que requiere que un usuario inicie sesión para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="d0c8b-148">Aprenda a crear un registro de aplicación que no necesite la interacción del usuario y se pueda ejecutar en un servidor.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="d0c8b-149">En el registro de su aplicación en Azure Portal, vaya a **Permisos de API**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="d0c8b-150">Seleccione **Agregar permiso** y seleccione **Customer Insights** en el panel lateral.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="d0c8b-151">En **Tipo de permiso**, seleccione **Permisos de aplicación** y seleccione el permiso **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="d0c8b-152">Seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="d0c8b-153">Para otorgar el consentimiento de administrador sobre este permiso de aplicación, debe agregar una entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="d0c8b-154">Instale el módulo de PowerShell Azure Active Directory (AD): `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="d0c8b-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="d0c8b-155">Conéctese con su cuenta de AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="d0c8b-156">Puede encontrar su id. de inquilino en **Información general** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="d0c8b-157">Ejecute el siguiente comando para agregar una entidad de servicio de Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` El parámetro AppId pertenece a la aplicación de la API de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Ejemplo de entidad de servicio":::

1. <span data-ttu-id="d0c8b-159">Vuelva a **Permisos de API** para el registro de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="d0c8b-160">Seleccione **Otorgar consentimiento de administrador para...** para completar el registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animado para otorgar el consentimiento del administrador.":::

1. <span data-ttu-id="d0c8b-162">Para concluir, tenemos que agregar el nombre del registro de la aplicación como usuario en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="d0c8b-163">Abra Customer Insights, vaya a **Administrador** > **Permisos** y seleccione **Agregar usuario**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="d0c8b-164">Busque el nombre del registro de su aplicación, selecciónelo en los resultados de búsqueda y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="d0c8b-165">Bibliotecas de cliente de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d0c8b-165">Customer Insights client libraries</span></span>

<span data-ttu-id="d0c8b-166">Esta sección le ayuda a empezar a utilizar las bibliotecas de cliente disponibles para las API de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="d0c8b-167">Todo el código fuente de la biblioteca y las aplicaciones de muestra se pueden encontrar en la [página de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="d0c8b-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="d0c8b-168">C# NuGet</span></span>

<span data-ttu-id="d0c8b-169">Obtenga información sobre cómo comenzar a usar las bibliotecas de cliente de C# de NuGet.org. Para obtener más información sobre el paquete NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="d0c8b-170">Actualmente, este paquete se dirige a los marcos netstandard2.0 y netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="d0c8b-171">Agregar la biblioteca de cliente de C# a un proyecto de C#</span><span class="sxs-lookup"><span data-stu-id="d0c8b-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="d0c8b-172">En Visual Studio, abra el **NuGet Administrador de paquetes** para su proyecto.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="d0c8b-173">Busque **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="d0c8b-174">Seleccione **Instalar** para agregar el paquete al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="d0c8b-175">Alternativamente, ejecute este comando en la **Consola del administrador de paquetes de NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="d0c8b-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Agregar el paquete NuGet a un proyecto de Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="d0c8b-177">Usar la biblioteca de cliente de C#</span><span class="sxs-lookup"><span data-stu-id="d0c8b-177">Use the C# client library</span></span>

1. <span data-ttu-id="d0c8b-178">Utilice la [Biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obtener un `AccessToken` usando su [Registro de la aplicación de Azure](#create-a-new-app-registration-in-the-azure-portal) existente.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="d0c8b-179">Después de autenticarse y adquirir correctamente un token, cree uno nuevo o utilice un `HttpClient` existente con la **"Autorización" DefaultRequestHeaders** establecida en **<access token> de portador** y **Ocp-Apim-Subscription-Key** establecido en la [**clave de suscripción** de su entorno de Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="d0c8b-180">Restablezca el encabezado **Autorización** cuando sea apropiado.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="d0c8b-181">Por ejemplo, cuando haya expirado el token.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="d0c8b-182">Pase este `HttpClient` a la construcción del cliente de `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Muestra de httpclient":::

1. <span data-ttu-id="d0c8b-184">Realice llamadas con el cliente a los "métodos de extensión", por ejemplo, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="d0c8b-185">Si el acceso al `Microsoft.Rest.HttpOperationResponse` subyacente es preferible, utilice los "métodos de mensaje http", por ejemplo `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="d0c8b-186">La respuesta probablemente será del tipo `object` porque el método puede devolver varios tipos (por ejemplo, `IList<InstanceInfo>` y `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="d0c8b-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="d0c8b-187">Para comprobar el tipo de retorno, puede convertir de forma segura los objetos en los tipos de respuesta especificados en la [Página de detalles de la API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para esa operación.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="d0c8b-188">Si necesita más información sobre la solicitud, utilice los **métodos de mensaje http** para acceder al objeto de respuesta sin procesar.</span><span class="sxs-lookup"><span data-stu-id="d0c8b-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="d0c8b-189">Paquete NodeJS</span><span class="sxs-lookup"><span data-stu-id="d0c8b-189">NodeJS package</span></span>

<span data-ttu-id="d0c8b-190">Utilice las bibliotecas cliente de NodeJS disponibles a través de NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="d0c8b-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="d0c8b-191">Paquete de Python</span><span class="sxs-lookup"><span data-stu-id="d0c8b-191">Python package</span></span>

<span data-ttu-id="d0c8b-192">Utilice las bibliotecas cliente de Python disponibles a través de PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="d0c8b-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
