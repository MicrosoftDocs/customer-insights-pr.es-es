---
title: Personalice sus experiencias con datos sobre usuarios conocidos y desconocidos
description: Incorpore la información sobre usuarios anteriormente desconocidos cuando conozca su identidad.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224316"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalice sus experiencias con datos sobre usuarios conocidos y desconocidos

La gestión de los datos de los clientes no es un desafío nuevo, pero se está volviendo cada vez más difícil a medida que los usuarios navegan por los diversos canales digitales que ofrecen las marcas. Un usuario que es conocido (autenticado) en un canal se vuelve desconocido (no autenticado) en otro si no ha iniciado sesión. El problema a menudo es que los usuarios no autenticados (desconocidos) no tienen un id. común. Podría usarse para asociar atributos de perfiles significativos y generar perfiles de clientes unificados. Customer Insights ayuda a resolver este problema al ingerir datos de métodos de seguimiento en sus sistemas de origen. La consolidación de perfiles desconocidos y conocidos ofrece a las organizaciones una vista completa de los perfiles actualizados y sus transacciones históricas, comportamientos y datos demográficos. Incluso va un paso más allá al proporcionar una resolución de identidad que le permite unificar la actividad del cliente en múltiples canales, incluido su sitio web, compras en la tienda, programas de fidelización, etc.

## <a name="sample-scenario"></a>Escenario de ejemplo

Pensemos en una cadena de café, que tiene una amplia base de clientes que compra café y alimentos en las tiendas y pide productos en línea. A menudo, los visitantes en línea no están autenticados cuando navegan por los productos, lo que los convierte en "usuarios desconocidos". Es difícil para la cadena de café ofrecer ofertas y experiencias personalizadas si los usuarios son desconocidos. Por otro lado, los clientes pueden iniciar sesión en su cuenta y convertirse en "usuarios conocidos" de la empresa al unirse a un sistema de fidelización, lo que a su vez permite experiencias más personalizadas. Customer Insights puede ayudar a la cadena de café a obtener información sobre usuarios conocidos y previamente desconocidos.

Con Customer Insights, la empresa puede combinar perfiles de clientes con datos de actividad de sesiones no autenticadas (desconocidas) después de que un usuario inicia sesión y se vuelve conocido. La cadena de café puede traer datos de otros orígenes de datos utilizando conectores integrados en Customer Insights para combinar identidades de clientes de varios canales.

## <a name="prerequisites"></a>Requisitos previos

- Los datos web se recopilan y contienen los “id. de visitante” para todos los visitantes.
- Los datos web contienen "id. de usuario autenticadas" para visitantes registrados. Estas id. están vinculadas con el sistema de fidelización.
- Los datos de eventos de alto valor como “Vista del producto” y “Pago” se definen e incluyen en los datos de origen junto con la marca de tiempo del evento y un id. de evento.

La siguiente tabla muestra un ejemplo simplificado de cómo se pueden capturar eventos web de alto valor.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|23-07-2022 10:00:00|abc123|--|Vista de producto|
|2|23-07-2022 10:05:00|abc123|707|Inicio de sesión de fidelización|
|3|23-07-2022 10:10:00|abc123|707|Tomar prestado|
|4|23-07-2022 10:20:00|xyz789|--|Vista de producto|

## <a name="data-ingestion"></a>Ingesta de datos

Los datos sobre los clientes pueden originarse en su sitio web como datos de eventos y pueden almacenarse en sus propios servicios de análisis de datos internos o de terceros. Los datos web contienen usuarios conocidos y desconocidos si el sitio web tiene un flujo de autenticación que se integra con un servicio de autenticación. Por ejemplo, un sistema de comercio electrónico que requiere que los usuarios proporcionen sus detalles completos para finalizar una transacción de compra. O un sistema de fidelización que requiere autenticación para confirmar un destinatario válido de los descuentos de recompensas.

