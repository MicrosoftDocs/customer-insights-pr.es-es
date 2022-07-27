---
title: Relaciones entre entidades y rutas de entidades
description: Cree y administre relaciones entre entidades de múltiples fuentes de datos.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: 5477798a8b9e0771d390e403379b7447eb7baddd
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081855"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Relaciones entre entidades y rutas de entidades

Las relaciones conectan entidades y definen un gráfico de sus datos cuando las entidades comparten un identificador común, una clave externa. Se puede hacer referencia a esta clave externa de una entidad a otra. Las entidades conectadas habilitan la definición de segmentos y medidas basadas en múltiples orígenes de datos.

Hay tres tipos de relaciones: 
- Sistema no editable de relaciones, creado por el sistema como parte del proceso de unificación de datos
- Relaciones heredadas no editables, que se crean automáticamente a partir de la ingesta de fuentes de datos 
- Relaciones personalizadas editables, creadas y configuradas por usuarios

## <a name="non-editable-system-relationships"></a>Relaciones no editables de sistema

Durante la unificación de datos, las relaciones del sistema se crean automáticamente en función de la comparación inteligente. Estas relaciones ayudan a relacionar los registros del perfil del cliente con los registros correspondientes. El siguiente diagrama ilustra la creación de tres relaciones basadas en el sistema. La entidad del cliente se empareja con otras entidades para producir la entidad unificada *Cliente*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama con rutas de relación para la entidad cliente con tres 1-n Relaciones.":::

- La **relación *CustomerToContact*** fue creada entre la entidad *Cliente* y la entidad *Contacto*. La entidad *Cliente* obtiene el campo de clave **Contact_contactID** para relacionarse con el campo de clave de la entidad *Contacto* **contactID**.
- La **relación *CustomerToContact*** fue creada entre la entidad *Cliente* y la entidad *Cuenta*. La entidad *Cliente* obtiene el campo de clave **Account_accountId** para relacionarse con el campo de clave de la entidad *Cuenta* **accountID**.
- La **relación *CustomerToWebAccount*** fue creada entre la entidad *Cliente* y la entidad *WebAccount*. La entidad *Cliente* obtiene el campo de clave **WebAccount_webaccountID** para relacionarse con el campo de clave de la entidad *WebAccount* **webaccountId**.

## <a name="non-editable-inherited-relationships"></a>Relaciones no editables heredadas

Durante el proceso de ingestión de datos, el sistema verifica las fuentes de datos en busca de relaciones existentes. Si no existe ninguna relación, el sistema las crea automáticamente. Estos relaciones también se utilizan en procesos posteriores.

## <a name="create-a-custom-relationship"></a>Crear una relación personalizada

La relación consiste en una *entidad fuente* que contiene la clave externa y una *entidad objetivo* al que apunta la clave externa de la entidad de origen. 

1. Vaya a **Datos** > **Relaciones**.

2. Selecciona **Nueva relación**.

3. En el panel **Nueva relación**, proporcione la siguiente información:

   :::image type="content" source="media/relationship-add.png" alt-text="Nuevo panel lateral de relaciones con campos de entrada vacíos.":::

   - **Nombre de la relación**: nombre que refleja el propósito de la relación. Ejemplo: CustomerToSupportCase.
   - **Descripción**: Descripción de la relación.
   - **Entidad origen**: entidad que se utiliza como origen en la relación. Ejemplo: SupportCase.
   - **Entidad destino**: entidad que se utiliza como destino en la relación. Ejemplo: Cliente.
   - **Cardinalidad de fuente**: especifique la cardinalidad de la entidad fuente. La cardinalidad describe el número de elementos posibles en un conjunto. Siempre se relaciona con la cardinalidad del objetivo. Puedes elegir entre **Uno** y **Muchos**. Solo se admiten relaciones de varios a uno y de uno a uno.  
     - Varios a uno: varios registros de origen pueden relacionarse con un registro de destino. Ejemplo: varios casos de soporte de un solo cliente.
     - Uno a uno: un registro de origen único se relaciona con un registro de destino. Ejemplo: un ID de fidelidad para un solo cliente.

     > [!NOTE]
     > Puede crear una relación de varios a varios creando dos relaciones de varios a uno y una entidad de vinculación que conecte la entidad de origen y la entidad de destino.

   - **Cardinalidad de destino**: Seleccione la cardinalidad de los registros de la entidad de destino. 
   - **Campo de clave de origen**: el campo de clave externa en la entidad de origen. Ejemplo: SupportCase podría usar CaseID como un campo de clave externa.
   - **Campo clave de destino**: el campo clave de la entidad de destino. Ejemplo el cliente podría usar el campo clave **CustomerID** campo clave.

