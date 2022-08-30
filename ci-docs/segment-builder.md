---
title: Crear segmentos complejos con el generador de segmentos
description: Use el generador de segmentos para crear segmentos complejos agrupándolos en función de varios atributos.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304770"
---
# <a name="create-complex-segments-with-segment-builder"></a>Crear segmentos complejos con el generador de segmentos

Defina filtros complejos basados en el cliente unificado o contacto unificado y sus entidades relacionadas. Cada segmento, después del procesamiento, crea un conjunto de registros de cliente o contacto que puede exportar y sirve para tomar medidas.

> [!TIP]
> Los segmentos basados en **clientes individuales** incluyen automáticamente la información de contacto disponible para los miembros del segmento. En las **cuentas comerciales**, si [unificó](data-unification.md) cuentas y contactos, elija si el segmento se basa en cuentas o contactos comerciales. Para exportar a un destino que espera información de contacto, utilice un segmento de contactos. Para exportar a un destino que espera información de cuenta, utilice un segmento de cuentas.

## <a name="segment-builder"></a>Generador de segmentos

La siguiente imagen ilustra los diversos aspectos del generador de segmentos. Muestra un segmento que da como resultado un grupo de clientes. Los clientes compraron productos en un plazo de tiempo específico y obtuvieron puntos de recompensa o gastaron una cierta cantidad de dinero.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos del constructor de segmentos." lightbox="media/segment-builder-overview.png":::

1. Organice su segmento con reglas y subreglas. Cada regla o subregla consta de condiciones. Combinar las condiciones con operadores lógicos.

1. Elija la [ruta de la relación](relationships.md) entre entidades que se aplica a una regla. La ruta de la relación determina qué atributos se pueden usar en una condición.

1. Gestione reglas y subreglas. Cambie la posición de una regla o elimínela.

1. Agregue condiciones y construya el nivel correcto de anidamiento usando subreglas.

1. Aplique operaciones de conjunto a reglas conectadas.

1. Use el panel de atributos para agregar atributos de entidad disponibles o crear condiciones basadas en atributos. El panel muestra la lista de entidades y atributos, según la ruta de relación seleccionada, que están disponibles para la regla seleccionada.

1. Agregue condiciones basadas en atributos a reglas y subreglas existentes o agréguelas a una nueva regla.

1. Deshaga y rehaga cambios mientras construye el segmento.

El ejemplo anterior ilustra la capacidad de segmentación. Hemos definido un segmento para los clientes que compraron al menos 500 $ de productos en línea *y* tienen interés en el desarrollo de software.

## <a name="create-a-new-segment-with-segment-builder"></a>Crear un nuevo segmento con el generador de segmentos

1. Vaya a **Segmentos**.

