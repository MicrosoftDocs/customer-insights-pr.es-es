---
title: Novedades de Dynamics 365 Customer Insights
description: Información sobre nuevas funciones, mejoras y correcciones de errores.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 4b5b95d1774d22827b3c08c2b6ccbb7858f1b04b
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054039"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novedades de Dynamics 365 Customer Insights

¡Estamos entusiasmados de anunciar nuestras actualizaciones más recientes! Este artículo resume las características de vista previa pública, las mejoras de disponibilidad general y las actualizaciones de características. Para ver los planes de características a largo plazo, eche un vistazo a los [planes de lanzamiento de Dynamics 365 y Power Platform](/dynamics365/release-plans/).

Implementamos actualizaciones región por región. Por tanto, algunas regiones pueden tener las características antes que otras. A menos que se especifique lo contrario, no es necesario que realice ninguna acción y actualizaremos la aplicación automáticamente sin tiempo de inactividad.

> [!TIP]
> Para enviar y votar en solicitudes de características y sugerencias de productos, vaya a [Portal de ideas de aplicaciones de Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Actualizaciones de mayo de 2022

Las actualizaciones de mayo de 2022 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="updated-data-unification-experience"></a>Experiencia de unificación de datos actualizada

 La unificación de datos le permite unificar fuentes de datos que alguna vez fueron dispares en un solo maestro conjunto de datos que proporciona una vista unificada de esos datos. Los datos se pueden unificar en una sola entidad o en varias entidades. Primero, debe [seleccionar entidades y campos de origen](map-entities.md), [eliminar registros duplicados](remove-duplicates.md), especificar reglas para [condiciones coincidentes](match-entities.md) y definir los [campos a incluir en los perfiles de clientes unificados](merge-entities.md).

Para obtener más información, consulte [Información general de unificación de datos](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Página de inicio actualizada en Customer Insights

**Inicio** le guía a través del proceso de configuración de las funciones clave y proporciona una descripción general de los segmentos, las medidas y los datos de enriquecimiento. Hemos actualizado la experiencia para proporcionar información más relevante de un vistazo.

Para obtener más información, consulte [Explorar Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Rastrear el uso de un segmento

Ahora puede [seguir el uso de un segmento](segments.md#track-usage-of-a-segment) en aplicaciones, que se basan en la organización de Dataverse que está conectada con Customer Insights. Para [Segmentos de Customer Insights utilizados en recorridos de clientes de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), el sistema le informa sobre el uso de ese segmento.

### <a name="export-to-criteo"></a>Exportar a Criteo

Criteo es una plataforma en línea que ayuda a los usuarios a administrar la publicidad digital. Ahora puede exportar segmentos de perfiles de clientes unificados para generar campañas, proporcionar marketing por correo electrónico y utilizar grupos específicos de clientes con Criteo.

Para obtener más información, consulte [Exportar segmentos a Criteo (vista previa)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Estructura de documentación refinada para la creación de entornos

Hemos revisado los documentos de ayuda relacionados con la creación y administración de entornos en Customer Insights. Los artículos ahora están agrupados bajo el nodo Entornos en la tabla de contenido. Los artículos reestructurados brindan más orientación sobre las diferentes formas de configurar entornos y tienen una estructura más clara. Si tiene comentarios para compartir, infórmenos a través de los controles que se encuentran al final de los artículos de ayuda.

Para obtener más información, consulte [Cómo: Crear un nuevo entorno](create-environment.md).

## <a name="april-2022-updates"></a>Actualizaciones de abril de 2022

Las actualizaciones de abril de 2022 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="dun--bradstreet-enrichment-preview"></a>Enriquecimiento de Dun & Bradstreet (vista previa)

Dun & Bradstreet proporciona datos comerciales, análisis e información para las empresas. Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa. Entre los enriquecimientos se incluyen atributos como número DUNS, tamaño de la empresa, su ubicación, su sector y mucho más.

Para más información, vea [Enriquecimiento de perfiles de empresa con Dun & Bradstreet (vista previa)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definir el tipo de medida al crear una nueva medida

Ahora puede distinguir entre medidas para perfiles individuales y medidas en toda su empresa. Mientras que las medidas comerciales se muestran en la página de inicio de Customer Insights, las medidas de los clientes se exponen en las vistas detalladas de los clientes.

Para más información, vea [Usar el generador de medidas para crear medidas desde cero](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidación de la documentación de Customer Insights

Revisamos nuestros artículos de documentación y eliminamos las menciones de información de participación y capacidades de información de audiencia. En el futuro, nos referiremos constantemente al nombre del producto Customer Insights cuando escribamos sobre las funciones principales de la aplicación. Este cambio también conduce a una reestructuración significativa de la tabla de contenido, la estructura de URL y las rutas de archivo en el depósito de documentación subyacente. Todos sus marcadores o enlaces existentes continúan funcionando y redirigen a las URL actualizadas.

Si desea hacernos saber cómo percibe ese cambio o detecta algo que no funciona como se esperaba, díganoslo [enviando comentarios para esta página](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

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

Para obtener más información, consulte [Habilitar uso compartido de datos con Dataverse desde su propio Azure Data Lake Storage (versión preliminar)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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