---
title: Información general de los segmentos
description: Descripción general de los segmentos y cómo crearlos y gestionarlos.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170702"
---
# <a name="segments-overview"></a>Información general de los segmentos

Los segmentos le permite agrupar a los clientes según los atributos demográficos, transaccionales o de comportamiento. Puede usar segmentos para dirigir a los clientes campañas promocionales, actividades de ventas y acciones de atención al cliente con el fin de lograr sus objetivos empresariales.

Los perfiles de clientes que coinciden con los filtros de una definición de segmento se denominan *miembros* de un segmento. Se aplican algunos [límites de servicio](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Crear un segmento

Elija cómo crear una un segmento según su objetivo de público.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

- Segmentos complejos con el generador de segmentos: [Crear el suyo propio](segment-builder.md)
- Segmentos simples con un operador: [Segmento rápido](segment-quick.md)
- Forma con tecnología de IA para encontrar clientes similares: [Clientes similares](find-similar-customer-segments.md)
- Sugerencias con tecnología de IA basadas en medidas o atributos: [Segmentos sugeridos basados en medidas](suggested-segments.md)
- Sugerencias basadas en actividades: [Segmentos sugeridos basados en la actividad del cliente](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

- Segmentos sencillos o complejos con el generador de segmentos: [Crear el suyo propio](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Administrar segmentos existentes

Vaya a la página **Segmentos** para ver los segmentos que creó, su estado, el número de miembros y la última vez que se actualizaron los datos. Puede ordenar la lista de segmentos por cualquier columna o use el cuadro de búsqueda para encontrar el segmento que desea administrar.

Seleccione un segmento para ver las acciones disponibles.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento seleccionado con lista desplegable de opciones y opciones disponibles." lightbox="media/segments-selected-segment.png":::

- [**Vea**](#view-segment-details) los detalles del segmento, incluida la tendencia del recuento de miembros y una vista previa de los miembros del segmento.
- **Descargar** la lista de miembros como archivo .CSV.
- **Editar** el segmento para cambiar sus propiedades.
- **Crear duplicado** de un segmento. Puede optar por editar sus propiedades de inmediato o guardar el duplicado.
- [**Actualice**](#refresh-segments) el segmento para incluir los últimos datos.
- **Activar** o **Desactivar** el segmento. Los segmentos inactivos no se actualizarán durante una [actualización programada](system.md#schedule-tab) y tienen el **Estado** catalogado como **Omitido**, lo que indica que ni siquiera se intentó una actualización. Los segmentos activos se actualizan según su tipo: estáticos o dinámicos.
- **Haga estático** o **haga dinámico** el tipo de segmento. Los segmentos estáticos deben actualizarse manualmente. Los segmentos dinámicos se actualizan automáticamente durante las actualizaciones del sistema
- [**Encuentre clientes similares**](find-similar-customer-segments.md) del segmento.
- **Cambiar nombre** de segmento.
- **Etiqueta** para [administrar etiquetas](work-with-tags-columns.md#manage-tags) para el segmento.
- [**Gestione exportaciones**](#export-segments) para ver los segmentos relacionados con las exportaciones y gestionarlas. [Más información sobre exportaciones.](export-destinations.md)
- **Eliminar** el segmento.
- **Columnas** para [personalizar las columnas](work-with-tags-columns.md#customize-columns) de esa pantalla.
- **Filtro** para [filtrar en etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Buscar nombre** para buscar por nombre de segmento.

## <a name="view-segment-details"></a>Ver detalles de un segmento

En la página **Segmentos**, seleccione un segmento para ver el historial de procesamiento y los miembros del segmento.

La parte superior de la página incluye un gráfico de tendencia que visualiza cambios en el recuento de miembros. Pase el puntero sobre los puntos de datos para ver el recuento de miembros en una fecha específica. Cambie el plazo de tiempo de la visualización.

:::image type="content" source="media/segment-time-range.png" alt-text="Segmentar intervalo de tiempo.":::

La parte inferior contiene una lista de los miembros del segmento.

> [!NOTE]
> Los campos que aparecen en esta lista se basan en los atributos de las entidades de su segmento.
>
>La lista es una vista previa de los miembros del segmento coincidentes y muestra los primeros 100 registros de su segmento para que pueda evaluarlo rápidamente y revisar sus definiciones si es necesario. Para ver todos los registros coincidentes, [exporte el segmento](export-destinations.md).

## <a name="refresh-segments"></a>Actualizar segmentos

Los segmentos se pueden actualizar de forma automática o manualmente, a petición. Para actualizar manualmente uno o más segmentos, selecciónelos y elija **Actualizar**.

A [programar una actualización automática](system.md#schedule-tab), vaya a **Administración** > **Sistema** > **Programar**. Se aplican las siguientes reglas:

- Todos los segmentos con el tipo **Dinámico** o **Expansión** se actualizarán automáticamente a la cadencia establecida. Cuando se completa la actualización, el **Estado** indica si hubo algún problema al actualizar el segmento. La **Última actualización** muestra una marca de tiempo de la última actualización exitosa. Si ocurre un error, seleccione el error para ver detalles sobre lo que sucedió.
- Segmentos con el tipo **Estático** *no* se actualizarán automáticamente. La **Última actualización** muestra una marca de tiempo de la última vez que se ejecutó o actualizó manualmente el segmento estático.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Exporte segmentos a otras aplicaciones para utilizar más los datos. Exporte un segmento desde la página de segmentos o la [página de exportaciones](export-destinations.md).

1. Vaya a la página **Segmentos** y seleccione el segmento que desea exportaar.

1. Seleccione **Administrar exportaciones**. La página **Exportaciones (vista previa) para segmento** se abre. Vea todas las exportaciones configuradas agrupadas por si contienen el segmento actual o no.

   1. Para agregar el segmento seleccionado a una exportación, **Edite** la exportación respectiva para seleccionar el segmento correspondiente y luego guárdela. En entornos para clientes individuales, seleccione la exportación en la lista y seleccione **Agregar segmento** para lograr el mismo resultado.

   1. Para crear una nueva exportación con el segmento seleccionado, seleccione **Agregar exportación**. Para obtener más información sobre la creación de exportaciones, consulte [Configurar una nueva exportación](export-destinations.md#set-up-a-new-export).

1. Seleccione **Atrás** para volver a la página principal de los segmentos.

## <a name="track-usage-of-a-segment"></a>Rastrear el uso de un segmento

Si usa segmentos en aplicaciones, que se basan en la misma organización de Microsoft Dataverse que está conectada con Customer Insights, puede realizar un seguimiento del uso de un segmento. Para [Segmentos de Customer Insights utilizados en recorridos de clientes de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), el sistema le informa sobre el uso de ese segmento.

Al editar un segmento que se está usando dentro del entorno de Customer Insights, o en un recorrido del cliente en Marketing, un banner del [generador de segmentos](segment-builder.md) le informa sobre las dependencias. Inspeccione los detalles de dependencia directamente desde el banner o seleccionando **Uso** en el generador de segmentos.

El panel **Uso de segmento** muestra los detalles sobre el uso de este segmento en aplicaciones basadas en Dataverse. Para los segmentos que se usan en los recorridos del cliente, encontrará un vínculo para inspeccionar el recorrido en Marketing donde se usa este segmento. Si tiene permisos para obtener acceso a la aplicación Marketing, vea más detalles allí.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Panel lateral con detalles del uso del segmento en el generador de segmentos.":::

El sistema le informa sobre el uso de un segmento rastreado cuando intenta eliminarlo. Si el segmento que va a eliminar se utiliza en un recorrido del cliente en Marketing, ese recorrido se detendrá para todos los usuarios del segmento. Si el recorrido forma parte de una campaña de marketing, la supresión afectará a esa misma campaña. Sin embargo, aún puede eliminar el segmento a pesar de las advertencias.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Cuadro de diálogo para confirmar la eliminación del segmento cuando se usa un segmento en una aplicación de Dataverse.":::

### <a name="supported-apps"></a>Aplicaciones admitidas

El uso se rastrea actualmente en las siguientes aplicaciones basadas en Dataverse:

- [Recorridos del cliente en Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
