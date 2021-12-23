---
title: Características nuevas y mejoradas
description: Información sobre nuevas funciones, mejoras y correcciones de errores.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 346ef93e8471580b782618550ca4eb71b3f3c921
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884283"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novedades de la capacidad de informaciones de público de Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

¡Estamos entusiasmados de anunciar nuestras actualizaciones más recientes! Este artículo resume las características de vista previa pública, las mejoras de disponibilidad general y las actualizaciones de características. Para ver los planes de características a largo plazo, eche un vistazo a los [planes de lanzamiento de Dynamics 365 y Power Platform](/dynamics365/release-plans/).

Implementamos actualizaciones región por región. Por tanto, algunas regiones pueden tener las características antes que otras. A menos que se especifique lo contrario, no es necesario que realice ninguna acción y actualizaremos la aplicación automáticamente sin tiempo de inactividad.

> [!TIP]
> Para enviar y votar en solicitudes de características y sugerencias de productos, vaya a [Portal de ideas de aplicaciones de Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2021-updates"></a>Actualizaciones de noviembre de 2021

Las actualizaciones de noviembre de 2021 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="segment-membership-now-available-in-dataverse"></a>Membresía de segmento ahora disponible en Dataverse

La información de membresía de segmento para perfiles de clientes ahora está disponible en Dataverse junto con los perfiles y conocimientos de los clientes. Las aplicaciones de acción de Dynamics 365 y las aplicaciones basadas en modelos pueden usar estos datos para buscar detalles de membresía de segmento para un cliente determinado.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Las actividades admiten detalles a nivel de contacto para cuentas comerciales

Ahora puede configurar, mostrar y filtrar actividades para contactos en los cronogramas de actividad de su cuenta comercial para comprender mejor qué contactos de la cuenta participaron en actividades específicas.

## <a name="october-2021-updates"></a>Actualizaciones de octubre de 2021

Las actualizaciones de octubre de 2021 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="b-to-b"></a>B-to-B

A partir de octubre de 2021, puede trabajar con cuentas comerciales y sus contactos relacionados en Customer Insights. Antes, la aplicación se adaptaba principalmente a consumidores individuales. Se actualizaron varias áreas de funciones para admitir escenarios B-to-B además de un nuevo tipo de entorno. Para obtener una descripción general de las funciones B-to-B compatibles, consulte [Trabajar con cuentas comerciales en audiencia insights](work-with-business-accounts.md).

Las siguientes secciones destacan algunas de las áreas clave que se adaptaron para respaldar las cuentas comerciales y los consumidores individuales.

#### <a name="export-segments-based-on-business-accounts"></a>Exportar segmentos basados en cuentas comerciales

Todas las exportaciones de segmentos en audiencia insights están disponibles en el contexto de las cuentas comerciales. La mayoría de las exportaciones de segmentos requieren configuración adicional e [información de contacto proyectada](segment-builder.md#create-a-new-segment) en los segmentos subyacentes para que sean válidas para las cuentas de negocio. Para obtener más información, consulte [Exportar segmentos](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Utilice la exportación de anuncios de LinkedIn con cuentas comerciales

La exportación de anuncios de LinkedIn ahora está disponible para la segmentación de contactos y empresas en el contexto de cuentas comerciales. Al seleccionar la orientación de la empresa como su enfoque principal de la exportación de LinkedIn, puede exportar segmentos creados en cuentas comerciales sin la necesidad de proyectar la información de contacto. Para obtener más información, consulte la documentación sobre [Exportación de anuncios de LinkedIn](export-linkedin-ads.md) y la diferencia entre [segmentación de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) y [segmentación de la empresa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Crear medidas basadas en cuentas comerciales y su jerarquía

El generador de medidas le permite crear medidas en torno a cuentas comerciales y, opcionalmente, utilizar la información de jerarquía. La información de jerarquía se utiliza para acumular un cálculo de medida en una cuenta y todas sus subcuentas relacionadas. Por ejemplo, puede crear medidas como los ingresos totales para cada grupo de cuentas comerciales identificadas por su jerarquía. Para obtener más información, consulte [Definir y administrar medidas](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Crear segmentos basados en cuentas comerciales y su jerarquía

El generador de segmentos le permite crear segmentos de cuentas comerciales que opcionalmente incluyen información de contacto para cada cuenta en un segmento. Si ha configurado la jerarquía de cuentas, puede utilizar la información de la jerarquía de cuentas en la creación de segmentos. Para obtener más información, consulte [Crear un nuevo segmento](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Conserve sus cuentas comerciales con conocimientos profundos sobre su tendencia a la deserción

El modelo de abandono de clientes predicción ahora también admite cuentas comerciales. Puede evaluar el riesgo de abandono no solo para una cuenta, sino también para una combinación de una cuenta y una categoría de producto o servicio que le compren. Esta adición le ayuda a comprender si es más probable que una cuenta deje de comprarle en general o solo para una determinada categoría de bienes o servicios. Para ayudarlo aún más a usar este modelo de inteligencia artificial, también enumera las razones por las que es probable que una cuenta se pierda. Para más información, vea [Cancelación de transacciones predicción (vista previa)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Ver los contactos de una cuenta comercial en la vista Cliente

Si las cuentas comerciales están asignadas a cuentas relacionadas, la aplicación Customer Insights muestra estos contactos relacionados como parte de la vista de detalles del cliente. Para obtener más información, consulte [Perfiles de cliente](customer-profiles.md).


## <a name="september-2021-updates"></a>Actualizaciones de septiembre de 2021

Las actualizaciones de septiembre de 2021 incluyen nuevas funciones, mejoras de rendimiento y correcciones de errores.

### <a name="activities"></a>Actividades

- **Mejoras de la escala de tiempo de actividad** Hemos ampliado los filtros para la escala de tiempo de actividad en los perfiles de clientes. Además, puede utilizar el nuevo panel de filtro para filtrar por tipo de actividad y por fecha. Las fechas se pueden filtrar usando diferentes condiciones. Para más información, vea [Ver escala de tiempo de actividad en perfiles de clientes](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relaciones

- **Compatibilidad con relaciones de múltiples saltos** Utilice relaciones de múltiples saltos al configurar actividades y definir relaciones entre entidades. Las relaciones de múltiples saltos usan una entidad intermedia para conectar dos entidades. Al configurar una actividad, puede utilizar una relación de múltiples saltos para conectar su entidad de actividad a una entidad intermedia y luego a una entidad de cliente. Puede combinar relaciones de múltiples saltos con relaciones de múltiples rutas. Para más información, vea [Relaciones de múltiples saltos](relationships.md#multi-hop-relationship).

- **Compatibilidad con relaciones de múltiples rutas** Utilice relaciones de múltiples rutas al configurar actividades y definir relaciones entre entidades. Las relaciones de múltiples rutas relacionan una entidad de origen con más de una entidad. Al configurar una actividad, puede utilizar una relación de múltiples rutas para conectar su entidad de actividad a varias entidades de cliente. Puede combinar relaciones de múltiples rutas con relaciones de múltiples saltos. Para más información, vea [Relaciones de múltiples rutas](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Actualizaciones de agosto de 2021

Las actualizaciones de julio y agosto de 2021 incluyen una nueva característica, mejoras de rendimiento y correcciones de errores.

### <a name="extensibility"></a>Extensibilidad

- **Exportar segmentos a Klaviyo**: hemos ampliado nuestros [destinos de exportación para incluir Klaviyo](export-klaviyo.md). Ahora puede exportar segmentos para crear campañas, realizar marketing por correo electrónico y usar grupos concretos de clientes con Klaviyo. 


## <a name="june-2021-updates"></a>Actualizaciones de junio de 2021

Las actualizaciones de junio de 2021 incluyen diversas características, mejoras de rendimiento y correcciones de errores.

### <a name="data-ingestion"></a>Ingesta de datos

- **Actualizaciones mejoradas del progreso de unificación de datos**: ahora puede ver actualizaciones de estado dinámicas mejores y más detalladas en los pasos del [proceso de unificación de datos](data-unification.md). Esta característica permite realizar un seguimiento del progreso detallado para comprender el flujo del proceso y tomar medidas en caso de que algún paso requiera atención.

### <a name="extensibility"></a>Extensibilidad

- **Exportar segmentos y otros datos a Salesforce Marketing Cloud**: hemos ampliado nuestros destinos de exportación para incluir [Salesforce Marketing Cloud](export-salesforce.md). Ahora puede exportar segmentos y otros tipos de datos a Salesforce Marketing Cloud a través de una exportación SFTP de marca. La importación de datos puede automatizarse completamente en Salesforce y usarse para crear campañas de marketing más efectivas.  
 
- **Exportar segmentos a ActiveCampaign**: hemos ampliado nuestros destinos de exportación para incluir [ActiveCampaign](export-active-campaign.md). Ahora puede exportar segmentos creados en Customer Insights para generar campañas, ejecutar marketing por correo electrónico y aprovechar grupos concretos de clientes con ActiveCampaign.
 
- **Exportar segmentos a Sendinblue**: hemos ampliado nuestros destinos de exportación para incluir [Sendinblue](export-sendinblue.md). Ahora puede exportar segmentos creados en Customer Insights para generar campañas, ejecutar marketing por correo electrónico y aprovechar grupos concretos de clientes con Sendinblue.
 
### <a name="ux-updates"></a>Actualizaciones de la experiencia del usuario 

- **Página Clientes nueva y mejorada y página de detalles del perfil**: hemos rediseñado la página Clientes y las páginas de detalles del perfil para mejorar la experiencia del usuario y el rendimiento. Estos cambios permiten ver, ordenar, buscar y filtrar clientes. Ahora los filtros ahora se representan en la URL para compartir los resultados de la búsqueda con otros usuarios sin problemas. Los resultados de la búsqueda también se pueden guardar como un segmento.    
  Para mejorar la legibilidad, ahora la página de detalles de los perfiles de los clientes agrupa los datos en varias subsecciones, como datos demográficos, identificadores y otros atributos de perfil. Otras secciones de la página de detalles del perfil son más interactivas ahora. Por ejemplo, la sección de actividades ahora permite filtrar y ordenar.


## <a name="may-2021-updates"></a>Actualizaciones de mayo de 2021

Las actualizaciones de mayo de 2021 incluyen varias funciones, mejoras de rendimiento y correcciones de errores.

### <a name="data-ingestion"></a>Ingesta de datos

- **Ver o modificar metadatos o definición de entidad al adjuntar datos de su Azure Data Lake Storage** Ahora puede ver y editar metadatos o definición de entidad en información de público al adjuntar datos de una carpeta de Common Data Model en su Azure Data Lake Storage. Esta capacidad proporciona retroalimentación en tiempo real, validación de modelos y verificación de errores. Le permite editar model.json y manifest.json sin problemas.

### <a name="extensibility"></a>Extensibilidad

- **Exportaciones de segmentos mejoradas, programación personalizada y duplicación** Ahora puede [ver todas las exportaciones de un segmento específico](export-destinations.md#view-exports-and-export-details) en una lista. Esta nueva vista ayuda a administrar cómo se usa un segmento específico y adaptar las exportaciones existentes o crear nuevas.    
  Usted puede [definir programas de actualización personalizados](export-destinations.md#schedule-and-run-exports) para exportaciones individuales o varias exportaciones a la vez. Hasta ahora, todas las exportaciones se ejecutaban con cada actualización del sistema.    
  En lugar de crear una nueva exportación desde cero, puede comenzar basándose en una existente para ahorrar algo de tiempo.

- **Exportar segmentos a Microsoft Advertising** Hemos ampliado nuestros destinos de exportación para incluir Microsoft Advertising. Cree públicos de coincidencia personalizada en Microsoft Advertising con sus datos de perfil de cliente unificados y use los públicos para sus campañas de publicidad. Para más información, vea [Exportar segmentos a Microsoft Advertising](export-microsoft-advertising.md).

- **Exportar segmentos a anuncios de LinkedIn** Hemos ampliado nuestros destinos de exportación para incluir anuncios de LinkedIn y permitirle desbloquear la segmentación de contactos y la segmentación de empresas a través de LinkedIn exportando los datos unificados de su perfil de cliente. Para más información, vea [Exportar segmentos a LinkedIn Ads](export-linkedin-ads.md).


- **Exportar segmentos a Omnisend** Hemos ampliado nuestros destinos de exportación para incluir Omnisend. Use los segmentos creados en información de público para generar campañas, ofrecer marketing por correo electrónico y aprovechar grupos específicos de clientes con Omnisend. Para más información, vea [Exportar segmentos a Omnisend](export-omnisend.md)

### <a name="predictions"></a>Predicciones

- **Informe de usabilidad de datos de entrada** El informe de usabilidad de datos de entrada proporciona una vista consolidada de los errores y advertencias que pueden estar generando sus predicciones listas para usar. También ofrece recomendaciones sobre cómo mejorar el rendimiento del modelo.    
  El informe está disponible después de que un modelo haya completado su proceso de formación. Se crea para cada modelo por separado, independientemente de si se completó correctamente o no.
  Actualmente, esta función solo está disponible para el modelo Transaction Churn. Para obtener más información, consulte [Informe de usabilidad de datos de entrada](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relaciones

- **Visualizador de relaciones** La vista del visualizador de relaciones le permite ver todos los Relaciones existentes entre las entidades y su cardinalidad. Relaciones ahora están organizadas en grupos: creado por el usuario, sistema y relaciones heredadas. También puede exportar una vista como imagen. Para obtener más información, consulte el tema sobre [Ver relaciones](relationships.md#view-relationships). 

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

- **Exportar segmentos a RollWorks**. Hemos ampliado nuestros destinos de exportación para incluir RollWorks. Ahora puede exportar segmentos de Customer Insights a los públicos de RollWorks y utilizarlos como referencia para su publicidad B2B.    
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

  Los administradores pueden copiar configuraciones de entorno a un nuevo entorno en la misma organización. Esta característica amplía la funcionalidad del entorno de copia para los casos en los que se usan orígenes de datos basados en un lago de datos administrado por Microsoft Dataverse o una carpeta de Common Data Model.

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