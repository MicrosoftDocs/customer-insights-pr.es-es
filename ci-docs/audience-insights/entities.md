---
title: Entidades y conjuntos de datos
description: Ver los datos en la página Entidades.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732102"
---
# <a name="entities-in-audience-insights"></a>Entidades en la información de público

Después de [configurar los orígenes de datos](data-sources.md), vaya a la página **Entidades** para evaluar la calidad de los datos procesados. Las entidades se consideran conjuntos de datos. Múltiples capacidades de Dynamics 365 Customer Insights se construyen alrededor de estas entidades. Revisarlas de cerca puede ayudarle a validar la salida de esas capacidades.

La página **Entidades** enumera entidades e incluye varias columnas:

- **Nombre**: el nombre de la entidad de datos. Si ve un símbolo de advertencia junto a un nombre de entidad, significa que los datos de esa entidad no se cargaron correctamente.
- **Origen**: El tipo de origen de datos que procesó la entidad
- **Creada por**: Nombre de la persona que creó la entidad.
- **Creado**: Fecha y hora de creación de la entidad
- **Actualizado**: Nombre de la persona que actualizó la entidad
- **Estado**: Detalles sobre la última actualización de la entidad

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorar los datos de una entidad específica

Seleccione una entidad para explorar los diferentes campos y registros incluidos en esa entidad.

> [!div class="mx-imgBorder"]
> ![Selecciona una entidad.](media/data-manager-entities-data.png "Seleccionar una entidad")

- La pestaña **Datos** muestra una tabla que enumera detalles sobre los registros individuales de la entidad.

> [!div class="mx-imgBorder"]
> ![Tabla de campos.](media/data-manager-entities-fields.PNG "Tabla de campos")

- La pestaña **Atributos** está seleccionada de forma predeterminada y muestra una tabla para revisar los detalles de la entidad seleccionada, como nombres de campo, tipos de datos y tipos. La columna **Tipo** muestra los tipos asociados a Common Data Model, que son definidos automáticamente por el sistema o [asignados manualmente](map-entities.md) por los usuarios. Estos tipos son tipos semánticos que pueden diferir de los tipos de datos de los atributos. Por ejemplo, el campo *Correo electrónico* tiene debajo un tipo de datos *Texto* pero su tipo (semántico) de Common Data Model podría ser *Correo electrónico* o *Dirección de correo electrónico*.

> [!NOTE]
> Ambas tablas muestran solo un ejemplo de los datos de la entidad. Para ver el conjunto de datos completo, vaya a la página **Orígenes de datos**, seleccione una entidad, seleccione **Editar** y, a continuación, vea los datos de esta entidad con el editor de Power Query como se explica en [Orígenes de datos](data-sources.md).

Para obtener más información sobre los datos procesados en la entidad, la columna **Resumen** proporciona algunas características importantes de los datos, como nulos, valores que faltan, valores únicos, recuentos y distribuciones, según corresponda a los datos.

Seleccione el icono de gráfico para ver el resumen de los datos.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumen.](media/data-manager-entities-summary.png "Tabla de resumen de datos")

## <a name="entity-specific-information"></a>Información específica de la entidad

La siguiente sección proporciona información sobre algunas entidades creadas por el sistema.

### <a name="corrupted-data-sources"></a>Orígenes de datos dañados

Los campos de un origen de datos ingerido pueden contener datos dañados. Los registros con campos dañados se exponen en entidades creadas por el sistema. Saber cuáles son los registros dañados ayuda a identificar qué datos hay que revisar y actualizar en el sistema de origen. Después de la siguiente actualización del origen de datos, los registros corregidos se transfieren a Customer Insights y se pasan a los procesos posteriores. 

Por ejemplo, una columna 'cumpleaños' tendrá el tipo de datos establecido como 'fecha'. El registro de un cliente tiene la fecha de nacimiento establecida como '01/01/19777'. El sistema marcará este registro como dañado. Ahora, alguien puede cambiar la fecha de nacimiento en el sistema de origen a '1977'. Después de una actualización automática de los orígenes de datos, el campo tiene un formato válido y el registro se eliminará de la entidad dañada. 

Vaya a **Datos** > **Entidades** y busque las entidades dañadas en la sección **Sistema**. Esquema de nomenclatura de entidades dañadas: 'DataSourceName_EntityName_corrupt'.

Customer Insights aún procesa registros dañados. Sin embargo, esto puede causar problemas al trabajar con datos unificados.

Las siguientes comprobaciones se ejecutan en los datos ingeridos para exponer registros dañados: 

- El valor de un campo no coincide con el tipo de datos de su columna.
- Los campos contienen caracteres que hacen que las columnas no coincidan con el esquema esperado. Por ejemplo: comillas con formato incorrecto, comillas sin escape o caracteres de nueva línea.
- Si hay columnas datetime/date/datetimeoffset, si su formato no sigue el formato ISO estándar, debe especificarse en el modelo.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
