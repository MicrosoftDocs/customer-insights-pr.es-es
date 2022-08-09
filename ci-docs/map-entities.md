---
title: Seleccionar campos de origen para la unificación de datos
description: El primer paso en el proceso de unificación es seleccionar entidades, atributos, claves primarias y tipos semánticos para asignar datos al perfil de cliente unificado.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139803"
---
# <a name="select-source-fields-for-data-unification"></a>Seleccionar campos de origen para la unificación de datos

El primer paso en la unificación es seleccionar las entidades y campos dentro de sus conjuntos de datos que desea unificar. Seleccione entidades que contengan detalles relacionados con el cliente, como nombre, dirección, número de teléfono y correo electrónico. Puede seleccionar una o más entidades.

## <a name="select-entities-and-fields"></a>Seleccionar entidades y campos

1. Vaya a **Datos** > **Unificar**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de pantalla de la página de destino de Unify para la experiencia de primera ejecución con la opción Comenzar resaltada.":::

1. Seleccione **Comenzar**.

1. En la página **Campos de origen**, seleccione **Seleccionar entidades y campos**. El panel **Seleccionar entidades y campos** se muestra.

1. Seleccione al menos una entidad.

1. Para cada entidad seleccionada, identifique los campos que desea usar para hacer coincidir los registros de clientes y los campos para incluir en el perfil unificado. Estos campos se llaman *Atributos*. Puede seleccionar los atributos requeridos individualmente de una entidad o incluir todos los atributos de una entidad seleccionando la casilla de verificación en el nivel de la entidad. Puede buscar palabras clave en todos los atributos y entidades para seleccionar los atributos necesarios que desea asignar.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de pantalla de entidades y atributos seleccionados.":::

   En este ejemplo, estamos agregando las entidades **Contactos** y **CustomerLoyalty**. Al elegir estas entidades, puede obtener información sobre cuáles de los clientes comerciales en línea son miembros del programa de fidelización.

1. Seleccione **Aplicar** para confirmar sus selecciones. Se muestran las entidades y atributos seleccionados.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccione la clave principal y el tipo semántico para los atributos

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de pantalla de las entidades seleccionadas con la clave principal no seleccionada." lightbox="media/m3_select_primary.png":::

Para cada entidad, realice los siguientes pasos.

1. Elija la **Clave principal**. La clave principal es un atributo exclusivo de la entidad. Para que un atributo pueda ser una clave principal válida, no debe incluir valores duplicados, no deben faltar valores ni debe haber valores nulos. Los atributos de tipo de datos de cadena, entero y GUID se admiten como claves principales.

1. Para usar modelos de IA para predicción inteligente de semántica, ahorre tiempo y mejore la precisión, asegúrese de que la **asignación inteligente** está activada. La asignación inteligente destaca la recomendación de semántica basada en IA en el campo **Tipo**. Puede anular la selección sugerida eligiendo cualquier tipo semántico de la lista de opciones disponibles.

1. Para cada atributo, elija un **Tipo** de semántica que mejor describa ese atributo, como el nombre, la ciudad o la dirección de correo electrónico.

   > [!NOTE]
   > Un campo debe corresponder al tipo semántico *Person.FullName* para completar el nombre del cliente en la tarjeta del cliente. De lo contrario, las tarjetas de cliente aparecerán sin nombre.

   1. Para cambiar el tipo de atributo que el sistema identificó, seleccione otro tipo. Si el tipo no existe, cree un tipo semántico personalizado seleccionando el campo **Tipo** para el atributo e ingresando su nombre de tipo semántico personalizado.

   1. Para agregar un atributo que contenga una URL a imágenes de perfil o logotipos disponibles públicamente, seleccione la entidad y el campo que contiene la URL. Escriba lo siguiente en el campo **Tipo**:
      - Para una persona: Person.ProfileImage
      - Para una organización: Organization.LogoImage

   1. Para un atributo de nombre de cuenta, ingrese "Organization.Name" en el campo **Tipo**.

1. Revise los atributos donde se identifica automáticamente un tipo semántico. Estos atributos se enumeran en **Revisar campos mapeados**. Solo los atributos con el mismo tipo se pueden combinar en el paso **Campos de clientes unificados**. Los tipos semánticos se utilizan para sugerir ideas automáticamente. Asegúrese de que los tipos que elija sean coherentes en todas las entidades seleccionadas.

1. Para los atributos que no se asignan automáticamente a un tipo semántico, seleccione un campo de tipo semántico, ingrese su nombre de tipo de atributo personalizado o déjelos sin asignar. Estos atributos se enumeran en **Definir los datos en los campos no asignados**.

1. Después de completar los pasos para cada entidad, seleccione **Guardar campos de origen**.

1. Seleccione **Siguiente**.

> [!div class="nextstepaction"]
> [Siguiente paso: Eliminar duplicados](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
