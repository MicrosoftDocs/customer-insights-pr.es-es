---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar la conexión y a exportar a Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759658"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="6888f-103">Usar segmentos en Dynamics 365 Marketing (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6888f-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6888f-104">Use los [segmentos](segments.md) creados para generar campañas y contactar con grupos específicos de clientes con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6888f-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="6888f-105">Para obtener más información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="6888f-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="6888f-106">Requisito previo para una conexión</span><span class="sxs-lookup"><span data-stu-id="6888f-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="6888f-107">Los registros de contacto deben estar presentes en Dynamics 365 Marketing antes de poder exportar un segmento de Customer Insights a Marketing.</span><span class="sxs-lookup"><span data-stu-id="6888f-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="6888f-108">Más información sobre cómo ingerir contactos en [Dynamics 365 Marketing usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6888f-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="6888f-109">La exportación de segmentos de las informaciones de público a Marketing no creará nuevos registros de contactos en las instancias de Marketing.</span><span class="sxs-lookup"><span data-stu-id="6888f-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="6888f-110">Los registros de contacto de Marketing deben ingerirse en las informaciones de público y usarse como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6888f-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="6888f-111">También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.</span><span class="sxs-lookup"><span data-stu-id="6888f-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="6888f-112">Configurar conexión a Marketing</span><span class="sxs-lookup"><span data-stu-id="6888f-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="6888f-113">Vaya a **Administrador** > **Conexiones**.</span><span class="sxs-lookup"><span data-stu-id="6888f-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6888f-114">Seleccione **Agregar conexión** y elija **Dynamics 365 Marketing** para configurar la conexión.</span><span class="sxs-lookup"><span data-stu-id="6888f-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="6888f-115">Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="6888f-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6888f-116">El nombre y el tipo de conexión describe esta conexión.</span><span class="sxs-lookup"><span data-stu-id="6888f-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6888f-117">Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="6888f-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6888f-118">Elija quién puede utilizar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="6888f-118">Choose who can use this connection.</span></span> <span data-ttu-id="6888f-119">Si no realiza ninguna acción, el valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="6888f-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6888f-120">Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6888f-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6888f-121">Introduzca la dirección URL de Marketing de su organización en el campo **Dirección del servidor**.</span><span class="sxs-lookup"><span data-stu-id="6888f-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6888f-122">En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6888f-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="6888f-123">Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6888f-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6888f-124">Seleccione **Guardar** para completar la conexión.</span><span class="sxs-lookup"><span data-stu-id="6888f-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="6888f-125">Configurar una exportación</span><span class="sxs-lookup"><span data-stu-id="6888f-125">Configure an export</span></span>

<span data-ttu-id="6888f-126">Puede configurar esta exportación si tiene acceso a una conexión de este tipo.</span><span class="sxs-lookup"><span data-stu-id="6888f-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6888f-127">Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6888f-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6888f-128">Vaya a **Datos** > **Exportaciones**.</span><span class="sxs-lookup"><span data-stu-id="6888f-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6888f-129">Para crear una exportación nueva, seleccione **Agregar destino**.</span><span class="sxs-lookup"><span data-stu-id="6888f-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6888f-130">En el campo **Conexión para exportación**, elija una conexión de la sección Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="6888f-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="6888f-131">Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="6888f-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6888f-132">Elija uno o más segmentos.</span><span class="sxs-lookup"><span data-stu-id="6888f-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="6888f-133">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6888f-133">Select **Save**.</span></span>

<span data-ttu-id="6888f-134">Guardar una exportación no ejecuta la exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6888f-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6888f-135">La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6888f-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6888f-136">Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6888f-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
