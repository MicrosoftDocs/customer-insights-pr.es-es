---
title: Trabajar con API
description: Utilice las API y conozca las limitaciones.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: a460ec87ec85f0614f944d352588d4ca899f8120
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755471"
---
# <a name="work-with-customer-insights-apis"></a>Trabajar con las API de Customer Insights

Dynamics 365 Customer Insights proporciona API para crear sus propias aplicaciones basadas en los datos de Customer Insights.

> [!IMPORTANT]
> Los detalles de estas API se enumeran en la [Referencia de las API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Incluyen información adicional sobre operaciones, parámetros y respuestas.

En este artículo, se describe cómo acceder a las API de Customer Insights, crear un registro de aplicaciones de Azure y comenzar con las bibliotecas de clientes.

## <a name="get-started-trying-the-customer-insights-apis"></a>Comenzar a probar las API de Customer Insights

1. [Inicie sesión](https://home.ci.ai.dynamics.com) en Customer Insights. Si aún no tiene una suscripción, [Regístrese para obtener una versión de prueba de Customer Insights](https://aka.ms/tryci).

1. Para habilitar las API en su entorno de Customer Insights, vaya a **Administración** > **Permisos**. Necesitará permisos de administrador para hacerlo.

1. Vaya a la pestaña **API** y seleccione el botón **Habilitar**.    
 
   La habilitación de las API crea una clave de suscripción primaria y secundaria para su instancia que se usa en las solicitudes de API. Puede regenerar las claves seleccionando **Regenerar primaria** o **Regenerar secundaria** en **Administración** > **Permisos** > **API**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Seleccione **Explorar nuestras API** para [probar las API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Elija una operación de API y seleccione **Intentarlo**.

1. En el panel lateral, establezca el valor en el menú desplegable **Autorización** a **implícito**. El encabezado `Authorization` se agrega con un token de portador. Su clave de suscripción se completará automáticamente.
  
1. Opcionalmente, agregue todos los parámetros de consulta necesarios.

1. Desplácese hacia la parte inferior del panel lateral y seleccione **Enviar**.

La respuesta HTTP pronto aparecerá a continuación.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Crear un registro de nueva aplicación en Azure Portal

Estos pasos lo ayudarán a comenzar a usar las API de Customer Insights en una aplicación de Azure con permisos delegados. Asegúrese de completar primero la [sección de introducción](#get-started-trying-the-customer-insights-apis).

1. Inicie sesión en [Azure Portal](https://portal.azure.com) con la cuenta que puede acceder a los datos de Customer Insights.

1. A la izquierda, seleccione **Registros de aplicaciones**.

1. Seleccione **Nuevo registro**, facilite un nombre de aplicación y elija el tipo de cuenta.
 
   Opcioonalmente, agregue una URL de redireccionamiento. http://localhost es suficiente para desarrollar una aplicación en su equipo local.

1. En el registro de su nueva aplicación, vaya a **Permisos de API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Seleccione **Agregar permiso** y seleccione **Customer Insights** en el panel lateral.

1. En **Tipo de permiso**, seleccione **Permisos delegados** y seleccione el permiso **user_impersonation**.

1. Seleccione **Agregar permisos**. Si necesita acceder a la API sin que un usuario inicie sesión, revise la sección [Permisos de aplicaciones de servidor a servidor](#server-to-server-application-permissions).

1. Seleccione **Otorgar consentimiento de administrador para...** para completar el registro de la aplicación.

Puede utilizar la aplicación/id. de cliente para el registro de esta aplicación con la biblioteca de autenticación de Microsoft (MSAL) para obtener un token de portador para enviar con su solicitud a la API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Para obtener más información sobre MSAL, consulte [Descripción general de la biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Para obtener más información sobre el registro de aplicaciones en Azure, consulte [Registrar una aplicación](/graph/auth-register-app-v2).

Para obtener información sobre el uso de las API en nuestras bibliotecas cliente, consulte [Bibliotecas cliente de Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisos de aplicaciones de servidor a servidor

La [sección de registro de aplicaciones](#create-a-new-app-registration-in-the-azure-portal) describe cómo registrar una aplicación que requiere que un usuario inicie sesión para la autenticación. Aprenda a crear un registro de aplicación que no necesite la interacción del usuario y que se pueda ejecutar en un servidor.

1. En el registro de su aplicación en Azure Portal, vaya a **Permisos de API**.

1. Seleccione **Agregar permiso**. 

1. Seleccione la pestaña **API que usa mi organización** y elija **Dynamics 365 AI for Customer Insights** en la lista. 

1. Para **Tipo de permiso**, seleccione **Permisos de aplicación** y, después, seleccione el permiso **CustomerInsights.Api.All**.

1. Seleccione **Agregar permisos**.

1. Vuelva a **Permisos de API** para el registro de su aplicación.

1. Seleccione **Otorgar consentimiento de administrador para...** para completar el registro de la aplicación.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Para concluir, tenemos que agregar el nombre del registro de la aplicación como usuario en Customer Insights.  
   
   Abra Customer Insights, vaya a **Administrador** > **Permisos** y seleccione **Agregar usuario**.

1. Busque el nombre del registro de su aplicación, selecciónelo en los resultados de búsqueda y seleccione **Guardar**.

## <a name="sample-queries"></a>Consultas de ejemplo

Hemos compilado una breve lista de consultas de muestra de OData para trabajar con las API: [Ejemplos de consultas de OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Bibliotecas de cliente de Customer Insights

Esta sección le ayuda a empezar a utilizar las bibliotecas de cliente disponibles para las API de Customer Insights. Todo el código fuente de la biblioteca y las aplicaciones de muestra se pueden encontrar en la [página de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Obtenga información sobre cómo comenzar a usar las bibliotecas de cliente de C# de NuGet.org. Para obtener más información sobre el paquete NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Actualmente, este paquete se dirige a los marcos netstandard2.0 y netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Agregar la biblioteca de cliente de C# a un proyecto de C#

1. En Visual Studio, abra el **NuGet Administrador de paquetes** para su proyecto.

1. Busque **Microsoft.Dynamics.CustomerInsights.Api**.

1. Seleccione **Instalar** para agregar el paquete al proyecto.
 
   Alternativamente, ejecute este comando en la **Consola del administrador de paquetes de NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Usar la biblioteca de cliente de C#

1. Utilice la [Biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obtener un `AccessToken` usando su [Registro de la aplicación de Azure](#create-a-new-app-registration-in-the-azure-portal) existente.

1. Después de autenticar y adquirir correctamente un token, construya uno nuevo o use un `HttpClient` existente con la **"Autorización" DefaultRequestHeaders** ajustada en **Portador "token de acceso"** y **Ocp-Apim-Subscription-Key** establecido en la [**clave de suscripción** de su entorno de Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Restablezca el encabezado **Autorización** cuando sea apropiado. Por ejemplo, cuando haya expirado el token.

1. Pase este `HttpClient` a la construcción del cliente de `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Realice llamadas con el cliente a los "métodos de extensión", por ejemplo, `GetAllInstancesAsync`. Si el acceso al `Microsoft.Rest.HttpOperationResponse` subyacente es preferible, utilice los "métodos de mensaje http", por ejemplo `GetAllInstancesWithHttpMessagesAsync`.

1. La respuesta probablemente será del tipo `object` porque el método puede devolver varios tipos (por ejemplo, `IList<InstanceInfo>` y `ApiErrorResult`). Para comprobar el tipo de retorno, utilice los objetos en los tipos de respuesta especificados en la [página de detalles de la API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para esa operación.    
   
   Si necesita más información sobre la solicitud, utilice los **métodos de mensaje http** para acceder al objeto de respuesta sin procesar.

### <a name="nodejs-package"></a>Paquete NodeJS

Utilice las bibliotecas cliente de NodeJS disponibles a través de NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paquete de Python

Utilice las bibliotecas cliente de Python disponibles a través de PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]