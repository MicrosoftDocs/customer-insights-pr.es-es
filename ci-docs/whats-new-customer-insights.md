---
title: Características nuevas y mejoradas
description: Información sobre nuevas funciones, mejoras y correcciones de errores.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647898"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novedades de Dynamics 365 Customer Insights

¡Estamos entusiasmados de anunciar nuestras actualizaciones más recientes! Este artículo resume las características de vista previa pública, las mejoras de disponibilidad general y las actualizaciones de características. Para ver los planes de características a largo plazo, eche un vistazo a los [planes de lanzamiento de Dynamics 365 y Power Platform](/dynamics365/release-plans/).

Implementamos actualizaciones región por región. Por tanto, algunas regiones pueden tener las características antes que otras. A menos que se especifique lo contrario, no es necesario que realice ninguna acción y actualizaremos la aplicación automáticamente sin tiempo de inactividad.

> [!TIP]
> Para enviar y votar en solicitudes de características y sugerencias de productos, vaya a [Portal de ideas de aplicaciones de Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Actualizaciones de marzo de 2022

Las actualizaciones de marzo de 2022 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="liveramp-abilitec-enrichment-preview"></a>Enriquecimiento de LiveRamp AbiliTec (versión preliminar)

LiveRamp proporciona resolución de identidad y consolidación de datos de clientes. Puede asignar identificadores personales en sus datos de cliente al gráfico de identidad de AbiliTec y recibir id. de AbiliTec. A continuación, puede utilizar estos id. para una mejor unificación de los datos de sus clientes.

Para más información, vea [Enriquecer los perfiles de los clientes con datos de identidad de LiveRamp (versión preliminar)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organice segmentos y medidas con etiquetas y filtros
Si su organización mantiene muchos segmentos o medidas, encontrar el correcto a veces puede ser un desafío. Esta nueva característica le permite organizar listas usando etiquetas y columnas. Ayuda a encontrar datos de forma rápida y sencilla y a personalizar las vistas.

Para obtener más información, consulte [Trabajar con etiquetas y columnas](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Habilitar el intercambio de datos con Dataverse al usar su propia cuenta de almacenamiento

Si su entorno usa Azure Data Lake Storage para almacenar datos de Customer Insights, el uso compartido de datos con Microsoft Dataverse requiere alguna configuración extra.
Antes, solo podía habilitar el uso compartido de datos con Dataverse cuando sus datos se almacenaban en nuestro lago de datos administrado. 

Para obtener más información, consulte [Habilitar uso compartido de datos con Dataverse desde su propio Azure Data Lake Storage (versión preliminar)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nuevos destinos de exportación: Iterable y Braze

Seguimos ampliando nuestro ecosistema de destinos de exportación con nuevas conexiones. Ahora puede exportar segmentos a Iterable y Braze para usar sus servicios de activación.

Para obtener más información, consulte [Exportar segmentos a Iterable (versión preliminar)](export-iterable.md) y [Exportar segmentos a Braze (versión preliminar)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Mejoras en la exportación de Marketo y Google Ads

Cambiar las API en los servicios conectados genera actualizaciones para que los conectores funcionen de manera fiable y sin problemas. Hemos publicado algunas actualizaciones para las exportaciones a los servicios de Marketo y Google Ads:

- Google Ads: la nueva versión del conector de exportación de Google Ads simplifica la experiencia de autenticación y ahora le permite crear nuevas audiencias de Google Ads automáticamente. 
- Marketo: la nueva versión del conector de exportación de Marketo brinda soporte para el id. de Marketo, lo que le permite evitar la duplicación de datos, actualizar registros existentes y crear nuevos registros en Marketo. 


## <a name="february-2022-updates"></a>Actualizaciones de febrero de 2022

Las actualizaciones de febrero de 2022 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="general-availability-for-prediction-models"></a>Disponibilidad general para modelos de predicción

Modelos de predicción listos para usar, incluidos **abono de suscripción**, **abono transaccional** y **valor de por vida del cliente (CLV)**, estarán disponibles de forma general como parte de Customer Insights. 

Para obtener más información, consulte [Información general de predicciones](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nuevo origen de datos: Integración con Azure Synapse Analytics (versión preliminar)

Azure Synapse Analytics es un servicio de análisis empresarial que acelera el tiempo de obtención de información en los almacenamientos de datos y los sistemas de macrodatos.

Las organizaciones que ya utilizan Azure Synapse Analytics puede ingerir esos datos en Customer Insights. 

Para más información, vea [Conectar un origen de datos de Azure Synapse (versión preliminar)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Enriquecimiento de LiveRamp (versión preliminar)

LiveRamp proporciona resolución de identidad y consolidación de datos de clientes. Puede asignar identificadores personales en sus datos de cliente al gráfico de identidad de AbiliTec y recibir id. de AbiliTec. A continuación, puede utilizar estos id. para una mejor unificación de los datos de sus clientes.

Para más información, vea [Enriquecer los perfiles de los clientes con datos de identidad de LiveRamp (versión preliminar)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Enriquecimiento de orígenes de datos (versión preliminar)

Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de sus clientes antes de la unificación de datos. Los enriquecimientos origen de datos ayudan a producir datos más completos y de mayor calidad que pueden ayudar a lograr mejores resultados una vez que unifique sus datos.

Para obtener más información, consulte [Enriquecimiento de orígenes de datos (versión preliminar)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Cambiar propietario del entorno

Si bien varios usuarios pueden tener permisos de administrador en Customer Insights, solo un usuario es el propietario de un entorno. Una experiencia mejorada le permite cambiar los propietarios de un entorno y reclamar la propiedad si un propietario anterior deja la organización. 

Para más información, consulte [Cambiar el propietario de un entorno](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>El proceso de preparación de datos enumera el motivo de corrupción de los registros dañados

La preparación de datos ahora muestra el motivo de la corrupción para todos los campos con datos corruptos. La información se proporciona en el nivel de registro individual para una identificación sencilla. 

Para más información, vea [Orígenes de datos corruptos](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Fin de la versión preliminar de las características de generación de informes en la capacidad de información de interacción

La versión preliminar de las conclusiones sobre la interacción de Dynamics 365 Customer Insights finalizaron el 15 de febrero de 2022.  
Este cambio significa que la experiencia de prueba de Customer Insights ya no incluye la posibilidad de crear embudos ni otras funcionalidades de informes.

Le invitamos a explorar y evaluar las muchas otras características de [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), la plataforma de datos de clientes (CDP) de Microsoft.    
 
Durante un periodo de transición, los participantes actuales de la versión preliminar siguen teniendo acceso a algunas capacidades y funcionalidades de la versión preliminar:

- Obtener el código para instrumentar un sitio web o una aplicación móvil. 
- Ver eventos y propiedades de los eventos. 
- Mejorar los perfiles unificados con eventos ingeridos y refinados para beneficiarse de todo el valor de sus datos de clientes.
  
Durante el periodo de transición, los eventos capturados se siguen transmitiendo al Data Lake conectado. Una vez desactivada esta funcionalidad, el intercambio de datos se detendrá y no se enviarán nuevos eventos al almacenamiento conectado.
Póngase en contacto directamente con el equipo de su cuenta Microsoft si tiene preguntas sobre el fin de la versión preliminar de capacidades. Su equipo de cuentas le mantendrá al tanto de los próximos lanzamientos. 

## <a name="january-2022-updates"></a>Actualizaciones de enero de 2022

Las actualizaciones de enero de 2022 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Análisis de sentimiento de los comentarios del cliente

Customer Insights proporciona una nueva función impulsada por IA para sintetizar las opiniones del cliente e identificar aspectos comerciales específicos como oportunidades para mejoras específicas. Al analizar los comentarios escritos de sus clientes, puede obtener información precisa a bajo coste. Análisis de sentimientos impulsado por modelos de procesamiento de lenguaje natural (NLP) que generan dos informaciones derivadas para cada id. de cliente. Una puntuación de opinión (de -5 a 5) y una lista de aspectos comerciales aplicables. 

Para obtener más información, consulte [Analizar la opinión en los comentarios de los clientes (versión preliminar)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]