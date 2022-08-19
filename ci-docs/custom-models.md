---
title: Modelos personalizados de aprendizaje automático | Microsoft Docs
description: Trabaje con modelos personalizados de Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 3fad8a6cba71da80d4cc34be4084275e0d0a3622
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245824"
---
# <a name="custom-machine-learning-models"></a>Modelos personalizados de aprendizaje automático

> [!NOTE]
> El soporte para Machine Learning Studio (clásico) finalizará el 31 de agosto de 2024. Le recomendamos que haga la transición a [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) para esa fecha.
>
> A partir del 1 de diciembre de 2021, no podrá crear nuevos recursos de Machine Learning Studio (clásico). Hasta el 31 de agosto de 2024, puede seguir utilizando los recursos Machine Learning Studio (clásico) existentes. Para obtener más información, consulte [Migrar a Azure Machine Learning](/azure/machine-learning/migrate-overview).


**Inteligencia** > **Modelos personalizados** le permite administrar flujos de trabajo basados en los modelos de Azure Machine Learning. Los flujos de trabajo le ayudan a elegir los datos a partir de los cuales desea generar información y asignar los resultados a los datos unificados de sus clientes. Para obtener más información sobre cómo crear modelos de ML personalizados, consulte [Usar modelos basados en Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsable

Las predicciones ofrecen capacidades para crear mejores experiencias para los clientes, mejorar las capacidades comerciales y las secuencias de ingresos. Le recomendamos encarecidamente que equilibre el valor de su predicción con el impacto que tiene y los sesgos que pueden introducirse de manera ética. Obtenga más información sobre cómo Microsoft [aborda la IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). También puede aprender sobre [técnicas y procesos de aprendizaje automático responsable](/azure/machine-learning/concept-responsible-ml) específicos de Azure Machine Learning.

## <a name="prerequisites"></a>Requisitos previos

- Esta función admite servicios web publicados a través de [Canalizaciones por lotes de Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Necesita una cuenta de almacenamiento de Azure Data Lake Gen2 asociada con su instancia de Azure Studio para usar esta característica. Para más información, consulte [Crear una cuenta de almacenamiento de segunda generación de Azure Data Lake Storage](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Para las áreas de trabajo de Azure Machine Learning con canalizaciones, necesita permisos de acceso de administrador de propietario o usuario al área de trabajo de Azure Machine Learning.

   > [!NOTE]
   > Los datos se transfieren entre sus instancias de Customer Insights y los servicios web o canalizaciones de Azure seleccionados en el flujo de trabajo. Al transferir datos a un servicio de Azure, asegúrese de que el servicio esté configurado para procesar los datos de la manera necesaria y en la ubicación necesaria a fin de su organización cumpla con los requisitos legales o normativos para esos datos.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Agregar un flujo de trabajo nuevo

1. Vaya a **Inteligencia** > **Modelos personalizados** y seleccione **Nuevo flujo de trabajo**.

1. Asigne el modelo personalizado a un nombre reconocible en el campo **Nombre**.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del panel Nuevo flujo de trabajo.](media/new-workflowv2.png "Captura de pantalla del Nuevo panel de flujo de trabajo")

1. Seleccione la organización que contiene el servicio web en **Inquilino que contiene su servicio web**.

1. Si su suscripción a Azure Machine Learning se encuentra en un inquilino diferente de Customer Insights, seleccione **iniciar sesión** con sus credenciales para la organización seleccionada.

1. Selecciona las **Áreas de trabajo** asociadas con su servicio web. 

1. Elija la canalización de Azure Aprendizaje automático en el desplegable **Servicio web que contiene tu modelo**. A continuación, seleccione **Siguiente**.    
   Aprender más acerca de [publicar una canalización en Azure Machine Learning usando el diseñador](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o el [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Su canalización debe publicarse en un [punto de conexión de canalización](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Para cada **Entrada de servicio web**, seleccione la coincidencia de **Entidad** de Customer Insights y seleccione **Siguiente**.
   > [!NOTE]
   > El flujo de trabajo del modelo personalizado aplicará heurística para asignar los campos de entrada del servicio web a los atributos de la entidad según el nombre y el tipo de datos del campo. Verá un error si un campo de servicio web no se puede asignar a una entidad.

   > [!div class="mx-imgBorder"]
   > ![Configurar un flujo de trabajo.](media/intelligence-screen2-updated.png "Configurar un flujo de trabajo")

1. En el paso **Parámetros de salida del modelo**, establezca las siguientes propiedades:
      1. Introduzca la salida **Nombre de la entidad** a la que desea que fluyan los resultados de salida de la canalización.
      1. Seleccione el **Nombre del parámetro del almacén de datos de salida** de su canalización por lotes desde el menú desplegable.
      1. Seleccione el **Nombre del parámetro de la ruta de salida** de su canalización por lotes desde el menú desplegable.

      > [!div class="mx-imgBorder"]
      > ![Panel de parámetros de salida del modelo.](media/intelligence-screen3-outputparameters.png "Panel de parámetros de salida del modelo")

1. Seleccione el atributo correspondiente de la lista desplegable **Id. de cliente en los resultados** que identifica clientes y seleccione **Guardar**.

   > [!div class="mx-imgBorder"]
   > ![Relacionar los resultados con el panel Datos de clientes.](media/intelligence-screen4-relatetocustomer.png "Relacionar los resultados con el panel de datos de clientes")

1. Verá la pantalla **Flujo de trabajo guardado** con detalles sobre el flujo de trabajo.    
   Si configuró un flujo de trabajo para una canalización Aprendizaje automático de Azure, Customer Insights se adjunta al área de trabajo que contiene la canalización. Customer Insights obtendrá un rol **Colaborador** en el área de trabajo de Azure.

1. Seleccione **Listo**.

1. Ahora puede ejecutar el flujo de trabajo desde la página **Modelos personalizados**.

## <a name="edit-a-workflow"></a>Editar un flujo de trabajo

1. En la página **Modelos personalizados**, seleccione los puntos suspensivos verticales (&vellip;) en la columna **Acciones**, junto a un flujo de trabajo que creó previamente, y seleccione **Editar**.

1. Puede actualizar el nombre reconocible de su flujo de trabajo en el campo **Nombre para mostrar**, pero no puede cambiar el servicio web o la canalización configurados. Seleccione **Siguiente**.

1. Para cada **Entrada de servicio web**, puede actualizar la coincidencia de **Entidad** de Customer Insights. A continuación, seleccione **Siguiente**.

1. En el paso **Parámetros de salida del modelo**, establezca las siguientes propiedades:
      1. Introduzca la salida **Nombre de la entidad** a la que desea que fluyan los resultados de salida de la canalización.
      1. Seleccione el **Nombre del parámetro del almacén de datos de salida** para su canalización de prueba.
      1. Seleccione el **Nombre del parámetro de la ruta de salida** para su canalización de prueba.

1. Seleccione el atributo correspondiente de la lista desplegable **Id. de cliente en los resultados** que identifica clientes y seleccione **Guardar**.
   Elija un atributo de la salida de inferencia con valores similares a la columna de identificador de cliente de la entidad Cliente. Si no tiene esa columna en su conjunto de datos, elija un atributo que identifique de forma exclusiva la fila.

## <a name="run-a-workflow"></a>Ejecutar un flujo de trabajo

1. En la página **Modelos personalizados**, seleccione los puntos suspensivos verticales (&vellip;) en la columna **Acciones**, junto a un flujo de trabajo que creó previamente.

1. Seleccione **Ejecutar**.

Su flujo de trabajo también se ejecuta automáticamente con cada actualización programada. Más información acerca de [configurar actualizaciones programadas](schedule-refresh.md).

## <a name="delete-a-workflow"></a>Eliminar un flujo de trabajo

1. En la página **Modelos personalizados**, seleccione los puntos suspensivos verticales (&vellip;) en la columna **Acciones**, junto a un flujo de trabajo que creó previamente.

1. Seleccione **Eliminar** y confirme la eliminación.

Su flujo de trabajo será eliminado. La [entidad](entities.md) que se creó cuando creó el flujo de trabajo persiste y se puede ver desde la página **Entidades**.

## <a name="results"></a>Resultados

Los resultados de un flujo de trabajo se almacenan en la entidad configurada durante la fase de parámetro de salida del modelo. Puede acceder a estos datos desde la [página de entidades](entities.md) o con [acceso a la API](apis.md).

### <a name="api-access"></a>Acceso API

Para que la consulta de OData específica obtenga datos de una entidad de modelo personalizada, use el siguiente formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Sustituya `<your instance id>` con el identificador de su entorno de Customer Insights, que encontrará en la barra de direcciones de su navegador cuando acceda a Customer Insights.

1. Reemplace `<custom model output entity>` con el nombre de entidad que proporcionó durante el paso Parámetros de salida del modelo de la configuración del modelo personalizado.

1. Reemplace `<guid value>` con el identificador de cliente del cliente para el que desea acceder al registro. Por lo general, puede encontrar esta identificación en la [página de perfiles de clientes](customer-profiles.md) en el campo CustomerID.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

- ¿Por qué no puedo ver mi canalización al configurar un flujo de trabajo de modelo personalizado?    
  Este problema suele deberse a un problema de configuración en la canalización. Asegúrese de que [el parámetro de entrada está configurado](azure-machine-learning-experiments.md#dataset-configuration), y el [parámetros de ruta y almacén de datos de salida](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) también están configurados.

- ¿Qué significa el error "No se pudo guardar el flujo de trabajo de inteligencia"?    
  Los usuarios suelen ver este mensaje de error si no tienen privilegios de propietario o acceso de usuario Administrador en el espacio de trabajo. El usuario necesita un nivel más alto de permisos para permitir que Customer Insights procese el flujo de trabajo como un servicio en lugar de usar las credenciales del usuario para ejecuciones posteriores del flujo de trabajo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
