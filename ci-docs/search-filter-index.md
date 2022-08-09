---
title: Administrar el índice de búsqueda y filtro para perfiles de clientes
description: Encuentre rápidamente información sobre perfiles de clientes unificados y filtre los atributos especificados.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187930"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Administrar el índice de búsqueda y filtro para perfiles de clientes

El resultado de unificar los datos de clientes es una entidad *Cliente* que proporciona una vista unificada de su base total de clientes. Para que los usuarios [encuentren rápidamente información sobre un cliente específico o un grupo de clientes](customer-profiles.md), un administrador debe configurar las capacidades **Buscar** y **Filtrar** de la página **Clientes**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtro de búsqueda":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definir atributos de búsqueda y campos indexados

Si es la primera vez que define atributos de búsqueda como administrador, defina primero los campos indexados. Le sugerimos que elija todos los atributos por los cuales los usuarios pueden buscar y filtrar clientes en la página **Clientes**. Solo pueden especificarse atributos que existan en la entidad *Cliente* que creó durante el proceso de unificación de datos.

1. Vaya a **Clientes** y seleccione **Índice de Buscar y filtrar**.

1. Seleccione **+Agregar**.

1. Seleccione en la lista los atributos que desea agregar como campos indexados y haga clic en **Aplicar**.

1. Para agregar más atributos, seleccione **Agregar**. Para eliminar un atributo seleccionado, seleccione el atributo y luego **Eliminar**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Página Índice de Buscar y filtrar":::

1. Seleccione **Ejecutar** una vez que esté listo para aplicar su configuración de búsqueda y filtro. Una vez procesados los cambios, los verá en las [tarjetas de cliente de la página del cliente](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definir las opciones de filtrado para un atributo dado

Configure los campos que pueden utilizarse para filtrar clientes en la página **Clientes**.

1. Vaya a **Clientes** y seleccione **Índice de Buscar y filtrar**.

1. Seleccione un atributo y **Agregar filtro**. Defina el número de resultados y el orden en que se organizarán. Dependiendo del tipo de datos del atributo, aparece uno de los siguientes paneles.

   - Atributos de tipo cadena: Especifique el número de resultados deseados en el panel **Filtro de cadena** y la directiva de orden mediante la cual se organizarán.

   - Atributos de tipo numérico: Especifique los intervalos incluidos en el panel **Filtro de número** y la directiva de orden mediante la cual se organizarán.

   - Atributos de tipo fecha: Especifique los intervalos incluidos en el panel **Filtro de fecha** y la directiva de orden mediante la cual se organizarán.

1. Seleccione **Aceptar**. Repita para todos los atributos por los que desea filtrar.

1. Seleccione **Ejecutar** una vez que esté listo para aplicar su configuración de búsqueda y filtro. Una vez procesados los cambios, los verá en las [tarjetas de cliente de la página del cliente](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Ver campos de cliente indexados

La página **Índice de búsqueda y filtrado** muestra la siguiente información:

- **Nombre**: representa el nombre del atributo tal y como aparece en la entidad *Cliente*.
- **Tipo de datos**: Especifica si el tipo de datos es una cadena, un número o una fecha.
- **Incluidos en la búsqueda**: Especifica si este atributo se puede utilizar para buscar clientes en la página **Clientes** usando el campo **Buscar**.
- **Agregar filtro**: Control para definir cómo se puede utilizar este atributo para filtrar en la página **Clientes**.

## <a name="next-steps"></a>Pasos siguientes

Revise la [página de perfiles unificados](customer-profiles.md) para buscar perfiles o usar los campos indexados para ver un subconjunto de todos los perfiles unificados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