Los datos de eventos de nuestro ejemplo anterior contienen los distintos id. de perfil de los usuarios conocidos y desconocidos. En los eventos 1 y 4, los usuarios son desconocidos, mientras que en los eventos 2 y 3, el usuario con id. abc123 se registra en un programa de fidelización.

:::image type="content" source="media/website-data-source.png" alt-text="Orígenes de datos, incluido el sitio web de Contoso.":::

Para obtener más información acerca de las opciones disponibles de ingesta de datos, consulte [Información general de orígenes de datos](data-sources.md).

## <a name="data-unification"></a>Unificación de datos

La convergencia de identidades desconocidas con identidades conocidas ayuda a habilitar la personalización basada en los comportamientos de los usuarios, independientemente del estado de su perfil (conocido o desconocido). El contenido personalizado para todos los usuarios ayuda a los clientes a llegar rápidamente a los productos o servicios más relevantes que les interesan en ese momento.

Dado que algunos de los usuarios de nuestros datos son conocidos, podemos usar Customer Insights para combinar esos datos con el perfil del usuario. Para obtener más información sobre cómo unificar perfiles de cliente, consulte [Descripción general de la unificación de datos](data-unification.md).

1. Seleccione los campos de origen de la entidad de datos web. Utilice los datos de perfil que se almacenan en sus datos web y seleccione los campos que representan id. con datos demográficos.

   :::image type="content" source="media/website-source-fields.png" alt-text="Campos de origen para el origen de datos web.":::

1. Agregar reglas para combinar registros duplicados. Para datos web, elija los datos más completos.

1. Configure reglas y condiciones de coincidencia. Los datos de eventos de los perfiles web de este ejemplo se compararán en id. con los perfiles de los otros orígenes de datos que contienen información del cliente. Configure reglas de coincidencia exacta en id. como reglas separadas con cada una de las otras entidades de perfil que tienen una clave principal correspondiente o una coincidencia de id. En el ejemplo, los datos del perfil del evento web se usan como la última entidad coincidente para que otros datos del perfil se combinen primero.
   1. No comprobar **Incluir todos los registros** crea perfiles unificados para usuarios conocidos e incluye sus id. de usuarios desconocidos correspondientes. Es útil en escenarios en los que está interesado en ver las actividades de comportamiento pasadas de usuarios conocidos cuando aún eran desconocidos.
   1. La comprobación de **Incluir todos los registros** crea registros de perfil separados para usuarios desconocidos. Los usuarios desconocidos obtienen un id. de cliente único. En el futuro, cuando se asocie un perfil conocido en los datos del perfil de eventos web, el recorrido del usuario recién conocido se podrá ver y utilizar para la personalización en función de los datos de comportamiento pasados desconocidos también.

:::image type="content" source="media/website-match-rule.png" alt-text="Regla de coincidencia para la entidad del sitio web de origen de datos.":::

## <a name="get-insights"></a>Obtener información

Si se crean perfiles de clientes para usuarios desconocidos y conocidos, los datos de eventos web de gran valor se pueden utilizar como [actividades](activities.md). Estas actividades se pueden utilizar para crear más información. Por ejemplo, los clientes que visitaron un sitio web hace seis meses (cuando aún eran desconocidos) o los clientes que no tienen un id. de fidelización nunca completaron un pago.

:::image type="content" source="media/website-known-unknown.png" alt-text="Captura de pantalla de la página de clientes con clientes conocidos y desconocidos.":::

[Enriquezca](enrichment-hub.md) sus datos, genere [medidas](measures.md) y cree [segmentos](segments.md) para una mayor activación.

Por ejemplo, puede crear segmentos de usuarios conocidos que miraron algunos productos pero nunca completaron el pago.

Para obtener más información, consulte [Información general de los segmentos](segments.md).

## <a name="activate-insights"></a>Activar informaciones

Hay varias formas de exportar sus datos y tomar medidas en función de los conocimientos subyacentes.

Para obtener más información, consulte [Información general de exportación](export-destinations.md).
