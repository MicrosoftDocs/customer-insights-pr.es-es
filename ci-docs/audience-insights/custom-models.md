---
title: Modelos personalizados de aprendizaje automático | Microsoft Docs
description: Trabaje con modelos personalizados de Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668924"
---
# <a name="custom-machine-learning-models"></a>Modelos personalizados de aprendizaje automático

**Inteligencia** > **Modelos personalizados** le permite administrar flujos de trabajo basados en los modelos de Azure Machine Learning. Los flujos de trabajo le ayudan a elegir los datos a partir de los cuales desea generar información y asignar los resultados a los datos unificados de sus clientes. Para obtener más información sobre cómo crear modelos de ML personalizados, consulte [Usar modelos basados en Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsable

Las predicciones ofrecen capacidades para crear mejores experiencias para los clientes, mejorar las capacidades comerciales y las secuencias de ingresos. Le recomendamos encarecidamente que equilibre el valor de su predicción con el impacto que tiene y los sesgos que pueden introducirse de manera ética. Obtenga más información sobre cómo Microsoft [aborda la IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). También puede aprender sobre [técnicas y procesos de aprendizaje automático responsable](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) específicos de Azure Machine Learning.

## <a name="prerequisites"></a>Requisitos previos

- Actualmente, esta característica admite servicios web publicados a través de [Machine Learning Studio (clásico)](https://studio.azureml.net) y [Canalizaciones por lotes de Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Necesita una cuenta de almacenamiento de Azure Data Lake Gen2 asociada con su instancia de Azure Studio para usar esta característica. Para más información, consulte [Crear una cuenta de almacenamiento de segunda generación de Azure Data Lake Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Agregar un flujo de trabajo nuevo

1. Vaya a **Inteligencia** > **Modelos personalizados** y seleccione **Nuevo flujo de trabajo**.

1. Asigne el modelo personalizado a un nombre reconocible en el campo **Nombre**.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del Nuevo panel de flujo de trabajo](media/new-workflowv2.png "Captura de pantalla del Nuevo panel de flujo de trabajo")

1. Seleccione la organización que contiene el servicio web en **Inquilino que contiene su servicio web**.

1. Si su suscripción a Azure Machine Learning se encuentra en un inquilino diferente de Customer Insights, seleccione **iniciar sesión** con sus credenciales para la organización seleccionada.

1. Selecciona las **Áreas de trabajo** asociadas con su servicio web. Se enumeran dos secciones, una para Azure Machine Learning v1 (Machine Learning Studio (clásico)) y Azure Machine Learning v2 (Azure Machine Learning). Si no está seguro de cuál es el espacio de trabajo adecuada para su servicio web Machine Learning Studio (clásico), seleccione **Cualquiera**.

1. Elija el servicio web Machine Learning Studio (clásico) o la canalización de Azure Machine Learning en el desplegable del **Servicio web que contiene su modelo**. A continuación, seleccione **Siguiente**.
   - Aprender más acerca de [publicar un servicio web en Machine Learning Studio (clásico)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Aprender más acerca de [publicar una canalización en Azure Machine Learning usando el diseñador](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o el [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Su canalización debe publicarse en un [punto de conexión de canalización](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Para cada **Entrada de servicio web**, seleccione **Entidad** correspondiente de información de público y seleccione **Siguiente**.

   > [!div class="mx-imgBorder"]
   > ![Configurar un flujo de trabajo](media/intelligence-screen2-updated.png "Configurar un flujo de trabajo")

1. En el paso **Parámetros de salida del modelo**, establezca las siguientes propiedades:
   - Machine Learning Studio (clásico)
      1. Introduzca la salida **Nombre de la entidad** a la que desea que fluyan los resultados de salida del servicio web.
   - Aprendizaje automático de Azure
      1. Introduzca la salida **Nombre de la entidad** a la que desea que fluyan los resultados de salida de la canalización.
      1. Seleccione el **Nombre del parámetro del almacén de datos de salida** de su canalización por lotes desde el menú desplegable.
      1. Seleccione el **Nombre del parámetro de la ruta de salida** de su canalización por lotes desde el menú desplegable.
      
      > [!div class="mx-imgBorder"]
      > ![Panel de parámetros de salida del modelo](media/intelligence-screen3-outputparameters.png "Panel de parámetros de salida del modelo")

1. Seleccione el atributo correspondiente de la lista desplegable **Resultados de id. de cliente** que identifica a los clientes y seleccione **Guardar**.
   
   > [!div class="mx-imgBorder"]
   > ![Relacionar los resultados con el panel de datos de clientes](media/intelligence-screen4-relatetocustomer.png "Relacionar los resultados con el panel de datos de clientes")

1. Verá la pantalla **Flujo de trabajo guardado** con detalles sobre el flujo de trabajo.    
   Si configuró un flujo de trabajo para una canalización de Azure Machine Learning, la información de público se adjuntará al espacio de trabajo que contiene la canalización. La información de público obtendrá un rol de **Colaborador** en el área de trabajo de Azure.

1. Seleccione **Listo**.

1. Ahora puede ejecutar el flujo de trabajo desde la página **Modelos personalizados**.

## <a name="edit-a-workflow"></a>Editar un flujo de trabajo

1. En la página **Modelos personalizados**, seleccione los puntos suspensivos verticales en la columna **Acciones**, junto a un flujo de trabajo que creó previamente, y seleccione **Editar**.

1. Puede actualizar el nombre reconocible de su flujo de trabajo en el campo **Nombre para mostrar**, pero no puede cambiar el servicio web o la canalización configurados. Seleccione **Siguiente**.

1. Para cada **Entrada de servicio web**, puede actualizar la **Entidad** correspondiente desde la información de público. A continuación, seleccione **Siguiente**.

1. En el paso **Parámetros de salida del modelo**, establezca las siguientes propiedades:
   - Machine Learning Studio (clásico)
      1. Introduzca la salida **Nombre de la entidad** a la que desea que fluyan los resultados de salida del servicio web.
   - Aprendizaje automático de Azure
      1. Introduzca la salida **Nombre de la entidad** a la que desea que fluyan los resultados de salida de la canalización.
      1. Seleccione el **Nombre del parámetro del almacén de datos de salida** para su canalización de prueba.
      1. Seleccione el **Nombre del parámetro de la ruta de salida** para su canalización de prueba.

1. Seleccione el atributo correspondiente de la lista desplegable **Resultados de id. de cliente** que identifica a los clientes y seleccione **Guardar**.
   Debe elegir un atributo de la salida de inferencia con valores similares a la columna de id. de cliente de la entidad Cliente. Si no tiene esa columna en su conjunto de datos, elija un atributo que identifique de forma exclusiva la fila.

## <a name="run-a-workflow"></a>Ejecutar un flujo de trabajo

1. En la página **Modelos personalizados**, seleccione los puntos suspensivos verticales en la columna **Acciones**, junto a un flujo de trabajo que creó previamente.

1. Seleccione **Ejecutar**.

Su flujo de trabajo también se ejecuta automáticamente con cada actualización programada. Más información acerca de [configurar actualizaciones programadas](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Eliminar un flujo de trabajo

1. En la página **Modelos personalizados**, seleccione los puntos suspensivos verticales en la columna **Acciones**, junto a un flujo de trabajo que creó previamente.

1. Seleccione **Eliminar** y confirme la eliminación.

Su flujo de trabajo será eliminado. La [entidad](entities.md) que se creó cuando creó el flujo de trabajo persiste y se puede ver desde la página **Entidades**.
