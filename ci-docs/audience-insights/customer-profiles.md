---
title: Ver perfiles de clientes
description: Obtenga una vista combinada de los datos unificados de sus clientes.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596888"
---
# <a name="customer-profiles"></a>Perfiles de clientes

La página **Clientes** muestra una vista combinada de sus clientes, basada en los datos de perfil recopilados de [todos los orígenes de datos](data-sources.md). Los perfiles de cliente están disponibles una vez [creada la entidad Cliente unificado](data-unification.md). Asegúrese de completar el proceso de unificación de datos para obtener vistas más completas de sus clientes. La página también le permite buscar clientes.

Los clientes pueden ser individuos u organizaciones (versión preliminar). Cada perfil de cliente u organización está representado por una ventana. Seleccione una ventana para ver información adicional sobre ese cliente u organización específico. Utilice los controles de paginación en la parte inferior de la lista para ver registros adicionales.

> [!div class="mx-imgBorder"] 
> ![Perfiles de cliente B2C](media/profiles-customers.png "Perfiles de cliente B2C")

Organizaciones (vista previa)
> [!div class="mx-imgBorder"] 
> ![Perfiles de cliente B2B](media/profile-customers-b2b.png "Perfiles de cliente B2B")

> [!NOTE]
> Si no puede ver los mosaicos cuando selecciona **Clientes** en navegación, su Administrador necesita [definir al menos un atributo de que se pueda buscar](search-filter-index.md) en el **Índice de Buscar y filtrar**.

## <a name="search-for-customers"></a>Buscar clientes

Busque clientes introduciendo un nombre o algún otro atributo en el cuadro de búsqueda. La búsqueda solo funciona en la entidad Perfil de cliente creada durante el proceso de unificación de datos.

Como administrador, puede configurar los atributos que se pueden buscar mediante la página de **Índice de Buscar y filtrar**. Si desea obtener más información, consulte el tema sobre [Administrar Índice de Buscar y filtrar](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clientes

Puede filtrar clientes por los campos de entidad Perfil de cliente. Al igual que en la búsqueda, el administrador primero tendrá que definir los campos como filtrables mediante la página **Índice de Buscar y filtrar**.

1. Seleccione **Filtro** en la página **Clientes**.

2. Active las casillas situadas junto a los atributos por los que desea filtrar clientes.

   > [!div class="mx-imgBorder"] 
   > ![Perfiles de clientes](media/profiles-customers3.png "Perfiles de clientes")

3. Elimine sus filtros seleccionando **Limpiar filtros** en la página **Clientes**.

##  <a name="customer-details-page"></a>Panel de detalles del cliente

Seleccione cualquiera de los mosaicos de clientes para abrir la **Página de detalles del cliente**. Esta vista contiene información unificada para el cliente seleccionado.

Los detalles del cliente incluyen:

-   **Mosaico de perfil de cliente:** este mosaico muestra los diferentes valores de la entidad de perfil de cliente unificado. Estos detalles pueden incluir la dirección de correo electrónico, el nombre, la ciudad, etc. 

-   **Intereses potenciales, marcas potenciales:** muestra si configuró un enriquecimiento propio. Representa intereses y afinidades potenciales para las marcas que podría tener un cliente con un perfil similar al de este cliente. Para más información, consulte [Enriquecer los perfiles de los clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md).

-   **Medidas:** muestra si configuró una o más medidas de un tipo específico: medidas de atributos del cliente. Incluyen KPI calculados en torno a sus clientes a nivel de cliente individual. Para obtener más información, consulte [Definir y administrar medidas](measures.md).

-   **Escala de tiempo de actividad:** muestra si ha configurado actividades. La vista de la línea de tiempo contiene actividades ordenadas cronológicamente de este cliente, comenzando por la actividad más reciente. Para obtener más información, consulte [Actividades del cliente](activities.md).

Seleccione **Volver a Clientes** para volver a la página de búsqueda de clientes.

## <a name="next-steps"></a>Pasos siguientes

[Agregar más orígenes de datos](data-sources.md) o [crear segmentos de clientes](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]