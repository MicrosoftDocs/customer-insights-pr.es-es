---
title: Ejemplos de OData para las API de Dynamics 365 Customer Insights
description: Ejemplos de uso común de Open Data Protocol (OData) para consultar las API de Customer Insights para revisar datos.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740047"
---
# <a name="odata-query-examples"></a>Ejemplos de consulta de OData

El Protocolo de datos abiertos (OData) es un protocolo de acceso a datos basado en protocolos centrales como HTTP. Utiliza metodologías comúnmente aceptadas como REST para la web. Hay varios tipos de bibliotecas y herramientas que se pueden usar para consumir servicios OData.

Este artículo enumera algunas consultas de ejemplo solicitadas con frecuencia para ayudarlo a crear sus propias implementaciones basadas en las [API de Customer Insights](apis.md).

Debe modificar los ejemplos de consulta para que funcionen en los entornos de destino: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` donde {instanceId} es el GUID del entorno de Customer Insights que desea consultar. La [operación ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) permite encontrar el {InstanceId} al que tiene acceso.
- {CID}: GUID de un registro de cliente unificado. Ejemplo: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identificador de la clave primaria de un registro de cliente en un origen de datos. Ejemplo: `CNTID_1002`
- {DSname}: Cadena con el nombre de entidad de un origen de datos que se transfiere a Customer Insights. Ejemplo: `Website_contacts`.
- {SegmentName}: Cadena con el nombre de la entidad de salida de un segmento en Customer Insights. Ejemplo: `Male_under_40`.

## <a name="customer"></a>Customer

La siguiente tabla contiene un conjunto de consultas de muestra para la entidad *Cliente*.


|Tipo de consulta |Ejemplo  | Nota  |
|---------|---------|---------|
|Id. de cliente único     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Clave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Las claves alternativas persisten en la entidad de cliente unificada       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|En    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Clave alternativa + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Buscar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Devuelve los 10 mejores resultados para una cadena de búsqueda      |
|Suscripción de segmento  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Devuelve un número predeterminado de filas de la entidad de segmentación.      |

## <a name="unified-activity"></a>Actividad unificada

La siguiente tabla contiene un conjunto de consultas de muestra para la entidad *UnifiedActivity*.

|Tipo de consulta |Ejemplo  | Nota  |
|---------|---------|---------|
|Actividad de CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Enumera las actividades de un perfil de cliente específico |
|Plazo de tiempo de la actividad    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Actividades de un perfil de cliente en un período de tiempo       |
|Tipo actividad    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Actividad por nombre para mostrar     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Ordenación de actividades    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordenar actividades en orden ascendente o descendente       |
|Actividad ampliada de la pertenencia al segmento  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Otros ejemplos

La siguiente tabla contiene un conjunto de consultas de muestra para otras entidades.

|Tipo de consulta |Ejemplo  | Nota  |
|---------|---------|---------|
|Medidas de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marcas enriquecidas de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Intereses enriquecidos de CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Cláusula In + Expandir     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |