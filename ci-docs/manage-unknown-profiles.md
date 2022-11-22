---
title: Administrar perfiles desconocidos con Customer Insights
description: Trabaje con perfiles de clientes desconocidos que se crean y administran en Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776842"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Administrar perfiles desconocidos con Customer Insights

Los usuarios de Internet a menudo no están identificados o son anónimos en línea. Incluso los clientes más leales pueden aparecer como "desconocidos" si no están registrados en diferentes dispositivos. Para muchas marcas, los usuarios conocidos o autenticados son la minoría a pesar de las crecientes expectativas de los clientes en torno a la personalización. Con el futuro de las cookies de terceros en duda, la gestión de las preferencias de los usuarios basadas en los datos propios en su lugar es crucial para lograr experiencias personalizadas.

La personalización memorable depende de su grado de conocimiento del cliente y Customer Insights lo ayuda a hacerlo mediante el seguimiento de todos sus clientes.  No tiene que limitar o detener el uso de los datos recopilados al inicio del recorrido del cliente. Customer Insights le permite traer sus propios datos para crear un perfil de cliente para usuarios desconocidos. Luego puede usar ese perfil para otras acciones, a pesar de que falte la información de contacto. Importe datos propios de fuentes como la web, dispositivos móviles o sistemas de CRM en Customer Insights para enriquecer los perfiles de los clientes de forma continua. A medida que unifique más interacciones, [cambie el cliente *desconocido* a un cliente *conocido*](unknown-to-known.md).

## <a name="sample-scenario"></a>Escenario de ejemplo

Suponga que un usuario utiliza su dispositivo móvil para navegar por su sitio de comercio electrónico. El sitio web asigna al visitante "mobile_guest123" como un identificador único y comienza a recopilar actividades de comportamiento basadas en su actividad en línea. Por ejemplo, qué páginas visitaron, cuánto tiempo pasaron en esas páginas o en qué enlaces hicieron clic. No sabe su nombre o dirección de correo electrónico, pero estos datos pueden ayudar a proporcionar a las marcas información significativa sobre este usuario específico. A su vez, puede poner en práctica esos conocimientos la próxima vez que el usuario visite el sitio. Consulte Customer Insights para "mobile_guest123" para recuperar la lista de segmentos del usuario, como "orgánico", "clientes de pedidos anticipados móviles", "clientes de alto valor", etc., o recuperar el perfil para crear experiencias web personalizadas. También puede exportar los datos a cualquier sistema de activación para hacer lo mismo.

## <a name="prerequisites"></a>Requisitos previos

- Ingerir datos propios en Customer Insights
- Cada entidad tiene una identificación única que se establece como clave principal
- Se unifica cada entidad con una clave primaria para la personalización
- El sistema de gestión de contenido de su sitio puede usar las API (para la personalización web basada en la comunicación directa con Customer Insights)

La siguiente tabla muestra un ejemplo simplificado de cómo se pueden capturar eventos web de alto valor.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Vista de producto|
|2|09-18-2022 10:05:00|abc123|CookieID1|Vista de producto|
|3|09-18-2022 10:10:00|abc123|CookieID1|Agregar al carro|
|4|09-21-2022 09:05:00|abc123|CookieID1|Vista de producto|

## <a name="data-ingestion"></a>Ingesta de datos

Para obtener más información acerca de las opciones disponibles de ingesta de datos, consulte [Información general de orígenes de datos](data-sources.md).

## <a name="data-unification"></a>Unificación de datos

Para obtener más información sobre cómo unificar perfiles de cliente, consulte [Descripción general de la unificación de datos](data-unification.md).

## <a name="get-insights"></a>Obtener información

[Enriquezca](enrichment-hub.md) sus datos, genere [medidas](measures.md) y cree [segmentos](segments.md) para una mayor activación.

Por ejemplo, puede crear segmentos de usuarios desconocidos que navegaron por las mismas páginas de productos pero nunca completaron el pago.

## <a name="activation"></a>Activación

Con sus datos en Customer Insights y sus conocimientos listos para trabajar, puede utilizar Customer Insights para la personalización:

1. Utilice [API OData](apis.md) para recuperar una pertenencia a un segmento o un perfil de cliente Para obtener más ejemplos, consulte [Ejemplos de consultas de OData para las API de Customer Insights](odata-examples.md).

1. [Exporte](export-destinations.md) sus datos a sus sistemas de activación.

Ejemplo: un usuario desconocido visita un sitio web varias veces y visita las páginas de productos de varios modelos de zapatos de cuero. Con esos datos disponibles en Customer Insights, puedes incluir al usuario desconocido en el segmento de personas que están interesadas en zapatos de cuero. Use este segmento para informar la personalización de la creación de su sitio web para los visitantes que regresan. En la próxima visita, el sitio reconoce al usuario desconocido y podría ofrecerle un cupón del 10% en zapatos de cuero.

[!INCLUDE [footer-include](includes/footer-banner.md)]
