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
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050968"
---
# <a name="segments-overview"></a>Información general de los segmentos

Los segmentos le permite agrupar a los clientes según los atributos demográficos, transaccionales o de comportamiento. Puede usar segmentos para dirigir a los clientes campañas promocionales, actividades de ventas y acciones de atención al cliente con el fin de lograr sus objetivos empresariales.

Los perfiles de clientes que coinciden con los filtros de una definición de segmento se denominan *miembros* de un segmento. Se aplican algunos [límites de servicio](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Crear un nuevo segmento

Hay múltiples formas de crear un nuevo segmento: 

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

- Segmento complejo con generador de segmentos: [Crear el nuestro](segment-builder.md#create-a-new-segment) 
- Segmentos simples con un operador: [Segmento rápido](segment-builder.md#quick-segments) 
- Forma con tecnología de IA para encontrar clientes similares: [Clientes similares](find-similar-customer-segments.md) 
- Sugerencias con tecnología de IA basadas en medidas o atributos: [Segmentos sugeridos para mejorar las medidas](suggested-segments.md) 
- Sugerencias basadas en actividades: [Segmentos sugeridos basados en la actividad del cliente](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

- Segmento complejo con generador de segmentos: [Crear el nuestro](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Administrar segmentos existentes

Vaya a la página **Segmentos** para ver todos los segmentos guardados y administrarlos.

Cada segmento está representado por una fila que incluye información adicional sobre el segmento.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento seleccionado con lista desplegable de opciones y opciones disponibles." lightbox="media/segments-selected-segment.png":::

Las siguientes acciones están disponibles cuando selecciona un segmento:

- **Ver** los detalles del segmento, incluida la tendencia del recuento de miembros de una vista previa de los miembros del segmento.
- **Descargar** la lista de miembros como archivo .CSV.
- **Editar** el segmento para cambiar sus propiedades.
- **Crear duplicado** de un segmento. Puede optar por editar sus propiedades de inmediato o guardar el duplicado.
- **Actualizar** el segmento para incluir los últimos datos.
- **Activar** o **Desactivar** el segmento. Para los segmentos inactivos, existe la definición de segmento, pero aún no contiene ningún cliente. Un segmento activo busca clientes que coincidan con la definición del segmento. Si una [actualización programada](system.md#schedule-tab) está configurada, los segmentos inactivos tienen el **Estado** catalogado como **Omitido**, lo que indica que ni siquiera se intentó una actualización. Cuando se activa un segmento inactivo, se actualizará y se incluirá en las actualizaciones programadas.
  Alternativamente, puede usar la funcionalidad **Programar más tarde** en el desplegable **Activar/Desactivar** para especificar una fecha y hora futuras para la activación y desactivación de un segmento en particular.
- **[Encuentre clientes similares](find-similar-customer-segments.md)** del segmento.
- **Cambiar nombre** de segmento.
- **Etiqueta** para [administrar etiquetas](work-with-tags-columns.md#manage-tags) para el segmento.
- **Descargar** la lista de miembros como archivo .CSV.
- **Gestionar exportaciones** para ver el segmento relacionado con las exportaciones y gestionarlas. [Más información sobre exportaciones.](export-destinations.md)
- **Eliminar** el segmento.
- **Columnas** para [personalizar las columnas](work-with-tags-columns.md#customize-columns) de esa pantalla.
- **Filtro** para [filtrar en etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Buscar nombre** para buscar por nombre de segmento.

## <a name="refresh-segments"></a>Actualizar segmentos

Puede actualizar todos los segmentos a la vez seleccionando **Actualizar todo** en la página **Segmentos** o puede actualizar uno o varios segmentos cuando los selecciona y elige **Actualizar** desde las opciones. Alternativamente, puede configurar una actualización periódica en **Administración** > **Sistema** > **Programar**. Cuando se configura una actualización periódica, se aplican las siguientes reglas:

- Todos los segmentos con el tipo **Dinámico** o **Expansión** se actualizarán automáticamente a la cadencia establecida. Cuando se completa la actualización, el **Estado** indica si hubo algún problema al actualizar el segmento. La **Última actualización** muestra una marca de tiempo de la última actualización exitosa. Si ocurre un error, seleccione el error para ver detalles sobre lo que sucedió.
- Segmentos con el tipo **Estático** *no* se actualizarán automáticamente. La **Última actualización** muestra una marca de tiempo de la última vez que se ejecutaron o actualizaron manualmente los segmentos estáticos.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Puede exportar un segmento desde la página de segmentos o la [página de exportaciones](export-destinations.md). 

1. Vaya a la página **Segmentos**.

1. Seleccione los puntos suspensivos verticales (&vellip;) para el segmento que desea exportar.

1. Seleccione **Gestionar exportaciones** de la lista desplegable de acciones.

1. La página **Exportaciones (vista previa) para segmento** se abre. Puede ver todas las exportaciones configuradas agrupadas por si contienen el segmento actual o no.

   1. Para agregar el segmento seleccionado a una exportación, **Edite** la exportación respectiva para seleccionar el segmento correspondiente y luego guárdela. En entornos para clientes individuales, puede seleccionar la exportación en la lista y seleccionar **Agregar segmento** para lograr el mismo resultado.

   1. Para crear una nueva exportación con el segmento seleccionado, seleccione **Agregar exportación**. Para obtener más información sobre la creación de exportaciones, consulte [Configurar una nueva exportación](export-destinations.md#set-up-a-new-export).

1. Seleccione **Atrás** para volver a la página principal de los segmentos.

## <a name="track-usage-of-a-segment"></a>Rastrear el uso de un segmento

Si usa segmentos en aplicaciones, que se basan en la misma organización de Microsoft Dataverse que está conectada con Customer Insights, puede realizar un seguimiento del uso de un segmento. Para [Segmentos de Customer Insights utilizados en recorridos de clientes de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), el sistema le informa sobre el uso de ese segmento.

Al editar un segmento que se está usando dentro del entorno de Customer Insights, o en un recorrido del cliente en Marketing, un banner del [generador de segmentos](segment-builder.md) le informa sobre las dependencias. Puede inspeccionar los detalles de dependencia directamente desde el banner o seleccionando **Uso** en el generador de segmentos.

El panel **Uso de segmento** muestra los detalles sobre el uso de este segmento en aplicaciones basadas en Dataverse. Para los segmentos que se usan en los recorridos del cliente, encontrará un vínculo para inspeccionar el recorrido en Marketing donde se usa este segmento. Si tiene permisos para obtener acceso a la aplicación Marketing, puede tener acceso a más detalles allí.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Panel lateral con detalles del uso del segmento en el generador de segmentos.":::

El sistema le informa sobre el uso de un segmento rastreado cuando intenta eliminarlo. Si el segmento que va a eliminar se utiliza en un recorrido del cliente en Marketing, ese recorrido se detendrá para todos los usuarios del segmento. Si el recorrido forma parte de una campaña de marketing, la supresión afectará a esa misma campaña. Sin embargo, aún puede eliminar el segmento a pesar de las advertencias.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Cuadro de diálogo para confirmar la eliminación del segmento cuando se usa un segmento en una aplicación de Dataverse.":::

### <a name="supported-apps"></a>Aplicaciones admitidas

El uso se rastrea actualmente en las siguientes aplicaciones basadas en Dataverse:

- [Recorridos del cliente en Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Ver el historial de procesamiento y los miembros del segmento

Puede ver datos consolidados sobre un segmento revisando sus detalles.

En la página **Segmentos**, seleccione el segmento que desea revisar.

La parte superior de la página incluye un gráfico de tendencia que visualiza cambios en el recuento de miembros. Pase el puntero sobre los puntos de datos para ver el recuento de miembros en una fecha específica.

Puede actualizar el período de tiempo de la visualización.

> [!div class="mx-imgBorder"]
> ![Segmentar intervalo de tiempo.](media/segment-time-range.png "Segmentar intervalo de tiempo")

La parte inferior contiene una lista de los miembros del segmento.

> [!NOTE]
> Los campos que aparecen en esta lista se basan en los atributos de las entidades de su segmento.
>
>La lista es una vista previa de los miembros del segmento coincidentes y muestra los primeros 100 registros de su segmento para que pueda evaluarlo rápidamente y revisar sus definiciones si es necesario. Para ver todos los registros coincidentes, debe [exportar el segmento](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
