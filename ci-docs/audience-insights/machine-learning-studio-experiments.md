---
title: Experimentos de Machine Learning Studio (clásico)
description: Use modelos de Machine Learning Studio (clásico) en Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598360"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Usar modelos basados en Azure Machine Learning Studio (clásico)

Los datos unificados en Dynamics 365 Customer Insights son un origen para crear modelos de aprendizaje automático que pueden generar información empresarial adicional. Customer Insights se integra con Machine Learning Studio (clásico) para usar sus propios modelos personalizados. Para ver cómo los modelos desarrollados en AAzure Machine Learning se integran con Customer Insights, consulte [Experimentos de Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Requisitos previos

- Acceso a Customer Insights
- Una suscripción de Azure Enterprise activa
- [Perfiles de cliente unificados](data-unification.md)
- Configuración de [Exportación de entidades a Azure Blob Storage](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Configurar Machine Learning Studio clásico

En un primer paso, necesitamos crear un espacio de trabajo y abrir Machine Learning Studio (clásico).

1. Vaya a [https://www.portal.azure.com](https://www.portal.azure.com/) e inicie sesión.

1. Seleccione **Crear un recurso**.

1. Busque **Espacio de trabajo Machine Learning Studio** y seleccione **Crear**.

1. Introduzca los detalles requeridos para [crear el espacio de trabajo](/azure/machine-learning/studio/create-workspace). Elija el **Nivel de precios del plan de servicio web** según la cantidad de datos que planea importar. Para un mejor rendimiento, seleccione la **Ubicación** geográficamente más cercana a usted.

1. Después de crear el recurso, aparecerá el panel del espacio de trabajo Machine Learning Studio. Seleccione **Ejecutar Machine Learning Studio**.

   ![Interfaz de usuario de Azure Machine Learning Studio](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Trabajar con Azure Machine Learning Studio

Ahora puede crear un nuevo experimento o importar una plantilla de experimento existente desde la galería de muestras. Hay experimentos de ejemplo para tres escenarios estándar:

- [Predicción de abandono](#churn-analysis)

- [Valor del tiempo de vida del cliente](#customer-lifetime-value-prediction)

- [Recomendación de producto o siguiente mejor acción](#productrecommendation-or-next-best-action)

1. Si crea un nuevo experimento o utiliza una plantilla de experimento de la galería, debe configurar las propiedades de **Importar datos**. Use la experiencia guiada o proporcione detalles directamente para acceder al Azure Blob Storage que contiene sus datos.  

   ![Experimento con Azure Machine Learning Studio](media/azure-machine-learning-studio-experiment.png)

1. Ahora puede crear una canalización de procesamiento personalizada para limpiar y preprocesar los datos, extraer características y entrenar un modelo adecuado.

1. Pruebe y optimice el modelo de rendimiento.

1. Cuando esté satisfecho con la calidad de un modelo, seleccione **Configurar servicio web** > **Servicio web predictivo**. Esta opción importa el modelo entrenado y la canalización de características del experimento de entrenamiento a un servicio predictivo. El servicio predictivo puede tomar otro conjunto de datos de entrada con el esquema utilizado en el experimento de entrenamiento para hacer predicciones.

   ![Configurar un servicio web predictivo](media/predictive-webservice-control.png)

1. Una vez que el experimento del servicio web predictivo tenga éxito, puede implementarlo para la programación automática. Para que el servicio web funcione con Customer Insights, seleccione **Implementar servicio web** > **Implementar servicio web [nuevo] Vista previa**. [Más información sobre implementar un servicio web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Implementar un servicio web predictivo](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modelos de muestra de la galería

Usaremos un escenario ficticio de Contoso Hotel para los modelos de este artículo. Contoso Hotel recopila los siguientes datos:

- Datos de CRM que consisten en la actividad de la estancia en el hotel. El conjunto de datos incluye información sobre las fechas de estancia de cada cliente registrado. También contiene información sobre la reserva, los tipos de habitaciones, los detalles del gasto, etc. Los datos abarcan cuatro años, desde enero de 2014 hasta enero de 2018.
- Perfiles de clientes de los huéspedes del hotel. Estos perfiles contienen información sobre cada cliente, incluido su nombre, fecha de nacimiento, dirección postal, sexo y número de teléfono.
- Uso de servicios que ofrece el hotel, como spa, lavandería, WiFi o mensajería. Esta información se registra para cada cliente registrado. Normalmente, el uso de los servicios está relacionado con la estancia. En algunos casos, los clientes pueden utilizar los servicios sin alojarse en el hotel.

## <a name="churn-analysis"></a>Análisis de abandono

El análisis de abandono se aplica a diferentes áreas comerciales. En este ejemplo, veremos el abandono del servicio, específicamente en el contexto de los servicios hoteleros, como se describe anteriormente. Proporciona un ejemplo funcional de una canalización de modelos de extremo a extremo que se puede utilizar como punto de partida para cualquier otro tipo de modelo de abandono.

### <a name="definition-of-churn"></a>Definición de abandono

La definición de abandono puede diferir según el escenario. En este ejemplo, un huésped que no ha visitado el hotel en el último año debe etiquetarse como abandonado.  

La plantilla de experimento se puede importar desde la galería. Primero, asegúrese de importar los datos para **Actividad de estancia en hotel**, **Información del cliente** y **Datos de uso del servicio** desde Azure Blob Storage.

   ![Importar datos para el modelo de abandono](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Caracterización

Basándonos en la definición de abandono, primero identificamos las características sin procesar que influirán en la etiqueta. Luego, procesamos estas características sin procesar en características numéricas que se pueden usar con los modelos Aprendizaje automático. La integración de datos ocurre en Customer Insights para que podamos unir estas tablas usando el *Id. de cliente*.

   ![Unir datos importados](media/join-imported-data.png)

La caracterización para construir el modelo para el análisis de abandono puede ser un poco complicada. Los datos son una función del tiempo con la nueva actividad hotelera registrada diariamente. Durante la caracterización, queremos generar características estáticas a partir de los datos dinámicos. En este caso, generamos múltiples características de la actividad hotelera con una ventana deslizante de un año. También ampliamos las características categóricas como el tipo de habitación o el tipo de reserva en características separadas mediante la codificación one-hot.  

Lista final de características:

| **Número**  | **Columna_original**          | **Funciones derivadas**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Tipo de habitación                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tipo de reserva                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Categoría de viaje              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dólares gastados                | TotalDollarSpent                                                                                                                          |
| 5           | Fechas de entrada y salida  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Uso de servicios                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Selección de modelo

Ahora tenemos que elegir el algoritmo óptimo para usar. En este caso, la mayoría de las funciones se basan en funciones categóricas. Normalmente, los modelos basados en árboles de decisión funcionan bien. Si solo hay características numéricas, las redes neuronales podrían ser una mejor opción. La máquina de vectores de soporte (SVM) también es un buen candidato en tales situaciones; sin embargo, necesita algunos ajustes para obtener el mejor rendimiento. Nosotros elegimos **Árbol de decisión mejorado de dos clases** como el primer modelo de elección, seguido de **SVM de dos clases** como segundo modelo. Azure Machine Learning Studio le permite realizar pruebas A/B, por lo que es beneficioso comenzar con dos modelos en lugar de uno.

La siguiente imagen muestra la canalización de evaluación y entrenamiento de modelos de Azure Machine Learning Studio:

![Modelo de abandono en Azure Machine Learning Studio](media/azure-machine-learning-model.png)

También aplicamos una técnica llamada **Importancia de la característica de permutación**, un aspecto importante de la optimización del modelo. Los modelos integrados tienen poca o ninguna información sobre el impacto de cualquier característica específica en la predicción final. La calculadora de importancia de características utiliza un algoritmo personalizado para calcular la influencia de características individuales en el resultado de un modelo específico. La importancia de la característica se normaliza entre +1 y -1. Una influencia negativa significa que la característica correspondiente tiene una influencia contraria a la intuición en el resultado y debe eliminarse del modelo. Una influencia positiva indica que la función está contribuyendo en gran medida a la predicción. Estos valores no son coeficientes de correlación, ya que son métricas diferentes. Para más información, consulte [Importancia de la característica de permutación](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

La totalidad del [experimento de abandono está disponible en Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predicción del valor de la vida del cliente

El cálculo del valor de vida del cliente (CLTV) es una de las métricas clave que una empresa puede utilizar para evaluar y segmentar a sus clientes. Para el negocio hotelero, es fundamental conocer a sus clientes. Por ejemplo, conocer los factores que crean buenos clientes es una información crucial. Ayuda a la gerencia del hotel a evaluar en qué características deben enfocarse y mejorar para satisfacer a sus clientes más rentables. Estas decisiones pueden tener un impacto directo en las ventas y las ganancias.  

### <a name="definition-of-cltv"></a>Definición de CLTV

Para este ejemplo, definimos el CLTV de un cliente como el importe total en dólares que se espera que el cliente gaste en los próximos 365 días. Usaremos los datos de los últimos tres años de todos los clientes para predecir este valor.

### <a name="featurization"></a>Caracterización

En este caso, la caracterización será muy similar al escenario de abandono. Sin embargo, las etiquetas y los valores predichos son diferentes a los definidos anteriormente.

### <a name="model-selection"></a>Selección de modelo

La predicción del CLTV es un problema de regresión, ya que el valor predicho es una variable continua con valor positivo. Según las propiedades de la característica, seleccionamos **Regresión de árbol de decisión potenciada** como un algoritmo y **Regresión de redes neuronales** como otro algoritmo para entrenar el modelo.

## <a name="product-recommendation-or-next-best-action"></a>Recomendación de producto o Siguiente mejor acción

La recomendación de productos en un escenario de hotel se interpreta como la recomendación de servicios ofrecidos por el hotel a los clientes. El objetivo es elegir los servicios adecuados para los clientes de manera que se maximice su uso. Es similar a las recomendaciones de películas para usuarios de servicios de transmisión de video.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definición de recomendación de producto o siguiente mejor acción

Definimos el objetivo como maximizar el monto en dólares del uso del servicio al ofrecer los mejores servicios de combinación a los clientes del hotel de acuerdo con sus intereses.

### <a name="featurization"></a>Caracterización

Al igual que el modelo de abandono, estamos uniendo el ServiceCustomerID del hotel con el CustomerID, para crear recomendaciones de forma coherente para cada CustomerID.

![Caracterización del modelo de recomendación](media/azure-machine-learning-model-featurization.png)

Los datos con origen en tres entidades diferentes y las características se derivan de ellas. La caracterización del problema de recomendación es diferente en comparación con los escenarios de abandono o CLTV. El modelo de recomendación necesita datos de entrada en forma de tres conjuntos de características.

### <a name="model-selection"></a>Selección de modelo

Predecimos productos o servicios utilizando el algoritmo llamado **Entrenar Recomendador de Matchbox** para entrenar el modelo de recomendación.

![Algoritmo de Recomendaciones de productos](media/azure-machine-learning-model-recommendation-algorithm.png)

Los tres puertos de entrada para el modelo **Entrenar Recomendador de Matchbox** incluye los datos de uso del servicio de formación, la descripción del cliente (opcional) y la descripción del servicio. Hay tres formas diferentes de puntuar el modelo. Uno es para la evaluación del modelo donde se calcula una puntuación de Ganancia acumulada descontada normalizada (NDCG) para clasificar los elementos calificados. En este experimento, tenemos la puntuación NDCG de 0,97. Las otras dos opciones son puntuar el modelo en todo el catálogo de servicios recomendables, o puntuar solo en elementos que los usuarios no han utilizado antes.

Si miramos más a fondo las distribuciones de las recomendaciones en todo el catálogo de servicios, notamos que teléfono, Wi-Fi y servicio de mensajería son los principales servicios a reomendar. Esto es consistente con lo que encontramos a partir de las distribuciones de los datos de consumo del servicio:

![Salida del modelo de recomendación](media/azure-machine-learning-model-output.png)

La totalidad del [experimento de recomendación de producto está disponible en Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrar modelos personalizados

Para utilizar estas predicciones en Customer Insights, debe **exportar** las predicciones junto con los id. de cliente. [Expórtelas a la misma ubicación de almacenamiento de Azure Blob](/azure/storage/common/storage-import-export-data-from-blobs) a la que exporta los datos de origen. El servicio web predictivo se puede programar para que se ejecute regularmente y actualice las puntuaciones.

Los datos generados por el modelo personalizado se pueden utilizar para enriquecer aún más los datos de sus clientes. Para más información, ver [Modelos personalizados de aprendizaje automático](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]