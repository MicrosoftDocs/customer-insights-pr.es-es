---
title: Auditoría de Dynamics 365 Customer Insights con Azure Monitor
description: Aprenda a enviar registros a Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354429"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Reenvío de registros en Dynamics 365 Customer Insights con Azure Monitor (versión preliminar)

Dynamics 365 Customer Insights proporciona una integración directa con Azure Monitor. Los registros de recursos de Azure Monitor le permiten supervisar y enviar registros a [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) o transmitirlos a [centros de eventos de Azure](https://azure.microsoft.com/services/event-hubs/).

Customer Insights envía los siguientes registros de eventos:

- **Eventos de auditoría**
  - **APIEvent** - permite el seguimiento de cambios realizado a través de la IU de Dynamics 365 Customer Insights.
- **Eventos operativos**
  - **WorkflowEvent** - El flujo de trabajo permite configurar [Fuentes de datos](data-sources.md), [unificar](data-unification.md) y [enriquecer](enrichment-hub.md) y finalmente [exportar](export-destinations.md) datos en otros sistemas. Todos esos pasos se pueden realizar individualmente (por ejemplo, desencadenar una sola exportación) u orquestados (por ejemplo, actualización de datos de fuentes de datos que desencadenan el proceso de unificación que generará enriquecimientos adicionales y, una vez hecho, exportar los datos a otro sistema). Para obtener más información, vea el [esquema WorkflowEvent](#workflow-event-schema)..
  - **APIEvent** - todas las llamadas API a la instancia del cliente para Dynamics 365 Customer Insights. Para obtener más información, vea el [esquema APIEvent](#api-event-schema)..

## <a name="set-up-the-diagnostic-settings"></a>Configurar los valores de diagnóstico

### <a name="prerequisites"></a>Requisitos previos

Para configurar diagnósticos en Customer Insights, se deben cumplir los siguientes requisitos previos:

- Debe disponer de una [suscripción activa de Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Tiene permisos de [administrador](permissions.md#administrator) en Customer Insights.
- Tiene el rol de **Colaborador** y **Administrador de acceso de usuario** en el recurso de destino en Azure. El recurso puede ser una cuenta de Azure Storage, un Centro de eventos de Azure o un área de trabajo de Azure Log Analytics. Para obtener más información, vea [Agregar o quitar asignaciones de roles de Azure mediante Azure Portal](/azure/role-based-access-control/role-assignments-portal).
- Los [requisitos de destino](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) para Azure Storage, Centro de eventos de Azure o Azure Log Analytics se cumplieron.
- Tiene al menos el rol **Lector** en el grupo de recursos al que pertenece el recurso.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurar diagnósticos con Azure Monitor

1. En Customer Insights, seleccione **Sistema** > **Diagnóstico** para ver los destinos de diagnóstico configurados en esta instancia.

1. Seleccione **Agregar destino**.

   > [!div class="mx-imgBorder"]
   > ![Conexión de diagnóstico](media/diagnostics-pane.png "Conexión de diagnóstico")

1. Proporcione un nombre en el campo **Nombre del destino de los diagnósticos**.

1. Elija el **Inquilino** de la suscripción de Azure con el recurso de destino y seleccione **Iniciar sesión**.

1. Seleccione el **Tipo de recurso** (Cuenta de almacenamiento, Centro de eventos o análisis de registros).

1. Seleccione la **Suscripción** para el recurso de destino.

1. Seleccione el **grupo de recursos** para el recurso de destino.

1. Seleccione el **recurso**.

1. Confirme la declaración de **Privacidad y cumplimiento de datos**.

1. Seleccione **Conectarse al sistema** para conectarse al recurso de destino. Los registros comienzan a aparecer en el destino después de 15 minutos, si la API está en uso y genera eventos.

### <a name="remove-a-destination"></a>Quitar un destino

1. Vaya a **Sistema** > **Diagnóstico**.

1. Seleccione el destino de diagnóstico en la lista.

1. En la columna **Acciones**, seleccion el icono **Eliminar**.

1. Confirme la eliminación para detener el reenvío de registros. El recurso de la suscripción de Azure no se eliminará. Puede seleccionar el enlace en la columna **Comportamiento** para abrir el portal de Azure para el recurso seleccionado y eliminarlo allí.

## <a name="log-categories-and-event-schemas"></a>Categorías de registro y esquemas de eventos

Actualmente, los [eventos de API](apis.md) y los eventos de flujo de trabajo son compatibles y se aplican las siguientes categorías y esquemas.
El esquema de registro sigue el [Esquema común de Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorías

Customer Insights proporciona dos categorías:

- **Eventos de auditoría**: [Eventos de API](#api-event-schema) para rastrear los cambios de configuración en el servicio. Las operaciones `POST|PUT|DELETE|PATCH` entran en esta categoría.
- **Eventos operativos**: [eventos de API](#api-event-schema) o [eventos de flujo de trabajo](#workflow-event-schema) generado durante el uso del servicio.  Por ejemplo, las solicitudes `GET` o los eventos de ejecución de un flujo de trabajo.

## <a name="configuration-on-the-destination-resource"></a>Configuración en el recurso de destino

Según su elección del tipo de recurso, se aplicarán automáticamente los siguientes pasos:

### <a name="storage-account"></a>Storage account

El director de servicio Customer Insights obtiene el permiso **Cuenta de almacenamiento colaborador** sobre el recurso seleccionado y crea dos contenedores bajo el espacio de nombres seleccionado:

- `insight-logs-audit` que contiene **eventos de auditoría**
- `insight-logs-operational` que contiene **eventos operativos**

### <a name="event-hub"></a>Centro de eventos

El director de servicio Customer Insights obtiene el permiso **Propietario de datos de centros de eventos de Azure** sobre el recurso seleccionado y creará dos centros de eventos bajo el espacio de nombres seleccionado:

- `insight-logs-audit` que contiene **eventos de auditoría**
- `insight-logs-operational` que contiene **eventos operativos**

### <a name="log-analytics"></a>Log Analytics

El director de servicio Customer Insights obtiene el permiso **Log Analytics colaborador** sobre el recurso. Los registros estarán disponibles en **Registros** > **Tablas** > **Gestión de registros** en el espacio de trabajo de Log Analytics seleccionado. Amplíe la solución **Gestión de registros** y localice las tablas `CIEventsAudit` y `CIEventsOperational`.

- `CIEventsAudit` que contiene **eventos de auditoría**
- `CIEventsOperational` que contiene **eventos operativos**

Bajo la ventana **Consultas**, expanda la solución **Auditoría** y localice las consultas de ejemplo proporcionadas al buscar `CIEvents`.

## <a name="event-schemas"></a>Esquemas de eventos

Los eventos de API y los eventos de flujo de trabajo tienen una estructura común y detalles en los que difieren, consulte [Esquema de eventos de API](#api-event-schema) o [esquema de eventos de flujo de trabajo](#workflow-event-schema).

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
| `identity`        | String    | Opcionales          | Objeto JSON que describe la identidad del usuario o la aplicación que realizó la operación.       | Vea la sección [Identidad](#identity-schema).     |  |
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
|                 |

#### <a name="workflow-properties-schema"></a>Esquema de propiedades de flujo de trabajo

Los eventos de flujo de trabajo tienen las siguientes propiedades.

| Campo              | Workflow | Task | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sí      | Sí  | Siempre `WorkflowEvent`, marcando el evento como evento de flujo de trabajo.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sí      | Sí  | Identificador de la ejecución del flujo de trabajo. Todos los eventos de flujo de trabajo y tareas dentro de la ejecución del flujo de trabajo tienen el mismo `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sí      | Sí  | Identificador de la operación, consulte [Tipos de operación].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Sí      | No   | Solo flujo de trabajo. Número de tareas que desencadena el flujo de trabajo.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sí      | No   | Opcional. Solo eventos de flujo de trabajo. [objectId del usuario](/azure/marketplace/find-tenant-object-id#find-user-object-id) de Azure Active Directory que activó el flujo de trabajo; consulte también `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sí      | No   | Actualización `full` o `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sí      | No   | `OnDemand` o `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sí      | No   | `Running` o  `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sí      | Sí  | Marca de hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sí      | Sí  | Marca de hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sí      | Sí  | Marca de hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sí      | Sí  | `instanceId` de Customer Insights                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Sí  | - Para OperationType = `Export`, el identificador es la guía de la configuración de exportación. <br> - Para OperationType = `Enrichment`, es la guía del enriquecimiento <br> - Para OperationType `Measures` y `Segmentation`, el identificador es el nombre de la entidad. |
| `properties.friendlyName`                    | No       | Sí  | Nombre fácil de usar de la exportación o la entidad que se procesa.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sí  | Opcional. Mensaje de error con más detalles.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sí  | Opcional. Para OperationType `Export` solo. Identifica el tipo de exportación. Para obtener más información, consulte [Descripción general de los destinos de exportación](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sí  | Opcional. Para OperationType `Export` solo. Contiene una lista de entidades configuradas en la exportación.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sí  | Opcional. Para OperationType `Export` solo. Mensaje detallado para la exportación.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sí  | Opcional. Para OperationType `Segmentation` solo. Indica el número total de miembros que tiene el segmento.                                                                                                                                                    |
