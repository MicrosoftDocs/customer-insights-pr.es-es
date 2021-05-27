---
title: Características nuevas y mejoradas
description: Información sobre nuevas funciones, mejoras y correcciones de errores.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988941"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novedades de la capacidad de informaciones de público de Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

¡Estamos entusiasmados de anunciar nuestras actualizaciones más recientes! Este artículo resume las características de vista previa pública, las mejoras de disponibilidad general y las actualizaciones de características. Para ver los planes de características a largo plazo, eche un vistazo a los [planes de lanzamiento de Dynamics 365 y Power Platform](/dynamics365/release-plans/).

Implementamos actualizaciones región por región. Por tanto, algunas regiones pueden tener las características antes que otras. A menos que se especifique lo contrario, no es necesario que realice ninguna acción y actualizaremos la aplicación automáticamente sin tiempo de inactividad.

> [!TIP]
> Para enviar y votar en solicitudes de características y sugerencias de productos, vaya a [Portal de ideas de aplicaciones de Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="april-2021-updates"></a>Actualizaciones de abril de 2021

Las actualizaciones de abril de 2021 incluyen varias características, mejoras de rendimiento y correcciones de errores.

### <a name="data-unification"></a>Unificación de datos
 
- **Experiencia de combinación mejorada para la unificación de datos**    
  
   Ahora tenemos una experiencia de usuario mejorada en la configuración de combinación del proceso de unificación de datos. Los cambios incluyen el orden intuitivo de los campos combinados y estadísticas detalladas sobre los campos combinados y singleton.

- **Reordenación de entidades y configuración de todos los registros de origen en la entidad Cliente**  
      
   Ahora puede reordenar y eliminar entidades de un plan de combinación existente en el proceso de unificación de datos. Ofrece flexibilidad para reordenar las entidades en el proceso de coincidencia de acuerdo con las necesidades comerciales. Además, habilitamos la inclusión de todos los registros no coincidentes en la entidad *Cliente*, que les permite definir su conjunto de datos de perfil de cliente.

### <a name="enrichments"></a>Enriquecimientos

 - **Nuevo enriquecimiento: direcciones mejoradas**    
  
   Nos complace presentar un nuevo enriquecimiento para mejorar las direcciones en los datos de sus clientes. Las direcciones de sus datos pueden no estar estructuradas, estar incompletas o ser incorrectas. Esta característican utiliza los modelos de Microsoft para normalizar y enriquecer sus direcciones en el formato Common Data Model para una mejor precisión y conocimientos.
 
   Para más información, vea [Enriquecimiento de perfiles de clientes con direcciones mejoradas](enrichment-enhanced-addresses.md).

- **Experiencia de configuración guiada para enriquecimientos**    
  
   Revisamos la experiencia de configuración para enriquecerlos con una experiencia sencilla y guiada. Ahora tiene un proceso claro paso a paso para crear y editar enriquecimientos.
 
   Además, hemos separado la configuración de conexiones para enriquecimientos de terceros, para permitir que múltiples enriquecimientos utilicen la misma conexión. Solo los administradores pueden configurar nuevas conexiones, pero las conexiones creadas están disponibles tanto para administradores como para colaboradores.    

   Para obtener más información, consulte [Información general de conexiones](connections.md).

- **Múltiples enriquecimientos del mismo tipo**    
  
   Ahora permitimos a los usuarios crear y administrar múltiples enriquecimientos del mismo tipo de enriquecimiento. Por ejemplo, ahora puede crear dos enriquecimientos de direcciones independientes para enriquecer dos segmentos de clientes diferentes. Se aplican límites sobre la cantidad de enriquecimientos del mismo tipo que se pueden crear y varían según el tipo de enriquecimiento.
  
   Para más información, consulte [Enriquecimiento de perfiles de clientes](enrichment-hub.md).

## <a name="march-2021-updates"></a>Actualizaciones de marzo de 2021

Las actualizaciones de marzo de 2021 incluyen varias funciones, mejoras de rendimiento y correcciones de errores.

### <a name="activities"></a>Actividades

- **Asistente de actividad y tipos semánticos**

   Hemos mejorado y actualizado nuestra experiencia de asignación de actividades para guiar y simplificar la creación de asignaciones de actividades. En esta nueva experiencia, los usuarios obtienen una experiencia guiada para ayudarles a completar cada paso del proceso. En el paso de asignación de actividades, además de elegir entre muchos tipos de actividades, el usuario puede elegir asignar semánticamente datos para *Suscripción* y/o *SalesOrderLine* para los esquemas estándar del sector, que se pueden utilizar para el consumo posterior.   

   Para obtener más información, consulte [Actividades del cliente](activities.md).

### <a name="data-ingestion"></a>Ingesta de datos

- **Conéctese a fuentes de datos locales usando flujos de datos y puertas de enlace de Power Platform**. Nos complace anunciar la versión preliminar de los flujos de datos y la conectividad local de Power Platform mediante puertas de enlace en Customer Insights con un entorno de Power Platform o Dataverse asociado. Cualquier nueva fuente de datos creada en un entorno de Customer Insights con un entorno de Dataverse asociado pasará por defecto a los flujos de datos de Power Platform que incorporan la conectividad de datos local y un amplio conjunto de conectores y funciones de transformación.

### <a name="extensibility"></a>Extensibilidad

- **Exportaciones organizadas en conexiones y exportaciones**. Hemos cambiado el nombre de la página **Destinos de exportación** a **Conexiones** y agregado una página separada para **Exportaciones**. Como parte de esta actualización, realizaremos la transición de las exportaciones existentes a pares de una conexión y una exportación utilizando esa conexión. Los administradores ahora ven más claro los datos salientes en la página **Conexiones**. Todos los roles de usuario tienen acceso a la página **Exportaciones**, pero solo los administradores pueden optar por permitir que los colaboradores editen exportaciones específicas con conexiones compartidas.     
  Para más información, vea [Resumen de conexiones](connections.md) y [Resumen de exportaciones](export-destinations.md).

- **Exportar segmentos a Campaign Monitor**. Hemos ampliado nuestros destinos de exportación para incluir Campaign Monitor. Ahora puede exportar segmentos de Customer Insights a las listas de Campaign Monitor y utilizarlos como valor de referencia para sus campañas de marketing.    
   Para obtener más información, consulte [Exportar a Campaign Monitor](export-campaign-monitor.md).

- **Exportar segmentos a Constant Contact**. Hemos ampliado nuestros destinos de exportación para incluir Constant Contact. Ahora puede exportar segmentos de Customer Insights a las listas de Constant Contact y utilizarlos como valor de referencia para sus campañas de marketing.   
   Para obtener más información, consulte [Exportar a Constant Contact](export-constant-contact.md).

- **Exportar segmentos a RollWorks**. Hemos ampliado nuestros destinos de exportación para incluir RollWorks. Ahora puede exportar segmentos de Customer Insights a las audiencias de RollWorks y utilizarlos como valor de referencia para sus anuncios B2B.    
   Para obtener más información, consulte [Exportar a RollWorks](export-rollworks.md).

- **Exportar segmentos a Snapchat**. Hemos ampliado nuestros destinos de exportación para incluir Snapchat. Ahora puede exportar segmentos de Customer Insights a las audiencias de Snapchat y utilizarlos como valor de referencia para sus anuncios.     
   Para obtener más información, consulte [Exportar a Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predicciones

- **Utilice filtros de productos en recomendaciones de productos predictivas**. Hemos agregado la capacidad de usar filtros de productos en nuestro modelo de recomendación de productos. Ahora puede crear un predicción que use solo un subconjunto de sus productos.    
   Para más información, vea [Configurar filtros de productos](predict-product-recommendation.md#configure-product-filters).

- **Crea segmentos a partir de predicciones de modelos**. Hemos agregado una forma rápida de crear segmentos utilizando los resultados de un modelo de predicción. Desde la página de resultados del modelo, puede crear fácilmente un nuevo segmento seleccionando la nueva opción **Crear segmento**.    
  Para más información, vea [Crear un segmento basado en un modelo predicción](prediction-based-segment.md).

- **Explicaciones para recomendaciones de productos**. Hemos agregado información que explica los factores clave aprendidos por el modelo de IA para generar recomendaciones de productos y el grado en que esos factores contribuyen a las recomendaciones de productos. Esta información se agrega a la pantalla de resultados del modelo.    
   Para más información, consulte [Revisar un estado de predicción y los resultados](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Actualizaciones de febrero de 2021

Las actualizaciones de febrero de 2021 incluyen diversas características, mejoras de rendimiento y correcciones de errores.

#### <a name="extensibility"></a>Extensibilidad

- **Exportar segmentos a AdRoll**

  Hemos ampliado nuestros destinos de exportación para incluir AdRoll. Ahora puede exportar segmentos de Customer Insights a las audiencias de AdRoll y utilizarlos como base para su publicidad. Para más información, consulte [Conector para AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmentos
 
- **Duplicar un segmento**
  
  Para crear un segmento nuevo basado en uno existente, ahora puede duplicar un segmento y editar el segmento duplicado para refinarlo más. 

- **Agregar atributos adicionales a un segmento**

  Ahora puede incluir atributos en la salida de su segmento, incluso si estos atributos no forman parte del perfil del cliente. Por ejemplo, incluya los identificadores de suscripción en un segmento aunque sea parte de la entidad de suscripción que tiene una relación M:1 con la entidad del cliente. Siempre que el atributo pertenezca a una entidad relacionada con la entidad del cliente, ahora puede incluir estos atributos.  

#### <a name="predictions"></a>Predicciones

- **Crear una predicción de recomendaciones de producto**

  Comprender en lo que los clientes están interesados en comprar es uno de los primeros pasos necesarios para mejorar los ingresos comerciales y fomentar la lealtad del cliente a través de la personalización y el compromiso. Ofrecer recomendaciones de productos que no están alineados con los intereses de su cliente puede crear una sensación de desconexión entre el cliente y su empresa y, en última instancia, limitar los ingresos y la experiencia potenciales generales para un cliente. 

  Con sus propios datos, ahora puede crear predicciones sobre qué productos es probable que sus clientes compren en el futuro. Para más información, consulte [Predicción de recomendación de producto](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administración del sistema

- **El entorno de copia admite más tipos de fuentes de datos**

  Los administradores pueden copiar configuraciones de entorno a un nuevo entorno en la misma organización. Esta característica amplía la funcionalidad del entorno de copia para los casos en los que las fuentes de datos basadas en un lago de datos de Common Data Service o carpeta de Common Data Model se usan.

## <a name="january-2021-updates"></a>Actualizaciones de enero de 2021

Las actualizaciones de enero de 2021 incluyen diversas características, mejoras de rendimiento y correcciones de errores.

#### <a name="extensibility"></a>Extensibilidad

- **Funcionalidad ampliada y rendimiento mejorado para la exportación SFTP**: ahora puede exportar todas las entidades de salida de Customer Insights a un host SFTP. Anteriormente, la exportación se limitaba a las entidades de segmento. Además, el rendimiento de la exportación SFTP permite un mayor volumen de datos en menos tiempo, dependiendo del rendimiento de su host SFTP.    
  Para más información, consulte [Conector para SFTP (versión preliminar)](export-sftp.md).  

#### <a name="segments"></a>Segmentos

- **Segmentos sugeridos con tecnología de aprendizaje automático para mejorar las métricas**: hay una nueva forma de descubrir y crear segmentos. El sistema utiliza un modelo de IA para sugerir segmentos que pueden ayudar a mejorar un KPI (medida) que ya está rastreando. Mostramos el alcance de la influencia de los atributos que selecciona en una medida u otro atributo principal. Esta información ayuda a encontrar segmentos potenciales que presentan oportunidades.    
  Para más información, consulte [Segmentos sugeridos (versión preliminar)](suggested-segments.md).

#### <a name="data-unification"></a>Unificación de datos

- **Experiencia correspondencia mejorada**: en el área de unificación de datos, se actualizó la experiencia de correspondencia. Le permite configurar y ver las reglas de coincidencia, incluidas las estadísticas detalladas para explicar mejor cómo funcionan las correspondencias. Hay opciones para deshabilitar una regla de correspondencia para que ya no esté activa mientras se conserva la configuración, reglas arrastrar y soltar y mucho más.
  Para obtener más información, consulte [Entidades de correspondencia](match-entities.md).

- **Los resultados de la desduplicación del proceso de correspondencia están disponibles como una entidad**: el resultado del proceso de desduplicación del proceso de correspondencia ahora se escriben en una entidad separada para un análisis más detallado. Esta entidad consta de los campos utilizados en el proceso de desduplicación y el registro elegido y los registros alternativos correspondientes que se fusionan con el registro elegido.
  Para más información, consulte [Resultados de la desduplicación como una entidad](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administración del sistema

- **Comparta datos con fluidez con Microsoft Dataverse**: ahora puede compartir los resultados de Customer Insights con aplicaciones Microsoft Dataverse que utilizan la instancia de Data Lake gestionada de Microsoft Dataverse. Una vez que asocie un entorno Dataverse con Customer Insights, tiene la opción de habilitar el intercambio de datos.
  Para más información, consulte [Administrar entornos](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]