---
title: Buscar y filtrar perfiles de clientes
description: Encuentre rápidamente información sobre perfiles de clientes unificados y filtre los atributos especificados.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 4445f44b87a5947c3dfcf43ddb49dca9f25b69aa
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354530"
---
# <a name="customer-profiles-search--filter-index"></a>Perfiles de clientes: índice de búsqueda y filtro

El resultado de unificar los datos de sus clientes es una entidad Perfil del Cliente que proporciona una vista unificada de su base total de clientes. Para [encontrar rápidamente información sobre un cliente específico o un grupo de clientes](customer-profiles.md), puede configurar las funciones **Buscar** y **Filtrar** en la página **Clientes**. Siga leyendo para aprender cómo los administradores pueden editar los atributos en la página **Índice de Buscar y filtrar**, que están disponibles para que los usuarios puedan buscarlos y filtrarlos.

   :::image type="content" source="media/search-filter.png" alt-text="Filtro de búsqueda":::

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Agregar campos y especificar atributos

Si es la primera vez que define atributos de búsqueda como administrador, primero debe definir los campos indexados. Le sugerimos que elija todos los atributos por los cuales los usuarios pueden buscar y filtrar clientes en la página **Clientes**. Solo puede especificar atributos que existan en la entidad Perfil del cliente que creó durante el proceso de unificación de datos.

1. Abra la página **Clientes** y seleccione **Índice de Buscar y filtrar**.

2. Seleccione **+Agregar** para especificar los campos indexados.

3. Seleccione en la lista los atributos que desea agregar como campos indexados. Siempre puede agregar más atributos seleccionando **Agregar**. También puede quitar los atributos seleccionados seleccionando el símbolo **Quitar**.

## <a name="explore-the-indexed-customer-fields-table"></a>Explore la tabla de campos de clientes indexados

La siguiente información se proporciona en la tabla.

- **Nombre**: Representa el nombre del atributo tal como aparece en la entidad Perfil del cliente.
- **Tipo de datos**: Especifica si el tipo de datos es una cadena, un número o una fecha.
- **Incluidos en la búsqueda**: Especifica si este atributo se puede utilizar para buscar clientes en la página **Clientes** usando el campo **Buscar**.
- **Agregar filtro**: Control para definir cómo se puede utilizar este atributo para filtrar en la página **Clientes**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Edición de opciones de filtrado para un atributo dado

El menú **Filtrar** de la página **Clientes** puede incluir un número variable de niveles de atributo (por ejemplo, diferentes grupos de edad para filtrar clientes).

1. Seleccione **Agregar filtro** para un atributo dado en la página **Índice de Buscar y filtrar**. Puede definir el número de resultados y el orden en que se organizarán. Dependiendo del tipo de datos del atributo, aparece uno de los siguientes paneles.

- Atributos de tipo cadena: Especifique el número de resultados deseados en el panel **Opciones de filtro de cadena** y la directiva de orden mediante la cual se organizarán.

- Atributos de tipo numérico: Especifique los intervalos incluidos en el panel **Opciones de filtro de número** y la directiva de orden mediante la cual se organizarán.

- Atributos de tipo fecha: Especifique los intervalos incluidos en el panel **Opciones de filtro de fecha** y la directiva de orden mediante la cual se organizarán.

2. Seleccione **Guardar** para aplicar los cambios.

3. Seleccione **Ejecutar** una vez que esté listo para aplicar su configuración. Una vez procesados los cambios, los encontrará en las [ tarjetas de cliente de la página del cliente](customer-profiles.md). 

## <a name="next-steps"></a>Pasos siguientes

Revise la [página de perfiles unificados](customer-profiles.md) para buscar perfiles o usar los campos indexados para ver un subconjunto de todos los perfiles unificados.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
