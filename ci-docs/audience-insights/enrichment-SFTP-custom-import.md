---
title: Enriquecimiento con importación personalizada SFTP
description: Información general sobre el enriquecimiento de importación personalizada SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304671"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="fe5c8-103">Enriquezca los perfiles de los clientes con datos personalizados (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="fe5c8-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="fe5c8-104">La importación personalizada del Protocolo de transferencia segura de archivos (SFTP) le permite importar datos que no tienen que pasar por el proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="fe5c8-105">Es una forma flexible, segura y fácil de incorporar sus datos.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="fe5c8-106">La importación personalizada SFTP se puede utilizar en combinación con la [Exportación SFTP](export-sftp.md) que le permite exportar los datos del perfil del cliente necesarios para el enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="fe5c8-107">Luego, los datos se pueden procesar y enriquecer, y la importación personalizada SFTP se puede utilizar para devolver los datos enriquecidos a la función Audiencie Insights de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe5c8-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fe5c8-108">Prerequisites</span></span>

<span data-ttu-id="fe5c8-109">Para configurar la importación personalizada de SFTP, se deben cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="fe5c8-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fe5c8-110">Tiene el nombre del archivo y la ubicación (ruta) del archivo que se va a importar en el host SFTP.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="fe5c8-111">Hay un archivo *model.json* que especifica [el esquema de Common Data Model](/common-data-model/) para que los datos se importen.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="fe5c8-112">Este archivo debe estar en el mismo directorio que el archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="fe5c8-113">Una conexión SFTP ya ha sido configurada por un administrador *o* tiene permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="fe5c8-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="fe5c8-114">Necesitará las credenciales de usuario, la dirección URL y el número de puerto para la ubicación SFTP desde la que desea importar los datos.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="fe5c8-115">Configurar la importación</span><span class="sxs-lookup"><span data-stu-id="fe5c8-115">Configure the import</span></span>

1. <span data-ttu-id="fe5c8-116">Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="fe5c8-117">En la **ventana de importación personalizada de SFTP**, seleccione **Enriquecer mis datos** y, luego, seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ventana de importación personalizada de SFTP.":::

1. <span data-ttu-id="fe5c8-119">Seleccione una [conexión](connections.md) en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="fe5c8-120">Contacte con un administrador si no hay conexión disponible.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="fe5c8-121">Si es un administrador, puede crear una conexión seleccionando **Agregar conexión** y eligiendo **Importación personalizada de SFTP** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="fe5c8-122">Seleccione **Conectar a importación personalizada** para confirmar la conexión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="fe5c8-123">Seleccione **Siguiente** y especifique la **Ruta** y el **Nombre del archivo** del archivo de datos que desea importar.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de pantalla al especificar la ubicación de los datos.":::

1. <span data-ttu-id="fe5c8-125">Seleccione **Siguiente** y proporcione un nombre para el enriquecimiento y un nombre para la entidad de salida.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="fe5c8-126">Seleccione **Guardar enriquecimiento** después de revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="fe5c8-127">Configurar la conexión para la importación personalizada de SFTP</span><span class="sxs-lookup"><span data-stu-id="fe5c8-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="fe5c8-128">Debe ser un administrador para configurar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="fe5c8-129">Seleccione **Agregar conexión** cuando configure un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Importación personalizada.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="fe5c8-130">Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="fe5c8-131">Especifique un nombre de usuario y contraseña y una dirección URL de host válidos para el servidor SFTP en el que residen los datos que se importarán.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="fe5c8-132">Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="fe5c8-133">Seleccione **Verificar** para validar la configuración.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="fe5c8-134">Una vez que se ha completado la verificación, la conexión se puede guardar seleccionando **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe5c8-135">![Página de configuración de conexión de Experian](media/enrichment-SFTP-connection.png "Página de configuración de conexión de Experian").</span><span class="sxs-lookup"><span data-stu-id="fe5c8-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="fe5c8-136">Definición de asignaciones de campos</span><span class="sxs-lookup"><span data-stu-id="fe5c8-136">Defining field mappings</span></span> 

<span data-ttu-id="fe5c8-137">El directorio que contiene el archivo que se va a importar en el servidor SFTP también debe contener un archivo *model.json*.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="fe5c8-138">Este archivo define el esquema que se utilizará para importar los datos.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="fe5c8-139">El esquema tiene que usar [Common Data Model](/common-data-model/) para especificar la asignación de campo.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="fe5c8-140">Un ejemplo sencillo de un archivo model.json tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="fe5c8-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="fe5c8-141">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="fe5c8-141">Enrichment results</span></span>

<span data-ttu-id="fe5c8-142">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fe5c8-143">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fe5c8-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fe5c8-144">El tiempo de procesamiento dependerá del tamaño de los datos a importar y de la conexión al servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="fe5c8-145">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de enriquecimiento personalizados recién importados en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="fe5c8-146">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fe5c8-147">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe5c8-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fe5c8-148">Next steps</span></span>

<span data-ttu-id="fe5c8-149">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fe5c8-150">Cree [segmentos](segments.md) y [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para brindar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="fe5c8-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
