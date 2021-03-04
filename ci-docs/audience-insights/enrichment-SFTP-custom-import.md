---
title: Enriquecimiento con importación personalizada SFTP
description: Información general sobre el enriquecimiento de importación personalizada SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269627"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="e9db4-103">Enriquezca los perfiles de los clientes con datos personalizados (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="e9db4-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="e9db4-104">La importación personalizada del Protocolo de transferencia segura de archivos (SFTP) le permite importar datos que no tienen que pasar por el proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="e9db4-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="e9db4-105">Es una forma flexible, segura y fácil de incorporar sus datos.</span><span class="sxs-lookup"><span data-stu-id="e9db4-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="e9db4-106">La importación personalizada SFTP se puede utilizar en combinación con la [Exportación SFTP](export-sftp.md) que le permite exportar los datos del perfil del cliente necesarios para el enriquecimiento.</span><span class="sxs-lookup"><span data-stu-id="e9db4-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="e9db4-107">Luego, los datos se pueden procesar, enriquecer y la importación personalizada de SFTP se puede utilizar para devolver los datos enriquecidos a la capacidad de información de público de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e9db4-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9db4-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e9db4-108">Prerequisites</span></span>

<span data-ttu-id="e9db4-109">Para configurar la importación personalizada de SFTP, se deben cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="e9db4-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e9db4-110">Tiene credenciales de usuario (nombre de usuario y contraseña) para la ubicación SFTP desde donde se importarán los datos.</span><span class="sxs-lookup"><span data-stu-id="e9db4-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="e9db4-111">Tiene la URL y el número de puerto (generalmente 22) para el host STFP.</span><span class="sxs-lookup"><span data-stu-id="e9db4-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="e9db4-112">Tiene el nombre de archivo y la ubicación del archivo que se va a importar en el servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="e9db4-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="e9db4-113">Hay un archivo *model.json* que especifica el esquema de los datos que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="e9db4-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="e9db4-114">Este archivo debe estar en el mismo directorio que el archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="e9db4-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="e9db4-115">Tiene permisos de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="e9db4-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="e9db4-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="e9db4-116">Configuration</span></span>

1. <span data-ttu-id="e9db4-117">Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="e9db4-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e9db4-118">En el **mosaico de importación personalizada de SFTP Technologies**, seleccione **Enriquecer mis datos**.</span><span class="sxs-lookup"><span data-stu-id="e9db4-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9db4-119">![Mosaico de importación personalizado de SFTP](media/SFTP_Custom_Import_tile.png "Mosaico de importación personalizado de SFTP")</span><span class="sxs-lookup"><span data-stu-id="e9db4-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="e9db4-120">Seleccione **Comenzar** y proporcione las credenciales y la dirección del servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="e9db4-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="e9db4-121">Por ejemplo, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="e9db4-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="e9db4-122">Introduzca el nombre del archivo que contiene los datos y la ruta al archivo en el servidor SFTP si no está en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="e9db4-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="e9db4-123">Confirme todas las entradas seleccionando **Conectarse a la importación personalizada**.</span><span class="sxs-lookup"><span data-stu-id="e9db4-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9db4-124">![Control flotante de configuración de importación personalizada SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Control flotante de configuración de importación personalizada SFTP")</span><span class="sxs-lookup"><span data-stu-id="e9db4-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="e9db4-125">Definición de asignaciones de campos</span><span class="sxs-lookup"><span data-stu-id="e9db4-125">Defining field mappings</span></span> 

<span data-ttu-id="e9db4-126">El directorio que contiene el archivo que se va a importar en el servidor SFTP también debe contener un archivo *model.json*.</span><span class="sxs-lookup"><span data-stu-id="e9db4-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="e9db4-127">Este archivo define el esquema que se utilizará para importar los datos.</span><span class="sxs-lookup"><span data-stu-id="e9db4-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="e9db4-128">El esquema tiene que usar [Common Data Model](https://docs.microsoft.com/common-data-model/) para especificar la asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="e9db4-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="e9db4-129">Un ejemplo sencillo de un archivo model.json tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e9db4-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="e9db4-130">Resultados del enriquecimiento</span><span class="sxs-lookup"><span data-stu-id="e9db4-130">Enrichment results</span></span>

<span data-ttu-id="e9db4-131">Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="e9db4-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e9db4-132">También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e9db4-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e9db4-133">El tiempo de procesamiento dependerá del tamaño de los datos a importar y de la conexión al servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="e9db4-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="e9db4-134">Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de enriquecimiento personalizados recién importados en **Mis enriquecimientos**.</span><span class="sxs-lookup"><span data-stu-id="e9db4-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="e9db4-135">Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="e9db4-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e9db4-136">Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="e9db4-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9db4-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e9db4-137">Next steps</span></span>

<span data-ttu-id="e9db4-138">Utilice los datos enriquecidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="e9db4-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e9db4-139">Cree [segmentos](segments.md), [medidas](measures.md) y [exporte los datos](export-destinations.md) para brindar experiencias personalizadas a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="e9db4-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]