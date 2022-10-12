---
title: Modelos personalizados de aprendizaje automático | Microsoft Docs
description: Trabaje con modelos personalizados de Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609767"
---
# <a name="custom-machine-learning-models"></a>Modelos personalizados de aprendizaje automático

> [!NOTE]
> El soporte para Machine Learning Studio (clásico) finalizará el 31 de agosto de 2024. Le recomendamos que haga la transición a [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) para esa fecha.
>
> A partir del 1 de diciembre de 2021, no podrá crear nuevos recursos de Machine Learning Studio (clásico). Hasta el 31 de agosto de 2024, puede seguir utilizando los recursos Machine Learning Studio (clásico) existentes. Para obtener más información, consulte [Migrar a Azure Machine Learning](/azure/machine-learning/migrate-overview).

Los modelos personalizados permiten administrar flujos de trabajo basados en modelos de Azure Machine Learning. Los flujos de trabajo le ayudan a elegir los datos a partir de los cuales desea generar información y asignar los resultados a los datos unificados de sus clientes. Para obtener más información sobre cómo crear modelos de ML personalizados, consulte [Usar modelos basados en Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Requisitos previos

- Servicios web publicados a través de [Canalizaciones por lotes de Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- La canalización debe publicarse en un [punto de conexión de canalización](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Una [cuenta de almacenamiento de Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) asociada con su instancia de Azure Studio.
- Para las áreas de trabajo de Azure Machine Learning con canalizaciones, permisos de acceso de administrador de propietario o usuario al área de trabajo de Azure Machine Learning.

  > [!NOTE]
  > Los datos se transfieren entre sus instancias de Customer Insights y los servicios web o canalizaciones de Azure seleccionados en el flujo de trabajo. Al transferir datos a un servicio de Azure, asegúrese de que el servicio esté configurado para procesar los datos de la manera necesaria y en la ubicación necesaria a fin de su organización cumpla con los requisitos legales o normativos para esos datos.

## <a name="add-a-new-workflow"></a>Agregar un flujo de trabajo nuevo

1. Vaya a **Inteligencia** > **Modelos personalizados** y seleccione **Nuevo flujo de trabajo**.

1. Especifique un **Nombre** reconocible.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Captura de pantalla del panel Nuevo flujo de trabajo.":::

1. Seleccione la organización que contiene el servicio web en **Inquilino que contiene su servicio web**.

1. Si su suscripción a Azure Machine Learning se encuentra en un inquilino diferente de Customer Insights, seleccione **iniciar sesión** con sus credenciales para la organización seleccionada.

1. Selecciona las **Áreas de trabajo** asociadas con su servicio web.

1. Elija la canalización de Azure Aprendizaje automático en el desplegable **Servicio web que contiene tu modelo**. A continuación, seleccione **Siguiente**.
   Aprender más acerca de [publicar una canalización en Azure Machine Learning usando el diseñador](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) o el [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Para cada **Entrada de servicio web**, seleccione la coincidencia de **Entidad** de Customer Insights. A continuación, seleccione **Siguiente**.
   > [!NOTE]
   > El flujo de trabajo del modelo personalizado aplicará heurística para asignar los campos de entrada del servicio web a los atributos de la entidad según el nombre y el tipo de datos del campo. Verá un error si un campo de servicio web no se puede asignar a una entidad.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configurar un flujo de trabajo.":::

1. Para **Parámetros de salida del modelo**, establezca las siguientes propiedades:
   - **Nombre de la entidad** para los resultados de salida de canalización
   - **Nombre del parámetro del almacén de datos de salida** de su canalización de prueba
   - **Nombre del parámetro de ruta de salida** de su canalización de prueba

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Panel de parámetros de salida del modelo.":::

1. Seleccione el atributo correspondiente de **Id. de cliente en los resultados** que identifica clientes y seleccione **Guardar**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Relacionar los resultados con el panel Datos de clientes.":::

   La pantalla **Flujo de trabajo guardado** muestra detalles sobre el flujo de trabajo. Si configuró un flujo de trabajo para una canalización Aprendizaje automático de Azure, Customer Insights se adjunta al área de trabajo que contiene la canalización. Customer Insights obtendrá un rol **Colaborador** en el área de trabajo de Azure.

1. Seleccione **Listo**. Aparece la página **Modelos personalizados**.

1. Seleccione los puntos suspensivos verticales (&vellip;) para el flujo de trabajo y seleccione **Ejecutar**. Su flujo de trabajo también se ejecuta automáticamente con cada [actualización programada](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Administrar un flujo de trabajo existente

Vaya a **Inteligencia** > **Modelos personalizados** para ver los flujos de trabajo que ha creado.

Seleccione un flujo de trabajo para ver las acciones disponibles.

- **Editar** un flujo de trabajo
- **Ejecutar** un flujo de trabajo
- [**Eliminar**](#delete-a-workflow) un flujo de trabajo

### <a name="edit-a-workflow"></a>Editar un flujo de trabajo

1. Vaya a **Inteligencia** > **Modelos personalizados**.

1. Junto al flujo de trabajo que desea actualizar, seleccione los puntos suspensivos verticales (&vellip;) y seleccione **Editar**.

1. Cambie **Nombre para mostrar** si es necesario, y seleccione **Siguiente**.

1. Para cada **Entrada de servicio web**, actualice la coincidencia de **Entidad** de Customer Insights, si es necesario. A continuación, seleccione **Siguiente**.

1. Para **Parámetros de salida del modelo**, cambie cualquiera de las siguientes propiedades:
   - **Nombre de la entidad** para los resultados de salida de canalización
   - **Nombre del parámetro del almacén de datos de salida** de su canalización de prueba
   - **Nombre del parámetro de ruta de salida** de su canalización de prueba

1. Cambie el atributo correspondiente de **ID de cliente en resultados** para identificar los clientes. Elija un atributo de la salida de inferencia con valores similares a la columna de identificador de cliente de la entidad Cliente. Si no tiene esa columna en su conjunto de datos, elija un atributo que identifique de forma exclusiva la fila.

1. Seleccione **Guardar**

### <a name="delete-a-workflow"></a>Eliminar un flujo de trabajo

1. Vaya a **Inteligencia** > **Modelos personalizados**.

1. Junto al flujo de trabajo que desea eliminar, seleccione los puntos suspensivos verticales (&vellip;) y seleccione **Eliminar**.

1. Confirme la eliminación.

Su flujo de trabajo será eliminado. La [entidad](entities.md) que se creó cuando creó el flujo de trabajo persiste y se puede ver desde la página **Datos** > **Entidades**.

## <a name="view-the-results"></a>Ver resultados

Los resultados de un flujo de trabajo se almacenan en el nombre de entidad definido para **Parámetros de salida del modelo**. Acceda a estos datos desde la página [**Datos** > **Entidades**](entities.md) o con [acceso a la API](apis.md).

### <a name="api-access"></a>Acceso API

Para que la consulta de OData específica obtenga datos de una entidad de modelo personalizada, use el siguiente formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Sustituya `<your instance id>` con el identificador de su entorno de Customer Insights, que se muestra en la barra de direcciones de su navegador cuando acceda a Customer Insights.

1. Reemplace `<custom model output entity>` con el nombre de la entidad que proporcionó para **Parámetros de salida del modelo**.

1. Reemplace `<guid value>` con el identificador de cliente del cliente al que desea acceder. Este ID se muestra en la [página de perfiles de clientes](customer-profiles.md) en el campo CustomerID.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

- ¿Por qué no puedo ver mi canalización al configurar un flujo de trabajo de modelo personalizado?
  Este problema suele deberse a un problema de configuración en la canalización. Asegúrese de que [el parámetro de entrada está configurado](azure-machine-learning-experiments.md#dataset-configuration), y el [parámetros de ruta y almacén de datos de salida](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) también están configurados.

- ¿Qué significa el error "No se pudo guardar el flujo de trabajo de inteligencia"? 
  Los usuarios suelen ver este mensaje de error si no tienen privilegios de propietario o acceso de usuario Administrador en el espacio de trabajo. El usuario necesita un nivel más alto de permisos para permitir que Customer Insights procese el flujo de trabajo como un servicio en lugar de usar las credenciales del usuario para ejecuciones posteriores del flujo de trabajo.

- ¿Se admite un enlace privado punto de conexión/privado para el flujo de trabajo de mi modelo personalizado?
  Customer Insights actualmente no es compatible con punto de conexión privado para modelos personalizados listos para usar, pero hay una solución manual disponible. Póngase en contacto con el servicio de soporte técnico para conocer los detalles.

## <a name="responsible-ai"></a>IA responsable

Las predicciones ofrecen capacidades para crear mejores experiencias para los clientes, mejorar las capacidades comerciales y las secuencias de ingresos. Le recomendamos encarecidamente que equilibre el valor de su predicción con el impacto que tiene y los sesgos que pueden introducirse de manera ética. Obtenga más información sobre cómo Microsoft [aborda la IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). También puede aprender sobre [técnicas y procesos de aprendizaje automático responsable](/azure/machine-learning/concept-responsible-ml) específicos de Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