4. Seleccione **Guardar** para crear la relación personalizada.

## <a name="set-up-account-hierarchies"></a>Configurar jerarquías de cuenta

Los entornos que están configurados para usar cuentas de negocio como público de destino principal pueden configurar jerarquías de cuentas para cuentas comerciales relacionadas. Por ejemplo, una empresa que tiene unidades de negocio independientes. 

Las organizaciones crean jerarquías de cuentas para administrar mejor las cuentas y sus relaciones entre sí. Customer Insights admite jerarquías de cuentas primarias-secundarias que ya existen en los datos de clientes ingeridos. Por ejemplo, cuentas de Dynamics 365 Sales. Estas jerarquías se pueden configurar en la página **Relaciones**.

1. Vaya a **Datos** > **Relaciones**.
1. Seleccione la pestaña **Jerarquía de cuenta**.
1. Seleccione **Nueva jerarquía de cuenta**. 
1. En el panel **Jerarquía de cuentas**, proporcione un nombre para la jerarquía. El sistema crea un nombre para la entidad de salida. Puede modificar el nombre de la entidad de nombre de salida.
1. Seleccione la entidad que contiene la jerarquía de cuentas. Suele estar en la misma entidad que contiene las cuentas.
1. Seleccione el **ID de cuenta** y el **Id. de cuenta primaria** de la entidad seleccionada 
1. Seleccione **Guardar** para aplicar la configuración y finalizar la jerarquía de cuentas.

## <a name="view-relationships"></a>Vista de relaciones

La página Relaciones enumera todos los Relaciones que se han creado. Cada fila representa una relación, que también incluye detalles sobre la entidad de origen, la entidad de destino y la cardinalidad. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de Relaciones y opciones en la barra de acciones de la página Relaciones.":::

