---
title: Configuración del sistema en Customer Insights
description: Obtenga información sobre la configuración del sistema en Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653637"
---
# <a name="system-configuration"></a>Configuración del sistema

Para acceder a las configuraciones del sistema, vaya a **Administración** > **Sistema** para ver una lista de tareas y procesos del sistema.

La página **Sistema** incluye las siguientes pestañas:
- [Estado de ejecución](#status-tab)
- [Programa](#schedule-tab)
- [Uso de API](#api-usage-tab)
- [Acerca de](#about-tab)
- [General](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Pestañas de configuración en la página del sistema.":::

## <a name="status-tab"></a>Pestaña Estado

La **pestaña Estado** le permite realizar un seguimiento del progreso de las tareas, la ingesta de datos, las exportaciones de datos y varios otros procesos de productos importantes. Revise la información de esta pestaña para asegurarse de que sus tareas y procesos activos estén completos.

Esta pestaña incluye tablas con información del estado e información sobre el procesamiento para varios procesos. Cada tabla sigue el **Nombre** de la tarea y su entidad correspondiente, el **Estado** de su ejecución más reciente, y cuál fue la **Última actualización**. Puede ver los detalles de las últimas ejecuciones seleccionando la tarea o el nombre del proceso. 

Seleccione el estado junto a la tarea o proceso en la columna **Estado** para abrir el panel **Detalles de progreso**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel de detalles del progreso del sistema":::

### <a name="status-definitions"></a>Definiciones de estado

El sistema utiliza los siguientes estados para tareas y procesos:

|Estado de ejecución  |Definición  |
|---------|---------|
|Cancelada |El usuario canceló el procesamiento antes de que finalizara.   |
|Con errores   |Se han producido errores al ingerir datos.         |
|Error  |El procesamiento ha fallado.  |
|Sin iniciar   |El origen de datos aún no tiene datos ingeridos o sigue en modo de borrador.         |
|Procesamiento  |La tarea o el proceso está en curso.  |
|Actualizando    |La ingesta de datos está en curso. Para cancelar esta operación, seleccione **Detener la actualización** en la columna **Acciones**. Al detener la actualización de un origen de datos se revertirá a su último estado de actualización.       |
|Omitida  |Se omitió la tarea o el proceso. Uno o más de los procesos posteriores de los que depende esta tarea fallan o se omiten.|
|Operación correcta  |La tarea o el proceso finalizó correctamente. Para las fuentes de datos, indica que los datos se han ingerido correctamente si se menciona una hora en la columna **Refrescado**.|
|En cola | El procesamiento está en cola y comenzará una vez que se completen todas las tareas y procesos anteriores. Para obtener más información, consulte [Procesos de actualización](#refresh-processes).|

### <a name="refresh-processes"></a>Procesos de actualización

La actualización de tareas y procesos se ejecuta de acuerdo con el [horario configurado](#schedule-tab). 

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

## <a name="schedule-tab"></a>Pestaña Programación

Utilice la pestaña **Programación** para programar actualizaciones automáticas de todos sus [orígenes de datos ingeridos](data-sources.md). Las actualizaciones automáticas ayudan a garantizar que las actualizaciones desde sus orígenes de datos se reflejan en sus perfiles de clientes unificados.

> [!NOTE]
> Los orígenes de datos gestionadas por usted se actualizan en sus propias programaciones. Para programar la actualización de los orígenes de datos gestionadas por usted, configure los ajustes de actualización en ese origen de datos específico desde la página **Orígenes de datos**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Configuración de actualización del flujo de datos de Power Platform.":::

1. Vaya a **Administración** > **Sistema** y seleccione la pestaña **Programación**.

2. El estado predeterminado para la actualización programada es **Desactivado**. Para habilitar actualizaciones programadas, cambie el control de alternancia en la parte superior de la pantalla a **Activo**.

3. Elija entre actualizaciones **Semanales** (predeterminado) y **Diarias**. Si tiene la intención de programar actualizaciones semanales, seleccione uno o más días en los que desea ejecutar la actualización.

4. Establezca su **Zona horaria**, luego use el desplegable **Hora** para establecer su calendario de actualización. Cuando haya terminado, seleccione **Establecer**. Si desea programar varias actualizaciones en un solo día, seleccione **Agregar otra hora**.

5. Seleccione **Guardar** para aplicar los cambios.

## <a name="about-tab"></a>Pestaña Acerca de

La pestaña **Acerca de** contiene el **Nombre para mostrar** de la organización, el **ID del entorno** activo, la **Región** y su **ID de sesión**. Si tiene más de un entorno de trabajo, debe proporcionar a cada uno un nombre fácilmente identificable.

## <a name="general-tab"></a>Pestaña General

Puede cambiar el idioma y el formato de país/región en la pestaña **General**.

Customer Insights [admite muchos idiomas](/dynamics365/get-started/availability). La aplicación usa su preferencia de idioma para mostrar elementos como el menú, el texto de etiquetas y los mensajes del sistema en su idioma preferido.

Los datos importados y la información que introdujo manualmente no se traducen.

### <a name="update-the-settings"></a>Actualizar la configuración

Para cambiar el idioma preferido, elija un **Idioma** en el menú desplegable.

Para cambiar su formato preferido de fechas, hora y números, use el menú desplegable **Formato de país o región**. Se muestra una vista previa de formato debajo de este campo. El sistema sugerirá automáticamente una selección cuando elija un nuevo idioma.

Seleccione **Guardar** para confirmar las selecciones.

## <a name="api-usage-tab"></a>Pestaña de uso de API

Encuentre detalles sobre el uso de la API en tiempo real y vea qué eventos ocurrieron en un período de tiempo determinado. Elija el plazo de tiempo en el menú desplegable **Seleccionar plazo de tiempo**. 

El **Uso de API** contiene tres secciones: 
- **Llamadas API**: un gráfico que visualiza el número agregado de llamadas API en el plazo de tiempo seleccionado.

- **Transferencia de datos**: un gráfico que muestra la cantidad de datos que se transfirieron a través de la API en el período de tiempo seleccionado.

-  **Operaciones**: una tabla con filas para cada operación de API disponible y detalles sobre el uso de las operaciones. Puede seleccionar un nombre de operación para ir a [la referencia de API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operaciones que utilizan la [ingesta de datos en tiempo real](real-time-data-ingestion.md) contienen un botón con un símbolo binocular para ver el uso de la API en tiempo real. Seleccione el botón para abrir un panel lateral que contiene detalles para el uso de la API de tiempo real en el entorno actual.   
   Utilice el cuadro **Agrupar por** en el panel **Uso de API en tiempo real** para elegir la mejor forma de presentar sus interacciones en tiempo real. Puede agrupar los datos por método de API, nombre calificado de entidad (entidad ingerida), creado por (origen del evento), resultado (éxito o error) o códigos de error. Los datos están disponibles como gráfico del historial y como tabla.


[!INCLUDE [footer-include](includes/footer-banner.md)]
