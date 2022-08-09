---
title: Entidades en Customer Insights
description: Ver los datos en la página Entidades.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183606"
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

## <a name="entity-specific-information"></a>Información específica de la entidad

La siguiente sección proporciona información sobre algunas entidades creadas por el sistema.

### <a name="corrupted-data-sources"></a>Orígenes de datos dañados

Los campos de un origen de datos ingerido pueden contener datos dañados. Los registros con campos dañados se exponen en entidades creadas por el sistema. Saber cuáles son los registros dañados ayuda a identificar qué datos hay que revisar y actualizar en el sistema de origen. Después de la siguiente actualización del origen de datos, los registros corregidos se transfieren a Customer Insights y se pasan a los procesos posteriores. 

Por ejemplo, una columna 'cumpleaños' tendrá el tipo de datos establecido como 'fecha'. El registro de un cliente tiene la fecha de nacimiento establecida como '01/01/19777'. El sistema marcará este registro como dañado. Ahora, alguien puede cambiar la fecha de nacimiento en el sistema de origen a '1977'. Después de una actualización automática de los orígenes de datos, el campo tiene un formato válido y el registro se eliminará de la entidad dañada.

Vaya a **Datos** > **Entidades** y busque las entidades dañadas en la sección **Sistema**. Esquema de nomenclatura de entidades dañadas: 'DataSourceName_EntityName_corrupt'. Seleccione una entidad dañada para identificar todos los campos dañados y la razón a nivel de registro individual.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivo de los daños.":::

Customer Insights aún procesa registros dañados. Sin embargo, esto puede causar problemas al trabajar con datos unificados.

Las siguientes comprobaciones se ejecutan en los datos ingeridos para exponer registros dañados:

- El valor de un campo no coincide con el tipo de datos de su columna.
- Los campos contienen caracteres que hacen que las columnas no coincidan con el esquema esperado. Por ejemplo: comillas con formato incorrecto, comillas sin escape o caracteres de nueva línea.
- Si hay columnas datetime/date/datetimeoffset, su formato debe especificarse en el modelo si no sigue el formato ISO estándar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