Esta página ofrece un conjunto de opciones para relaciones existentes y nuevas: 
- **Nueva relación**: [Crear una relación personalizada](#create-a-custom-relationship).
- **Visualizador**: [Explore el visualizador de relaciones](#explore-the-relationship-visualizer) para ver un diagrama de red de relaciones existente y su cardinalidad.
- **Filtrado por**: elija el tipo de Relaciones para mostrar en la lista.
- **Buscar Relaciones**: utilice una búsqueda basada en texto en las propiedades de Relaciones.

### <a name="explore-the-relationship-visualizer"></a>Explore el visualizador de relaciones

El visualizador de relaciones muestra un diagrama de red de relaciones existente entre entidades conectadas y su cardinalidad. También visualiza la ruta de la relación.

Para personalizar la vista, puede cambiar la posición de los cuadros arrastrándolos en el lienzo.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla del diagrama de red del visualizador de relaciones con conexiones entre entidades relacionadas.":::

Opciones disponibles: 
- **Exportar como imagen**: guarda la vista actual como un archivo de imagen.
- **Cambiar a diseño horizontal / vertical**: cambia la alineación de las entidades y relaciones.
- **Editar**: actualiza las propiedades de relaciones personalizadas en el panel de edición y guarda los cambios.

## <a name="relationship-paths"></a>Rutas de relación

Una ruta de relación describe las entidades que están conectadas con Relaciones entre una entidad de origen y una entidad de destino. Se utiliza al crear un segmento o una medida que incluye otras entidades además de la entidad de perfil unificado y existen múltiples opciones para llegar a la entidad de perfil unificado. 

Una ruta de relación informa al sistema sobre qué Relaciones acceder a la entidad de perfil unificado. Diferentes rutas de relación pueden producir resultados diferentes.

Por ejemplo, la entidad *eCommerce_eCommercePurchases* tiene las siguientes relaciones con la entidad *Cliente* del perfil unificado:

- eCommerce_eCommercePurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente 

Una ruta de relación determina qué entidades puede usar al crear reglas para medidas o segmentos. La elección de la opción con la ruta de relación más larga probablemente producirá menos resultados porque los registros coincidentes deben ser parte de todas las entidades. En este ejemplo, un cliente debe haber comprado productos a través de comercio electrónico (eCommerce_eCommercePurchases) en un punto de venta (POS_posPurchases) y participar en nuestro programa de fidelización (loyaltyScheme_loyCustomers). Al elegir la primera opción, es probable que obtenga más resultados porque los clientes solo necesitan existir en una entidad adicional.

### <a name="direct-relationship"></a>Relación directa

Una relación se clasifica como **relación directa** cuando una entidad fuente se relaciona con una entidad objetivo con una sola relación.

Por ejemplo, si una entidad de actividad llamada *eCommerce_eCommercePurchases* se conecta a una entidad objetivo *eCommerce_eCommerceContacts* a través de *ContactId* solo, es una relación directa.

:::image type="content" source="media/direct_Relationship.png" alt-text="La entidad de origen se conecta directamente a la entidad de destino.":::

#### <a name="multi-path-relationship"></a>Relación de múltiples rutas

Una **relación de múltiples rutas** es un tipo especial de relación directa que conecta una entidad de origen con más de una entidad de destino.

Por ejemplo, si una entidad de actividad llamada *eCommerce_eCommercePurchases* se relaciona con dos entidades objetivo, ambas *eCommerce_eCommerceContacts* y *loyaltyScheme_loyCustomers*, es una relación de múltiples rutas.

:::image type="content" source="media/multi-path_relationship.png" alt-text="La entidad de origen se conecta directamente a más de una entidad de destino a través de una relación de varios saltos.":::

### <a name="indirect-relationship"></a>Relación indirecta

Una relación se clasifica como **relación indirecta** cuando una entidad fuente se relaciona con una o más entidades adicionales antes de relacionarse con una entidad de destino.

#### <a name="multi-hop-relationship"></a>Relación de múltiples saltos

Una *relación de varios saltos* es una *relación indirecta* que le permite conectar una entidad de origen a una entidad de destino a través de una o más entidades intermediarias.

Por ejemplo, si una entidad de actividad llamada *eCommerce_eCommercePurchasesWest* se conecta a una entidad intermedia llamada *eCommerce_eCommercePurchasesEast* y luego se conecta a una entidad de destino llamada *eCommerce_eCommerceContacts*, es una relación de varios saltos.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="La entidad de origen se conecta directamente a una entidad de destino con una entidad intermedia.":::

### <a name="multi-hop-multi-path-relationship"></a>Relación de múltiples saltos y rutas

Las relaciones de múltiples saltos y rutas se pueden usar juntas para crear **relaciones de múltiples saltos y rutas**. Este tipo especial combina las funciones de las relaciones de **múltiples saltos** y **múltiples rutas**. Le permite conectarse a más de una entidad de destino mientras usa entidades intermedias.

Por ejemplo, si una entidad de actividad llamada *eCommerce_eCommercePurchasesWest* se conecta a una entidad intermedia llamada *eCommerce_eCommercePurchasesEast* y luego se conecta a una entidad de destino llamada *eCommerce_eCommerceContacts* y *loyaltyScheme_loyCustomers*, es una relación de varias rutas y saltos.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="La entidad de origen se conecta directamente a una entidad de destino y se conecta a otra entidad de destino a través de una entidad intermedia.":::

## <a name="manage-existing-relationships"></a>Administrar las relaciones existentes 

En la página Relaciones, cada relación está representada por una fila. 

Seleccione una relación y elija una de las siguientes opciones: 
 
- **Editar**: actualiza las propiedades de relaciones personalizadas en el panel de edición y guarda los cambios.
- **Eliminar**: elimina relaciones personalizadas.
- **Vista**: ver relaciones creadas por el sistema y heredadas. 

## <a name="next-step"></a>Siguiente paso

El sistema y las relaciones personalizadas se usan para [crear segmentos](segments.md) y [medidas](measures.md) basándose en múltiples orígenes de datos que ya no están aislados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
