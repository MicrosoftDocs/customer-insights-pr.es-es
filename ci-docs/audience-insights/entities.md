---
title: Entidades y conjuntos de datos
description: Ver los datos en la página Entidades.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596428"
---
# <a name="entities-in-audience-insights"></a>Entidades en la información de público

Después de [configurar los orígenes de datos](data-sources.md), vaya a la página **Entidades** para evaluar la calidad de los datos procesados. Las entidades se consideran conjuntos de datos. Múltiples capacidades de Dynamics 365 Customer Insights se construyen alrededor de estas entidades. Revisarlas de cerca puede ayudarle a validar la salida de esas capacidades.

La página **Entidades** enumera entidades e incluye varias columnas:

- **Nombre**: el nombre de la entidad de datos. Si ve un símbolo de advertencia junto a un nombre de entidad, significa que los datos de esa entidad no se cargaron correctamente.
- **Origen**: El tipo de origen de datos que procesó la entidad
- **Creada por**: Nombre de la persona que creó la entidad.
- **Creado**: Fecha y hora de creación de la entidad
- **Actualizada por**: Nombre de la persona que actualizó la entidad.
- **Última actualización**: Fecha y hora de la última actualización de la entidad
- **Última actualización**: fecha y hora de la última actualización de datos

## <a name="exploring-a-specific-entitys-data"></a>Explorar los datos de una entidad específica

Seleccione una entidad para explorar los diferentes campos y registros incluidos en esa entidad.

> [!div class="mx-imgBorder"]
> ![Seleccionar una entidad](media/data-manager-entities-data.png "Seleccionar una entidad")

- La pestaña **Datos** está seleccionada de forma predeterminada y muestra una tabla con detalles sobre registros individuales de la entidad.

> [!div class="mx-imgBorder"]
> ![Tabla de campos](media/data-manager-entities-fields.PNG "Tabla de campos")

- La pestaña **Campos** muestra una tabla para revisar los detalles de la entidad seleccionada, como nombres de campo, tipos de datos y tipos. La columna **Tipo** muestra los tipos asociados a Common Data Model, que son definidos automáticamente por el sistema o [asignados manualmente](map-entities.md) por los usuarios. Se trata de tipos semánticos que pueden diferir de los tipos de datos de los atributos: por ejemplo, el campo *Correo electrónico* siguiente tiene un tipo de datos *Texto*, pero su tipo de Common Data Model (semántico) puede ser *Email* o *EmailAddress*.

> [!NOTE]
> Ambas tablas muestran solo un ejemplo de los datos de la entidad. Para ver el conjunto de datos completo, vaya a la página **Orígenes de datos**, seleccione una entidad, seleccione **Editar** y, a continuación, vea los datos de esta entidad con el editor de Power Query como se explica en [Orígenes de datos](data-sources.md).

Para obtener más información sobre los datos procesados en la entidad, la columna **Resumen** proporciona algunas características importantes de los datos, como nulos, valores que faltan, valores únicos, recuentos y distribuciones, según corresponda a los datos.

Seleccione el icono de gráfico para ver el resumen de los datos.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumen](media/data-manager-entities-summary.png "Tabla de resumen de datos")

### <a name="next-step"></a>Paso siguiente

Consulte el tema [Unificar](data-unification.md) para obtener información sobre cómo *asignar*, *emparejar* y *combinar* los datos procesados.


[!INCLUDE[footer-include](../includes/footer-banner.md)]