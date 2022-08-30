---
title: Ver perfiles de clientes
description: Vea sus datos de clientes unificados, incluido el uso de búsqueda y filtro
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303804"
---
# <a name="view-customer-profiles"></a>Ver perfiles de clientes

Los perfiles de cliente están disponibles una vez [cree la entidad *Cliente* unificada](data-unification.md). La página **Clientes** muestra una vista combinada de sus perfiles unificados de clientes. Los clientes pueden ser personas u organizaciones.

Vaya a la página **Clientes** para ver sus clientes y sus perfiles. Cada perfil de cliente se representa con un mosaico. Utilice los controles de paginación para obtener más registros. La tarjeta muestra campos de la entidad *Cliente* definida en el **Índice de Buscar y filtrar**. El sistema selecciona el orden de los campos dentro de cada tarjeta.

> [!NOTE]
> Si no puede ver los mosaicos cuando selecciona **Clientes**, su administrador debe [definir al menos un atributo de búsqueda](search-filter-index.md) en el **Índice de Buscar y filtrar**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Página de clientes que muestra mosaicos de resultados.":::

Seleccione cualquiera de las siguientes acciones:
- [Ver detalles del cliente](#view-customer-details)
- [Administrar el índice de búsqueda y filtro](search-filter-index.md) (solo administradores)
- [Filtrar de clientes](#filter-customers)
- **Expandir tarjetas** o **Contraer tarjetas** para expandir o contraer la información que se muestra en el mosaico del cliente
- **Ordenar por** un atributo particular
- [Buscar clientes](#search-for-customers)

  > [!NOTE]
  > Para usar la búsqueda y el filtro, un administrador debe configurar los atributos de búsqueda y definir los campos filtrables usando el índice de búsqueda y filtro.

## <a name="search-for-customers"></a>Buscar clientes

Busque clientes introduciendo un nombre o algún otro atributo en **Buscar clientes**. Los atributos de búsqueda están definidos por el administrador y provienen de la entidad *Cliente* unificada.

> [!NOTE]
> **Cadena** es el único tipo de datos que se incluye en la búsqueda. Úselo en el campo **Buscar clientes** de la página Clientes para buscar clientes.

## <a name="filter-customers"></a>Filtrar de clientes

Puede filtrar clientes por campos de entidad *Cliente*. Los campos filtrables son definidos por el administrador.

1. En la página **Clientes**, seleccione **Mostrar filtros**. Se muestra el panel de filtro.

1. Active las casillas situadas junto a los atributos por los que desea filtrar clientes.

1. Quite todos los filtros seleccionando **Borrar filtros** o borre una casilla junto a un atributo seleccionado.

1. Seleccione **Ocultar filtros** para cerrar el panel de filtro.

1. Para guardar los resultados del filtro como un [segmento](segments.md), seleccione **Guardar filtros como segmento**.
   1. Escriba un nombre para el segmento.
   1. Seleccione **Guardar** para guardar el segmento.
   1. Elija si desea ejecutar el segmento ahora seleccionando **Activar** o ejecútelo **Más tarde**.

## <a name="view-customer-details"></a>Ver detalles del cliente

En la página **Clientes**, seleccione un mosaico de cliente para ver los detalles del cliente seleccionado.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Panel de detalles del cliente.":::

Los detalles del cliente incluyen:

**Mosaico de perfil de cliente**: muestra los diferentes valores de la entidad *Cliente* unificada. Si un campo no tiene ningún valor para el perfil de cliente seleccionado, no se mostrará excepto por el campo dirección. El mosaico está estructurado en secciones:

- La primera sección muestra un conjunto predefinido de campos seguidos de todos los campos que forman parte del índice de Buscar y filtrar. Todos los campos relacionados con la dirección se combinan en una sola línea, que aparece incluso si el perfil no tiene información de dirección.
- **Contactos para este cliente** visualización en entornos para cuentas comerciales (B-to-B). Cada contacto se muestra con sus campos. Los campos vacíos están ocultos.
- **Campos adicionales** muestra los campos restantes del cliente seleccionado, excepto los id.
- **Id.** enumera todos los id. por su nombre de entidad correspondiente. Los campos se identifican como id. por su semántica.

**Escala de tiempo de actividad** muestra datos si ha configurado [actividades](activities.md). La vista de escala de tiempo contiene actividades ordenadas cronológicamente del cliente seleccionado, comenzando con la actividad más reciente.

**Información**:

- **Medidas**: aparece si ha configurado [medidas de atributos de cliente](measures.md). Incluyen KPI calculados en torno a sus clientes a nivel de cliente individual.

- **Intereses potenciales, marcas potenciales** aparece si configuró un [enriquecimiento de afinidad de marca o de intereses](enrichment-microsoft.md). Representa intereses y afinidades potenciales para las marcas basadas en otros clientes cuyo perfil es similar al perfil de cliente seleccionado.

Seleccione **Volver a Clientes** para volver a la página **Clientes**.

## <a name="next-steps"></a>Pasos siguientes

[Agregar más orígenes de datos](data-sources.md), [enriquecer perfiles unificados](enrichment-hub.md) o [crear segmentos](segments.md) para trabajar con perfiles de clientes unificados en otras aplicaciones.

[!INCLUDE [footer-include](includes/footer-banner.md)]
