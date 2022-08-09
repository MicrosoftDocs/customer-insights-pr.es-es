---
title: Crear medidas con el generador de medidas
description: Cree medidas desde cero para analizar las métricas clave de su negocio.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170886"
---
# <a name="create-measures-with-measure-builder"></a>Crear medidas con el generador de medidas

El generador de medidas le permite definir cálculos mediante operadores matemáticos, funciones de agregación y filtros. Defina medidas con atributos de entidades que estén relacionadas con la entidad unificada *Cliente*.

La creación de medidas en entornos B2C y B2B funciona de la misma manera. Sin embargo, si su entorno B2B [usa cuentas con jerarquías](relationships.md#set-up-account-hierarchies), puede optar por agregar la medida a través de subcuentas relacionadas.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

Cree medidas a nivel de clientes individuales (atributo de cliente, medida de cliente) o a nivel de empresa/organización (medida de empresa). El atributo de cliente y la medida de cliente le permiten seguir el rendimiento por cliente. Por ejemplo, el gasto total de cada cliente. Las medidas de negocio siguen el rendimiento de cada negocio. Por ejemplo, los ingresos totales de la empresa.

- Atributo del cliente: genera la salida como un nuevo atributo, que se guarda como una nueva columna en la entidad generada por el sistema llamada *Medida_cliente*. Cuando se actualiza un atributo de cliente, todos los demás atributos de cliente de la entidad *Medida_cliente* se actualizan simultáneamente. Además, los atributos del cliente se muestran en la tarjeta de perfil del cliente. Una vez ejecutado o guardado, los atributos de cliente no se pueden cambiar a medidas de cliente.

- Medida del cliente: genera la salida como una entidad propia y no se puede cambiar a un atributo del cliente una vez ejecutada o guardada. Las medidas del cliente no se muestran en la tarjeta de perfil del cliente.

- Medida empresarial: genera resultados como entidad propia y se muestran en la página de inicio de su entorno de Customer Insights.

1. Vaya a **Medidas**.

1. Seleccione **Nuevo** > **Generar el suyo**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Pantalla de configuración vacía para una medida B2C. " lightbox="media/measure-b2c.png":::

1. Seleccione **Editar detalles** junto a la medida sin título. Especifique un nombre para la medida. Opcionalmente, agregue [etiquetas](work-with-tags-columns.md#manage-tags) a la nueva medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar cuadro de diálogo de detalles":::

1. Seleccione **Listo**.

1. Para realizar un seguimiento del rendimiento a nivel empresarial, cambie **Tipo de medida** a **Nivel de negocio**. De forma predeterminada, aparece seleccionada la opción **Nivel de cliente**. **Nivel de cliente** agrega automáticamente el atributo *CustomerId* a Dimensiones mientras **Nivel de negocio** lo elimina automáticamente.

1. En el área de configuración, elija la función de agregación en el menú desplegable **Seleccionar función**. Las funciones de agregación incluyen:
   - **Sum**
   - **Media**
   - **Contar**
   - **Contar únicos**
   - **Max**
   - **Min**
   - **First**: toma el primer valor del registro de datos.
   - **Último**: toma el último valor que se agregó al registro de datos
   - **ArgMax**: encuentra el registro de datos que da el valor máximo de una función objetivo
   - **ArgMin**: encuentra el registro de datos que da el valor mínimo de una función objetivo

1. Seleccione **Agregar atributo** para seleccionar los para crear esta medida.

   1. Seleccione la pestaña **Atributos**.
   1. Entidad de datos: elija la entidad que incluye el atributo que desea medir.
   1. Atributo de datos: elija el atributo que desea utilizar en la función de suma para calcular la medida. Puede seleccionar solo un atributo a la vez.
   1. Opcionalmente, elija un atributo de datos en una medida existente, seleccionando la pestaña **Medidas** o bien, busque una entidad o un nombre de medida.
   1. Seleccione **Agregar**.

1. Para generar medidas más complejas, agregue más atributos o use operadores matemáticos en su función de medida.

1. Para agregar filtros, seleccione la opción **Filtrar** en el área de configuración. La aplicación de filtros solo usará los registros que coincidan con los filtros para calcular la medida.
  
   1. En la sección **Agregar atributo** del panel **Filtros**, seleccione el atributo que desea utilizar para crear filtros.
   1. Configure los operadores de filtro para definir el filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar**.

1. Seleccione **Dimensión** para elegir más campos a agregar como columnas a la entidad de salida de la medida.

   1. Seleccione **Editar dimensiones** para agregar los atributos de datos según los cuales desea agrupar los valores de medida. Por ejemplo, ciudad o género.
      > [!TIP]
      > Si seleccionó **Nivel de cliente** como el **Tipo de medida**, el atributo *CustomerId* ya está agregado. Si elimina el atributo, **Tipo de medida** cambia a **Nivel de negocio**.
   1. Seleccione **Listo**.

1. Si hay valores en sus datos que deben sustituirse por un entero, seleccione **Reglas**. Configure la regla y asegúrese de elegir solo números enteros como sustitución. Por ejemplo, reemplace *null* con *0*.

1. Si hay varias rutas entre la entidad de datos que asignó y la entidad *Cliente*, debe elegir una de las [rutas de relación de entidad](relationships.md) identificadas. Los resultados de la medición pueden variar según la ruta seleccionada.

   1. Seleccione **Ruta de relación** y elija la ruta de la entidad que debe usarse para identificar su medida. Si solo hay un camino hacia la entidad *Cliente*, este control no se mostrará.
   1. Seleccione **Listo**.

1. Para agregar más cálculos para la medida, seleccione **Nuevo cálculo**. Utilice solo entidades en la misma ruta de la entidad para los nuevos cálculos. Aparecerán más cálculos a modo de columnas nuevas en la entidad de los resultados de la medida. Opcionalmente, seleccione **Editar nombre** para crear un nombre para el cálculo.

1. Seleccione los puntos suspensivos verticales (&vellip;) en el cálculo para **Duplicar** o **Quitar** un cálculo de una medición.

1. En el área **Vista previa**, verá el esquema de datos de la entidad de los resultados de la medida, incluidos los filtros y las dimensiones. La vista previa reacciona dinámicamente a los cambios en la configuración.

1. Seleccione **Ejecutar** para calcular los resultados de la medida configurada. Seleccione **Guardar y cerrar** si desea mantener la configuración actual y ejecutar la medida más tarde. Se muestra la página **Medidas**.

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

Cree medidas a nivel de cuentas individuales (medida de clientes) o a nivel de todas las cuentas (medida de empresa).

- Medida del cliente: genera una salida como entidad propia. Las medidas del cliente no se muestran en la tarjeta de perfil del cliente.

- Medida empresarial: genera resultados como entidad propia y se muestran en la página de inicio de su entorno de Customer Insights.

1. Vaya a **Medidas**.

1. Seleccione **Nuevo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Pantalla de configuración vacía para una medida B2B. ":::

1. Seleccione **Editar detalles** junto a la medida sin título. Especifique un nombre para la medida. Opcionalmente, agregue [etiquetas](work-with-tags-columns.md#manage-tags) a la nueva medida. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar cuadro de diálogo de detalles":::

1. Seleccione **Listo**.

1. En el área de configuración, elija la función de agregación en el menú desplegable **Seleccionar función**. Las funciones de agregación incluyen:
   - **Sum**
   - **Media**
   - **Contar**
   - **Contar únicos**
   - **Max**
   - **Min**
   - **First**: toma el primer valor del registro de datos.
   - **Último**: toma el último valor que se agregó al registro de datos

1. Seleccione **Agregar atributo** para seleccionar los para crear esta medida.

   1. Seleccione la pestaña **Atributos**.
   1. Entidad de datos: elija la entidad que incluye el atributo que desea medir.
   1. Atributo de datos: elija el atributo que desea utilizar en la función de suma para calcular la medida. Puede seleccionar solo un atributo a la vez.
   1. Opcionalmente, elija un atributo de datos en una medida existente, seleccionando la pestaña **Medidas** o bien, busque una entidad o un nombre de medida.
   1. Seleccione **Agregar** para agregar el atributo seleccionado a la medida.

1. Para generar medidas más complejas, agregue más atributos o use operadores matemáticos en su función de medida.

1. Para agregar filtros, seleccione la opción **Filtrar** en el área de configuración. La aplicación de filtros solo usará los registros que coincidan con los filtros para calcular la medida.
  
   1. En la sección **Agregar atributo** del panel **Filtros**, seleccione el atributo que desea utilizar para crear filtros.
   1. Configure los operadores de filtro para definir el filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar** para agregar los filtros para la medida.

1. Seleccione **Dimensión** para elegir más campos a agregar como columnas a la entidad de salida de la medida.

   1. Seleccione **Editar dimensiones** para agregar los atributos de datos según los cuales desea agrupar los valores de medida. Por ejemplo, ciudad o género.
      > [!TIP]
      > El atributo *CustomerId* ya está agregado, lo que indica que es un tipo de medida en el nivel de cliente. Si elimina el atributo, el tipo de medida cambia a nivel de negocio.
   1. Seleccione **Listo** para agregar dimensiones a la medida.

1. Si hay valores en sus datos que deben sustituirse por un entero, seleccione **Reglas**. Configure la regla y asegúrese de elegir solo números enteros como sustitución. Por ejemplo, reemplace *null* con *0*.

1. Si [usa cuentas con jerarquías](relationships.md#set-up-account-hierarchies), revise **Subir subcuentas**.
   - Si está configurado como **Apagado**, la medida se calcula para cada cuenta. Cada cuenta obtiene su propio resultado.
   - Si está configurado como **Activado**, seleccione **Editar** para elegir la jerarquía de cuentas de acuerdo con las jerarquías ingeridas. La medida arrojará un solo resultado porque está agregada con subcuentas.

1. Si hay varias rutas entre la entidad de datos que asignó y la entidad *Cliente*, debe elegir una de las [rutas de relación de entidad](relationships.md) identificadas. Los resultados de la medición pueden variar según la ruta seleccionada.

   1. Seleccione **Ruta de relación** y elija la ruta de la entidad que debe usarse para identificar su medida. Si solo hay un camino hacia la entidad *Cliente*, este control no se mostrará.
   1. Seleccione **Listo** para aplicar su selección.

1. Seleccione los puntos suspensivos verticales (&vellip;) en el cálculo para **Duplicar** o **Quitar** un cálculo de una medición.

1. En el área **Vista previa**, verá el esquema de datos de la entidad de los resultados de la medida, incluidos los filtros y las dimensiones. La vista previa reacciona dinámicamente a los cambios en la configuración.

1. Seleccione **Ejecutar** para calcular los resultados de la medida configurada. Seleccione **Guardar y cerrar** si desea mantener la configuración actual y ejecutar la medida más tarde. Se muestra la página **Medidas**.

---

## <a name="next-step"></a>Siguiente paso

Utilice medidas existentes para crear [un segmento de clientes](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
