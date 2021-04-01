---
title: Asignar entidades para la unificación de datos
description: Mapa de datos para crear perfiles de cliente unificados.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596014"
---
# <a name="map-entities-and-attributes"></a>Correlacionar entidades y atributos

**Mapa** es la primera etapa en el proceso de unificación de datos de informaciones de público. La asignación consta de tres fases:

- *Selección de entidades*: identifique las entidades combinables que conducen a un conjunto de datos con información más completa sobre sus clientes.
- *Selección de atributos*: para cada entidad, identifique las columnas que desea combinar y conciliar en las fases de *coincidencia* y *combinación*. Estas columnas se llaman *Atributos*.
- *Selección de clave principal y tipo semántico*: Para cada entidad, identifique un atributo que desee definir como clave principal para esa entidad, y para cada atributo, identifique un tipo semántico que mejor describa ese atributo.

Para obtener más información sobre el flujo general de unificación de datos, consulte [Unificar](data-unification.md).

## <a name="select-the-first-entities"></a>Seleccione las primeras entidades

1. En las informaciones de público, vaya a **Datos** > **Unificar** > **Asignar**.

2. Inicie la fase de mapa seleccionando **Seleccionar entidades**.

3. Seleccione las entidades y atributos que desea utilizar en las fases *coincidencia* y *combinación*. Puede seleccionar los atributos requeridos individualmente de una entidad o incluir todos los atributos de una entidad seleccionando la casilla **Incluir todos los campos** en el nivel de entidad. Se recomienda seleccionar al menos dos entidades para beneficiarse del proceso de unificación de datos.

   > [!div class="mx-imgBorder"]
   > ![Ejemplo de agregar entidades](media/data-manager-configure-map-add-entities-example.png "Ejemplo de agregar entidades")

   En este ejemplo, agregamos las entidades **eCommerceContactos** y **loyCustomers**. Al elegir estas entidades, puede obtener información sobre cuáles de los clientes comerciales en línea son miembros del programa de fidelización.
   
   Puede buscar palabras clave en todos los atributos y entidades para seleccionar los atributos necesarios que desea asignar.
   
     > [!div class="mx-imgBorder"]
   > ![Ejemplo de campos de búsqueda](media/data-manager-configure-map-search-fields-example.png "Ejemplo de campos de búsqueda")

4. Seleccione **Aplicar** para confirmar sus selecciones.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccione la clave principal y el tipo semántico para los atributos

Después de seleccionar sus entidades, la página **Mapa** enumera las entidades seleccionadas para su revisión. Defina la clave principal de una entidad e identifique el tipo semántico de un atributo en la entidad.

- **Clave principal**: seleccione un atributo como clave principal para cada una de las entidades. Para que un atributo pueda ser una clave principal válida, no debe incluir valores duplicados, no deben faltar valores ni debe haber valores nulos. Los atributos de tipo de datos de cadena, entero y GUID se admiten como claves principales y se mostrarán en un campo para que usted seleccione.

- **Tipo semántico de atributo**: Categorías de los atributos, como dirección de correo electrónico o nombre. Para usar modelos de IA para predicción inteligente de semántica, ahorrar tiempo y mejorar la precisión, configure **Asignación inteligente** a **Activada**. La asignación inteligente destaca la recomendación de semántica basada en IA en el campo **Tipo**. Si lo configura en **Desactivado**, verá nuestras recomendaciones de asignación regular. Puede seleccionar cualquier tipo semántico de la lista de opciones disponibles y anular la selección sugerida.

> [!div class="mx-imgBorder"]
> ![Tipo de atributo y predicción de semántica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo y predicción de semántica")

También es posible agregar un tipo semántico personalizado. Seleccione el campo de tipo para un atributo y escriba el nombre de tipo semántico personalizado. De esta forma, también puede cambiar los tipos de atributos que el sistema identificó.

Todos los atributos para los que se identifica automáticamente un tipo semántico se agrupan en la sección **Revisar campos asignados**. Revise estos atributos y sus tipos semánticos porque se utilizarán para combinar sus entidades en el paso de combinación de la unificación de datos.

Los atributos que no se asignan automáticamente a un tipo semántico se agrupan en la sección **Definir los datos en los campos sin asignar**. Seleccione el campo de tipo semántico para los atributos sin asignar, o introduzca su nombre de tipo de atributo personalizado.

> [!div class="mx-imgBorder"]
> ![Clave principal y tipo de atributo](media/data-manager-configure-map-add-attributes.png "Clave principal y tipo de atributo")

> [!NOTE]
> Un campo se debe asignar al tipo semántico Person.FullName para completar el nombre del cliente en la tarjeta del cliente. De lo contrario, las tarjetas de cliente aparecerán sin nombre. 

## <a name="add-and-remove-attributes-and-entities"></a>Agregar y quitar atributos y entidades

1. En **Unificar** > **Asignar**, seleccione **Editar campos**.

2. En el panel **Editar campos**, agregue o quite atributos y entidades. Utilice la búsqueda o desplácese para buscar y seleccionar sus atributos y entidades de interés. No puede eliminar un atributo o una entidad si ya se han asociado.

   > [!div class="mx-imgBorder"]
   > ![Agregar o quitar atributos](media/configure-data-map-edit.png "Agregar o quitar atributos")

3. Seleccione **Aplicar**.

## <a name="add-images-to-profiles"></a>Agregar imágenes a perfiles

Si una entidad contiene URL para imágenes de perfil o logotipos disponibles públicamente, puede agregarlas al perfil de cliente unificado.

Seleccione la entidad y busque el campo que contiene la URL de la imagen de perfil. En el campo de entrada **Tipo**, escriba manualmente el siguiente valor: 
- Para una persona: Person.ProfileImage
- Para una organización: Organization.LogoImage

Continúe con los pasos de unificación y asegúrese de que el atributo que contiene la URL de la imagen también se agregue en el paso [Combinación](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Establecer atributos para organizaciones

Para las organizaciones (versión preliminar), el tipo de atributo debe asignarse a "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Clave principal y tipo de atributo B2B](media/configure-data-map-edit-b2b.png "Clave principal y tipo de atributo B2B")

## <a name="next-step"></a>Paso siguiente

Como parte del proceso de unificación de datos, vaya a la página **Coincidencia**. Visite [**Coincidencia**](match-entities.md) para obtener información sobre esta fase.

> [!TIP]
> Mira el siguiente video: [Primeros pasos: crear un perfil de cliente unificado](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]