---
title: Datos de Customer Insights en Microsoft Dataverse
description: Utilice entidades de Customer Insights como tablas en Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547647"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabajar con datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece la opción de hacer que las entidades de salida estén disponibles en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integración permite compartir datos fácilmente y el desarrollo personalizado a través de un enfoque de código bajo / sin código. Las [entidades de salida](#output-entities) están disponibles como tablas en un entorno de Dataverse. Puede usar los datos para cualquier otra aplicación basada en tablas de Dataverse. Estas tablas permiten escenarios como flujos de trabajo automatizados a través de Power Automate o crear aplicaciones con Power Apps. La implementación actual admite principalmente búsquedas en las que se pueden obtener datos de las entidades de Customer Insights disponibles para un id. de cliente determinado.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Adjuntar un entorno de Dataverse a Customer Insights

**Organización existente**

Los administradores pueden configurar Customer Insights para [utilizar un entorno de Dataverse existente](create-environment.md) cuando crean un entorno de Customer Insights. Al proporcionar la URL al entorno Dataverse, se adjunta a su nuevo entorno de información de público. Los entornos de Customer Insights y Dataverse deben estar alojados en la misma región. 

Si no desea utilizar un entorno de Dataverse existente, el sistema crea un nuevo entorno para los datos de Customer Insights en su inquilino. 

> [!NOTE]
> Si sus organizaciones ya utilizan Dataverse en su inquilino, es importante recordar que en [Dataverse la creación del entorno está controlada por un administrador](/power-platform/admin/control-environment-creation). Por ejemplo, si está configurando un nuevo entorno de información de público con su cuenta de organización y el administrador ha inhabilitado la creación de entornos Dataverse de prueba para todos, excepto los administradores, no puede crear un nuevo entorno de prueba.
> 
> Los entornos de prueba de Dataverse creados en Customer Insights tienen 3 GB de almacenamiento que no contarán para la capacidad general que tiene derecho al inquilino. Las suscripciones de pago de Dataverse obtienen derecho a 15 GB para la base de datos y 20 GB para el almacenamiento de archivos.

**Nueva organización**

Si crea una nueva organización al configurar Customer Insights, el sistema crea automáticamente un nuevo entorno de Dataverse en su organización para usted.

## <a name="output-entities"></a>Entidades de salida

Algunas entidades de salida de información de público están disponibles como tablas en Dataverse. Las secciones siguientes describen el esquema esperado de estas tablas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecimiento](#enrichment)
- [Predicción](#prediction)
- [Suscripción de segmento](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Esta tabla contiene el perfil de cliente unificado de Customer Insights. El esquema para un perfil de cliente unificado depende de las entidades y atributos utilizados en el proceso de fusión. Un esquema de perfil de cliente generalmente contiene un subconjunto de los atributos de la [Definición de Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La tabla AlternateKey contiene claves de las entidades que participaron en el proceso de unificación.

|Column  |Tipo  |Descripción  |
|---------|---------|---------|
|DataSourceName    |String         | Nombre del origen de datos. Por ejemplo: `datasource5`        |
|EntityName        | String        | Nombre de entidad en información de público. Por ejemplo: `contact1`        |
|AlternateValue    |String         |Id. alternativo que se asigna al Id. de cliente. Ejemplo: `cntid_1078`         |
|KeyRing           | Texto de varias líneas        | Valor JSON  </br> Muestra: [{"dataSourceName":" datasource5 ",</br>"entityName": "contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Id. del perfil de cliente unificado.         |
|AlternateKeyId     | GUID         |  GUID determinista de AlternateKey basado en msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Ejemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta tabla contiene actividades de los usuarios que están disponibles en Customer Insights.

| Column            | Tipo        | Descripción                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Id. del perfil de cliente                                                                      |
| ActivityId        | String      | ID interno de la actividad del cliente (clave principal)                                       |
| SourceEntityName  | String      | Nombre de la entidad de origen                                                                |
| SourceActivityId  | String      | Clave principal de la entidad de origen                                                       |
| ActivityType      | String      | Tipo de actividad semántica o nombre de la actividad personalizada                                        |
| ActivityTimeStamp | DATETIME    | Marca de tiempo de actividad                                                                      |
| Puesto             | String      | Título o nombre de la actividad                                                               |
| Descripción       | String      | Descripción de actividad                                                                     |
| Dirección URL               | String      | Enlace a una URL externa específica de la actividad                                         |
| SemanticData      | Cadena JSON | Incluye una lista de pares clave-valor para campos de mapeo semántico específicos para el tipo de actividad |
| RangeIndex        | String      | Marca de tiempo Unix utilizada para ordenar la línea de tiempo de la actividad y las consultas de rango efectivo |
| mydynci_unifiedactivityid   | GUID | ID interno de la actividad del cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta tabla contiene los datos de salida de las medidas basadas en atributos del cliente.

| Column             | Tipo             | Descripción                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Id. del perfil de cliente        |
| Medidas           | Cadena JSON      | Incluye una lista de pares clave-valor para el nombre y los valores de la medida para el cliente dado | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Id. del perfil de cliente |


### <a name="enrichment"></a>Enriquecimiento

Esta tabla contiene el resultado del proceso de enriquecimiento.

| Column               | Tipo             |  Descripción                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Id. del perfil de cliente                                 |
| EnrichmentProvider   | String           | Nombre del proveedor del enriquecimiento                                  |
| EnrichmentType       | String           | Tipo de enriquecimiento                                      |
| Valores               | Cadena JSON      | Lista de atributos producidos por el proceso de enriquecimiento |
| msdynci_enrichmentid | GUID             | GUID determinista generado a partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicción

Esta tabla contiene el resultado de predicciones de modelo.

| Column               | Tipo        | Descripción                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Id. del perfil de cliente                                  |
| ModelProvider        | String      | Nombre del proveedor del modelo                                      |
| No                | String      | Nombre del modelo                                                |
| Valores               | Cadena JSON | Lista de atributos producidos por el modelo |
| msdynci_predictionid | GUID        | GUID determinista generado a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Suscripción de segmento

Esta tabla contiene información de suscripción de segmento de los perfiles de cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Id. del perfil de cliente        |
| SegmentProvider      | String       | Aplicación que publica los segmentos. Predeterminado: Información del público         |
| SegmentMembershipType | String       | Tipo de cliente en el registro de suscripción de este segmento. Admite varios tipos, como cliente, contacto o cuenta. Predeterminado: Cliente  |
| Segmentos       | Cadena JSON  | Lista de segmentos únicos de los que el perfil del cliente es miembro      |
| msdynci_identifier  | String   | Identificador único del registro de suscripción de segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista generado por `msdynci_identifier`          |
