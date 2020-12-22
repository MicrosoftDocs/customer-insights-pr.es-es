---
title: Configuración del sistema en las informaciones de público
description: Más información sobre la configuración del sistema en la capacidad de informaciones de público de Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407048"
---
# <a name="system-configuration"></a>Configuración del sistema

La página **Sistema** incluye cuatro pestañas: **Estado**, **Programación**, **Acerca de** y **General**.

> [!div class="mx-imgBorder"]
> ![Página del sistema](media/system-tabs.png "Página del sistema")

## <a name="status-tab"></a>Pestaña Estado

La **pestaña Estado** le permite seguir el progreso de la ingesta de datos, exportaciones de datos y varios procesos importantes del producto. Revise la información de esta pestaña para asegurarse de que los procesos activos estén completos.

Esta pestaña incluye tablas de estado para **Orígenes de datos**, **Procesos del sistema** y **Preparación de datos**. Cada tabla sigue el **Nombre** de la tarea y su entidad correspondiente, el **Estado** de su ejecución más reciente, y cuál fue la **Última actualización**.

Vea los detalles de las últimas ejecuciones de las tareas seleccionando su nombre.

### <a name="status-types"></a>Tipos de estado

Existen seis tipos de estado para las tareas. Los siguientes tipos de estado también se muestran en las páginas *Coincidir*, *Combinar*, *Orígenes de datos*, *Segmentos*, *Medidas*, *Enriquecimiento*, *Actividades* y *Predicciones*:

- **Procesando:** La tarea está en progreso. El estado puede cambiar a Correcto o Error.
- **Correcto:** Tarea completada con éxito.
- **Omitido:** La tarea se saltó. Uno o más de los procesos posteriores de los que depende esta tarea fallan o se omiten.
- **Error:** El procesamiento de la tarea ha generado un error.
- **Cancelado:** El procesamiento fue cancelado por el usuario antes de que terminara.
- **En cola:** El procesamiento se pone en cola y comenzará una vez que se completen todas las tareas posteriores. Para obtener más información, consulte [Actualizar directivas](#refresh-policies).

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

Busque detalles sobre el uso de la API en tiempo real y vea qué eventos ocurrieron en un intervalo de tiempo determinado. Para más información, consulte [Ingesta de datos en tiempo real](real-time-data-ingestion.md).
