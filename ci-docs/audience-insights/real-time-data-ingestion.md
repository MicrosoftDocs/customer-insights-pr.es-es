---
title: Ingestión y limitaciones de datos en tiempo real
description: Información general sobre las capacidades en tiempo real en las informaciones de público.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270301"
---
# <a name="real-time-data-ingestion-preview"></a>Ingesta de datos en tiempo real (vista previa)

La funcionalidad casi en tiempo real le permite ver, en segundos, las últimas interacciones que sus clientes han realizado con sus productos o servicios.

Las [actualizaciones programadas](system.md#schedule-tab) incluyen una gran cantidad de registros y varias operaciones complejas. Primero, los datos se extraen del origen de datos. A continuación, los datos se unifican y luego se enriquecen con información adicional. Cada ejecución de este proceso puede llevar de minutos a horas.

La funcionalidad en tiempo real proporciona datos inmediatamente para su empleo, hasta que la actualización programada posterior extrae estos datos del origen de datos.

Las actualizaciones en tiempo real tienen un tiempo de caducidad después del cual ya no anulan el valor de origen de datos:

- Las actualizaciones de perfil se mantendrán durante 4 horas.
- Las actividades se mantendrán durante 30 días.

Estos valores son parámetros de llamada de API que puede cambiar. Su objetivo es garantizar que sus datos de origen sigan siendo su fuente de verdad. Si desea que las actualizaciones en tiempo real se incluyan durante más tiempo, debe agregarlas a un origen de datos para que se extraigan durante la próxima actualización programada.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Actualización en tiempo real de los campos unificados del perfil del cliente

Los perfiles actualizados se mostrarán en la vista de la tarjeta del cliente, o en cualquier otra visualización, en unos segundos.

Debido a que las operaciones en tiempo real tienen lugar después de la unificación de datos, solo se aplican a los perfiles de clientes unificados. En consecuencia, los cambios de perfil en tiempo real no actualizarán medidas, la pertenencia de segmentos o los enriquecimientos.

### <a name="limitations"></a>Limitaciones

- Los perfiles de clientes pueden actualizarse, pero no crearse ni eliminarse.
- Exportar actualizaciones en tiempo real a sistemas externos, como Power BI, no es posible por el momento.

## <a name="real-time-creation-of-activities"></a>Creación de actividades en tiempo real

La API en tiempo real le permite publicar una nueva actividad desde su sistema de origen (un registro de origen individual) en un perfil de cliente unificado. La nueva actividad estará disponible como una actividad unificada en la línea de tiempo de ese perfil de cliente unificado en cuestión de segundos. Puede ver la línea de tiempo en la vista de la tarjeta del cliente o cualquier otra integración de línea de tiempo que haya configurado.

> [!NOTE]
>
> - Las actividades son inmutables. No cambian una vez que se crean.
> - Actualmente, los segmentos y las medidas no se actualizan en función de la nueva actividad.
> - Las actividades agregadas solo a través de la API en tiempo real no son parte de las exportaciones y no se mostrarán en PowerBI.

Hay dos formas de conectar con la API de tiempo real:

- [indirectamente](#connect-via-the-dynamics-365-customer-insights-connector), utilizando el [conector de Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)
- [directamente](#connect-directly-to-the-real-time-api), con código

Ambas formas comparten los siguientes requisitos previos:

- Un entorno de Customer Insights
- Perfiles de cliente unificados
- Actividades configuradas y ejecutadas
- Permisos de colaborador o administrador para autenticar su cuenta

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Conectarse a través del conector de Dynamics 365 Customer Insights

La API en tiempo real puede ingerir datos de un conector de Power Platform exclusivo, el [conector de Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), sin la necesidad de escribir e implementar ningún código.    
El conector puede realizar las mismas acciones en tiempo real que la API. Necesita una licencia válida para conectores premium. Para obtener más información, consulte [Preguntas más frecuentes sobre licencias de Power Apps y Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).

- [Power Apps o Power Automate](https://docs.microsoft.com/connectors/) de Power Platform
- [Aplicaciones lógicas](https://docs.microsoft.com/azure/connectors/apis-list) de Azure

Para obtener detalles sobre la creación de flujos, consulte la [documentación de Power Automate](https://docs.microsoft.com/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Conectarse directamente a la API en tiempo real

Puede utilizar las capacidades en tiempo real creando su propia canalización y conectándose directamente a la API de tiempo real.    
Puede publicar una actividad en el formato de su sistema de origen o en el formato UnifiedActivity. Obtenga el formato haciendo una llamada API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Los detalles de esta API, incluidos los parámetros y las respuestas, se pueden encontrar en la sección **EntityData** de la [referencia de las API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Para obtener más información, consulte [Trabajar con la API de Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Comprendar el uso en tiempo real con telemetría

Obtenga una descripción general del volumen de solicitudes a la API de tiempo real e información sobre los problemas que puede encontrar el sistema. Puede [acceder a la telemetría en tiempo real](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]