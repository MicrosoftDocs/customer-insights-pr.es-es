---
title: Crear y gestionar segmentos
description: Cree segmentos de clientes para agruparlos en función de diversos atributos.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685483"
---
# <a name="create-and-manage-segments"></a>Crear y gestionar segmentos

> [!IMPORTANT]
> En septiembre de 2021 se implementarán varios cambios en la experiencia de creación de segmentos: 
> - El generador de segmentos tendrá un aspecto ligeramente diferente, con elementos rediseñados y un flujo de usuarios mejorado.
> - Los nuevos operadores de fecha y hora y un selector de fechas mejorado están habilitados en el generador de segmentos.
> - Puede agregar o quitar condiciones y reglas de segmentos. 
> - Estarán disponibles las reglas anidadas que comiencen por una condición OR. Ya no necesita una condición AND en la capa más externa.
> - Un panel lateral para seleccionar atributos estará disponible constantemente.
> - Una opción para seleccionar rutas de acceso de relación de entidad.
> Para probar el generador de segmentos, envíe a cihelp [at] microsoft.com un correo electrónico con el asunto "Solicitud para habilitar el nuevo generador de segmentos". Incluya el nombre de su organización y el id. de su entorno de espacio aislado.

Defina filtros complejos basados en la entidad de cliente unificado y sus entidades relacionadas. Cada segmento, después del procesamiento, crea un conjunto de registros de entidades del cliente que puede exportar y sobre los que puede actuar. Los segmentos se gestionan en la página **Segmentos**. 

El siguiente ejemplo ilustra la capacidad de segmentación. Hemos definido un segmento para clientes que pidieron bienes por una cantidad mínima de $500 en los últimos 90 días *y* que participaron en una llamada de servicio al cliente que se escaló.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de pantalla de la UI del generador de segmentos con dos grupos que especifican un segmento de clientes.":::

## <a name="create-a-new-segment"></a>Crear un nuevo segmento

Hay múltiples formas de crear un nuevo segmento. Esta sección describe cómo crear un *segmento en blanco* desde cero. También puede crear un *segmento rápido* basado en entidades existentes o hacer uso de modelos de aprendizaje automático para obtener *segmentos sugeridos*. Más información: [Información general sobre los segmentos](segments.md).

Mientras crea un segmento, puede guardar un borrador. Se guardará como un segmento inactivo y no se podrá activar si termina con una configuración válida.

1. Vaya a la página **Segmentos**.

1. Seleccione **Nuevo** > **Segmento en blanco**.

1. En el panel **Nuevo segmento**, elija un tipo de segmento:

   - [Actualizar](segments.md#refresh-segments) **segmentos dinámicos** con programación periódica.
   - Los **segmentos estáticos** se ejecutan una vez, al crearlos.

1. Facilite un **Nombre de la entidad de salida** para el segmento. Opcionalmente, proporcione un nombre y una descripción que ayude a identificar el segmento.

1. Seleccione **Siguiente** para llegar a la página **Generador de segmentos**, donde define un grupo. Un grupo es un conjunto de clientes.

1. Elija la entidad que incluye el atributo por la que desea segmentar.

1. Elija el atributo de segmentación. Este atributo puede tener uno de los cuatro tipos de valores siguientes: numérico, cadena, fecha o booleano.

1. Elija un operador y un valor para el atributo seleccionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro de grupo personalizado.](media/customer-group-numbers.png "Filtro de grupo del cliente")

   |Número |Definición  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |valor         |

   1. Para agregar más condiciones a un grupo, puede usar dos operadores lógicos:

      - Operador **AND**: Ambas condiciones deben cumplirse como parte del proceso de segmentación. Esta opción es más útil cuando define condiciones en diferentes entidades.

      - Operador **OR**: Cualquiera de las condiciones debe cumplirse como parte del proceso de segmentación. Esta opción es más útil cuando define varias condiciones para la misma entidad.

      > [!div class="mx-imgBorder"]
      > ![Operador OR donde cualquiera de las condiciones debe cumplirse.](media/segmentation-either-condition.png "Operador OR donde cualquiera de las condiciones debe cumplirse")

      Actualmente es posible anidar una operador **OR** bajo un operador **AND**, pero no al revés.

   1. Cada grupo coincide con un conjunto de clientes. Puede combinar grupos para incluir los clientes necesarios para su caso comercial.    
   Seleccione **Agregar grupo**.

      > [!div class="mx-imgBorder"]
      > ![Grupo de clientes agregar grupo.](media/customer-group-add-group.png "Grupo de clientes agregar grupo")

   1. Seleccione uno de los operadores establecidos: **Unión**, **Intersección** o **Excepto**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes agregar unión.](media/customer-group-union.png "Grupo de clientes agregar unión")

   - **Unión** une los dos grupos.

   - **Intersección** superpone los dos grupos. Solo se retienen en el grupo unificado los datos que *son comunes* a ambos grupos.

   - **Exceptuar** combina los dos grupos. Solo se retienen en el grupo A los datos que *no son comunes* a los datos del grupo B.

