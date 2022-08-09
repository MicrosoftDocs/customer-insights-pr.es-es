---
title: Conector de Power Apps (vista previa)
description: Conectar con Power Apps y Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196921"
---
# <a name="power-apps-connector-preview"></a>Conector de Power Apps (vista previa)

Lleve perfiles de clientes unificados a sus aplicaciones personalizadas con Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectar Power Apps y Dynamics 365 Customer Insights

Customer Insights es una de las muchas [fuentes disponibles para datos en Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte la documentación de Power Apps para aprender a [agregar una conexión de datos a una aplicación](/powerapps/maker/canvas-apps/add-data-connection). Le recomendamos que también revise [cómo Power Apps usa la delegación para manejar grandes conjuntos de datos en aplicaciones de lienzo](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponibles

Después de agregar Customer Insights como una conexión de datos, puede elegir las siguientes entidades en Power Apps:

- **Cliente**: para utilizar datos del [perfil de cliente unificado](customer-profiles.md).
- **UnifiedActivity**: para mostrar la [escala de tiempo de actividad](activities.md) en la aplicación.
- **ContactProfile**: para mostrar los contactos de un cliente. Esta entidad solo está disponible en entornos de Customer Insights para cuentas empresariales.

## <a name="limitations"></a>Limitaciones

### <a name="retrievable-entities"></a>Entidades recuperables

Solo puede recuperar las entidades **Cliente**, **UnifiedActivity**, **Segmentos** y **ContactProfile** entidades a través del conector Power Apps. ContactProfile solo está disponible en entornos de Customer Insights para cuentas de negocio. Se muestran otras entidades porque el conector subyacente las admite mediante desencadenadores en Power Automate.

Puede hacer un máximo de 100 llamadas cada 60 segundos. Puede llamar al punto de conexión de API varias veces usando el parámetro $skip. [Obtenga más información sobre el parámetro $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegación

La delegación funciona para la entidad **Cliente** y la entidad **UnifiedActivity**.

- Delegación para la entidad **Cliente**: para usar la delegación para esta entidad, los campos deben estar indexados en el [Índice de búsqueda y filtro](search-filter-index.md).  
- Delegación para **UnifiedActivity**: La delegación de esta entidad solo funciona para los campos **ActivityId** y **CustomerId**.  
- Delegación para **ContactProfile**: La delegación de esta entidad solo funciona para los campos **ContactId** y **CustomerId**. ContactProfile solo está disponible en entornos de Customer Insights para cuentas de negocio.

Para obtener más información sobre la delegación, vaya a [funciones y operaciones delegables de Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Ejemplo de control de galería

Opcionalmente, agregue perfiles de clientes a un [control de galería](/powerapps/maker/canvas-apps/add-gallery).

1. Agregue un control de **galería** a una aplicación que esté creando.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Agregar un elemento de galería.":::

1. Seleccione **Cliente** como origen de datos para elementos.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Seleccionar un origen de datos.":::

1. Cambie el panel de datos de la derecha para seleccionar qué campo mostrará la entidad Cliente en la galería.

1. Si desea mostrar cualquier campo del cliente seleccionado en la galería, complete la propiedad **Texto** de una etiqueta utilizando **{Name_of_the_gallery}.Selected.{property_name}**  
    - Por ejemplo: _Gallery1.Selected.address1_city_

1. Para mostrar la escala de tiempo unificada para un cliente, agregue un elemento de galería y agregue la propiedad **Items** utilizando **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Por ejemplo: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
