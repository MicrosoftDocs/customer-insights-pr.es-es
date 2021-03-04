---
title: Crear y administrar entornos
description: Obtenga información sobre cómo registrarse en el servicio y cómo administrar los entornos.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270133"
---
# <a name="manage-environments"></a><span data-ttu-id="9a38a-103">Administrar entornos</span><span class="sxs-lookup"><span data-stu-id="9a38a-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9a38a-104">Este artículo explica cómo crear una nueva organización y cómo aprovisionar un entorno.</span><span class="sxs-lookup"><span data-stu-id="9a38a-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="9a38a-105">Registrarse y crear una organización</span><span class="sxs-lookup"><span data-stu-id="9a38a-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="9a38a-106">Vaya al sitio web de [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="9a38a-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="9a38a-107">Seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="9a38a-108">Elija su escenario de registro preferido y seleccione el vínculo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9a38a-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="9a38a-109">Acepte los términos y condiciones y seleccione **Continuar** para empezar a crear la organización.</span><span class="sxs-lookup"><span data-stu-id="9a38a-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="9a38a-110">Una vez creado el entorno, se le redirigirá a [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="9a38a-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="9a38a-111">Use el entorno de demostración para explorar la aplicación o cree un nuevo entorno siguiendo los pasos de la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="9a38a-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="9a38a-112">Después de especificar la configuración del entorno, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="9a38a-113">Iniciará sesión después de que el entorno se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a38a-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="9a38a-114">Crear un entorno en una organización existente</span><span class="sxs-lookup"><span data-stu-id="9a38a-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="9a38a-115">Hay dos formas de crear un entorno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9a38a-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="9a38a-116">Puede especificar una configuración completamente nueva o copiar algunos valores de configuración de un entorno existente.</span><span class="sxs-lookup"><span data-stu-id="9a38a-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="9a38a-117">Para crear un entorno:</span><span class="sxs-lookup"><span data-stu-id="9a38a-117">To create an environment:</span></span>

