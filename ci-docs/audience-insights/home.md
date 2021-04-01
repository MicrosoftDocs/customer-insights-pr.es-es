---
title: Página de inicio en informaciones de público
description: Comience a explorar la aplicación en la página Inicio.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597256"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="189f1-103">Crear un nuevo entorno</span><span class="sxs-lookup"><span data-stu-id="189f1-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="189f1-104">Crear un entorno de prueba</span><span class="sxs-lookup"><span data-stu-id="189f1-104">Create a trial environment</span></span>

<span data-ttu-id="189f1-105">Puede registrarse para una prueba en la [página de suscripción de prueba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span><span class="sxs-lookup"><span data-stu-id="189f1-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="189f1-106">Las pruebas caducan después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="189f1-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="189f1-107">Elija la opción **Suscribirse para una prueba gratis** y seleccione **Registrarse ahora**.</span><span class="sxs-lookup"><span data-stu-id="189f1-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="189f1-108">Proporcione la dirección de correo electrónico de su trabajo o escuela, cuéntenos más sobre usted y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="189f1-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Cuadro de diálogo para registrarse para obtener una instancia de prueba:":::

1. <span data-ttu-id="189f1-110">Introduzca un **Nombre** para el nuevo entorno.</span><span class="sxs-lookup"><span data-stu-id="189f1-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="189f1-111">Seleccione el tipo de prueba.</span><span class="sxs-lookup"><span data-stu-id="189f1-111">Select the trial type.</span></span>

1. <span data-ttu-id="189f1-112">Elija la **Región** para su entorno.</span><span class="sxs-lookup"><span data-stu-id="189f1-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="189f1-113">Opcionalmente, para administradores de una organización de Dynamics 365: seleccione **Configuración avanzada** y proporcione la URL de su organización para usar características de predicción como el abandono de clientes.</span><span class="sxs-lookup"><span data-stu-id="189f1-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="189f1-114">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="189f1-114">Select **Create**.</span></span> 

<span data-ttu-id="189f1-115">Una vez creado el entorno, verá el entorno **Demo**, que le permite explorar la aplicación con datos ficticios.</span><span class="sxs-lookup"><span data-stu-id="189f1-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="189f1-116">Puede cambiar los datos de ejemplo para que coincidan con su industria.</span><span class="sxs-lookup"><span data-stu-id="189f1-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="189f1-117">Seleccione el icono **Configuración** en el encabezado y seleccione **Configuración de demostración**.</span><span class="sxs-lookup"><span data-stu-id="189f1-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="189f1-118">Además, puede cambiar el tema visual.</span><span class="sxs-lookup"><span data-stu-id="189f1-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="189f1-119">[Cambie al entorno](#switch-environments) que creó durante el proceso de registro para trabajar con sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="189f1-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="189f1-120">Cree un nuevo entorno de producción o de espacio aislado</span><span class="sxs-lookup"><span data-stu-id="189f1-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="189f1-121">En su entorno, seleccione el selector **Entornos** en el encabezado de la aplicación y seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="189f1-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="189f1-122">Siga los pasos como si [creara un entorno de prueba](#create-a-trial-environment).</span><span class="sxs-lookup"><span data-stu-id="189f1-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="189f1-123">De forma predeterminada, los datos se almacenan en el data lake administrado por Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="189f1-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="189f1-124">Obtenga una opción adicional al seleccionar **Configuración avanzada** para almacenar sus datos en su propio Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="189f1-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="189f1-125">Proporcione su nombre de cuenta y clave de cuenta para establecer una conexión con su Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="189f1-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="189f1-126">Al guardar datos en su Azure Data Lake Storage, acepta que los datos se transferirán a la ubicación geográfica adecuada y se almacenarán en ella para esa cuenta de Azure Storage, que puede ser distinta del lugar en el que se almacenan los datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="189f1-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="189f1-127">Obtenga más información en el Centro de confianza de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="189f1-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="189f1-128">Explorar la página principal</span><span class="sxs-lookup"><span data-stu-id="189f1-128">Explore the home page</span></span>

<span data-ttu-id="189f1-129">Puede [acceder a las informaciones de público de Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) en la siguiente URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="189f1-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="189f1-130">La página **Inicio** muestra una descripción general de los segmentos, las medidas y los datos de enriquecimiento (si están configurados) después de completar las etapas de [asignación](map-entities.md), [correspondencia](match-entities.md) y [combinación](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="189f1-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="189f1-131">![Información en página principal](media/home-page-insights.png "Información en página principal")</span><span class="sxs-lookup"><span data-stu-id="189f1-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="189f1-132">En **Segmentos recientes** verá grupos de clientes según los atributos demográficos, de comportamiento o transaccionales que haya definido.</span><span class="sxs-lookup"><span data-stu-id="189f1-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="189f1-133">La [creación de segmentos](segments.md) le ayuda a agrupar su base de clientes y orientar mejor sus actividades comerciales.</span><span class="sxs-lookup"><span data-stu-id="189f1-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="189f1-134">Las **Medidas recientes** muestran iconos con [indicadores clave de rendimiento (KPI)](measures.md) que ha definido.</span><span class="sxs-lookup"><span data-stu-id="189f1-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="189f1-135">Por ejemplo, la probabilidad promedio de que un cliente abandone o el gasto promedio en línea por cliente.</span><span class="sxs-lookup"><span data-stu-id="189f1-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="189f1-136">La sección **Enriquecimientos recientes** enumera los resultados de las ejecuciones de enriquecimiento que se completaron recientemente.</span><span class="sxs-lookup"><span data-stu-id="189f1-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="189f1-137">Los [enriquecimientos](enrichment-hub.md) agregan información sobre su base de clientes.</span><span class="sxs-lookup"><span data-stu-id="189f1-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="189f1-138">Por ejemplo, comprendiendo los intereses y las marcas por las que tienen afinidad.</span><span class="sxs-lookup"><span data-stu-id="189f1-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="189f1-139">Cambiar entornos</span><span class="sxs-lookup"><span data-stu-id="189f1-139">Switch environments</span></span>

<span data-ttu-id="189f1-140">Seleccione el control **Entorno** en la esquina superior derecha de la página para cambiar entornos.</span><span class="sxs-lookup"><span data-stu-id="189f1-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="189f1-141">![Cambiar entorno](media/home-page-environment-switcher.png "Cambiar entorno")</span><span class="sxs-lookup"><span data-stu-id="189f1-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="189f1-142">Los administradores pueden crear y administrar [entornos múltiples](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="189f1-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="189f1-143">Mantener más de un entorno puede ser útil si, por ejemplo, su organización opera internacionalmente y necesita segregar datos e información de diferentes maneras.</span><span class="sxs-lookup"><span data-stu-id="189f1-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="189f1-144">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="189f1-144">Next step</span></span>

<span data-ttu-id="189f1-145">Para ver sus propias ideas en la página de inicio, primero deberá [agregar orígenes de datos](data-sources.md) y [unificar](data-unification.md) sus datos para crear perfiles de clientes.</span><span class="sxs-lookup"><span data-stu-id="189f1-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]