---
title: Ver perfiles de clientes
description: Obtenga una vista combinada de los datos unificados de sus clientes.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 07d2206372f89cd7dcd9df84c87024a6f87d5eac
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623290"
---
# <a name="customer-profiles"></a>Perfiles de clientes

La página **Clientes** muestra una vista combinada de sus perfiles de clientes unificados. Los perfiles de clientes están disponibles una vez que [creó la entidad de cliente unificada](data-unification.md). La página le permite buscar clientes y definir el índice para esa búsqueda.

Los clientes pueden ser personas u organizaciones. Cada perfil de cliente se representa con una ventana. Utilice los controles de paginación para obtener más registros. La tarjeta muestra campos de la entidad *Cliente* definida en el **Índice de Buscar y filtrar**. Seleccione una ventana para ver los datos del cliente seleccionado en una página dedicada llamada [Página de detalles del cliente](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Página de clientes que muestra ventanas de resultados](media/customers-page-result-tiles-B2C.png "Página de clientes que muestra ventanas de resultados")

> [!NOTE]
> Si no puede ver las ventanas cuando selecciona **Clientes** en la navegación, su administrador debe [definir al menos un atributo de búsqueda](search-filter-index.md) en el **Índice de Buscar y filtrar**.

## <a name="search-for-customers"></a>Buscar clientes

Busque clientes introduciendo un nombre o algún otro atributo en el cuadro de búsqueda. La búsqueda solo funciona dentro de la entidad _Cliente_ creada durante el proceso de unificación de datos.

Como administrador, puede configurar los atributos que se pueden buscar mediante la página de **Índice de Buscar y filtrar**. Para obtener más información, vaya a [Administrar índice de Buscar y filtrar](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar de clientes

Puede filtrar clientes por campos de entidad _Cliente_. Al igual que en la búsqueda, el administrador primero tendrá que definir los campos como filtrables mediante la página **Índice de Buscar y filtrar**.

1. Seleccione **Mostrar filtros** en la página **Clientes**.

1. Active las casillas situadas junto a los atributos por los que desea filtrar clientes.

1. Elimine sus filtros seleccionando **Limpiar filtros** en la página **Clientes**.

## <a name="customer-details-page"></a>Panel de detalles del cliente

Seleccione cualquiera de los mosaicos de clientes para abrir la **Página de detalles del cliente**. Esta vista contiene información unificada para el cliente seleccionado. Los detalles del cliente incluyen el siguiente contenido:

**Ventana de perfil de cliente**: Esta ventana muestra los diferentes valores de la entidad _Cliente_ unificada. Si un campo no tiene ningún valor para el perfil de cliente seleccionado, no se mostrará. La ventana está estructurado en secciones:  
  - La primera sección muestra un conjunto predefinido de campos seguidos de todos los campos que forman parte del índice de Buscar y filtrar. Todos los campos relacionados con la dirección se combinan en una sola línea si el perfil contiene dichos campos. 
  - **Contactos para este cliente**: En entornos para cuentas de negocio, verá todos los contactos relacionados para este cliente en la segunda sección. Cada contacto se muestra con sus campos. Los campos vacíos están ocultos.
  - **Campos adicionales**: Muestra los campos restantes del cliente seleccionado, excepto los ID. 
  - **Identificaciones**: Enumera todos los ID bajo su nombre de entidad correspondiente. Los campos se identifican como ID por su semántica, que los clasifica como tales.

**Escala de tiempo de actividad**: Muestra datos si ha configurado actividades. La vista de escala de tiempo contiene actividades ordenadas cronológicamente del cliente seleccionado, comenzando con la actividad más reciente. Para obtener más información, vaya a [Actividades del cliente](activities.md).

**Información**:  
  - **Medidas**: Muestra si configuró una o más medidas de atributos del cliente. Incluyen KPI calculados en torno a sus clientes a nivel de cliente individual. Para obtener más información, vaya a [Definir y gestionar medidas](measures.md).

  - **Intereses potenciales, marcas potenciales**: Muestra si configuró un enriquecimiento de afinidad de marca o de intereses. Representa intereses y afinidades potenciales para las marcas basadas en otros clientes cuyo perfil es similar al perfil de cliente seleccionado. Para obtener más información, vaya a [Enriquecer perfiles de clientes con afinidades de marca e intereses](enrichment-microsoft.md).

Para volver a la página de búsqueda de clientes, seleccione **Volver a clientes**.

## <a name="next-steps"></a>Pasos siguientes

[Agregar más orígenes de datos](data-sources.md), [enriquecer perfiles unificados](enrichment-hub.md) o [crear segmentos](segments.md) para trabajar con perfiles de clientes unificados en otras aplicaciones.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
