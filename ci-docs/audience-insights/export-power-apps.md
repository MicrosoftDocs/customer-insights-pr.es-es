---
title: Conector de Power Apps
description: Conectar con Power Apps y Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598176"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector de Microsoft Power Apps (vista previa)

Lleve perfiles de clientes unificados a sus aplicaciones personalizadas con Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectar Power Apps y Dynamics 365 Customer Insights

Customer Insights es una de las muchas [fuentes disponibles para datos en Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte la documentación de Power Apps para aprender a [agregar una conexión de datos a una aplicación](/powerapps/maker/canvas-apps/add-data-connection). Le recomendamos que también revise [cómo Power Apps usa la delegación para manejar grandes conjuntos de datos en aplicaciones de lienzo](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponibles

Después de agregar Customer Insights como una conexión de datos, puede elegir las siguientes entidades en Power Apps:

- Cliente: para utilizar datos del [perfil de cliente unificado](customer-profiles.md).
- UnifiedActivity: para mostrar la [escala de tiempo de la actividad](activities.md) en la aplicación.

## <a name="limitations"></a>Limitaciones

### <a name="retrievable-entities"></a>Entidades recuperables

Solo puede recuperar las entidades **Cliente**, **UnifiedActivity** y **Segmentos** a través del conector de Power Apps. Se muestran otras entidades porque el conector subyacente las admite mediante desencadenadores en Power Automate.  

### <a name="delegation"></a>Delegación

La delegación funciona para la entidad Cliente y la entidad UnifiedActivity. 

- Delegación para la entidad **Cliente**: para usar la delegación para esta entidad, los campos deben estar indexados en [Índice de búsqueda y filtro](search-filter-index.md).  

- Delegación para **UnifiedActivity**: La delegación de esta entidad solo funciona para los campos **ActivityId** y **CustomerId**.  

- Para obtener más información sobre la delegación, consulte [Funciones y operaciones delegables de Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Ejemplo de control de galería

Por ejemplo, agregue perfiles de cliente a un [control de galería](/powerapps/maker/canvas-apps/add-gallery).

1. Agregue un control de **Galería** a una aplicación que esté creando.

> [!div class="mx-imgBorder"]
> ![Agregar un elemento de galería](media/connector-powerapps9.png "Agregar un elemento de galería")

1. Seleccione **Cliente** como origen de datos para elementos.

    > [!div class="mx-imgBorder"]
    > ![Seleccionar un origen de datos](media/choose-datasource-powerapps.png "Seleccionar un origen de datos")

1. Puede cambiar el panel de datos a la derecha para seleccionar qué campo mostrará la entidad de Cliente en la galería.

1. Si desea mostrar cualquier campo del cliente seleccionado en la galería, complete la propiedad Texto de una etiqueta:  **{Name_of_the_gallery}.Selected.{property_name}**

    Ejemplo: Gallery1.Selected.address1_city

1. Para mostrar la escala de tiempo unificada para un cliente, agregue un elemento Galería y agregue la propiedad Items: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Ejemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]