---
title: Ver configuración del sistema
description: Obtenga información sobre la configuración del sistema en Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396022"
---
# <a name="view-system-configuration"></a>Ver configuración del sistema

Vea la información del sistema, el estado del sistema y el uso de la API.

## <a name="view-api-usage"></a>Ver el uso de la API

Vea los detalles sobre el uso de la API en tiempo real y vea qué eventos ocurrieron en un período de tiempo determinado.

1. Vaya a **Administración** > **Sistema** y seleccione la pestaña **Uso de la API**.

1. **Seleccione un plazo de tiempo** que quiera ver.

   La página **Uso de API** contiene tres secciones:

   - **Llamadas API**: un gráfico que visualiza el número agregado de llamadas API en el plazo de tiempo seleccionado.
   - **Transferencia de datos**: un gráfico que muestra la cantidad de datos que se transfirieron a través de la API en el período de tiempo seleccionado.
   - **Operaciones**: una tabla con filas para cada operación de API disponible y detalles sobre el uso de las operaciones. Seleccioneun nombre de operación para ir a [la referencia de API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Ver información del sistema

Vea el nombre de entorno, id., región, tipo e id. de sesión.

1. Vaya a **Administración** > **Sistema** y seleccione la pestaña **Acerca de**.

1. Para ver el idioma y el país o región, seleccione la pestaña **General**.

### <a name="update-preferred-language-or-countryregion"></a>Actualizar idioma preferido o país y región

Customer Insights [admite muchos idiomas](/dynamics365/get-started/availability). La aplicación usa su preferencia de idioma para mostrar elementos como el menú, el texto de etiquetas y los mensajes del sistema en su idioma preferido.

Los datos importados y la información que introdujo manualmente no se traducen.

1. Vaya a **Administración** > **Sistema** y seleccione la pestaña **General**.

1. Para cambiar el idioma preferido, elija un **Idioma** en el menú desplegable.

1. Para cambiar su formato preferido de fechas, hora y números, use el menú desplegable **Formato de país o región**. Se muestra una versión preliminar del formato. El sistema sugiere automáticamente una selección cuando elija un nuevo idioma.

1. Seleccione **Guardar**.

## <a name="view-system-status"></a>Ver estado del sistema

Realice un seguimiento del progreso de las tareas, la ingesta de datos, las exportaciones de datos y varios otros procesos de productos importantes. Revise la información para asegurarse de que sus tareas y procesos activos estén completos.

1. Vaya a **Administración** > **Sistema** y seleccione la pestaña **Estado**.

   Estado e información sobre el procesamiento para varios procesos. Vea el **Nombre** de la tarea, el **Estado** de su ejecución más reciente, y cuál fue la **Última actualización**.

1. Para ver los detalles de las últimas ejecuciones, seleccione la tarea o el nombre del proceso.

1. Para ver los detalles del progreso de una tarea, seleccione el estado. El panel **Detalles del progreso** se muestra.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel de detalles del progreso del sistema":::

1. Para ver los detalles del progreso de todas las tareas, seleccione **Todo el flujo de trabajo**.

### <a name="status-definitions"></a>Definiciones de estado

El sistema utiliza los siguientes estados para tareas y procesos:

|Status  |Definición  |
|---------|---------|
|Cancelado |La tarea o el proceso se cancelaron antes de que finalizara.   |
|Con errores   |La tarea o el proceso tuvo errores.         |
|Error  |La tarea o el proceso ha fallado.  |
|Sin iniciar   |El origen de datos aún no ha ingerido datos o la tarea aún está en modo de borrador.         |
|Procesando  |La tarea o el proceso está en curso.  |
|Actualizando    |La tarea o el proceso está en curso. Para cancelar esta operación, seleccione **Actualizar** y **Cancelar trabajo**. Al detener la actualización de una tarea o proceso se revertirá a su último estado de actualización.       |
|Omitida  |Se omitió la tarea o el proceso. Uno o más de los procesos posteriores de los que depende esta tarea fallan o se omiten.|
|Operación correcta  |La tarea o el proceso finalizó correctamente. Para las fuentes de datos, indica que los datos se han ingerido correctamente si se menciona una hora en la columna **Refrescado**.|
|En cola | El procesamiento está en cola y comenzará una vez que se completen todas las tareas y procesos anteriores. Para obtener más información, consulte [Procesos de actualización](#refresh-processes).|

### <a name="refresh-processes"></a>Procesos de actualización

La actualización de tareas y procesos se ejecuta de acuerdo con el [horario configurado](schedule-refresh.md).

|Proceso  |Descripción  |
|---------|---------|
|Actividad  |Se ejecuta manualmente (actualización única). Depende del proceso de fusión. El conocimiento profundo depende de su procesamiento.|
|Vinculación del análisis |Se ejecuta manualmente (actualización única). Depende de los segmentos.  |
|Preparación del análisis |Se ejecuta manualmente (actualización única). Depende de los segmentos.  |
|Preparación de datos   |Necesita una entidad para ejecutarse. Las entidades origen de datos dependen de la ingestión. Las entidades enriquecidas dependen de los enriquecimientos. La entidad Cliente depende de la fusión.  |
|Orígenes de datos   |No depende de ningún otro proceso. La coincidencia depende de la finalización exitosa de este proceso.  |
|Enriquecimientos   |Se ejecuta manualmente (actualización única). Depende del proceso de fusión. |
|Destinos de exportación |Se ejecuta manualmente (actualización única). Depende de los segmentos.  |
|Información |Se ejecuta manualmente (actualización única). Depende de los segmentos.  |
|Inteligencia   |Depende de la combinación.   |
|Coincidir |Depende del procesamiento de los orígenes de datos utilizados en la definición de coincidencia.      |
|Medidas  |Se ejecuta manualmente (actualización única). Depende del proceso de fusión.  |
|Combinar   |Depende de la finalización del proceso de coincidencia. Los segmentos, las medidas, el enriquecimiento, la búsqueda, las actividades, las predicciones y la preparación de datos dependen de la finalización exitosa de este proceso.   |
|Perfiles   |Se ejecuta manualmente (actualización única). Depende del proceso de fusión. |
|Buscar   |Se ejecuta manualmente (actualización única). Depende del proceso de fusión. |
|Segmentos  |Se ejecuta manualmente (actualización única). Depende del proceso de fusión. El conocimiento profundo depende de su procesamiento.|
|Sistema   |Depende de la finalización del proceso de coincidencia. Los segmentos, las medidas, el enriquecimiento, la búsqueda, las actividades, las predicciones y la preparación de datos dependen de la finalización exitosa de este proceso.   |
|Usuario  |Se ejecuta manualmente (actualización única). Depende de las entidades.  |

Seleccione el estado de un proceso para ver los detalles del progreso de todo el trabajo en el que se encontraba. Los procesos de actualización anteriores pueden ayudarlo a comprender qué puede hacer para abordar una tarea o proceso **Omitidos** o **Puestos en cola**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
