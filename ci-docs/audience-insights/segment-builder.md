---
title: Crear segmentos con el generador de segmentos
description: Cree segmentos de clientes para agruparlos en función de diversos atributos.
ms.date: 03/25/2022
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
ms.openlocfilehash: 1a28289ecb740ab6cdfa603b2cd66376e7e8b576
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529606"
---
# <a name="create-segments"></a>Crear segmentos

Defina filtros complejos basados en la entidad de cliente unificado y sus entidades relacionadas. Cada segmento, después del procesamiento, crea un conjunto de registros de entidades del cliente que puede exportar y sobre los que puede actuar. Los segmentos se gestionan en la página **Segmentos**. Usted puede [crear nuevos segmentos](#create-a-new-segment) utilizando el generador de segmentos o [crear segmentos rápidos](#quick-segments) de otras áreas de la aplicación.

> [!TIP]
> - Los segmentos rápidos solo se admiten en entornos para **clientes individuales**.
> - Los segmentos basados en **clientes individuales** incluyen automáticamente la información de contacto disponible para los miembros del segmento. En entornos para **cuentas de negocio**, los segmentos se basan en cuentas (empresas o subsidiarias). Para incluir información de contacto en un segmento, utilice la funcionalidad **Atributos del proyecto** en el generador de segmentos. Asegúrese de que los orígenes de datos de contacto estén [asignadas semánticamente a la entidad ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Generador de segmentos

La siguiente imagen ilustra los diversos aspectos del generador de segmentos. Muestra un segmento que da como resultado un grupo de clientes. Los clientes compraron productos en un plazo de tiempo específico y obtuvieron puntos de recompensa o gastaron una cierta cantidad de dinero.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos del constructor de segmentos." lightbox="media/segment-builder-overview.png":::

1. Organice su segmento con reglas y subreglas. Cada regla o subregla consta de condiciones. Combinar las condiciones con operadores lógicos

1. Elija la [ruta de la relación](relationships.md) entre entidades que se aplica a una regla. La ruta de la relación determina qué atributos se pueden usar en una condición.

1. Gestione reglas y subreglas. Cambie la posición de una regla o elimínela.

1. Agregue condiciones y construya el nivel correcto de anidamiento usando subreglas.

1. Aplique operaciones de conjunto a reglas conectadas.

1. Use el panel de atributos para agregar atributos de entidad disponibles o crear condiciones basadas en atributos. El panel muestra la lista de entidades y atributos, según la ruta de relación seleccionada, que están disponibles para la regla seleccionada.

1. Agregue condiciones basadas en atributos a reglas y subreglas existentes o agréguelas a una nueva regla.

1. Deshaga y rehaga cambios mientras construye el segmento.

El ejemplo anterior ilustra la capacidad de segmentación. Hemos definido un segmento para los clientes que compraron al menos 500 $ de productos en línea *y* tienen interés en el desarrollo de software.

## <a name="create-a-new-segment"></a>Crear un nuevo segmento

Hay múltiples formas de crear un nuevo segmento. Esta sección describe cómo construir su propio segmento desde cero. También puede crear un *segmento rápido* basado en entidades existentes o hacer uso de modelos de aprendizaje automático para obtener *segmentos sugeridos*. Para obtener más información, vaya a [Información general de los segmentos](segments.md).

Mientras crea un segmento, puede guardar un borrador. En la etapa de borrador, un segmento se guarda como segmento inactivo. Cuando complete la configuración del segmento, ejecútela para activar el segmento. También puede **Activar** un segmento desde la página **Todos los segmentos**.

1. Vaya a la página **Segmentos**.

1. Seleccione **Nuevo** > **Generar el suyo**.

1. En la página del generador de segmentos, defina o redacte reglas. Una regla consta de una o más condiciones que definen un conjunto de clientes.

1. En la sección **Regla 1**, elija un atributo de una entidad por la que desee filtrar clientes. Hay dos formas de elegir atributos:
   - Revise la lista de entidades y atributos disponibles en el panel **Agregar a la regla** y seleccione el icono **+** próximo al atributo a agregar. Elija si desea agregar el atributo a una regla existente o utilizarlo para crear una nueva regla.
   - Escriba el nombre del atributo en la sección de reglas para ver sugerencias coincidentes.

1. Elija los operadores para especificar los valores coincidentes de la condición. El atributo puede tener uno de entre cuatro tipos de datos como valor: numérico, cadena, fecha o booleano. Dependiendo del tipo de datos del atributo, hay diferentes operadores disponibles para especificar la condición. Para los segmentos con cuentas de negocio, hay dos operadores especiales disponibles para incluir jerarquías potenciales entre las cuentas ingeridas. Utilice los operadores *secundario de* y *primario de* para incluir cuentas relacionadas.

1. Seleccione **Agregar condición** para agregar más condiciones a una regla. Para crear una regla bajo la regla actual, seleccione **Agregar subregla**.

1. Si una regla usa otras entidades distintas a la entidad *Cliente*, debe establecer la ruta de la relación. La ruta de la relación es necesaria para informar al sistema sobre las relaciones que desea que tengan acceso a la entidad de cliente unificado. Seleccione **Establecer ruta de relación** para mapear la entidad seleccionada a la entidad cliente unificada. Si solo hay una ruta de relación posible, el sistema la seleccionará automáticamente. Diferentes rutas de relación pueden producir resultados diferentes. Cada regla puede tener su propia ruta de relación.

   :::image type="content" source="media/relationship-path.png" alt-text="Ruta de relación potencial al crear una regla basada en una entidad asignada a la entidad cliente unificada.":::

   Por ejemplo, la entidad *eCommerce_eCommercePurchases* de la captura de pantalla tiene cuatro opciones de asignación a la entidad del *Cliente*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Cliente
   - eCommerce_eCommercePurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
   - eCommerce_eCommercePurchases> eCommerce_eCommerceContacts> POS_posPurchases> loyaltyScheme_loyCustomers> Cliente Al elegir la última opción, podemos incluir atributos de todas las entidades listadas en las condiciones de la regla. Es probable que obtengamos menos resultados porque los registros de clientes coincidentes deben ser parte de todas las entidades. En este ejemplo, se deben haber comprado productos a través de comercio electrónico (*eCommerce_eCommercePurchases*) en un punto de venta (*POS_posPurchases*) y participar en nuestro programa de fidelización (*loyaltyScheme_loyCustomers*). Al elegir la segunda opción, solo podemos elegir atributos de *eCommerce_eCommercePurchases* y la entidad *Cliente*. Esto probablemente dará por resultado más perfiles de clientes resultantes.

1. Si tiene varias condiciones en una regla, puede elegir qué operador lógico las conecta.  
   - Operador **Y**: deben cumplirse todas las condiciones para incluir un registro en el segmento. Esta opción es más útil cuando define condiciones en diferentes entidades.
   - Operador **O**: debe cumplirse cualquiera de las condiciones para incluir un registro en el segmento. Esta opción es más útil cuando define varias condiciones para la misma entidad.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regla con dos condiciones Y.":::

   Cuando se usa el operador O, todas las condiciones deben basarse en entidades incluidas en la ruta de la relación.

   - Puede crear varias reglas para crear diferentes conjuntos de registros de clientes. Puede combinar grupos para incluir los clientes necesarios para su caso comercial. Para crear una regla nueva, seleccione **Agregar regla**. Específicamente, si no puede incluir una entidad en una regla debido a la ruta de relación especificada, debe crear una nueva regla para elegir los atributos que la forman.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Agregue una nueva regla a un segmento y elija el operador del conjunto.":::

   - Seleccione uno de los operadores establecidos: **Unión**, **Intersección** o **Excepto**.

      - **Unión** une los dos grupos.
      - **Intersección** superpone los dos grupos. Solo se mantienen en el grupo unificado los datos que *son comunes* en ambos grupos.
      - **Exceptuar** combina los dos grupos. Solo se guardan los datos del grupo A que *no son comunes* a los datos del grupo B.

1. De forma predeterminada, los segmentos generan la entidad de salida que contiene todos los atributos de los perfiles de clientes que coinciden con los filtros definidos. Si un segmento se basa en otras entidades distintas a la entidad *Cliente*, puede agregar más atributos de estas entidades a la entidad de salida. Seleccione **Atributos del proyecto** para elegir los atributos que se agregarán a la entidad de salida.

   > [!IMPORTANT]
   > Para segmentos basados en cuentas de negocio, los detalles de uno o más contactos de cada cuenta de la entidad *ContactProfile* deben incluirse en el segmento para permitir que ese segmento se active o exporte a destinos que requieren información de contacto. Para obtener más información sobre la entidad *ContactProfile*, consulte [Asignaciones semánticas](semantic-mappings.md).
   > Un resultado de ejemplo para un segmento basado en cuentas comerciales con atributos proyectados de contactos podría verse así:
   >
   > |Identificador  |Nombre de cuenta  |Ingresos  |Nombre de contacto  | Rol del contacto|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 000 | [Abbie Moss, Ruth Soto]  | [CEO, Administrador de compras]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Ejemplo de atributos proyectados seleccionados en el panel lateral para agregarlos a la entidad de salida.":::
  
   Por ejemplo: un segmento se basa en una entidad que contiene datos de compra, que están relacionados con la entidad *Cliente*. El segmento busca todos los clientes de España que compraron bienes en el año en curso. Puede optar por agregar atributos, como el precio de los productos, o la fecha de compra a todos los registros de clientes coincidentes en la entidad de salida. Esta información puede resultar útil para analizar las correlaciones estacionales con el gasto total.

   > [!NOTE]
   > - **Atributos del proyecto** solo funciona para entidades que tienen una relación de uno a varios con la entidad del cliente. Por ejemplo, un cliente puede tener varias suscripciones.
   > - Si el atributo que desea proyectar está a más de un salto de la entidad *Cliente*, según lo definido por la relación, ese atributo debe usarse en cada regla de la consulta de segmento que está construyendo.
   > - Si el atributo que desea proyectar está a solo un salto de la entidad *Cliente*, no es necesario que ese atributo esté presente en cada regla de la consulta de segmento que está construyendo.
   > - Los **atributos proyectados** se tienen en cuenta al utilizar operadores de conjuntos.

1. Seleccione **Editar detalles** junto al segmento sin título. Proporcione un nombre para su segmento y actualice el **Nombre de la entidad de salida** sugerido para el segmento. Opcionalmente, agregue una descripción y [etiquetas](work-with-tags-columns.md#manage-tags) al segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Editar cuadro de diálogo de detalles":::

1. Seleccione **Ejecutar** para guardar el segmento, actívelo y comience a procesar su segmento según todas las reglas y condiciones. De lo contrario, se guardará como segmento inactivo.

1. Seleccione **Volver a Segmentos** para volver a la página **Segmentos**.

1. De forma predeterminada, el segmento se crea como segmento dinámico. Significa que el segmento se actualiza durante las actualizaciones del sistema. Para [detener la actualización automática](segments.md#manage-existing-segments), seleccione el segmento y elija la opción **Hacer estático**. Los segmentos estáticos se pueden [actualizar manualmente](segments.md#refresh-segments) en cualquier momento.

> [!TIP]
> - El generador de segmentos no sugerirá valores válidos de entidades al configurar los operadores para las condiciones. Puedes ir a **Datos** > **Entidades** y descargar los datos de la entidad para ver qué valores están disponibles.
> - Las condiciones basadas en las fechas le permiten cambiar entre fechas fijas y un rango de fechas flotante.
> - Si tiene varias reglas para su segmento, la regla que está editando tiene una línea azul vertical junto a ella.
> - Puede mover reglas y condiciones a otros lugares en la definición del segmento. Seleccione [...] junto a una regla o condición y elija cómo y dónde moverla.
> - Los controles **Deshacer** y **Rehacer** de la barra de comandos le permiten revertir los cambios.

## <a name="quick-segments"></a>Segmentos rápidos

Los segmentos rápidos le permiten crear segmentos simples con un solo operador rápidamente para obtener conocimientos de forma más rápida.

1. En la página **Segmentos**, seleccione **Nuevo** > **Crear desde**.
   - Seleccione la opción **Perfiles** para construir un segmento basado en la entidad *cliente unificado*.
   - Seleccione la opción **Medidas** para construir un segmento alrededor de medidas que haya creado previamente.
   - Selecciona la opción **Inteligencia** para crear un segmento alrededor de una de las entidades de salida que generó con las capacidades **Predicciones** o **Modelos personalizados**.

2. En el cuadro de diálogo **Nuevo segmento rápido**, seleccione un atributo en el campo desplegable **Campo**.

3. El sistema proporcionará más información que le ayudará a crear mejores segmentos de sus clientes.
   - Para los campos categóricos, mostraremos los 10 principales recuentos de clientes. Elija un **Valor** y seleccione **Revisar**.
   - Para un atributo numérico, el sistema mostrará qué valor de atributo corresponde al percentil de cada cliente. Elija un **Operador** y un **Valor**, luego seleccione **Revisar**.

4. El sistema le proporcionará un **Tamaño de segmento estimado**. Puede elegir si genera el segmento que ha definido o volver a visitarlo para obtener un tamaño de segmento diferente.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nombre y estimación de un segmento rápido.":::

5. Proporcione un **Nombre** y un **Nombre de entidad de salida** para su segmento. Opcionalmente, agregue [etiquetas](work-with-tags-columns.md#manage-tags).

6. Seleccione **Guardar** para crear el segmento.

7. Una vez que el segmento ha terminado de procesarse, puede verlo como cualquier otro segmento que haya creado.

## <a name="next-steps"></a>Pasos siguientes

[Exportar un segmento](export-destinations.md) y explorar la [Integración de tarjeta de cliente](customer-card-add-in.md) para usar segmentos en otras aplicaciones.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
