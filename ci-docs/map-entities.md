---
title: Seleccionar campos de origen para la unificación de datos
description: El primer paso en el proceso de unificación es seleccionar entidades, atributos, claves primarias y tipos semánticos para asignar datos al perfil de cliente unificado.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304586"
---
# <a name="select-source-fields-for-data-unification"></a>Seleccionar campos de origen para la unificación de datos

El primer paso en la unificación es seleccionar las entidades y campos dentro de sus conjuntos de datos que desea unificar. Seleccione entidades que contengan detalles relacionados con el cliente, como nombre, dirección, número de teléfono y correo electrónico. Puede seleccionar una o más entidades.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Seleccionar entidades y campos

1. Vaya a **Datos** > **Unificar**.

   Para clientes individuales (B a C), la página de destino **Unificar** muestra **Empezar** en el primer paso, **Campos de origen**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de pantalla de la página de destino Unificar para la experiencia de primera ejecución de clientes individuales.":::

   Para cuentas empresariales (B a B), la página de destino **Unificar** muestra **Unificar cuentas**, y meustra **Empezar** en el primer paso, **Campos de origen**. Los pasos **Unificar contactos (versión preliminar)** son opcionales y están pendientes de completar la unificación de la cuenta.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Captura de pantalla de la página de destino Unificar para la experiencia de primera ejecución de cuentas de negocio.":::

1. Seleccione **Comenzar**.

1. En la página **Campos de origen**, seleccione **Seleccionar entidades y campos**. El panel **Seleccionar entidades y campos** se muestra.

1. Seleccione al menos una entidad.

1. Para cada entidad seleccionada, identifique los campos que desea usar para hacer coincidir los registros de clientes y los campos para incluir en el perfil unificado. Estos campos se llaman *Atributos*. Puede seleccionar los atributos requeridos individualmente de una entidad o incluir todos los atributos de una entidad seleccionando la casilla de verificación en el nivel de la entidad. Puede buscar palabras clave en todos los atributos y entidades para seleccionar los atributos necesarios que desea asignar.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de pantalla de entidades y atributos seleccionados.":::

   En este ejemplo, agregamos las entidades **eCommerceContacts** y **loyCustomer**. Al elegir estas entidades, puede obtener información sobre cuáles de los clientes comerciales en línea son miembros del programa de fidelización.

1. Seleccione **Aplicar** para confirmar sus selecciones. Se muestran las entidades y atributos seleccionados.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccione la clave principal y el tipo semántico para los atributos

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de pantalla de las entidades seleccionadas con la clave principal no seleccionada." lightbox="media/m3_select_primary.png":::

Para cada entidad, realice los siguientes pasos.

1. Elija la **Clave principal**. La clave principal es un atributo exclusivo de la entidad. Para que un atributo pueda ser una clave principal válida, no debe incluir valores duplicados, no deben faltar valores ni debe haber valores nulos. Los atributos de tipo de datos de cadena, entero y GUID se admiten como claves principales.

1. Para usar modelos de IA para predicción inteligente de semántica, que ahorra tiempo y mejora la precisión, asegúrese de que la **asignación inteligente** está activada. La asignación inteligente proporciona recomendacones de semántica basada en IA en el campo **Tipo**.

1. Para cada atributo, elija un **Tipo** de semántica que mejor describa ese atributo, como el nombre, la ciudad o la dirección de correo electrónico.

   > [!NOTE]
   > En B a C, un campo debe corresponder al tipo semántico *Person.FullName* para completar el nombre del cliente en la tarjeta del cliente. En B a B, el nombre de la cuenta debe asignarse a *Organization.Name*. De lo contrario, las tarjetas de cliente aparecerán sin nombre.

   1. Para anular un tipo de atributo que el sistema identificó, seleccione otra opción. Si el tipo no existe, cree un tipo semántico personalizado seleccionando el campo **Tipo** para el atributo e ingresando su nombre de tipo semántico personalizado.

   1. Para agregar un atributo que contenga una URL a imágenes de perfil o logotipos disponibles públicamente, seleccione la entidad y el campo que contiene la URL. Escriba lo siguiente en el campo **Tipo**:
      - Para una persona: Person.ProfileImage
      - Para una organización: Organization.LogoImage

1. Revise los atributos donde se identifica automáticamente un tipo semántico. Estos atributos se enumeran en **Revisar campos mapeados**. Solo los atributos con el mismo tipo se pueden combinar en el paso **Unificar campos de clientes**. Los tipos semánticos se utilizan para sugerir ideas automáticamente. Asegúrese de que los tipos que elija sean coherentes en todas las entidades seleccionadas.

1. Para los atributos que no se asignan automáticamente a un tipo semántico, seleccione un campo de tipo semántico, ingrese su nombre de tipo de atributo personalizado o déjelos sin asignar. Estos atributos se enumeran en **Definir los datos en los campos no asignados**.

1. Después de completar los pasos para cada entidad, seleccione **Guardar campos de origen**.

1. Seleccione **Siguiente**.

> [!div class="nextstepaction"]
> [Siguiente paso: Eliminar duplicados](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
