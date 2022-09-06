---
title: Ejemplos de consultas de OData para las API de Customer Insights
description: Ejemplos de uso común de Open Data Protocol (OData) para consultar las API de Customer Insights para revisar datos.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387223"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Ejemplos de consultas de OData para las API de Customer Insights

El Protocolo de datos abiertos (OData) es un protocolo de acceso a datos basado en protocolos centrales como HTTP. Utiliza metodologías comúnmente aceptadas como REST para la web. Hay varios tipos de bibliotecas y herramientas que se pueden usar para consumir servicios OData.

Para ayudarle a crear sus propias implementaciones basadas en la [API de Customer Insights](apis.md), revise algunas consultas de ejemplo que suelen preguntarse.

Modifique los ejemplos de consulta para que funcionen en los entornos de destino:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` donde {instanceId} es el GUID del entorno de Customer Insights que desea consultar. La [operación ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) permite encontrar el {InstanceId} al que tiene acceso.
- {CID}: GUID de un registro de cliente unificado. Ejemplo: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identificador de la clave primaria de un registro de cliente en un origen de datos. Ejemplo: `CNTID_1002`
- {DSname}: Cadena con el nombre de entidad de un origen de datos que se transfiere a Customer Insights. Ejemplo: `Website_contacts`.
- {SegmentName}: Cadena con el nombre de la entidad de salida de un segmento en Customer Insights. Ejemplo: `Male_under_40`.

## <a name="customer"></a>Customer

Ejemplos de consultas para la entidad *Customer*.

|Tipo de consulta |Ejemplo  | Nota  |
|---------|---------|---------|
|Id. de cliente único     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Clave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Las claves alternativas persisten en la entidad de cliente unificada       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|En    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Clave alternativa + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Buscar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Devuelve los 10 mejores resultados para una cadena de búsqueda      |
|Suscripción de segmento  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Devuelve un número predeterminado de filas de la entidad de segmentación.      |
|Pertenencia al segmento para un cliente | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Devuelve el perfil del cliente si es miembro del segmento dado     |

## <a name="unified-activity"></a>Actividad unificada

Ejemplos de consultas para la entidad *UnifiedActivity*.

|Tipo de consulta |Ejemplo  | Nota  |
|---------|---------|---------|
|Actividad de CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Enumera las actividades de un perfil de cliente específico |
|Plazo de tiempo de la actividad    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Actividades de un perfil de cliente en un período de tiempo       |
|Tipo actividad    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Actividad por nombre para mostrar     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Ordenación de actividades    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordenar actividades en orden ascendente o descendente       |
|Actividad ampliada de la pertenencia al segmento  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Otros ejemplos

Ejemplos de consultas para otras entidades.

|Tipo de consulta |Ejemplo  | Nota  |
|---------|---------|---------|
|Medidas de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marcas enriquecidas de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Intereses enriquecidos de CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Cláusula In + Expandir     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Consultas OData no admitidas

Las siguientes consultas no se admiten en Customer Insights:

- `$filter` en las entidades de origen ingeridas. Solo puede ejecutar las consultas de $filter en las entidades del sistema que Customer Insights crea.
- `$expand` de una consulta `$search`. Ejemplo: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` de `$select` si solo se ha seleccionado un subconjunto de atributos. Ejemplo: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- Marca enriquecida de `$expand` o afinidades de un interés para un cliente determinado. Ejemplo: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Consulte las entidades de salida del modelo de predicción a través de la clave alternativa. Ejemplo: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
