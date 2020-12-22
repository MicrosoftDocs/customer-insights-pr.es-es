---
title: Experimentos de Azure Machine Learning
description: Use modelos basados en Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668797"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="4f9c7-103">Usar modelos basados en Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4f9c7-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="4f9c7-104">Los datos unificados en Dynamics 365 Customer Insights son un origen para crear modelos de aprendizaje automático que pueden generar información empresarial adicional.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="4f9c7-105">Customer Insights se integra con Machine Learning Studio (clásico) y Azure Machine Learning para usar sus propios modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="4f9c7-106">Consulte los [experimentos de Machine Learning Studio (clásico)](machine-learning-studio-experiments.md) para ver ejemplos de experimentos basados en Machine Learning Studio (clásico).</span><span class="sxs-lookup"><span data-stu-id="4f9c7-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="4f9c7-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4f9c7-107">Prerequisites</span></span>

- <span data-ttu-id="4f9c7-108">Acceso a Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f9c7-108">Access to Customer Insights</span></span>
- <span data-ttu-id="4f9c7-109">Una suscripción de Azure Enterprise activa</span><span class="sxs-lookup"><span data-stu-id="4f9c7-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="4f9c7-110">Perfiles de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="4f9c7-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="4f9c7-111">[Exportación de entidades a Azure Blob Storage](export-azure-blob-storage.md) configurado</span><span class="sxs-lookup"><span data-stu-id="4f9c7-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="4f9c7-112">Configurar el área de trabajo de Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4f9c7-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="4f9c7-113">Consulte [Crear un espacio de trabajo de Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) para ver diferentes opciones para crear el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="4f9c7-114">Para obtener el mejor rendimiento, cree el espacio de trabajo en una región de Azure que esté geográficamente más cerca de su entorno de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="4f9c7-115">Acceda a su espacio de trabajo a través de [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="4f9c7-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="4f9c7-116">Hay varias [formas de interactuar](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) con su espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="4f9c7-117">Trabajar con el diseñador de Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4f9c7-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="4f9c7-118">El diseñador de Azure Machine Learning proporciona un lienzo visual donde puede arrastrar y soltar conjuntos de datos y módulos, similar a Machine Learning Studio (clásico).</span><span class="sxs-lookup"><span data-stu-id="4f9c7-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="4f9c7-119">Una canalización por lotes creada a partir del diseñador se puede integrar en Customer Insights si se configura en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="4f9c7-120">Trabajo con el SDK de Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="4f9c7-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="4f9c7-121">Los científicos de datos y los desarrolladores de IA utilizan el [SDK de Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) para crear flujos de trabajo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="4f9c7-122">Actualmente, los modelos entrenados con el SDK no se pueden integrar directamente en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="4f9c7-123">Se requiere una canalización de inferencia por lotes que use ese modelo para la integración con Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="4f9c7-124">Requisitos de la canalización por lotes para integración con Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f9c7-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="4f9c7-125">Configuración del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="4f9c7-125">Dataset Configuration</span></span>

<span data-ttu-id="4f9c7-126">Necesita crear conjuntos de datos para usar datos de entidad de Customer Insights en su canalización de inferencia por lotes.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="4f9c7-127">Estos conjuntos de datos deben registrarse en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="4f9c7-128">Actualmente, solo se admiten [conjuntos de datos tabulares](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="4f9c7-129">Los conjuntos de datos que corresponden a los datos de la entidad deben parametrizarse como un parámetro de canalización.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="4f9c7-130">Parámetros de conjunto de datos en Designer</span><span class="sxs-lookup"><span data-stu-id="4f9c7-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="4f9c7-131">En el diseñador, abra **Seleccionar columnas en conjunto de datos** y seleccione **Establecer como parámetro de canalización**, donde proporciona un nombre para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="4f9c7-132">![Parámetrización de conjunto de datos en el diseñador](media/intelligence-designer-dataset-parameters.png "Parámetrización de conjunto de datos en el diseñador")</span><span class="sxs-lookup"><span data-stu-id="4f9c7-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="4f9c7-133">Parámetro de conjunto de datos en SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="4f9c7-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="4f9c7-134">Canalización de inferencia por lotes</span><span class="sxs-lookup"><span data-stu-id="4f9c7-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="4f9c7-135">En el diseñador, puede usarse una canalización de aprendizaje para crear o actualizar una canalización de inferencia.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="4f9c7-136">Actualmente, solo se admiten canalizaciones de inferencia por lotes.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="4f9c7-137">Con el SDK, puede publicar la canalización en un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="4f9c7-138">Actualmente, Customer Insights se integra con la canalización predeterminada en un punto de conexión de canalización por lotes en el espacio de trabajo de Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="4f9c7-139">Importar datos de canalización a Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f9c7-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="4f9c7-140">El diseñador proporciona el [Módulo de exportación de datos](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) que permite exportar la salida de una canalización al almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="4f9c7-141">Actualmente, el módulo debe usar el tipo de almacén de datos **Almacenamiento de blobs de Azure** y parametrizar el **Almacén de datos** y la **Ruta** relativa.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="4f9c7-142">Customer Insights anula ambos parámetros durante la ejecución de la canalización con un almacén de datos y una ruta a la que puede acceder el producto.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4f9c7-143">![Exportar configuración de módulo de datos](media/intelligence-designer-importdata.png "Exportar configuración de módulo de datos")</span><span class="sxs-lookup"><span data-stu-id="4f9c7-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="4f9c7-144">Al escribir la salida de la inferencia utilizando código, puede cargar la salida en una ruta dentro de un *almacén de datos registrado* del área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="4f9c7-145">Si la ruta y el almacén de datos están parametrizados en la canalización, Customer Insights podrá leer e importar la salida de la inferencia.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="4f9c7-146">Actualmente, se admite una única salida tabular en formato csv.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="4f9c7-147">La ruta debe incluir el directorio y el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="4f9c7-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
