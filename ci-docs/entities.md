---
title: Entidades en Customer Insights
description: Ver los datos en la página Entidades.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610119"
---
# <a name="entities-in-customer-insights"></a>Entidades en Customer Insights

Después de [configurar los orígenes de datos](data-sources.md), vaya a la página **Entidades** para evaluar la calidad de los datos procesados. Las entidades se consideran conjuntos de datos. Múltiples capacidades de Dynamics 365 Customer Insights se construyen alrededor de estas entidades. Revisarlas de cerca puede ayudarle a validar la salida de esas capacidades.

A medida que trabaja en Customer Insights para enriquecer sus datos o crear segmentos, medidas y actividades, las entidades que se crean a partir de esas acciones se muestran en la página **Entidades**.

## <a name="view-a-list-of-entities"></a>Ver una lista de entidades

Vaya a **Datos** > **Entidades** para ver una lista de entidades. La siguiente información se muestra para cada entidad.

- **Nombre**: nombre de la entidad de datos. Si ve un símbolo de advertencia junto a un nombre de entidad, significa que los datos de esa entidad no se cargaron correctamente.
- **Origen**: tipo de origen de datos que ingirió la entidad.
- **Actualizado**: la última vez que se actualizó la entidad.
- **Estado**: detalles sobre la última actualización de la entidad.

## <a name="explore-a-specific-entitys-data"></a>Explorar los datos de una entidad específica

1. Vaya a **Datos** > **Entidades**.
1. Seleccione una entidad para abrir la página de detalles.  
1. Explore los diferentes campos y registros incluidos para esa entidad.

- La pestaña **Atributos** está seleccionada de forma predeterminada y muestra detalles de la entidad seleccionada, como nombres de campo, tipos de datos y tipos. La columna **Tipo** muestra los tipos asociados a Common Data Model, que son definidos automáticamente por el sistema o [asignados manualmente](map-entities.md) por los usuarios. Estos tipos son tipos semánticos que pueden diferir de los tipos de datos de los atributos. Por ejemplo, el campo *Correo electrónico* tiene debajo un tipo de datos *Cadena* pero su tipo (semántico) de Common Data Model podría ser *Correo electrónico*, *EmailAddress* o *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabla de campos.":::

   > [!NOTE]
   > Esta página muestra solo un ejemplo de los datos de su entidad. Para ver el conjunto de datos completo, vaya a la página **Orígenes de datos**, seleccione una entidad, seleccione **Editar** y, a continuación, vea los datos de esta entidad con el editor de Power Query como se explica en [Orígenes de datos](data-sources.md).

   Para obtener más información sobre los datos ingeridos en la entidad, la columna **Resumen** proporciona algunas características importantes de los datos, como nulos, valores que faltan, valores únicos, recuentos y distribuciones, lo que corresponda a los datos. Seleccione el icono de gráfico para ver el resumen de los datos.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabla de resumen de datos.":::

- La pestaña **Datos** muestra detalles de registros individuales de la entidad. Los detalles enumerados dependen del tipo de datos de la entidad.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Selecciona una entidad.":::

- La pestaña **Informes** (disponible para algunas entidades) le permite visualizar sus datos mediante la creación de un informe, lo que incluye estas columnas:

  - **Nombre del informe**: nombre del informe.
  - **Creada por**: Nombre de la persona que creó la entidad.
  - **Creado**: Fecha y hora de creación de la entidad.
  - **Editada por**: Nombre de la persona que modificó la entidad.
  - **Editada**: Fecha y hora de modificación de la entidad.

[!INCLUDE [footer-include](includes/footer-banner.md)]