1. Seleccione **Nuevo** > **Generar el suyo**. En la página del generador de segmentos, defina o redacte reglas. Una regla consta de una o más condiciones que definen un conjunto de clientes.

   > [!NOTE]
   > Para entornos basados en cuentas comerciales, seleccione **Nuevo** > **Segmento de cuentas** o **Segmento de contactos (vista previa)** según el tipo de segmento que desee crear. Si se ha definido una [jerarquía de cuentas](relationships.md#set-up-account-hierarchies) y desea crear reglas para filtrar datos en función de la relación principal y secundaria, seleccione **¿Usar jerarquía? (avance)**, seleccione la jerarquía y luego **Aplicar**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Seleccionar el panel de jerarquía de cuenta en el segmento.":::

1. Seleccione **Editar detalles** junto al segmento sin título. Proporcione un nombre para su segmento y actualice el **Nombre de la entidad de salida** sugerido para el segmento. Opcionalmente, agregue una descripción y [etiquetas](work-with-tags-columns.md#manage-tags) al segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Editar cuadro de diálogo de detalles":::

1. En la sección **Regla 1**, elija un atributo de una entidad por la que desee filtrar clientes. Hay dos formas de elegir atributos:
   - Revise la lista de entidades y atributos disponibles en el panel **Agregar a la regla** y seleccione el icono **+** próximo al atributo a agregar. Elija si desea agregar el atributo a una regla existente o utilizarlo para crear una nueva regla.
   - Escriba el nombre del atributo en la sección de reglas para ver sugerencias coincidentes.

1. Elija los operadores para especificar los valores coincidentes de la condición. El atributo puede tener uno de entre cuatro tipos de datos como valor: numérico, cadena, fecha o booleano. Dependiendo del tipo de datos del atributo, hay diferentes operadores disponibles para especificar la condición.

1. Seleccione **Agregar condición** para agregar más condiciones a una regla. Para crear una regla bajo la regla actual, seleccione **Agregar subregla**.

1. Si una regla utiliza otras entidades además de la entidad *Cliente* (o *ContactProfile* para B a B), seleccione **Establecer ruta de relación** para asignar la entidad seleccionada a la entidad de cliente unificada. Si solo hay una ruta de relación posible, el sistema la selecciona automáticamente. Diferentes [rutas de relación](relationships.md#relationship-paths) pueden producir resultados diferentes. Cada regla puede tener su propia ruta de relación.

   :::image type="content" source="media/relationship-path.png" alt-text="Ruta de relación potencial al crear una regla basada en una entidad asignada a la entidad cliente unificada.":::

1. Si tiene varias condiciones en una regla, elija qué operador lógico las conecta.  
   - Operador **Y**: deben cumplirse todas las condiciones para incluir un registro en el segmento. Use esta opción al definir condiciones en diferentes entidades.
   - Operador **O**: debe cumplirse cualquiera de las condiciones para incluir un registro en el segmento. Use esta opción al definir varias condiciones para la misma entidad.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regla con dos condiciones Y.":::

   Cuando se usa el operador O, todas las condiciones deben basarse en entidades incluidas en la ruta de la relación.

1. Para crear diferentes conjuntos de registros de clientes, cree varias reglas. Para incluir los clientes necesarios para su caso comercial, combine grupos. Específicamente, si no puede incluir una entidad en una regla debido a la ruta de relación especificada, cree una nueva regla para elegir los atributos de esta.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Agregue una nueva regla a un segmento y elija el operador del conjunto.":::

   1. Seleccione **Agregar regla**.
   1. Seleccione uno de los operadores establecidos: **Unión**, **Intersección** o **Excepto**.

      - **Unión** une los dos grupos.
      - **Intersección** superpone los dos grupos. Solo se mantienen en el grupo unificado los datos que *son comunes* en ambos grupos.
      - **Exceptuar** combina los dos grupos. Solo se guardan los datos del grupo A que *no son comunes* a los datos del grupo B.

1. De forma predeterminada, la entidad de salida contiene todos los atributos de los perfiles de clientes que coinciden con los filtros definidos. En B a B cuando se utiliza la entidad *ContactProfile*, el ID de la cuenta se incluye automáticamente. Si un segmento se basa en entidades distintas de la entidad *Cliente* o para incluir más atributos de *ContactProfile*, seleccione **Atributos del proyecto** para agregar más atributos de estas entidades a la entidad de salida.
 
   Por ejemplo: un segmento se basa en una entidad que contiene datos de compra, que están relacionados con la entidad *Cliente*. El segmento busca todos los clientes de España que compraron bienes en el año en curso. Puede optar por agregar atributos, como el precio de los productos, o la fecha de compra a todos los registros de clientes coincidentes en la entidad de salida. Esta información puede resultar útil para analizar las correlaciones estacionales con el gasto total.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Ejemplo de atributos proyectados seleccionados en el panel lateral para agregarlos a la entidad de salida.":::
 
   Un resultado de ejemplo para un segmento basado en cuentas comerciales con atributos proyectados de contactos podría verse así:

   |Identificador  |Nombre de cuenta  |Ingresos  |Nombre de contacto  | Rol del contacto|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [CEO, Administrador de compras]

   > [!NOTE]
   > - **Atributos del proyecto** solo funciona para entidades que tienen una relación de uno a varios con la entidad *Cliente* o *ContactProfile*. Por ejemplo, un cliente puede tener varias suscripciones.
   > - Si el atributo que desea proyectar está a más de un salto de la entidad *Cliente* o *ContactProfile*, según lo definido por la relación, ese atributo debe usarse en cada regla de la consulta de segmento que está construyendo.
   > - Si el atributo que desea proyectar está a solo un salto de la entidad *Cliente* o *ContactProfile*, no es necesario que ese atributo esté presente en cada regla de la consulta de segmento que está construyendo.
   > - Los **atributos proyectados** se tienen en cuenta al utilizar operadores de conjuntos.

1. Seleccione **Ejecutar** para crear el segmento. Seleccione **Guardar** si desea mantener la configuración actual y ejecutar el seegmento más tarde. Se muestra la página **Segmentos**.

### <a name="segment-builder-tips"></a>Sugerencias del generador de segmentos

Al crear un segmento con el generador de segmentos, tenga en cuenta los siguientes consejos:

- El generador de segmentos no sugerirá valores válidos de entidades al configurar los operadores para las condiciones. Puedes ir a **Datos** > **Entidades** y descargar los datos de la entidad para ver qué valores están disponibles.
- Las condiciones basadas en fechas le permiten cambiar entre fechas fijas y un rango de fechas flotante.
- Si tiene varias reglas para su segmento, la regla que está editando tiene una línea azul vertical junto a ella.
- Puede mover reglas y condiciones a otros lugares en la definición del segmento. Seleccione los puntos suspensivos verticales (&vellip;) junto a una regla o condición y elija cómo y dónde moverla.
- Los controles **Deshacer** y **Rehacer** de la barra de comandos le permiten revertir los cambios.
- Después de crear un segmento, algunos segmentos le permiten [rastrear el uso del segmento](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Pasos siguientes

[Exportar un segmento](export-destinations.md) y explorar la [Integración de tarjeta de cliente](customer-card-add-in.md) para usar segmentos en otras aplicaciones.

[!INCLUDE [footer-include](includes/footer-banner.md)]
