---
title: Exportar registros de diagnóstico (versión preliminar)
description: Aprenda a enviar registros a Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: c573c46fda895d36d29712e75fe28b261c9b399a
ms.sourcegitcommit: 0b5bfe0145dbd325fa518df4561d6a0a9a352264
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2022
ms.locfileid: "9352822"
---
# <a name="export-diagnostic-logs-preview"></a>Exportar registros de diagnóstico (versión preliminar)

Reenviar registros de Customer Insights con Azure Monitor. Los registros de recursos de Azure Monitor le permiten supervisar y enviar registros a [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) o transmitirlos a [centros de eventos de Azure](https://azure.microsoft.com/services/event-hubs/).

Customer Insights envía los siguientes registros de eventos:

- **Eventos de auditoría**
  - **APIEvent**: permite el seguimiento de cambios realizado a través de la IU de Dynamics 365 Customer Insights.
- **Eventos operativos**
  - **WorkflowEvent**: le permite configurar [orígenes de datos](data-sources.md), [unificar](data-unification.md), [enriquecer](enrichment-hub.md) y [exportar](export-destinations.md) datos en otros sistemas. Estos pasos se pueden realizar individualmente (por ejemplo, desencadenar una única exportación). También se puede ejecutar orquestado (por ejemplo, actualización de datos de orígenes de datos que activa el proceso de unificación, que generará enriquecimientos y, una vez hecho esto, exportará los datos a otro sistema). Para obtener más información, vea el [esquema WorkflowEvent](#workflow-event-schema)..
  - **APIEvent**: envía todas las llamadas API a la instancia del cliente para Dynamics 365 Customer Insights. Para obtener más información, vea el [esquema APIEvent](#api-event-schema)..

## <a name="set-up-the-diagnostic-settings"></a>Configurar los valores de diagnóstico

### <a name="prerequisites"></a>Requisitos previos

- Una [suscripción de Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) activa.
- Permisos de [administrador](permissions.md#admin) en Customer Insights.
- Un recurso válido en Azure que sigue los [requisitos de destino](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) para Azure Storage, Centro de eventos de Azure o Azure Log Analytics.
- Tiene el rol de [Colaborador y Administrador de acceso de usuario](/azure/role-based-access-control/role-assignments-portal) en el recurso de destino en Azure. El recurso puede ser una cuenta de Azure Data Lake Storage, un Centro de eventos de Azure o un área de trabajo de Azure Log Analytics. Este permiso es necesario al configurar los ajustes de diagnóstico en Customer Insights, pero se puede cambiar después de una instalación correcta.
- Al menos el rol **Lector** en el grupo de recursos al que pertenece el recurso.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurar diagnósticos con Azure Monitor

1. En Customer Insights, vaya a **Administración** > **Sistema** y seleccione la pestaña **Diagnósticos**.

1. Seleccione **Agregar destino**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Conexión de diagnóstico":::

1. Proporcione un nombre en el campo **Nombre del destino de los diagnósticos**.

1. Seleccione el **Tipo de recurso** (Cuenta de almacenamiento, Centro de eventos o análisis de registros).

1. Seleccione **Suscripción**, **grupo de recursos** y **Recurso** para el recurso de destino. Consulte [Configuración en el recurso de destino](#configuration-on-the-destination-resource) para obtener permisos e información de registro.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Conectarse al sistema** para conectarse al recurso de destino. Los registros comienzan a aparecer en el destino después de 15 minutos, si la API está en uso y genera eventos.

## <a name="configuration-on-the-destination-resource"></a>Configuración en el recurso de destino

Según su elección del tipo de recurso, se aplicarán automáticamente los siguientes cambios:

### <a name="storage-account"></a>Storage account

El director de servicio Customer Insights obtiene el permiso **Cuenta de almacenamiento colaborador** sobre el recurso seleccionado y crea dos contenedores bajo el espacio de nombres seleccionado:

- `insight-logs-audit` que contiene **eventos de auditoría**
- `insight-logs-operational` que contiene **eventos operativos**

### <a name="event-hub"></a>Centro de eventos

El director de servicio Customer Insights obtiene el permiso **Propietario de datos de centros de eventos de Azure** sobre el recurso seleccionado y crea dos centros de eventos bajo el espacio de nombres seleccionado:

- `insight-logs-audit` que contiene **eventos de auditoría**
- `insight-logs-operational` que contiene **eventos operativos**

### <a name="log-analytics"></a>Log Analytics

El director de servicio Customer Insights obtiene el permiso **Log Analytics colaborador** sobre el recurso. Los registros están disponibles en **Registros** > **Tablas** > **Gestión de registros** en el espacio de trabajo de Log Analytics seleccionado. Amplíe la solución **Gestión de registros** y localice las tablas `CIEventsAudit` y `CIEventsOperational`.

- `CIEventsAudit` que contiene **eventos de auditoría**
- `CIEventsOperational` que contiene **eventos operativos**

Bajo la ventana **Consultas**, expanda la solución **Auditoría** y localice las consultas de ejemplo proporcionadas al buscar `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Eliminar un destino de diagnóstico

1. Vaya a **Administración** > **Sistema** y seleccione la pestaña **Diagnósticos**.

1. Seleccione el destino de diagnóstico en la lista.

   > [!TIP]
   > Eliminar el destino detiene el reenvío de registros, pero no elimina el recurso en la suscripción de Azure. Para eliminar el recurso en Azure, seleccione el enlace en la columna **Comportamiento** para abrir el portal de Azure para el recurso seleccionado y eliminarlo allí. Después elimine el destino de diagnóstico.

1. En la columna **Acciones**, seleccion el icono **Eliminar**.

1. Confirme la eliminación para eliminar el destino y detener el reenvío de registros.

## <a name="log-categories-and-event-schemas"></a>Categorías de registro y esquemas de eventos

Actualmente, los [eventos de API](apis.md) y los eventos de flujo de trabajo son compatibles y se aplican las siguientes categorías y esquemas.
El esquema de registro sigue el [Esquema común de Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorías

Customer Insights proporciona dos categorías:

- **Eventos de auditoría**: [Eventos de API](#api-event-schema) para rastrear los cambios de configuración en el servicio. Las operaciones `POST|PUT|DELETE|PATCH` entran en esta categoría.
- **Eventos operativos**: [eventos de API](#api-event-schema) o [eventos de flujo de trabajo](#workflow-event-schema) generado durante el uso del servicio.  Por ejemplo, las solicitudes `GET` o los eventos de ejecución de un flujo de trabajo.

## <a name="event-schemas"></a>Esquemas de eventos

Los eventos de API y los eventos de flujo de trabajo tienen una estructura común, pero con algunas diferencias. Para obtener más información, consulte [esquema de eventos de API](#api-event-schema) o [esquema de eventos de flujo de trabajo](#workflow-event-schema).

### <a name="api-event-schema"></a>Esquema de eventos de API

| Campo             | DataType  | Obligatorio/Opcional | Description       | Ejemplo        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Marca de tiempo | Necesario          | Marca de tiempo del evento (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Necesario          | ResourceId de la instancia que emitió el evento         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Necesario          | Nombre de la operación representada por este evento.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Necesario          | Categoría de registro del evento. `Operational` o `Audit`. Todas las solicitudes POST/PUT/PATCH/DELETE HTTP están etiquetadas con `Audit`, todo lo demás con `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Necesario          | Estado del evento. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opcionales          | Estado del resultado del evento. Si la operación corresponde a una llamada API de REST, es el código de estado HTTP.        | `200`             |
| `durationMs`      | Largo      | Opcionales          | Duración de la operación en milisegundos.     | `133`     |
| `callerIpAddress` | String    | Opcionales          | Dirección IP de la persona que llama, si la operación corresponde a una llamada API que proviene de una dirección IP disponible públicamente.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opcionales          | Objeto JSON que describe la identidad del usuario o la aplicación que realizó la operación.       | Vea la sección [Identidad](#identity-schema).     |  
| `properties`      | String    | Opcionales          | Objeto JSON con más propiedades para la categoría particular de eventos.      | Vea la sección [Propiedades](#api-properties-schema).    |
| `level`           | String    | Necesario          | El nivel de gravedad del evento.    | `Informational`, `Warning`, `Error` o `Critical`.           |
| `uri`             | String    | Opcionales          | URI de solicitud absoluta.    |               |

#### <a name="identity-schema"></a>Esquema de identidad

El objeto JSON `identity` tiene la siguiente estructura

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Campo                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Rol asignado para el usuario o la aplicación. Para obtener más información, consulte [permisos de usuario](permissions.md).                                     |
| `Authorization.RequiredRoles` | Roles requeridos para realizar la operación. El rol `Admin` puede realizar todas las operaciones.                                                    |
| `Claims`                      | Reclamaciones del token web JSON (JWT) de usuario o aplicación. Las propiedades de las reclamaciones varían según la organización y la configuración Azure Active Directory. |

#### <a name="api-properties-schema"></a>Esquema de propiedades de la API

Los [eventos de API](apis.md) tienen las siguientes propiedades.

| Campo                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Siempre `ApiEvent`, marcando el evento de registro como evento de API.                                                                 |
| `properties.userAgent`       | Agente del navegador que envía la solicitud o `unknown`.                                                                        |
| `properties.method`          | Método HTTP : `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Ruta relativa de la solicitud.                                                                                          |
| `properties.origin`          | URI que indica de dónde proviene una búsqueda o `unknown`.                                                                  |
| `properties.operationStatus` | `Success` para el código de estado HTTP < 400 <br> `ClientError` para el código de estado HTTP < 500 <br> `Error` para el estado HTTP> = 500 |
| `properties.tenantId`        | Id. de organización                                                                                                        |
| `properties.tenantName`      | Nombre de la organización.                                                                                              |
| `properties.callerObjectId`  | ObjectId de Azure Active Directory de la persona que llama.                                                                         |
| `properties.instanceId`      | `instanceId` de Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Esquema de evento de flujo de trabajo

El flujo de trabajo contiene varios pasos. [Ingerir orígenes de datos](data-sources.md), [unificar](data-unification.md), [enriquecer](enrichment-hub.md) y [exportar](export-destinations.md) datos. Todos esos pasos pueden ejecutarse individualmente u orquestados con los siguientes procesos.

#### <a name="operation-types"></a>Tipos de operación

| OperationType     | Grupo                                     |
| ----------------- | ----------------------------------------- |
| Ingesta         | [Orígenes de datos](data-sources.md)           |
| DataPreparation   | [Orígenes de datos](data-sources.md)           |
| Asignar               | [Unificación de datos](data-unification.md)   |
| Coincidir             | [Unificación de datos](data-unification.md)   |
| Merge             | [Unificación de datos](data-unification.md)   |
| ProfileStore      | [Perfiles de clientes](customer-profiles.md) |
| Buscar            | [Perfiles de clientes](customer-profiles.md) |
| Actividad          | [Actividades](activities.md)                  |
| AttributeMeasures | [Segmentos y medidas](segments.md)      |
| EntityMeasures    | [Segmentos y medidas](segments.md)      |
| Medidas          | [Segmentos y medidas](segments.md)      |
| Segmentación      | [Segmentos y medidas](segments.md)      |
| Enriquecimiento        | [Enriquecimiento](enrichment-hub.md)                                          |
| Inteligencia      | [Predicciones](predictions-overview.md)                                          |
| AiBuilder         | [Predicciones](predictions-overview.md)                                          |
| Información          | [Predicciones](predictions-overview.md)                                          |
| Export            | [Exportaciones](export-destinations.md)                                          |
| ModelManagement   | [Predicciones](custom-models.md)                                           |
| Relationship      | [Unificación de datos](relationships.md)                                           |

#### <a name="field-description"></a>Descripción del campo

| Campo           | DataType  | Obligatorio/Opcional | Description                                                                                                                                                   | Ejemplo                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Marca de tiempo | Necesario          | Marca de tiempo del evento (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Necesario          | ResourceId de la instancia que emitió el evento.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Necesario          | Nombre de la operación representada por este evento. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Vea [Tipos de operación](#operation-types) para referencia. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Necesario          | Categoría de registro del evento. Siempre `Operational` para los eventos de flujo de trabajo                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Necesario          | Estado del evento. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Largo      | Opcionales          | Duración de la operación en milisegundos.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opcionales          | Objeto JSON con más propiedades para la categoría particular de eventos.                                                                                        | Vea la subsección [Propiedades del flujo de trabajo](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Necesario          | El nivel de gravedad del evento.                                                                                                                                  | `Informational`, `Warning` o `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Esquema de propiedades de flujo de trabajo

Los eventos de flujo de trabajo tienen las siguientes propiedades.

| Campo              | Workflow | Task | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sí      | Sí  | Siempre `WorkflowEvent`, marcando el evento como evento de flujo de trabajo.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sí      | Sí  | Identificador de la ejecución del flujo de trabajo. Todos los eventos de flujo de trabajo y tareas dentro de la ejecución del flujo de trabajo tienen el mismo `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sí      | Sí  | Identificador de la operación, consulte [Tipos de operación](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Sí      | No   | Solo flujo de trabajo. Número de tareas que desencadena el flujo de trabajo.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sí      | No   | Opcional. Solo eventos de flujo de trabajo. [objectId del usuario](/azure/marketplace/find-tenant-object-id#find-user-object-id) de Azure Active Directory que activó el flujo de trabajo; consulte también `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sí      | No   | Actualización `full` o `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sí      | No   | `OnDemand` o `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sí      | No   | `Running` o  `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sí      | Sí  | Marca de hora UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sí      | Sí  | Marca de hora UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sí      | Sí  | Marca de hora UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sí      | Sí  | `instanceId` de Customer Insights                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Sí  | - Para OperationType = `Export`, el identificador es la guía de la configuración de exportación. <br> - Para OperationType = `Enrichment`, es la guía del enriquecimiento <br> - Para OperationType `Measures` y `Segmentation`, el identificador es el nombre de la entidad. |
| `properties.friendlyName`                    | No       | Sí  | Nombre fácil de usar de la exportación o la entidad que se procesa.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sí  | Opcional. Mensaje de error con más detalles.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sí  | Opcional. Para OperationType `Export` solo. Identifica el tipo de exportación. Para obtener más información, consulte [Descripción general de los destinos de exportación](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sí  | Opcional. Para OperationType `Export` solo. Contiene una lista de entidades configuradas en la exportación.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sí  | Opcional. Para OperationType `Export` solo. Mensaje detallado para la exportación.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sí  | Opcional. Para OperationType `Segmentation` solo. Indica el número total de miembros que tiene el segmento.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
