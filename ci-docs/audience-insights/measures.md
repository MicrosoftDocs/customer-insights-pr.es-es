---
title: Crear y editar medidas
description: Defina medidas relacionadas con el cliente para analizar y reflejar el rendimiento de ciertas áreas de negocio.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407047"
---
# <a name="define-and-manage-measures"></a>Definir y administrar medidas

**Medidas** representa indicadores clave de rendimiento (KPI) que reflejan el rendimiento y la salud de áreas comerciales específicas. Las informaciones de público proporcionan una experiencia intuitiva para crear diferentes tipos de medidas, utilizando un generador de consultas que no requiere que codifique o valide sus medidas manualmente. Puede realizar un seguimiento de sus medidas empresariales en la página **Inicio**, ver medidas para clientes específicos en la **Tarjeta de cliente** y utilizar medidas para definir segmentos de clientes en la página **Segmentos**.

## <a name="create-a-measure"></a>Crear una medida

Esta sección le guía a través de la creación de una medida desde cero. Puede crear medidas con datos de múltiples orígenes de datos que están conectadas a través de la entidad Cliente. Se aplican algunos [límites de servicio](service-limits.md).

1. En las informaciones de público, vaya a **Medidas**.

2. Seleccione **Nueva medida**.

3. Elija el **Tipo** de medida:

   - **Atributo de cliente**: Un campo único por cliente que refleja una puntuación, un valor o un estado para el cliente. Los atributos de cliente se crean como atributos en una nueva entidad generada por el sistema llamada **Customer_Measure**.

   - **Medida de cliente**: Información sobre el comportamiento del cliente con desglose por dimensiones seleccionadas. Se genera una nueva entidad para cada medida, potencialmente con múltiples registros por cliente.

   - **Medida empresarial**: Realiza un seguimiento del rendimiento y la salud de su negocio. Las medidas empresariales pueden tener dos salidas diferentes: una salida numérica que se muestra en la página **Inicio** o una nueva entidad que se encuentra en la página **Entidades**.

4. Proporcione un **Nombre** y un **Nombre para mostrar** opcional y luego seleccione **Siguiente**.

5. En la sección **Entidades**, seleccione la primera entidad en la lista desplegable. En este punto, debe decidir si se necesitan entidades adicionales como parte de su definición de medida.

   > [!div class="mx-imgBorder"]
   > ![Definición de la medida](media/measure-definition.png "Definición de la medida")

   Para agregar más entidades, seleccione **Agregar entidad** y seleccione las entidades que desea usar para la medida.

   > [!NOTE]
   > Puede seleccionar solo las entidades que tienen relaciones con su entidad inicial. Para obtener más información sobre la definición de relaciones, vea [Relaciones](relationships.md).

6. Opcionalmente, puede configurar variables. En la sección **Variables**, seleccione **Nueva variable**.

   Las variables son cálculos que se realizan en cada uno de los registros seleccionados. Por ejemplo, sumando ventas en el puntos de venta (POS) y en línea para cada uno de los registros de sus clientes.

7. Especifique un **Nombre** para la variable.

8. En el área **Expresión**, elija un campo con el que comenzar el cálculo.

9. Escriba una expresión en el área **Expresión** mientras selecciona más campos para incluir en su cálculo.

   > [!NOTE]
   > Actualmente, solo se admiten expresiones aritméticas. Además, el cálculo de variables no es compatible con entidades de diferentes [rutas de entidad](relationships.md).

10. Seleccione **Listo**.

11. En la sección **Definición de medida**, definirá cómo las entidades elegidas y las variables calculadas se agregan en una nueva entidad o atributo de medida.

12. Seleccione **Nueva dimensión**. Una dimensión se puede considerar como una función *agrupar por*. La salida de datos de su entidad o atributo de Medida se agrupará por todas sus dimensiones definidas.

    > [!div class="mx-imgBorder"]
    > ![Elegir ciclo agregado](media/measures-businessreport-measure-definition2.png "Elegir ciclo agregado")

    Seleccione o ingrese la siguiente información como parte de la definición de su dimensión:

    - **Entidad**: Si define una entidad de Medida, debe incluir al menos un atributo. Si define un atributo de Medida, incluirá solo un atributo de manera predeterminada. En esta selección se trata de elegir la entidad que incluye ese atributo.
    - **Campo**: Elija el atributo específico que se incluirá en su entidad o atributo de Medida.
    - **Cubo**: Elija si desea agregar datos diariamente, mensualmente o anualmente. Es una selección obligatoria solo si ha seleccionado un atributo de tipo Fecha.
    - **Como**: Define el nombre de su nuevo campo.
    - **Nombre para mostrar**: Define el nombre para mostrar del campo.

    > [!NOTE]
    > Su medida empresarial se guardará como una entidad de un solo número y aparecerá en la página **Principal** a menos que agregue más dimensiones a su medida. Después de agregar más dimensiones, la medida *no* se mostrará en la página **Inicio**.

13. Opcionalmente, agregue funciones de agregación. Cualquier agregación que cree produce un nuevo valor en su entidad o atributo de Medidas. Las funciones de agregación compatibles son: **Mín**, **Máx**, **Promedio**, **Mediana**, **Suma**, **Contar únicos**, **Primero** (toma el primer registro de un valor de dimensión) y **Último** (toma el último registro agregado a un valor de dimensión).

14. Seleccione **Guardar** para aplicar los cambios a la medida.

## <a name="manage-your-measures"></a>Administrar sus medidas

Después de crear al menos una medida, verá una lista de medidas en la página **Medidas**.

Encontrará información sobre el tipo de medida, el creador, la fecha y hora de creación, la última fecha y hora de edición, el estado (si la medida está activa, inactiva o con error) y la última fecha y hora de actualización. Cuando selecciona una medida de la lista, puede ver una vista previa de su resultado.

Para actualizar todas sus medidas al mismo tiempo, seleccione **Actualizar todo** sin seleccionar una medida específica.

> [!div class="mx-imgBorder"]
> ![Acciones para gestionar medidas individuales](media/measure-actions.png "Acciones para gestionar medidas individuales")

Alternativamente, seleccione una medida de la lista y realice una de las siguientes acciones:

- Seleccione el nombre de la medida para ver sus detalles.
- **Editar** la configuración de la medida.
- **Cambiar nombre** de la medida.
- **Eliminar** la medida.
- Seleccione los puntos suspensivos (...) y luego **Actualizar** para iniciar el proceso de actualización de la medida.
- Seleccione los puntos suspensivos (...) y luego **Descargar** para obtener un archivo .CSV de la medida.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para tareas/procesos. Además, la mayoría de los procesos [dependen de otros procesos posteriores](system.md#refresh-policies). Puede seleccionar el estado de un proceso para ver los detalles en el progreso de todo el trabajo. Después de seleccionar **Ver detalles** para una de las tareas del trabajo, encontrará información adicional: tiempo de procesamiento, última fecha de procesamiento y todos los errores y advertencias asociados con la tarea.

## <a name="next-step"></a>Siguiente paso

Puede utilizar medidas existentes para crear su primer segmento de clientes en la página **Segmentos**. Para más información, vea [Segmentos](segments.md).
