---
title: Solicitudes de interesados (DSR) en virtud del RGPD | Microsoft Docs
description: Responder a las solicitudes de los interesados en relación con la capacidad de informaciones de público para Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597532"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="3b678-103">Solicitudes del interesado (DSR) en el contexto del RGPD</span><span class="sxs-lookup"><span data-stu-id="3b678-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="3b678-104">Respuesta a las solicitudes de eliminación de los interesados del RGPD en relación con la capacidad de informaciones de público para Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3b678-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="3b678-105">El "derecho a la eliminación" de datos personales de los datos de los clientes de una organización es una protección clave en el Reglamento general de protección de datos (RGPD).</span><span class="sxs-lookup"><span data-stu-id="3b678-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="3b678-106">La eliminación de los datos personales incluye la eliminación de todos los datos personales y registros generados por el sistema, excepto la información del registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="3b678-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="3b678-107">Administrar solicitudes de eliminación de interesados</span><span class="sxs-lookup"><span data-stu-id="3b678-107">Manage data subject delete requests</span></span>

<span data-ttu-id="3b678-108">Las informaciones de público ofrecen las siguientes experiencias en el producto para eliminar datos personales de un cliente o usuario específico:</span><span class="sxs-lookup"><span data-stu-id="3b678-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="3b678-109">**Administrar solicitudes de eliminación de datos de clientes**: los datos de clientes de Customer Insights se procesan de orígenes de datos originales externos a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b678-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="3b678-110">Todas las solicitudes de eliminación del RGPD deben realizarse en el origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="3b678-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="3b678-111">**Gestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Customer Insights crea los datos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b678-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="3b678-112">Todas las solicitudes de eliminación del RGPD deben realizarse en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b678-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="3b678-113">Administrar solicitudes de eliminación de datos de clientes</span><span class="sxs-lookup"><span data-stu-id="3b678-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="3b678-114">Un administrador de Customer Insights puede seguir estos pasos para quitar datos del cliente que se eliminaron en el origen de datos:</span><span class="sxs-lookup"><span data-stu-id="3b678-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="3b678-115">Inicie sesión en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b678-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="3b678-116">En informaciones de público, vaya a **Datos** > **Orígenes de datos**</span><span class="sxs-lookup"><span data-stu-id="3b678-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="3b678-117">Para cada origen de datos de la lista que contiene datos de clientes eliminados:</span><span class="sxs-lookup"><span data-stu-id="3b678-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="3b678-118">Seleccione (...) y después **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="3b678-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="3b678-119">Compruebe el estado del origen de datos en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="3b678-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="3b678-120">Una marca de verificación significa que la actualización se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b678-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="3b678-121">Un triángulo de advertencia significa que algo salió mal.</span><span class="sxs-lookup"><span data-stu-id="3b678-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="3b678-122">Si se muestra un triángulo de advertencia, póngase en contacto con D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3b678-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3b678-123">![Administrar solicitudes de eliminación de datos de clientes del RGPD](media/gdpr-data-sources.png "Administrar solicitudes de eliminación de datos de clientes del RGPD")</span><span class="sxs-lookup"><span data-stu-id="3b678-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="3b678-124">Administrar solicitudes de eliminación de datos de usuarios</span><span class="sxs-lookup"><span data-stu-id="3b678-124">Manage delete requests for user data</span></span>

<span data-ttu-id="3b678-125">Un administrador de Customer Insights puede seguir estos pasos para eliminar los datos de clientes de Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="3b678-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="3b678-126">Inicie sesión en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b678-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="3b678-127">En informaciones de público, vaya a **Administración** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="3b678-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="3b678-128">Active la casilla del usuario que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="3b678-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="3b678-129">Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="3b678-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3b678-130">![Manejar las solicitudes de eliminación de datos de usuarios del RGPD](media/gdpr-permissions.png "Manejar las solicitudes de eliminación de datos de usuarios del RGPD")</span><span class="sxs-lookup"><span data-stu-id="3b678-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="3b678-131">Responder a las solicitudes de exportación del interesado de acuerdo con el RGPD</span><span class="sxs-lookup"><span data-stu-id="3b678-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="3b678-132">Como parte de nuestro compromiso de colaborar con usted en su viaje hacia el Reglamento General de Protección de Datos (RGPD), hemos desarrollado documentación para ayudarle a prepararse.</span><span class="sxs-lookup"><span data-stu-id="3b678-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="3b678-133">Esta documentación describe los pasos que puede seguir hoy para respaldar el cumplimiento del RGPD al usar las informaciones de público.</span><span class="sxs-lookup"><span data-stu-id="3b678-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="3b678-134">Administrar solicitudes de exportación y visualización</span><span class="sxs-lookup"><span data-stu-id="3b678-134">Manage export and view requests</span></span>

<span data-ttu-id="3b678-135">El derecho de la portabilidad de datos no permite a los interesados solicitar una copia de sus datos personales en formato electrónico (definido como “formato estructurado, de uso frecuente, de lectura mecánica e interoperable") que se puede transmitir a otro responsable de los datos.</span><span class="sxs-lookup"><span data-stu-id="3b678-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="3b678-136">Exportar datos de clientes (administración de inquilinos)</span><span class="sxs-lookup"><span data-stu-id="3b678-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="3b678-137">Un administrador de inquilinos puede seguir estos pasos para exportar datos:</span><span class="sxs-lookup"><span data-stu-id="3b678-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="3b678-138">Envíe un correo electrónico de D365CI@microsoft.com especificando la dirección de correo electrónico del cliente en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3b678-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="3b678-139">El equipo de Customer Insights enviará un correo electrónico a la dirección de correo electrónico del administrador del inquilino registrado, solicitando confirmación para exportar los datos.</span><span class="sxs-lookup"><span data-stu-id="3b678-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="3b678-140">Acepte la confirmación para exportar los datos del cliente solicitado.</span><span class="sxs-lookup"><span data-stu-id="3b678-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="3b678-141">Reciba los datos exportados a través de la dirección de correo electrónico del administrador del inquilino.</span><span class="sxs-lookup"><span data-stu-id="3b678-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="3b678-142">Exportar datos de usuarios (administrador de inquilinos)</span><span class="sxs-lookup"><span data-stu-id="3b678-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="3b678-143">Envíe un correo a D365CI@microsoft.com especificando la dirección de correo electrónico del usuario en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3b678-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="3b678-144">El equipo de Customer Insights enviará un correo electrónico a la dirección de correo electrónico del administrador del inquilino registrado, solicitando confirmación para exportar los datos.</span><span class="sxs-lookup"><span data-stu-id="3b678-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="3b678-145">Acepte la confirmación para exportar los datos del usuario solicitado.</span><span class="sxs-lookup"><span data-stu-id="3b678-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="3b678-146">Reciba los datos exportados a través de la dirección de correo electrónico del administrador del inquilino.</span><span class="sxs-lookup"><span data-stu-id="3b678-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]