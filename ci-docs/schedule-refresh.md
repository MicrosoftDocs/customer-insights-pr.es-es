---
title: Programar actualización del sistema
description: Programar la hora en que se debe actualizar el sistema
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246349"
---
# <a name="schedule-system-refresh"></a>Programar actualización del sistema

Programe actualizaciones automáticas de todos sus [orígenes de datos ingeridos](data-sources.md). Las actualizaciones automáticas ayudan a garantizar que las actualizaciones desde sus orígenes de datos se reflejan en sus perfiles de clientes unificados.

> [!NOTE]
> Los orígenes de datos de Power Query gestionados por usted se actualizan en sus propias programaciones. Para programar la actualización de los orígenes de datos de Power Query, configure los ajustes de actualización en ese origen de datos específico desde la página **Orígenes de datos**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Configuración de actualización del flujo de datos de Power Platform.":::

## <a name="set-system-refresh-schedule"></a>Establecer programación de actualización del sistema

1. Vaya a **Administración** > **Sistema** y seleccione la pestaña **Programación**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Programar la pestaña de actualización desde la página del sistema":::

1. El estado predeterminado para la actualización programada es **Desactivado**. Para habilitar actualizaciones programadas, cambie el control de alternancia en la parte superior de la pantalla a **Activo**.

1. Elija entre actualizaciones **Semanales** (predeterminado) y **Diarias**. Si tiene la intención de programar actualizaciones semanales, seleccione uno o más días en los que desea ejecutar la actualización.

1. Establezca su **Zona horaria**, luego use el desplegable **Hora** para establecer su calendario de actualización. Si desea programar varias actualizaciones en un solo día, seleccione **Agregar otra hora**.

1. Seleccione **Guardar** para aplicar los cambios.

[!INCLUDE [footer-include](includes/footer-banner.md)]