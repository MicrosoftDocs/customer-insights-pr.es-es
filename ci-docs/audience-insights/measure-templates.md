---
title: Crear medidas a partir de plantillas
description: Defina las medidas usando plantillas para casos de uso comunes.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529422"
---
# <a name="use-a-template-to-build-a-measure"></a>Usar una plantilla para construir una medida

Puede utilizar plantillas predefinidas de [medidas](measures.md) de uso común para crearlas. Las descripciones detalladas de las plantillas y una experiencia guiada le ayudan a crear medidas de manera eficiente. Las plantillas se basan en datos asignados de la entidad *Actividad unificada*. Así que asegúrese de haber configurado [actividades del cliente](activities.md) antes de crear una medida a partir de una plantilla.

Para crear medidas personalizadas, consulte [Usar el generador de medidas para crear medidas desde cero](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

Plantillas de medida disponibles: 
- Valor medio de transacción (ATV)
- Valor total de la transacción
- Ingresos medios diarios
- Ingresos medios anuales
- Recuento de transacciones
- Puntos de fidelización ganados
- Puntos de fidelización canjeados
- Saldo de puntos de fidelización
- Vida útil activa del cliente
- Duración de suscripción de fidelización
- Tiempo desde la última compra

## <a name="build-a-new-measure-using-a-template"></a>Crear una nueva medida usando una plantilla

1. Vaya a **Medidas**.

1. Seleccione **Nuevo** y seleccione **Elegir una plantilla**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla del menú desplegable al crear una nueva medida con resaltado en la plantilla.":::

1. Encuentre la plantilla que se adapte a sus necesidades y seleccione **Elegir plantilla**.

1. Revise los datos requeridos y seleccione **Comenzar** si tiene todos los datos en su lugar.

1. Seleccione **Editar detalles** junto al nombre de la medida. Especifique un nombre para la medida. Opcionalmente, agregue [etiquetas](work-with-tags-columns.md#manage-tags) a la nueva medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar cuadro de diálogo de detalles":::

1. Seleccione **Listo**.

1. En la sección **Establecer período de tiempo**, defina el período de tiempo de los datos a utilizar. Elija si desea que la nueva medida cubra todo el conjunto de datos seleccionando **Todo el tiempo** o si desea que la medida se centre en un **Período de tiempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que muestra la sección del período de tiempo al configurar una medida a partir de una plantilla.":::

1. En la siguiente sección, seleccione **Agregar datos** para elegir las actividades y asignar los datos correspondientes a partir de su entidad *Actividad unificada*.

    1. Paso 1 de 2: En **Tipo de actividad**, elija el tipo de entidad que desea utilizar. Para **Actividades**, seleccione las entidades que desea asignar.
    1. Paso 2 de 2: Elija el atributo de la entidad *Actividad unificada* para el componente requerido por la fórmula. Por ejemplo, para el valor de transacción promedio, es el atributo que representa el valor de la transacción. Para **Marca de tiempo de la actividad**, elija el atributo de la entidad Actividad unificada que representa la fecha y hora de la actividad.
   
1. Una vez que la asignación de datos se haya realizado correctamente, puede ver el estado como **Completo** y el nombre de las actividades y atributos asignadas.

1. Ahora puede seleccionar **Ejecutar** para calcular los resultados de la medida. Para refinarlo más tarde, seleccione **Guardar borrador**.

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

Esta función solo está disponible para medidas creadas en entornos con clientes individuales como público de destino principal.

---
