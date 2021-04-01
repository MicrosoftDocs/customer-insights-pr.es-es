---
title: Características nuevas y mejoradas
description: Información sobre nuevas funciones, mejoras y correcciones de errores.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598509"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novedades de la capacidad de informaciones de público de Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

¡Estamos entusiasmados de anunciar nuestras actualizaciones más recientes! Este artículo resume las características de vista previa pública, las mejoras de disponibilidad general y las actualizaciones de características. Para ver los planes de características a largo plazo, eche un vistazo a los [planes de lanzamiento de Dynamics 365 y Power Platform](/dynamics365/release-plans/).

También puede ver el siguiente video para obtener más información sobre las capacidades planificadas durante los últimos seis meses.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Implementamos actualizaciones región por región. Por tanto, algunas regiones pueden tener las características antes que otras. A menos que se especifique lo contrario, no es necesario que realice ninguna acción y actualizaremos la aplicación automáticamente sin tiempo de inactividad.

> [!TIP]
> Para enviar y votar en solicitudes de características y sugerencias de productos, vaya a [Portal de ideas de aplicaciones de Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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


## <a name="december-2020-updates"></a>Actualizaciones de diciembre de 2020

Las actualizaciones de diciembre de 2020 incluyen varias funciones, mejoras de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-december-2020"></a>Funciones nuevas y actualizadas en diciembre de 2020

#### <a name="data-enrichment"></a>Enriquecimiento de datos

- **Enriquecimientos de afinidad de marca e intereses mejorados**
  
  Simplificamos nuestras puntuaciones de afinidad para que sean más fáciles de entender y usar. Ahora puede identificar rápidamente a los clientes según la afinidad que tengan con una marca o interés determinados.

  Además, hemos agregado nuevas opciones de configuración para controlar mejor cómo desea que se enriquezcan los perfiles de sus clientes. 

  Para más información, consulte [Enriquecer los perfiles de los clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md).

- **Controlar qué perfiles enriquecer**

  Ahora puede enriquecer solo un subconjunto de sus perfiles de clientes con la opción para seleccionar una entidad de segmento en lugar de la entidad de cliente predeterminada. Cree un segmento con los perfiles de clientes que le gustaría enriquecer y selecciónelo en la configuración de enriquecimiento para su conjunto de datos de clientes.
  Actualmente, esta función solo está disponible para los enriquecimientos proporcionados por Experian y HERE Technologies. Pronto habilitaremos esta funcionalidad para más enriquecimientos.

  Para más información, vea [Enriquecer los perfiles de los clientes con datos demográficos de Experian](enrichment-experian.md) o [Enriquecimiento de perfiles de clientes con HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Extensibilidad

- **Activar los segmentos a través de Autopilot**

  Exporte segmentos a Autopilot y utilícelos con fines de marketing. Para más información, consulte [Conector para Autopilot (versión preliminar)](export-autopilot.md).

- **Activar los segmentos a través de SendGrid**

  Exporte segmentos a SendGrid y utilícelos con fines de marketing. Para más información, consulte [Conector para SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Administración del sistema

- **Experiencia de gestión ambiental actualizada**
  
  Ahora puede crear, editar, eliminar y restablecer entornos directamente desde el selector de entornos en el encabezado de la aplicación. 
  
  Además, el entorno que está utilizando se anclará en la parte superior del panel de entorno para que ya no necesite buscarlo.

  Para más información, consulte [Administrar entornos](manage-environments.md).

## <a name="november-2020-updates"></a>Actualizaciones de noviembre de 2020

Las actualizaciones de noviembre de 2020 incluyen varias funciones, mejoras de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-november-2020"></a>Funciones nuevas y actualizadas en noviembre de 2020

#### <a name="data-enrichment"></a>Enriquecimiento de datos

- **Traiga sus propios datos de enriquecimiento a través de la importación personalizada del Protocolo de transferencia segura de archivos (SFTP)**
  
  La importación personalizada de SFTP le permite importar datos de enriquecimiento que no tienen que pasar por el proceso de unificación de datos. Más información acerca de la importación personalizada SFTP.

  Para más información, consulte [Enriquecer los perfiles de los clientes con datos personalizados (versión preliminar)](enrichment-SFTP-custom-import.md).
 
- **Enriquecer los datos de sus clientes con datos de ubicación de HERE Technologies**

  Con los servicios de enriquecimiento de datos de HERE Technologies, puede construir una comprensión más precisa de la ubicación de sus clientes con normalización de direcciones, extracción de latitud y longitud, etc. Más información sobre el enriquecimiento con HERE Technologies.

  Para más información, consulte [Enriquecer los perfiles de los clientes con HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unificación de datos

- **Flexibilidad para habilitar la creación de perfiles de datos en entidades y campos seleccionados de su cuenta de almacenamiento**

  Puede indicar en qué entidades de datos y campos de una carpeta de Common Data Model su cuenta de almacenamiento de Azure Data Lake desea habilitar la creación de perfiles de datos como parte del proceso de ingesta de datos.

  Para más información, consulte [Conectarse a una carpeta de Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Extensibilidad

- **Activar los segmentos a través de Google Ads**

  Exporte segmentos desde las listas de público de y use estas listas para anunciar en Búsqueda de Google, la Red de visualización de Google, YouTube y Gmail. Obtenga más información sobre cómo activar sus segmentos a través de Google Ads.

  Para más información, consulte [Conector para Google Ads](export-google-ads.md).

- **Activar los segmentos a través de Marketo**

  Exporte segmentos a las audiencias de Marketo y utilice estas audiencias para la automatización de marketing. Obtenga más información sobre cómo activar sus segmentos a través de Marketo. 

  Para más información, consulte [Conector para Marketo](export-marketo.md).

- **Activar los segmentos a través de DotDigital**

  Exporte segmentos a DotDigital y utilícelos con fines de marketing. Obtenga más información sobre cómo activar sus segmentos a través de DotDigital. 

  Para más información, consulte [Conector para DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predicciones

- **Predecir abandono transaccional**

  La característica de predicción de abandono de transacciones le permite, sin la ayuda de un científico de datos, predecir la probabilidad de que un cliente deje de comprar productos o servicios.  Con la puntuación de predicción, puede combinar otra información sobre sus clientes, como el valor del cliente, para crear segmentos de alto riesgo de abandono o clientes de alto valor. Utilice este segmento para dirigirse directamente a los clientes a través de actividades de marketing, atención al cliente y otros escenarios para reducir el riesgo de abandono.
 
  Configure la definición de abandono como una ventana basada en el tiempo específica para su negocio y defina cuándo se considera que los clientes han abandonado. Por ejemplo, es posible que una tienda de comestibles desee considerar que un cliente ha abandonado si no ha comprado nada en los últimos 30 días.
 
  A medida que continúe creando la predicción, le guiaremos para saber cuáles son los datos necesarios y le permitiremos asignar datos sobre su negocio a los campos requeridos para predecir el abandono de los clientes. También puede establecer una programación para volver a entrenar el modelo en función de la nueva información de su sistema para adaptarse a las circunstancias comerciales cambiantes.
 
  Para más información, consulte [Predicción de abandono de transacciones (versión preliminar)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administración del sistema

- **Restablecer entorno**

  Restablezca todo en un entorno de una instancia seleccionada para comenzar de nuevo.

  Para más información, consulte [Restablecer un entorno existente](manage-environments.md#reset-an-existing-environment).


- **Conectarse a su cuenta de almacenamiento de Azure Data Lake mediante una entidad de servicio**

  Escriba la salida de datos y lea los datos de su cuenta de almacenamiento mediante una entidad de servicio de Azure. Las conexiones de cuentas de almacenamiento existentes pueden seguir usando la clave de cuenta. También ofrecen una opción de actualización para utilizar la entidad de servicio en el futuro. Las nuevas conexiones se basarán en el método de autenticación de la entidad de servicio para su cuenta de almacenamiento.

  Para más información, consulte [Conectarse a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure para informaciones de público](connect-service-principal.md).

## <a name="october-2020-updates"></a>Actualizaciones de octubre de 2020

Las actualizaciones de octubre de 2020 incluyen varias características, mejoras de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-october-2020"></a>Funciones nuevas y actualizadas en octubre de 2020

#### <a name="extensibility"></a>Extensibilidad

- **Exportar a Mailchimp**

Exporta segmentos a listas de audiencia existentes en Mailchimp para ofrecer una experiencia de correo electrónico personalizada para sus clientes.

Para más información, consulte [Conector para Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Enriquecimiento de datos

- **Desduplicar los registros de origen en una entidad Match**

Especifique las reglas de desduplicación en entidades utilizadas en el proceso de coincidencia para identificar registros duplicados. Combínelos en un registro y vincule todos los registros de origen a este registro combinado. Este registro desduplicado se utilizará después en el proceso de comparación entre entidades.

Para más información, consulte [Definir la deduplicación en una entidad coincidente](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administración del sistema

- **Orquestación: nueva opción de actualización en la fusión**

Hasta hoy, cuando ejecuta el proceso de fusión, el sistema ejecuta todos los procesos posteriores que dependen de la fusión y los procesos posteriores. Ahora puede verificar el resultado del proceso de fusión (la entidad cliente unificada) antes de usarlo en el procesamiento posterior, como segmentos o medidas.
En la página de fusión, ahora puede elegir ejecutar solo el paso de fusión y ejecutar solo este proceso. Para actualizar también todos los procesos posteriores, puede elegir ejecutar procesos de fusión y posteriores. 

## <a name="september-2020-updates"></a>Actualizaciones de septiembre de 2020

Las actualizaciones de septiembre de 2020 incluyen varias características, mejoras de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-september-2020"></a>Características nuevas y actualizadas en septiembre de 2020

#### <a name="activities"></a>Actividades

- **Predicción inteligente de semántica de atributos**

Esta nueva característica predice los tipos semánticos de atributos de entrada que se transmiten al proceso de unificación de datos. Utiliza modelos de aprendizaje automático que mejoran la precisión y ahorran tiempo.

#### <a name="enrichments"></a>Enriquecimientos

- **Enriquecimiento de datos demográficos de Experian**

El enriquecimiento de datos demográficos de Experian ahora está disponible en versión preliminar. Experian es un líder mundial en informes crediticios y servicios de marketing para consumidores y empresas. Con los [servicios de enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), puede desarrollar una comprensión más profunda de sus clientes enriqueciendo los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.

Para utilizar esta característica, debe tener una suscripción activa a Experian.

Para más información, vea [Enriquezca los perfiles de los clientes con datos demográficos de Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administración del sistema

- **Panel de detalles de la tarea**

El panel de detalles de la tarea le permite ver detalles sobre las tareas que ejecuta el sistema. Es una forma práctica de identificar problemas con la configuración y encontrar soluciones.
Revise los mensajes de error para ver cómo aborda los problemas potenciales.
 
- **Se ha agregado el procesamiento de información a más páginas**

Esta mejora agrega información sobre el estado de sus entidades en la página **Entidades** y **Clientes**.
 
Además, puede encontrar detalles sobre el progreso de los procesos, junto con los detalles de la tarea, en ambas páginas.

- **Mejoras en la página de estado del sistema**

Mejoramos la estructura de la tabla de detalles de estado en **Sistema** > **Estado** al revisar las exportaciones de datos.
 
Además, los errores en la columna **Detalles** ahora son más detallados y procesables. 
 
- **Cancelar revierte el trabajo al estado anterior**

Cuando cancela una tarea, por ejemplo, en el proceso de coincidencia, volverá a su último estado. Por ejemplo, si el proceso de coincidencia se completó ayer y lo cancela hoy, volverá al estado exitoso de ayer.


## <a name="august-2020-updates"></a>Actualizaciones de agosto de 2020

Las actualizaciones de agosto de 2020 de incluyen diversas características, mejoras de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-august-2020"></a>Características nuevas y actualizadas en agosto de 2020

#### <a name="data-unification"></a>Unificación de datos

- **Experiencia mejorada para la etapa de asignación durante la unificación de datos**

  La experiencia en la etapa de asignación en el proceso de unificación de datos le permite seleccionar entidades, atributos y definir la semántica de una manera más fluida.

  Los cambios son:
  
  - se requieren menos interacciones para agregar entidades y campos
  - capacidades de búsqueda mejoradas en la página de asignación
  - identificación visual y sencilla del tipo de campo sugerido

#### <a name="enrichment"></a>Enriquecimiento

- **Enriquecimiento de afinidades de interés disponible en más mercados**

  Estamos ampliando la disponibilidad del enriquecimiento de afinidades de interés a otros cinco mercados además de Estados Unidos: Canadá, Australia, Reino Unido, Francia y Alemania. Con esta extensión, puede enriquecer los datos de sus clientes con más intereses aplicables a estos mercados. También enriqueceremos los perfiles de sus clientes que se encuentran en estos mercados mediante el uso de datos de propiedad local de Microsoft Graph.
  Para más información, consulte [Enriquecer los perfiles de los clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Actualizaciones de julio de 2020

Las actualizaciones de julio de 2020 incluyen diversas características, mejoras de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-july-2020"></a>Características nuevas y actualizadas en julio de 2020

#### <a name="extensibility"></a>Extensibilidad

- **Desencadenador de Power Automate para el proceso de unificación completado**

  Hemos ampliado nuestros desencadenadores para Power Automate, lo que le permite crear una notificación o acción cuando se completa una actualización del proceso de unificación (mapa, coincidencia, fusión).    
  Para obtener más información, consulte [Conector de Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Enriquecimiento

- **Enriquecimiento de afinidades de marcas disponible en más mercados**

  Estamos ampliando la disponibilidad del enriquecimiento de afinidades de marcas a otros cinco mercados además de Estados Unidos: Canadá, Australia, Reino Unido, Francia y Alemania. Con esta extensión, puede enriquecer los datos de sus clientes con marcas locales en estos mercados. También enriqueceremos los perfiles de sus clientes que se encuentran en estos mercados mediante el uso de datos de propiedad local de Microsoft Graph.
  Para más información, consulte [Enriquecer los perfiles de los clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Actualizaciones de junio de 2020

Las actualizaciones de junio de 2020 incluyen diversas características, mejoras de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-june-2020"></a>Características nuevas y actualizadas en junio de 2020

#### <a name="enrichment"></a>Enriquecimiento

- **Enriquecimiento con datos de empresas de Leadspace**
  
  Defina campos en perfiles de clientes unificados que se utilizan para buscar datos de empresas relacionadas de Leadspace. Después de ejecutar el proceso de enriquecimiento, los perfiles B2B se enriquecen con más atributos, incluidos el tamaño de la empresa, la ubicación, el sector y mucho más.    
  Esta colaboración le permite mejorar la calidad de sus datos con aportaciones de servicios de terceros. Para utilizar este enriquecimiento, necesitará una licencia de Leadspace para acceder a los datos de empresas B2B. El sistema utilizará esa licencia para mantener sus datos enriquecidos continuamente.    
  Para más información, consulte [Enriquecimiento de perfiles de empresas con Leadspace](enrichment-leadspace.md).

- **Página del centro de enriquecimiento**

  Todo el enriquecimiento de datos disponible de proveedores de enriquecimiento propios y de terceros se configura en el mismo lugar. La configuración del enriquecimiento de datos es una experiencia perfecta que se gestiona desde un lugar común.    
  Para más información, consulte [Enriquecimiento de perfiles de clientes](enrichment-hub.md).

- **Enriquecimiento de afinidad de marca e interés por separado**

  Las afinidades de marcas e intereses ahora están disponibles como dos enriquecimientos independientes. Los enriquecimientos separados le brindan la flexibilidad de configurarlos y administrarlos individualmente, según los requisitos o necesidades de su negocio.    
  Para más información, consulte [Enriquecer los perfiles de los clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Extensibilidad

- **URL en las que se puede hacer clic para actividades unificadas en el complemento de tarjeta de cliente de Dynamics 365**

  Las actividades unificadas en el complemento de tarjeta de cliente ahora muestran URL clicables en las que se puede hacer clic si dichas URL se han definido durante la configuración de actividades.    
  Para obtener más información, consulte [Complemento de tarjeta de cliente](customer-card-add-in.md).

- **Afinidades de marca e intereses disponibles en el complemento de tarjeta de cliente de Dynamics 365**

  Un nuevo control en el complemento de tarjeta de cliente de Dynamics 365 le permite mostrar mejoras de marca e intereses en sus contactos en las aplicaciones de involucración del cliente en Dynamics 365.    
  Para obtener más información, consulte [Complemento de tarjeta de cliente](customer-card-add-in.md).

- **Más desencadenadores de Power Automate**

  Hemos ampliado nuestros desencadenadores para Power Automate y agregado los siguientes desencadenadores:
  - Reciba una notificación o realice una acción cuando se complete una actualización completa automatizada (fuentes de datos, unificación, segmentos, medidas, exportaciones)
  - Defina un umbral para una medida empresarial. Por ejemplo, puede crear una notificación que se envía cuando se supera el umbral definido. Además, el disparador trae información que le permite crear flujos de trabajo más complejos en Power Automate.    
  Para obtener más información, consulte [Conector de Power Automate](export-power-automate.md)

- **Exportar al administrador de anuncios de Facebook**
  
  Esta capacidad le permite exportar segmentos al Administrador de anuncios de Facebook. Los segmentos se exportan como audiencias personalizadas para usar perfiles de clientes unificados en campañas de marketing y anuncios de Facebook. Las audiencias personalizadas también se pueden utilizar para crear campañas en Instagram a través del administrador de anuncios de Facebook.    
  Para más información, consulte [Conector para el administrador de anuncios de Facebook](export-facebook.md).

#### <a name="predictions"></a>Predicciones

- **Cancelación de predicción de suscripción**

  Siga una experiencia guiada para crear predicciones de cancelación en áreas de suscripción como servicios en la nube, pertenencia de clientes y otros sectores. 

  La característica de predicción de cancelación de suscripción le permite predecir la probabilidad de que un cliente deje de utilizar productos o servicios basados en suscripción sin tratar con un científico de datos. Con la puntuación de predicción, puede combinar otra información sobre sus clientes para crear segmentos de alto riesgo de cancelación. Con la ayuda de este segmento, puede dirigirse directamente a los clientes en marketing, atención al cliente y otros escenarios para reducir el riesgo de abandono de clientes específicos para mejorar los ingresos y reducir los costos.

  Dentro de la experiencia, puede configurar la definición de cancelación como una ventana basada en el tiempo específica para su negocio. Por ejemplo, una empresa de transmisión de video que tiene un proceso de suscripción mensual puede querer plantearse que un cliente deje de estar interesado después de 15 días después del vencimiento de su suscripción.

  A medida que continúe con la predicción, le guiaremos a través de qué datos se necesitan y le permitiremos asignar datos sobre su negocio a los campos requeridos para predecir el abandono de sus clientes. A medida que cambia la información comercial, también puede establecer un cronograma para volver a entrenarse con nueva información de su sistema para adaptarse a las circunstancias comerciales cambiantes.    
  Para más información, consulte [Predicción de cancelación de suscripción (vista previa)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmentos

- **Buscar clientes similares**
  
  Encuentre clientes similares en su base de clientes utilizando inteligencia artificial. Un modelo de aprendizaje automático de clasificación binaria asigna una puntuación de similitud a los clientes del segmento expandido. La puntuación se basa en la similitud con los clientes del segmento de origen. Dependiendo de la puntuación de similitud, los perfiles de clientes se agregan a un segmento recién creado.

  A veces denominado modelado similar en marketing digital, utiliza un modelo de IA para ayudar a encontrar clientes que son similares a otro segmento de sus clientes al tener en cuenta más atributos. No solo le permite elegir los atributos, sino que también le permite especificar el número máximo de clientes que deberían estar en este nuevo segmento. El modelo de IA luego calculará las puntuaciones de similitud para cada cliente en función de sus atributos seleccionados y encontrará clientes con la puntuación de similitud promedio más alta. El segmento resultante incluirá clientes que se parecen al cliente en su segmento original.    
  Para más información, consulte [Clientes similares](find-similar-customer-segments.md).

- **Superposición de segmentos y diferenciadores**

  La superposición de segmentos le permite ver cuántos y qué clientes son comunes a dos o más segmentos. Por ejemplo, cómo un segmento de alto gasto se superpone con un segmento de clientes de alta satisfacción o cómo un segmento de clientes agitado se superpone con un segmento de clientes de baja satisfacción. Además, puede analizar cómo cambia la superposición en función de un atributo adicional de su elección.

  Los diferenciadores de segmento revelan lo que diferencia a un segmento del resto de sus clientes o de otro segmento. Todo lo que necesita hacer es identificar un segmento y el sistema identificará los atributos del perfil y las medidas que distinguen el segmento en forma de una lista clasificada de diferenciadores, desde el diferenciador más fuerte hasta el más débil.    
  Para obtener más información, consulte [Información detallada de segmentos (versión preliminar)](segment-insights.md).

- **Vida útil del segmento**
  
  Defina un horario para activar o desactivar un segmento.    
  Para más información, consulte [Administrar segmentos existentes](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Actualizaciones de mayo de 2020

Las actualizaciones de mayo de 2020 incluyen diversas características, actualizaciones de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-may-2020"></a>Características nuevas y actualizadas en mayo de 2020

#### <a name="data-ingestion"></a>Ingesta de datos

- **Ingesta de datos en tiempo real: vistas del historial**

  Al usar nuestra API para ingerir actualizaciones en tiempo real, puede ver hasta 30 días de historial agregado para estas actualizaciones. Tiene acceso a los agregados de todas las llamadas a API exitosas o fallidas, incluidos sus resultados, el sistema de origen y otros metadatos útiles.    
  Para más información, consulte [Ingesta de datos en tiempo real](real-time-data-ingestion.md).

- **Ingesta de datos en tiempo real: actualizaciones de perfil**

  Esta extensión de la ingesta de datos en tiempo real le permite ver, en segundos, cambios en campos específicos de perfil de usuario.    
  Además de la funcionalidad en tiempo real para las actividades, el sistema admite actualizaciones de baja latencia en los campos de perfil. Las actualizaciones en tiempo real para los campos de perfil tienen un tiempo de vencimiento y, por tanto, no reemplazan las actualizaciones programadas.    
  Para más información, consulte [Ingesta de datos en tiempo real](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Extensibilidad

- **Escala de tiempo y paginación actualizadas en el Complemento de tarjeta de cliente**

  La escala de tiempo de la solución de complemento de tarjeta de cliente coincide con la escala de tiempo de actividad. La paginación de la línea de tiempo mejoró, mostrando hasta 50 actividades a la vez. También permite cargar más actividades en la escala de tiempo.    
  Para obtener más información, consulte [Complemento de tarjeta de cliente](customer-card-add-in.md).

- Disparador de **Power Automate para cambios de segmento**

  Los disparadores para Power Automate definen de qué puede construir un flujo. El disparador recién agregado le permite definir un umbral para un segmento. Por ejemplo, puede crear una notificación que se envía cuando se supera el umbral definido.    
  Para obtener más información, vea [Conector de Power Automate](export-power-automate.md).

- **Soporte multiinquilino para modelos personalizados**

  Configure flujos de trabajo para modelos personalizados con un servicio web de un inquilino de Azure Machine Learning diferente. Puede iniciar sesión en el inquilino Aprendizaje automático de Azure al crear un nuevo flujo de trabajo para modelos personalizados. Esta capacidad es una adición a la capacidad existente de integración con su propio servicio web personalizado de Azure Machine Learning.    
  Para más información, ver [Modelos personalizados de aprendizaje automático](custom-models.md).

#### <a name="segments"></a>Segmentos

- **Automatización de ruta de entidad**

  Al crear un segmento, los usuarios deben definir la ruta de la entidad. Esta capacidad da un primer paso para automatizar la definición de ruta de entidad para que pueda centrarse en los criterios de segmentación que tenga pensados.    
  Si la entidad por la que desea segmentar a sus clientes está directamente relacionada con la entidad unificada del cliente, ya no necesitará definir la ruta de entidad. Sin embargo, si hay más de una ruta de entidad posible, aún debe definirla manualmente.

- **Acciones en múltiples segmentos**
  
  Los usuarios pueden seleccionar múltiples segmentos y realizar acciones en ellos, como actualizar los segmentos, con un solo clic.    

- **Actualizar segmentos**

  Los usuarios pueden actualizar un solo segmento o seleccionar solo los segmentos que desean actualizar.    

  
- **Mejoras a segmentos compuestos**

  Los usuarios pueden crear, editar y eliminar segmentos basados en otros segmentos. Por ejemplo, un segmento construido en otro segmento que se construyó en un tercer segmento.    

- **Página de lista de segmento**

  El nuevo diseño de la página de segmentos utiliza un formato de lista que le permite ver más segmentos a la vez. Se agrega un campo de búsqueda para buscar segmentos rápidamente. Los usuarios pueden ahora aplicar acciones como descargar o eliminar en múltiples segmentos a la vez. Se presenta una nueva experiencia de tendencia para identificar rápidamente cambios significativos en los segmentos.    
  Para obtener más información, vea [Crear y administrar segmentos](segments.md).

#### <a name="system-administration"></a>Administración del sistema

- **Customer Insights disponible en Microsoft Dynamics 365 Online Government**

  Con más y más canales para las interacciones, los datos de los ciudadanos se encuentran dispersos en una miríada de sistemas, lo que lleva a datos aislados y una vista fragmentada de la información sobre las interacciones de los ciudadanos. Sin una vista completa de las interacciones de cada ciudadano a través de los canales, es imposible que los gobiernos se modernicen a escala. Microsoft se compromete a apoyar las necesidades tecnológicas del gobierno para mantenerse a la altura de las expectativas de los ciudadanos de experiencias coherentes y dinámicas.    
  Con la oleada 1 de la versión 2020, Dynamics 365 Customer Insights estará disponible para Government Community Cloud (GCC), un entorno creado para satisfacer las mayores necesidades de cumplimiento de las agencias gubernamentales de Estados Unidos. Las agencias obtienen una vista unificada de los ciudadanos y utilizan inteligencia artificial prediseñada para obtener información que mejore las interacciones, capacite a los empleados y transforme las comunidades, al tiempo que reduce la complejidad de TI y respeta los estándares de cumplimiento y seguridad de los Estados Unidos. Dynamics 365 Government cumple los exigentes requisitos del Programa federal de administración de autorizaciones y riesgos (FedRAMP) de EE. UU., que permite a las agencias federales de los EE.UU. beneficiarse del ahorro de costos y la rigurosa seguridad de Microsoft Cloud.

## <a name="april-2020-updates"></a>Actualizaciones de abril de 2020

Las actualizaciones de abril de 2020 incluyen diversas características, actualizaciones de rendimiento y correcciones de errores.

### <a name="new-and-updated-features-in-april-2020"></a>Características nuevas y actualizadas en abril de 2020

#### <a name="activities"></a>Actividades

- **Asignar entidad de actividad al tipo de actividad estándar**
  
  La configuración y el almacenamiento de actividades se basan actualmente en un diseño estático para verlas en una línea de tiempo. El significado semántico de las actividades, que tiene potencial para múltiples casos de uso en modelos de IA, no se usa completamente en este momento. Planeamos hacer que la línea de tiempo de actividad sea más dinámica, según el tipo de actividad y una mejor comprensión semántica de las actividades. Esta característica tiene como objetivo identificar el tipo de actividad tal como se define en Common Data Model para cualquier actividad ingerida.
  Para obtener más información, consulte [Actividades del cliente](activities.md).

#### <a name="data-ingestion"></a>Ingesta de datos

- **Ingesta de datos en tiempo real: actividades**
  
  La ingestión de datos en tiempo real proporciona datos inmediatamente para su empleo, hasta que la actualización programada posterior extrae estos datos del origen de datos.    
  Para más información, consulte [Ingesta de datos en tiempo real](real-time-data-ingestion.md).

- **Mejoras en la preparación de datos**
  
  Obtenga más información sobre los datos ingeridos en una entidad. Con el resumen de datos, puede comprender las características de calidad de los datos que pueden ayudarle a tomar las medidas adecuadas.    
  Para obtener más información, consulte [Explorar datos de entidad](entities.md#exploring-a-specific-entitys-data).

- **Ingerir datos analíticos de Dynamics 365 con Common Data Service**
  
  Common Data Service está disponible como forma de crear orígenes de datos. Los clientes existentes de Dynamics 365 pueden ingerir entidades analíticas de Common Data Service a Customer Insights. Un solo origen de datos puede usar simultáneamente el mismo lago gestionado por Common Data Service en un entorno de Customer Insights.    
  Para más información, vea [Conectarse a datos en un data lake administrado por Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Extensibilidad

- **Exportar a LiveRamp**

  Active sus datos en LiveRamp® para conectarse a más de 500 plataformas en ecosistemas digitales, sociales y de televisión. Utilice sus datos en LiveRamp para orientar, suprimir y personalizar campañas publicitarias.    
  Para más información, consulte [Conector de LiveRamp&reg;](export-liveramp.md).

- **Complemento Teams de Customer Insights**
  
  El bot proporciona capacidades de búsqueda para perfiles de clientes unificados. Mostrará una tarjeta con hasta 15 campos del perfil de cliente resultante. Múltiples coincidencias devuelven una lista de resultados en la que puede seleccionar un perfil.    
  Para obtener más información, vea [Bot Teams para Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Medidas

- **Página de lista de medidas**
  
  Las mejoras en la página de medidas incluyen compatibilidad para acciones en una sola medida y en múltiples medidas a la vez. Además, encontrará un campo de búsqueda para buscar y seguir medidas rápidamente.    
  Para obtener más información, vea [Crear y administrar segmentos](segments.md).

- **Mejoras en medidas compuestas**
  
  Los usuarios pueden crear, editar y eliminar medidas basados en otras medidas. Por ejemplo, una medida construida en otra medida que se construyó en una tercera medida.

#### <a name="segments"></a>Segmentos

- **Otro operador**
  
  El operador In-set permite la segmentación para los clientes por varios valores de cadena posibles. Antes de agregar este operador, tenía que construir dichos segmentos con múltiples condiciones OR. El operador In-set le permite hacer eso con una sola condición.    
  Para obtener más información, vea [Crear y administrar segmentos](segments.md).

#### <a name="system-administration"></a>Administración del sistema

- **Copiar los ajustes de configuración a un nuevo entorno**
  
  Copie su configuración de un entorno a otro. Al crear un nuevo entorno, puede seleccionar un entorno existente desde el que desea copiar la configuración. Actualmente admitimos orígenes de datos, unificación de datos, relaciones, medidas y segmentos que se copiarán. Las credenciales origen de datos y los datos reales no se copian.    
  Para más información, consulte [Administrar entornos](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]