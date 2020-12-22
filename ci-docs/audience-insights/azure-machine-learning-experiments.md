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
# <a name="use-azure-machine-learning-based-models"></a>Usar modelos basados en Azure Machine Learning

Los datos unificados en Dynamics 365 Customer Insights son un origen para crear modelos de aprendizaje automático que pueden generar información empresarial adicional. Customer Insights se integra con Machine Learning Studio (clásico) y Azure Machine Learning para usar sus propios modelos personalizados. Consulte los [experimentos de Machine Learning Studio (clásico)](machine-learning-studio-experiments.md) para ver ejemplos de experimentos basados en Machine Learning Studio (clásico). 

## <a name="prerequisites"></a>Requisitos previos

- Acceso a Customer Insights
- Una suscripción de Azure Enterprise activa
- [Perfiles de cliente unificados](data-unification.md)
- [Exportación de entidades a Azure Blob Storage](export-azure-blob-storage.md) configurado

## <a name="set-up-azure-machine-learning-workspace"></a>Configurar el área de trabajo de Azure Machine Learning

1. Consulte [Crear un espacio de trabajo de Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) para ver diferentes opciones para crear el área de trabajo. Para obtener el mejor rendimiento, cree el espacio de trabajo en una región de Azure que esté geográficamente más cerca de su entorno de Customer Insights.

1. Acceda a su espacio de trabajo a través de [Azure Machine Learning Studio](https://ml.azure.com/). Hay varias [formas de interactuar](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) con su espacio de trabajo.

## <a name="work-with-azure-machine-learning-designer"></a>Trabajar con el diseñador de Azure Machine Learning

El diseñador de Azure Machine Learning proporciona un lienzo visual donde puede arrastrar y soltar conjuntos de datos y módulos, similar a Machine Learning Studio (clásico). Una canalización por lotes creada a partir del diseñador se puede integrar en Customer Insights si se configura en consecuencia. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Trabajo con el SDK de Azure Machine Learning

Los científicos de datos y los desarrolladores de IA utilizan el [SDK de Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) para crear flujos de trabajo de aprendizaje automático. Actualmente, los modelos entrenados con el SDK no se pueden integrar directamente en Customer Insights. Se requiere una canalización de inferencia por lotes que use ese modelo para la integración con Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Requisitos de la canalización por lotes para integración con Customer Insights

### <a name="dataset-configuration"></a>Configuración del conjunto de datos

Necesita crear conjuntos de datos para usar datos de entidad de Customer Insights en su canalización de inferencia por lotes. Estos conjuntos de datos deben registrarse en el espacio de trabajo. Actualmente, solo se admiten [conjuntos de datos tabulares](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) en formato .csv. Los conjuntos de datos que corresponden a los datos de la entidad deben parametrizarse como un parámetro de canalización.
   
* Parámetros de conjunto de datos en Designer
   
     En el diseñador, abra **Seleccionar columnas en conjunto de datos** y seleccione **Establecer como parámetro de canalización**, donde proporciona un nombre para el parámetro.

     > [!div class="mx-imgBorder"]
     > ![Parámetrización de conjunto de datos en el diseñador](media/intelligence-designer-dataset-parameters.png "Parámetrización de conjunto de datos en el diseñador")
   
* Parámetro de conjunto de datos en SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Canalización de inferencia por lotes
  
* En el diseñador, puede usarse una canalización de aprendizaje para crear o actualizar una canalización de inferencia. Actualmente, solo se admiten canalizaciones de inferencia por lotes.

* Con el SDK, puede publicar la canalización en un punto de conexión. Actualmente, Customer Insights se integra con la canalización predeterminada en un punto de conexión de canalización por lotes en el espacio de trabajo de Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importar datos de canalización a Customer Insights

* El diseñador proporciona el [Módulo de exportación de datos](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) que permite exportar la salida de una canalización al almacenamiento de Azure. Actualmente, el módulo debe usar el tipo de almacén de datos **Almacenamiento de blobs de Azure** y parametrizar el **Almacén de datos** y la **Ruta** relativa. Customer Insights anula ambos parámetros durante la ejecución de la canalización con un almacén de datos y una ruta a la que puede acceder el producto.
   > [!div class="mx-imgBorder"]
   > ![Exportar configuración de módulo de datos](media/intelligence-designer-importdata.png "Exportar configuración de módulo de datos")
   
* Al escribir la salida de la inferencia utilizando código, puede cargar la salida en una ruta dentro de un *almacén de datos registrado* del área de trabajo. Si la ruta y el almacén de datos están parametrizados en la canalización, Customer Insights podrá leer e importar la salida de la inferencia. Actualmente, se admite una única salida tabular en formato csv. La ruta debe incluir el directorio y el nombre del archivo.

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
