---
title: Conector de Power Apps
description: Conectar con Power Apps y Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ae2a3b7c05e9ed860da31853c47af2aec8634e7a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229053"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector de Microsoft Power Apps (vista previa)

Lleve perfiles de clientes unificados a sus aplicaciones personalizadas con Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectar Power Apps y Dynamics 365 Customer Insights

Customer Insights es una de las muchas [fuentes disponibles para datos en Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte la documentación de Power Apps para aprender a [agregar una conexión de datos a una aplicación](/powerapps/maker/canvas-apps/add-data-connection). Le recomendamos que también revise [cómo Power Apps usa la delegación para manejar grandes conjuntos de datos en aplicaciones de lienzo](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponibles

Después de agregar Customer Insights como una conexión de datos, puede elegir las siguientes entidades en Power Apps:

- **Cliente**: para utilizar datos del [perfil de cliente unificado](customer-profiles.md).
- **UnifiedActivity**: para mostrar la [escala de tiempo de actividad](activities.md) en la aplicación.
- **ContactProfile**: para mostrar los contactos de un cliente. Esta entidad solo está disponible en entornos de conclusiones del público para cuentas empresariales.

## <a name="limitations"></a>Limitaciones

### <a name="retrievable-entities"></a>Entidades recuperables

Solo puede recuperar las entidades **Cliente**, **UnifiedActivity**, **Segmentos** y **ContactProfile** entidades a través del conector Power Apps. ContactProfile solo está disponible en entornos de conclusiones del público para cuentas de negocio. Se muestran otras entidades porque el conector subyacente las admite mediante desencadenadores en Power Automate.

### <a name="delegation"></a>Delegación

La delegación funciona para la entidad **Cliente** y la entidad **UnifiedActivity**. 

- Delegación para la entidad **Cliente**: para usar la delegación para esta entidad, los campos deben estar indexados en [Índice de búsqueda y filtro](search-filter-index.md).  
- Delegación para **UnifiedActivity**: La delegación de esta entidad solo funciona para los campos **ActivityId** y **CustomerId**.  
- Delegación para **ContactProfile**: La delegación de esta entidad solo funciona para los campos **ContactId** y **CustomerId**. ContactProfile solo está disponible en entornos de conclusiones del público para cuentas de negocio.

Para obtener más información sobre la delegación, vaya a [funciones y operaciones delegables de Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Ejemplo de control de galería

Puede agregar perfiles de clientes a un [control de galería](/powerapps/maker/canvas-apps/add-gallery).

1. Agregue un control de **galería** a una aplicación que esté creando.

    > [!div class="mx-imgBorder"]
    > ![Agregar un elemento de galería.](media/connector-powerapps9.png "Agregue un elemento de galería.")

2. Seleccione **Cliente** como origen de datos para elementos.

    > [!div class="mx-imgBorder"]
    > ![Seleccionar un origen de datos.](media/choose-datasource-powerapps.png "Seleccione un origen de datos.")

3. Puede cambiar el panel de datos a la derecha para seleccionar qué campo mostrará la entidad de Cliente en la galería.

4. Si desea mostrar cualquier campo del cliente seleccionado en la galería, complete la propiedad **Texto** de una etiqueta utilizando **{Name_of_the_gallery}.Selected.{property_name}**  
    - Por ejemplo: _Gallery1.Selected.address1_city_

5. Para mostrar la escala de tiempo unificada para un cliente, agregue un elemento de galería y agregue la propiedad **Items** utilizando **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Por ejemplo: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
