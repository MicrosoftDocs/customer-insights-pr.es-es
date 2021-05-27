---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar la conexión y a exportar a Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976247"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="4268e-103">Usar segmentos en Dynamics 365 Sales (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4268e-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4268e-104">Use sus datos de clientes para crear listas de marketing, realizar un seguimiento de los flujos de trabajo y enviar promociones con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4268e-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="4268e-105">Requisito previo para una conexión</span><span class="sxs-lookup"><span data-stu-id="4268e-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="4268e-106">Los registros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales.</span><span class="sxs-lookup"><span data-stu-id="4268e-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="4268e-107">Más información sobre cómo ingerir contactos en [Dynamics 365 Sales usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="4268e-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="4268e-108">La exportación de segmentos de las informaciones de público a Sales no creará nuevos registros de contactos en las instancias de Sales.</span><span class="sxs-lookup"><span data-stu-id="4268e-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="4268e-109">Los registros de contacto de Sales deben ingerirse en las informaciones de público y usarse como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4268e-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="4268e-110">También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.</span><span class="sxs-lookup"><span data-stu-id="4268e-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="4268e-111">Configurar la conexión con Sales</span><span class="sxs-lookup"><span data-stu-id="4268e-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="4268e-112">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="4268e-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4268e-113">Seleccione **Agregar conexión** y elija **Dynamics 365 Sales** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="4268e-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="4268e-114">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="4268e-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4268e-115">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="4268e-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4268e-116">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="4268e-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4268e-117">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="4268e-117">Choose who can use this connection.</span></span> <span data-ttu-id="4268e-118">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="4268e-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4268e-119">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4268e-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4268e-120">Introduzca la dirección URL de Sales de su organización en el campo **Dirección del servidor**.</span><span class="sxs-lookup"><span data-stu-id="4268e-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="4268e-121">En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4268e-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="4268e-122">Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4268e-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="4268e-123">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="4268e-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="4268e-124">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="4268e-124">Configure an export</span></span>

<span data-ttu-id="4268e-125">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4268e-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4268e-126">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4268e-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4268e-127">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="4268e-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4268e-128">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="4268e-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4268e-129">En el campo **Conexión para exportación**, elija una conexión de la sección Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4268e-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="4268e-130">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="4268e-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4268e-131">Elija uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="4268e-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="4268e-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4268e-132">Select **Save**</span></span>

<span data-ttu-id="4268e-133">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4268e-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4268e-134">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4268e-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4268e-135">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4268e-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
