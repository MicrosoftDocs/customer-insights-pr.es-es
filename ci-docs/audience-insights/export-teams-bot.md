---
title: Bot para Microsoft Teams
description: Busque perfiles de clientes unificados en Microsoft Teams con la ayuda de un bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407037"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="fb720-103">Bot de Teams para Dynamics 365 Customer Insights (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="fb720-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="fb720-104">Conéctese con Microsoft Teams para permitir que un bot busque perfiles de clientes unificados en los canales de Teams.</span><span class="sxs-lookup"><span data-stu-id="fb720-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb720-105">![Bot de Teams mostrando un registro de cliente](media/teams-bot.png "Bot de Teams mostrando un registro de cliente")</span><span class="sxs-lookup"><span data-stu-id="fb720-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb720-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fb720-106">Prerequisites</span></span>

<span data-ttu-id="fb720-107">Para preparar y configurar el bot deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="fb720-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fb720-108">Hay al menos un [origen de datos agregado](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="fb720-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="fb720-109">Se ha completado la instancia de [proceso de unificación](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fb720-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="fb720-110">Se han agregado campos a [índice de búsqueda y filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="fb720-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="fb720-111">Customer Insights y Teams están en la misma organización.</span><span class="sxs-lookup"><span data-stu-id="fb720-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="fb720-112">Configurar el bot</span><span class="sxs-lookup"><span data-stu-id="fb720-112">Configure the bot</span></span>

1. <span data-ttu-id="fb720-113">En las informaciones de público, vaya a **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="fb720-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="fb720-114">En el icono de Microsoft Teams, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="fb720-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="fb720-115">Se le redirigirá al área **Aplicaciones** en equipos.</span><span class="sxs-lookup"><span data-stu-id="fb720-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="fb720-116">También puede abrir Teams y seleccionar **Aplicaciones** en la esquina inferior izquierda u [obtenerlo de AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directamente.</span><span class="sxs-lookup"><span data-stu-id="fb720-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="fb720-117">Busque **Customer Insights** y seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb720-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="fb720-118">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fb720-118">Select **Add**.</span></span>
1. <span data-ttu-id="fb720-119">Después de iniciar sesión en Customer Insights dentro de Teams, verá un mensaje de bienvenida y podrá empezar.</span><span class="sxs-lookup"><span data-stu-id="fb720-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="fb720-120">Cosas que puede hacer con el bot</span><span class="sxs-lookup"><span data-stu-id="fb720-120">Things you can do with the bot</span></span>

<span data-ttu-id="fb720-121">El bot proporciona capacidades de búsqueda para perfiles de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="fb720-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="fb720-122">Escriba **buscar** seguido de un nombre, dirección de correo electrónico o cualquier otro campo del perfil de cliente unificado que se haya agregado al índice de búsqueda y filtrado.</span><span class="sxs-lookup"><span data-stu-id="fb720-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="fb720-123">Obtendrá una tarjeta con hasta 15 campos del perfil de cliente resultante.</span><span class="sxs-lookup"><span data-stu-id="fb720-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="fb720-124">Múltiples coincidencias devuelven una lista de resultados en la que puede seleccionar un perfil.</span><span class="sxs-lookup"><span data-stu-id="fb720-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="fb720-125">Puede agregar el término de búsqueda entre comillas dobles para buscar una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="fb720-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="fb720-126">Si su organización mantiene varios entornos de Customer Insights en la misma organización, puede introducir **switchinstance** para elegir el entorno al que desea conectar el bot.</span><span class="sxs-lookup"><span data-stu-id="fb720-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="fb720-127">Escriba **ayuda** para ver una lista de comandos disponibles para el bot.</span><span class="sxs-lookup"><span data-stu-id="fb720-127">Enter **help** to see a list of available commands for the bot.</span></span>  