1. Si la entidad está conectada a la entidad unificada del cliente a través de [relaciones](relationships.md), debe definir la ruta de relación para crear un segmento válido. Agregue las entidades de la ruta de relación hasta que pueda seleccionar la entidad **Customer : CustomerInsights** del menú desplegable. Entonces, escoja **Todos los registros** para cada paso.

   > [!div class="mx-imgBorder"]
   > ![Ruta de relación durante la creación del segmento.](media/segments-multiple-relationships.png "Ruta de relación durante la creación del segmento")

1. De forma predeterminada, los segmentos generan una entidad de salida que contiene todos los atributos de los perfiles de clientes que coinciden con los filtros definidos. Si un segmento se basa en otras entidades distintas a la entidad *Cliente*, puede agregar más atributos de estas entidades a la entidad de salida. Seleccione **Atributos del proyecto** para elegir los atributos que se agregarán a la entidad de salida.  
  
   Ejemplo: un segmento se basa en una entidad que contiene datos de actividad del cliente que están relacionados con la entidad *Cliente*. El segmento busca a todos los clientes que llamaron a la mesa de ayuda en los últimos 60 días. Puede optar por agregar la duración de la llamada y el número de llamadas a todos los registros de clientes coincidentes en la entidad de salida. Esta información puede resultar útil para enviar un correo electrónico con vínculos útiles a artículos de ayuda en línea y preguntas frecuentes a los clientes que llaman con frecuencia.

   > [!NOTE]
   > - Los atributos proyectados solo funcionan para entidades que tienen una relación de uno a varios con la entidad del cliente. Por ejemplo, un cliente puede tener varias suscripciones.
   > - Solo puede proyectar atributos de una entidad que se utiliza en cada grupo de consulta de segmento que está creando.
   > - Los atributos proyectados se tienen en cuenta al utilizar operadores de conjuntos.

1. Seleccione **Guardar** para guardar el segmento. Su segmento se guardará y procesará si se validan todos los requisitos. De lo contrario, se guardará como borrador.

1. Seleccione **Volver a Segmentos** para volver a la página **Segmentos**.



## <a name="quick-segments"></a>Segmentos rápidos

Los segmentos rápidos le permiten crear segmentos simples con un solo operador rápidamente para obtener conocimientos de forma más rápida.

1. En la página **Segmentos**, seleccione **Nuevo** > **Crear desde**.

   - Seleccione la opción **Perfiles** para construir un segmento basado en la entidad *cliente unificado*.
   - Seleccione la opción **Medidas** para construir un segmento alrededor de medidas que haya creado previamente.
   - Selecciona la opción **Inteligencia** para crear un segmento alrededor de una de las entidades de salida que generó con las capacidades **Predicciones** o **Modelos personalizados**.

2. En el cuadro de diálogo **Nuevo segmento rápido**, seleccione un atributo en el campo desplegable **Campo**.

3. El sistema proporcionará información adicional que le ayudará a crear mejores segmentos de sus clientes.
   - Para los campos categóricos, mostraremos los 10 principales recuentos de clientes. Elija un **Valor** y seleccione **Revisar**.

   - Para un atributo numérico, el sistema mostrará qué valor de atributo corresponde al percentil de cada cliente. Elija un **Operador** y un **Valor**, luego seleccione **Revisar**.

4. El sistema le proporcionará un **Tamaño de segmento estimado**. Puede elegir si genera el segmento que ha definido o volver a visitarlo para obtener un tamaño de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nombre y estimación de un segmento rápido.](media/quick-segment-name.png "Nombre y estimación de un segmento rápido")

5. Dé un **Nombre** al segmento. Opcionalmente, proporcione un **Nombre para mostrar**.

6. Seleccione **Guardar** para crear el segmento.

7. Una vez que el segmento ha terminado de procesarse, puede verlo como cualquier otro segmento que haya creado.

## <a name="next-steps"></a>Pasos siguientes

[Exportar un segmento](export-destinations.md) y explorar la [Tarjeta de cliente](customer-card-add-in.md) y [Conectores](export-power-bi.md) para obtener información a nivel del cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
