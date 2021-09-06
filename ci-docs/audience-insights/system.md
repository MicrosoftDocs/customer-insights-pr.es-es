---
title: Configuración del sistema en las informaciones de público
description: Más información sobre la configuración del sistema en la capacidad de informaciones de público de Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2af8728009b4f1d53ebc2557bab8c79537a0dc5dda54477493ab1ad16f3f9a8a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035937"
---
# <a name="system-configuration"></a>Configuración del sistema

La página **Sistema** incluye las siguientes pestañas:
- [Estado de ejecución](#status-tab)
- [Programación](#schedule-tab)
- [Uso de API](#api-usage-tab)
- [Acerca de](#about-tab)
- [General](#general-tab)

> [!div class="mx-imgBorder"]
> ![Página del sistema.](media/system-tabs.png "Página del sistema")

## <a name="status-tab"></a>Pestaña Estado

La **Pestaña de estado** le permite realizar un seguimiento del progreso de la ingesta de datos, las exportaciones de datos y varios otros procesos de productos importantes. Revise la información de esta pestaña para asegurarse de que los procesos activos estén completos.

Esta pestaña incluye tablas con información del estado e información sobre el procesamiento para varios procesos. Cada tabla sigue el **Nombre** de la tarea y su entidad correspondiente, el **Estado** de su ejecución más reciente, y cuál fue la **Última actualización**.

Vea los detalles de las últimas ejecuciones de las tareas seleccionando su nombre.

### <a name="status-types"></a>Tipos de estado

Existen seis tipos de estado para las tareas. Los siguientes tipos de estado también se muestran en las páginas *Coincidir*, *Combinar*, *Orígenes de datos*, *Segmentos*, *Medidas*, *Enriquecimiento*, *Actividades* y *Predicciones*:

- **Procesando:** La tarea está en progreso. El estado puede cambiar a Correcto o Error.
- **Correcto:** Tarea completada con éxito.
- **Omitido:** La tarea se saltó. Uno o más de los procesos posteriores de los que depende esta tarea fallan o se omiten.
- **Error:** El procesamiento de la tarea ha generado un error.
- **Cancelado:** El procesamiento fue cancelado por el usuario antes de que terminara.
- **Puesto en cola**: el procesamiento está en cola y comenzará una vez que se completen todas las tareas anteriores. Para obtener más información, consulte [Actualizar directivas](#refresh-policies).

### <a name="refresh-policies"></a>Directivas de actualización

Esta lista muestra las políticas de actualización para cada uno de los procesos principales:

- **Orígenes de datos:** Funciona de acuerdo con el [horario configurado](#schedule-tab). No depende de ningún otro proceso. La coincidencia depende de la finalización exitosa de este proceso.
- **Coincidencia:** Funciona de acuerdo con el [horario configurado](#schedule-tab). Depende del procesamiento de los orígenes de datos utilizados en la definición de coincidencia. La combinación depende de la finalización exitosa de este proceso.
- **Combinar:** Funciona de acuerdo con el [horario configurado](#schedule-tab). Depende de la finalización del proceso de coincidencia. Los segmentos, las medidas, el enriquecimiento, la búsqueda, las actividades, las predicciones y la preparación de datos dependen de la finalización exitosa de este proceso.
- **Segmentos**: Se ejecuta manualmente (actualización única) y de acuerdo con el [horario configurado](#schedule-tab). Depende de la combinación. El conocimiento profundo depende de su procesamiento.
- **Medidas**: Se ejecuta manualmente (actualización única) y de acuerdo con el [horario configurado](#schedule-tab). Depende de la combinación.
- **Actividades**: Se ejecuta manualmente (actualización única) y de acuerdo con el [horario configurado](#schedule-tab). Depende de la combinación.
- **Enriquecimiento**: Se ejecuta manualmente (actualización única) y de acuerdo con el [horario configurado](#schedule-tab). Depende de la combinación.
- **Buscar**: Se ejecuta manualmente (actualización única) y de acuerdo con el [horario configurado](#schedule-tab). Depende de la combinación.
- **Preparación de datos:** Funciona de acuerdo con el [horario configurado](#schedule-tab). Depende de la combinación.
- **Conocimiento profundo**: Se ejecuta manualmente (actualización única) y de acuerdo con el [horario configurado](#schedule-tab). Depende de los segmentos.

Seleccione el estado de una tarea para ver los detalles del progreso de todo el trabajo en el que se encontraba. Las directivas de actualización anteriores pueden ayudarlo a comprender lo que puede hacer para abordar una tarea que se ha **Omitido** o **Puesto en cola**.

## <a name="schedule-tab"></a>Pestaña Programación

Utilice la pestaña **Programación** para programar actualizaciones automáticas de todos sus [orígenes de datos ingeridos](data-sources.md). Las actualizaciones automáticas ayudan a garantizar que las actualizaciones desde sus orígenes de datos se reflejan en sus perfiles de clientes unificados.

1. En las informaciones de público, vaya a **Administrador** > **Sistema** y seleccione la pestaña **Programación**.

2. El estado predeterminado para la actualización programada es **Desactivado**. Para habilitar actualizaciones programadas, cambie el control de alternancia en la parte superior de la pantalla a **Activo**.

3. Elija entre actualizaciones **Semanales** (predeterminado) y **Diarias**. Si tiene la intención de programar actualizaciones semanales, seleccione uno o más días en los que desea ejecutar la actualización.

4. Establezca su **Zona horaria**, luego use el desplegable **Hora** para establecer su calendario de actualización. Cuando haya terminado, seleccione **Establecer**. Si desea programar varias actualizaciones en un solo día, seleccione **Agregar otra hora**.

5. Seleccione **Guardar** para aplicar los cambios.

## <a name="about-tab"></a>Pestaña Acerca de

La pestaña **Acerca de** contiene el **Nombre para mostrar** de la organización, el **ID del entorno** activo, la **Región** y su **ID de sesión**. Si tiene más de un entorno de trabajo, debe proporcionar a cada uno un nombre fácilmente identificable.

## <a name="general-tab"></a>Pestaña General

Hay dos opciones en la pestaña **General**, **Idioma** y **Formato de país o región**.

La aplicación [admite varios idiomas](supported-languages.md). Para cambiar el idioma preferido, elija un **Idioma** en el menú desplegable.

Para cambiar su formato preferido de fechas, hora y números, use el menú desplegable **Formato de país o región**. Se muestra una vista previa de formato debajo de este campo. El sistema sugerirá automáticamente una selección cuando elija un nuevo idioma.

Seleccione **Guardar** para confirmar las selecciones.

## <a name="api-usage-tab"></a>Pestaña de uso de API

Encuentre detalles sobre el uso de la API en tiempo real y vea qué eventos ocurrieron en un período de tiempo determinado. Elija el plazo de tiempo en el menú desplegable **Seleccionar plazo de tiempo**. 

El **Uso de API** contiene tres secciones: 
- **Llamadas API**: un gráfico que visualiza el número agregado de llamadas API en el plazo de tiempo seleccionado.

- **Transferencia de datos**: un gráfico que muestra la cantidad de datos que se transfirieron a través de la API en el período de tiempo seleccionado.

-  **Operaciones**: una tabla con filas para cada operación de API disponible y detalles sobre el uso de las operaciones. Puede seleccionar un nombre de operación para ir a [la referencia de API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Las operaciones que utilizan la [ingesta de datos en tiempo real](real-time-data-ingestion.md) contienen un botón con un símbolo de binoculares para ver el uso de la API en tiempo real. Seleccione el botón para abrir un panel lateral que contiene detalles para el uso de la API de tiempo real en el entorno actual.   
   Utilice el cuadro **Agrupar por** en el panel **Uso de API en tiempo real** para elegir la mejor forma de presentar sus interacciones en tiempo real. Puede agrupar los datos por método de API, nombre calificado de entidad (entidad ingerida), creado por (origen del evento), resultado (éxito o error) o códigos de error. Los datos están disponibles como gráfico del historial y como tabla.


[!INCLUDE[footer-include](../includes/footer-banner.md)]