---
title: Conectar datos de Common Data Model a una cuenta de Azure Data Lake
description: Trabajar con datos de Common Data Model usando Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267881"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="d6ad8-103">Conectarse a una carpeta de Common Data Model mediante una cuenta de Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="d6ad8-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="d6ad8-104">Este artículo proporciona información sobre cómo ingerir datos de una carpeta de Common Data Model usando su cuenta de Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="d6ad8-105">Consideraciones importantes</span><span class="sxs-lookup"><span data-stu-id="d6ad8-105">Important considerations</span></span>

- <span data-ttu-id="d6ad8-106">Los datos de su Azure Data Lake deben seguir el estándar de Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="d6ad8-107">Otros formatos no son compatibles en este momento.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="d6ad8-108">La ingestión de datos admite solo cuentas de almacenamiento de Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="d6ad8-109">No puede usar cuentas de almacenamiento de Azure Data Lake Gen1 para ingerir datos.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="d6ad8-110">Para autenticarse con una entidad de servicio de Azure, asegúrese de que esté configurada en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="d6ad8-111">Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="d6ad8-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="d6ad8-112">El Azure Data Lake desde el que desea conectar e ingerir datos debe estar en la misma región de Azure que el entorno Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="d6ad8-113">No se admiten las conexiones a una carpeta de Common Data Model desde un lago de datos en una región de Azure diferente.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="d6ad8-114">Para conocer la región de Azure del entorno, vaya a **Administrador** > **Sistema** > **Acerca de** en la información de público.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="d6ad8-115">Los datos almacenados en servicios en línea pueden almacenarse en una ubicación diferente a la que se procesan o almacenan en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="d6ad8-116"> Al importar o conectarse a datos almacenados en servicios en línea, acepta que los datos pueden transferirse y almacenarse con Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="d6ad8-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="d6ad8-117">Conectar a una carpeta de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="d6ad8-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="d6ad8-118">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d6ad8-119">Seleccione **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="d6ad8-120">Seleccione **Conectarse a una carpeta de Common Data Model**, introduzca un **Nombre** como origen de datos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="d6ad8-121">Directrices de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="d6ad8-121">Name guidelines:</span></span> 
   - <span data-ttu-id="d6ad8-122">Empiece con una letra.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-122">Start with a letter.</span></span>
   - <span data-ttu-id="d6ad8-123">Utilice solo letras y números.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-123">Use letters and numbers only.</span></span> <span data-ttu-id="d6ad8-124">No se permiten caracteres especiales ni espacios.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="d6ad8-125">Utilice entre 3 y 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="d6ad8-126">Puede elegir entre usar una opción basada en recursos y una opción basada en suscripción para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="d6ad8-127">Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="d6ad8-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="d6ad8-128">Introduzca la información del **Contenedor** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6ad8-129">![Cuadro de diálogo para ingresar nuevos detalles de conexión para Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="d6ad8-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="d6ad8-130">Necesita uno de los siguientes roles, ya sea para el contenedor o la cuenta de almacenamiento mencionada anteriormente, para poder conectarse y crear un origen de datos:</span><span class="sxs-lookup"><span data-stu-id="d6ad8-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="d6ad8-131">Lector de datos de blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d6ad8-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="d6ad8-132">Propietario de datos de blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d6ad8-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="d6ad8-133">Colaborador de datos de blob de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d6ad8-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="d6ad8-134">En el diálogo **Seleccionar una carpeta de Common Data Model**, seleccione el archivo model.json o manifest.json del que importar datos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d6ad8-135">Cualquier archivo model.json o manifest.json asociado con otro origen de datos del entorno no se mostrará en la lista.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="d6ad8-136">Obtendrá una lista de entidades disponibles en el archivo model.json o manifest.json seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="d6ad8-137">Puede revisar y seleccionar de la lista de entidades disponibles y seleccionar **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="d6ad8-138">Todas las entidades seleccionadas se ingerirán desde el nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6ad8-139">![Cuadro de diálogo que muestra una lista de entidades de un archivo model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="d6ad8-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="d6ad8-140">Indique en qué entidades de datos desea habilitar la generación de perfiles de datos y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="d6ad8-141">La generación de perfiles de datos habilita el análisis y otras capacidades.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="d6ad8-142">Puede seleccionar la entidad completa, que selecciona todos los atributos de la entidad, o seleccionar ciertos atributos de su elección.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="d6ad8-143">De forma predeterminada, ninguna entidad está habilitada para la creación de perfiles de datos.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6ad8-144">![Cuadro de diálogo que muestra un perfil de datos](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="d6ad8-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="d6ad8-145">Después de guardar sus selecciones, se abre la página **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="d6ad8-146">Ahora debería ver la conexión de la carpeta de Common Data Model como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="d6ad8-147">Un archivo model.json o manifest.json solo se puede asociar con un origen de datos en el mismo entorno.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="d6ad8-148">Sin embargo, el mismo archivo model.json o manifest.json se puede utilizar para orígenes de datos en varios entornos.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="d6ad8-149">Editar un origen de datos de carpeta de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="d6ad8-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="d6ad8-150">Puede actualizar la clave de acceso para la cuenta de almacenamiento que contiene la carpeta Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="d6ad8-151">También puede cambiar el archivo model.json o manifest.json.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="d6ad8-152">Para conectarse a un contenedor diferente de su cuenta de almacenamiento o cambiar el nombre de la cuenta, [cree una nueva conexión de origen de datos](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="d6ad8-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="d6ad8-153">En informaciones del público, vaya a **Datos** > **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d6ad8-154">Junto al origen de datos que desea actualizar, seleccione los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="d6ad8-155">Seleccione la opción **Editar** de la lista.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="d6ad8-156">Opcionalmente, actualice la **Clave de acceso** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Diálogo para editar y actualizar una clave de acceso para un origen de datos existente](media/edit-access-key.png)

5. <span data-ttu-id="d6ad8-158">Opcionalmente, puede actualizar desde una conexión de clave de cuenta a una conexión basada en recursos o basada en suscripción.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="d6ad8-159">Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="d6ad8-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="d6ad8-160">No puede cambiar la información de **Contenido** al actualizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Cuadro de diálogo para especificar los detalles de la conexión de Azure Data Lake a una cuenta de almacenamiento existente](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="d6ad8-162">Necesita uno de los siguientes roles, ya sea para el contenedor o la cuenta de almacenamiento mencionada anteriormente, para poder conectarse y crear un origen de datos:</span><span class="sxs-lookup"><span data-stu-id="d6ad8-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="d6ad8-163">Lector de datos de blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d6ad8-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="d6ad8-164">Propietario de datos de blobs de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d6ad8-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="d6ad8-165">Colaborador de datos de blob de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d6ad8-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="d6ad8-166">Opcionalmente, elija un archivo model.json o manifest.json diferente con un conjunto diferente de entidades en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="d6ad8-167">Opcionalmente, puede seleccionar entidades adicionales para ingerir.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="d6ad8-168">También puede quitar cualquier entidad ya seleccionada si no hay dependencias.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d6ad8-169">Si hay dependencias en el archivo model.json o manifest.json existente y el conjunto de entidades, verá un mensaje de error y no podrá seleccionar un archivo model.json o manifest.json diferente.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="d6ad8-170">Elimine esas dependencias antes de cambiar el archivo model.json o manifest.json o cree un nuevo origen de datos con el archivo model.json o manifest.json que desea utilizar para evitar eliminar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="d6ad8-171">Opcionalmente, puede seleccionar atributos o entidades adicionales para habilitar la creación de perfiles de datos o deshabilitar los ya seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d6ad8-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]