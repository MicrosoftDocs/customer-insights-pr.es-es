---
title: Datos de Customer Insights en Microsoft Dataverse
description: Utilice entidades de Customer Insights como tablas en Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 220e01a06711a5d35b8df09e265017a6d8fd0490
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650063"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabajar con datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece la opción de hacer que las entidades de salida estén disponibles en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Esta integración permite compartir datos fácilmente y el desarrollo personalizado a través de un enfoque de código bajo / sin código. Las entidades de salida estarán disponibles como tablas en Dataverse. Estas tablas permiten escenarios como [flujos de trabajo automatizados a través de Power Automate](/power-automate/getting-started), [aplicaciones basadas en modelos](/powerapps/maker/model-driven-apps/) y [aplicaciones de lienzo](/powerapps/maker/canvas-apps/) mediante Power Apps. Puede utilizar los datos para cualquier otra aplicación basada en tablas de Dataverse. La implementación actual admite principalmente búsquedas en las que los datos de las entidades de información audiencia disponibles se pueden recuperar para un ID de cliente determinado.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Adjuntar un entorno de Dataverse a Customer Insights

**Organizaciones con entornos Dataverse existentes**

Organizaciones que ya usan Dataverse pueden [utilizar uno de sus entornos Dataverse existentes](get-started-paid.md) cuando un Administrador configura informaciones de público. Al proporcionar la URL al entorno Dataverse, se adjunta a su nuevo entorno de información de público. Para garantizar el mejor rendimiento posible, los entornos de Customer Insights y Dataverse deben estar alojados en la misma región.

Para adjuntar un entorno Dataverse, expanda **Ajustes avanzados** al crear el entorno de información de público. Proporcione la **URL de entorno de Microsoft Dataverse** y seleccione la casilla de verificación para **Habilitar el intercambio de datos**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Nueva organización**

Si crea una nueva organización al configurar Customer Insights, obtendrá automáticamente un entorno de Dataverse nuevo.

> [!NOTE]
> Si sus organizaciones ya utilizan Dataverse en su inquilino, es importante recordar que en [Dataverse la creación del entorno está controlada por un administrador](/power-platform/admin/control-environment-creation.md). Por ejemplo, si está configurando un nuevo entorno de información de público con su cuenta de organización y el administrador ha inhabilitado la creación de entornos Dataverse de prueba para todos, excepto los administradores, no puede crear un nuevo entorno de prueba.
> 
> Los entornos de prueba de Dataverse creados en Customer Insights tienen 3 GB de almacenamiento que no contarán para la capacidad general que tiene derecho al inquilino. Las suscripciones de pago de Dataverse obtienen derecho a 15 GB para la base de datos y 20 GB para el almacenamiento de archivos.

## <a name="output-entities"></a>Entidades de salida

Algunas entidades de salida de información de público están disponibles como tablas en Dataverse. Las secciones siguientes describen el esquema esperado de estas tablas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecimiento](#enrichment)
- [Predicción](#prediction)


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