1. <span data-ttu-id="9a38a-118">Seleccione el selector **Entorno** en el encabezado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9a38a-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="9a38a-119">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a38a-120">![Configuración del entorno](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="9a38a-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="9a38a-121">En el diálogo **Crear un nuevo entorno**, seleccione **Nuevo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="9a38a-122">Si quiere [copiar datos del entorno actual](#additional-considerations-for-copy-configuration-preview), seleccione **Copiar desde entorno existente**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="9a38a-123">Verá una lista de todos los entornos disponibles de su organización desde los que puede copiar datos.</span><span class="sxs-lookup"><span data-stu-id="9a38a-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="9a38a-124">Especifique los detalles siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a38a-124">Provide the following details:</span></span>
   - <span data-ttu-id="9a38a-125">**Nombre**: el nombre para este entorno.</span><span class="sxs-lookup"><span data-stu-id="9a38a-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="9a38a-126">Este campo ya se ha cumplimentado si ha copiado un entorno existente, pero puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="9a38a-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="9a38a-127">**Región**: la región en la que se implementa y hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="9a38a-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="9a38a-128">**Tipo**: Seleccione si desea crear un entorno de producción o de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="9a38a-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="9a38a-129">De manera opcional, puede seleccionar **Configuración avanzada**:</span><span class="sxs-lookup"><span data-stu-id="9a38a-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="9a38a-130">**Guardar todos los datos en**: Especifica dónde desea almacenar los datos de salida generados a partir de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a38a-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="9a38a-131">Tendrá dos opciones: **Almacenamiento de Customer Insights** (un Azure Data Lake administrado por el equipo de Customer Insights) y **Azure Data Lake Storage Gen2** (su propio Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="9a38a-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="9a38a-132">De forma predeterminada, la opción de almacenamiento de Customer Insights está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9a38a-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9a38a-133">Al guardar datos en Azure Data Lake Storage, acepta que los datos se transferirán a la ubicación geográfica adecuada y se almacenarán en ella para esa cuenta de almacenamiento de Azure, que puede ser distinta del lugar en el que se almacenan los datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a38a-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="9a38a-134">Obtenga más información en el Centro de confianza de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a38a-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="9a38a-135">Actualmente, las entidades ingeridas siempre se almacenan en el lago de datos administrados de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a38a-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="9a38a-136">Solo admitimos cuentas de almacenamiento de Azure Data Lake Gen2 de la misma región de Azure que seleccionó al crear el entorno.</span><span class="sxs-lookup"><span data-stu-id="9a38a-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="9a38a-137">Solo admitimos cuentas de almacenamiento habilitadas para cuentas de Espacio de nombres jerárquicos (HNS) de Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="9a38a-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="9a38a-138">Para la opción de Azure Data Lake Storage Gen2, puede elegir entre usar una opción basada en recursos y una opción basada en suscripción para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9a38a-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="9a38a-139">Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9a38a-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="9a38a-140">El nombre del **Contenedor** no se puede cambiar y será "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="9a38a-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="9a38a-141">Si quiere usar [predicciones](predictions.md) o configurar el intercambio de datos con aplicaciones y soluciones basadas en Microsoft Dataverse, proporcione la URL del entorno Microsoft Dataverse en **Configurar el uso compartido de datos con Microsoft Dataverse y habilitar funcionalidades adicionales**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="9a38a-142">Seleccione **Habilitar el uso compartido de datos** para compartir los datos de salida de Customer Insights con una instancia de Data Lake gestionada de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9a38a-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="9a38a-143">El uso compartido de datos con una instancia de Data Lake gestionada de Microsoft Dataverse no se admite en estos momentos cuando almacene todos los datos en su propia instancia de Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="9a38a-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="9a38a-144">La [predicción de valores perdidos en una entidad](predictions.md) actualmente no se admite cuando habilita el uso compartido de datos con una instancia de Data Lake gestionada de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9a38a-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="9a38a-145">![Opciones de configuración para permitir el uso compartido de datos con Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="9a38a-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="9a38a-146">Cuando ejecuta procesos, como la ingestión de datos o la creación de segmentos, las carpetas correspondientes se crearán en la cuenta de almacenamiento que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9a38a-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="9a38a-147">Se crearán archivos de datos y archivos model.json, y se agregarán a las subcarpetas correspondientes según el proceso que se ejecute.</span><span class="sxs-lookup"><span data-stu-id="9a38a-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="9a38a-148">Si crea varios entornos de Customer Insights y elige guardar las entidades de salida de esos entornos en su cuenta de almacenamiento, se crearán carpetas separadas para cada entorno, con ci_<environmentid> en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="9a38a-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="9a38a-149">Consideraciones adicionales para la configuración de copia (vista previa)</span><span class="sxs-lookup"><span data-stu-id="9a38a-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="9a38a-150">Se copian los siguientes valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="9a38a-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="9a38a-151">Configuración de características</span><span class="sxs-lookup"><span data-stu-id="9a38a-151">Feature configurations</span></span>
- <span data-ttu-id="9a38a-152">Fuentes de datos ingeridas e importadas</span><span class="sxs-lookup"><span data-stu-id="9a38a-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="9a38a-153">Configuración de unificación de datos (asignación, coincidencia, combinación)</span><span class="sxs-lookup"><span data-stu-id="9a38a-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="9a38a-154">Segmentos</span><span class="sxs-lookup"><span data-stu-id="9a38a-154">Segments</span></span>
- <span data-ttu-id="9a38a-155">Medidas</span><span class="sxs-lookup"><span data-stu-id="9a38a-155">Measures</span></span>
- <span data-ttu-id="9a38a-156">Relaciones</span><span class="sxs-lookup"><span data-stu-id="9a38a-156">Relationships</span></span>
- <span data-ttu-id="9a38a-157">Actividades</span><span class="sxs-lookup"><span data-stu-id="9a38a-157">Activities</span></span>
- <span data-ttu-id="9a38a-158">Índice de Buscar y filtrar</span><span class="sxs-lookup"><span data-stu-id="9a38a-158">Search & filter Index</span></span>
- <span data-ttu-id="9a38a-159">Exportar destinos</span><span class="sxs-lookup"><span data-stu-id="9a38a-159">Export destinations</span></span>
- <span data-ttu-id="9a38a-160">Actualización programada</span><span class="sxs-lookup"><span data-stu-id="9a38a-160">Scheduled refresh</span></span>
- <span data-ttu-id="9a38a-161">Enriquecimientos</span><span class="sxs-lookup"><span data-stu-id="9a38a-161">Enrichments</span></span>
- <span data-ttu-id="9a38a-162">Administración de modelos</span><span class="sxs-lookup"><span data-stu-id="9a38a-162">Model management</span></span>
- <span data-ttu-id="9a38a-163">Asignaciones de roles</span><span class="sxs-lookup"><span data-stu-id="9a38a-163">Role assignments</span></span>

<span data-ttu-id="9a38a-164">Los siguientes valores de configuración *no* se copian:</span><span class="sxs-lookup"><span data-stu-id="9a38a-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="9a38a-165">Perfiles de clientes.</span><span class="sxs-lookup"><span data-stu-id="9a38a-165">Customer profiles.</span></span>
- <span data-ttu-id="9a38a-166">Credenciales del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9a38a-166">Data source credentials.</span></span> <span data-ttu-id="9a38a-167">Debe especificar las credenciales para cada origen de datos y actualizar los orígenes de datos manualmente.</span><span class="sxs-lookup"><span data-stu-id="9a38a-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="9a38a-168">Orígenes de datos de la carpeta de Common Data Model y del lago gestionado por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9a38a-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="9a38a-169">Tendrá que crear esos orígenes de datos manualmente con el mismo nombre que en el entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="9a38a-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="9a38a-170">Al copiar un entorno, verá un mensaje de confirmación de que se ha creado el nuevo entorno.</span><span class="sxs-lookup"><span data-stu-id="9a38a-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="9a38a-171">Seleccione **Ir a orígenes de datos** para ver la lista de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="9a38a-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="9a38a-172">Todos los orígenes de datos mostrarán un estado de **Credenciales necesarias**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="9a38a-173">Edite los orígenes de datos e introduzca las credenciales para actualizarlas.</span><span class="sxs-lookup"><span data-stu-id="9a38a-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9a38a-174">![Orígenes de datos copiados](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="9a38a-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="9a38a-175">Después de actualizar los orígenes de datos, vaya a **Datos** > **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="9a38a-176">Aquí encontrará configuraciones del entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="9a38a-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="9a38a-177">Edítelos si es necesario o seleccione **Ejecutar** para iniciar el proceso de unificación de datos y crear la entidad de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="9a38a-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="9a38a-178">Cuando se haya completado la unificación de datos, vaya a **Medidas** y **Segmentos** para actualizarlos también.</span><span class="sxs-lookup"><span data-stu-id="9a38a-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="9a38a-179">Editar un entorno existente</span><span class="sxs-lookup"><span data-stu-id="9a38a-179">Edit an existing environment</span></span>

<span data-ttu-id="9a38a-180">Puede editar algunos de los detalles de los entornos existentes.</span><span class="sxs-lookup"><span data-stu-id="9a38a-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="9a38a-181">Seleccione el selector **Entorno** en el encabezado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9a38a-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="9a38a-182">Seleccione el icono de **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="9a38a-183">En el cuadro **Editar entorno**, puede actualizar la opción **Nombre para mostrar** del entorno, pero no puede cambiar **Región** o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="9a38a-184">Si un entorno está configurado para almacenar datos en Azure Data Lake Storage Gen2, puede actualizar la **Clave de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="9a38a-185">Sin embargo, no puede cambiar el **Nombre de cuenta** o el nombre de **Contenedor**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="9a38a-186">Opcionalmente, puede actualizar desde una conexión basada en clave de cuenta a una conexión basada en recursos o basada en suscripción.</span><span class="sxs-lookup"><span data-stu-id="9a38a-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="9a38a-187">Una vez actualizado, no puede volver a la clave de cuenta después de la actualización.</span><span class="sxs-lookup"><span data-stu-id="9a38a-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="9a38a-188">Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9a38a-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="9a38a-189">No puede cambiar la información de **Contenido** al actualizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="9a38a-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="9a38a-190">Restablecimiento de un entorno existente</span><span class="sxs-lookup"><span data-stu-id="9a38a-190">Reset an existing environment</span></span>

<span data-ttu-id="9a38a-191">Como administrador, puede restablecer un entorno a un estado vacío si desea eliminar todas las configuraciones y eliminar los datos ingeridos.</span><span class="sxs-lookup"><span data-stu-id="9a38a-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="9a38a-192">Seleccione el selector **Entorno** en el encabezado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9a38a-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="9a38a-193">Seleccione el entorno que desee restablecer y seleccione los puntos suspensivos **...**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="9a38a-194">Elija la opción **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="9a38a-195">Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="9a38a-196">Eliminar un entorno existente (disponible solo para administradores)</span><span class="sxs-lookup"><span data-stu-id="9a38a-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="9a38a-197">Como administrador, puede eliminar un entorno que administre.</span><span class="sxs-lookup"><span data-stu-id="9a38a-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="9a38a-198">Seleccione el selector **Entorno** en el encabezado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9a38a-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="9a38a-199">Seleccione el entorno que desee restablecer y seleccione los puntos suspensivos **...**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="9a38a-200">Elija la opción **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="9a38a-201">Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9a38a-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]