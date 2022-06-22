---
title: Usar consentimiento del cliente
description: Respete las preferencias de consentimiento de sus clientes en Customer Insights importando datos de consentimiento.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947508"
---
# <a name="use-customer-consent"></a>Usar consentimiento del cliente

Las regulaciones de privacidad y protección de datos ofrecen a las personas el derecho de gobernar cómo una organización usa sus datos personales. Ejemplos de dichas regulaciones son el Reglamento General de Protección de Datos en la Unión Europea o la Ley de Privacidad del Consumidor de California en los Estados Unidos. Estas regulaciones permiten a las personas optar por que sus datos personales no sean recopilados, procesados o compartidos con terceros.  

Los clientes pueden optar por retirar o retener su consentimiento para formas específicas de contacto. También pueden solicitarle que los excluya de la recopilación, el almacenamiento, el uso o la venta de sus datos personales. Es importante que su organización respete el consentimiento y las preferencias de privacidad de todos los clientes.  

Dynamics 365 Customer Insights lo ayuda a cumplir con las solicitudes de sus clientes importando y almacenando sus preferencias como parte de los perfiles de clientes unificados.

Si los datos de consentimiento se almacenan por separado de los perfiles de sus clientes, [agregue sus datos de consentimiento como un nuevo origen de datos](#import-and-unify-consent-data). El origen de datos que contiene los datos de consentimiento se agrega al proceso de unificación de datos. La unificación exitosa de los datos de consentimiento y los perfiles de clientes conduce a perfiles de clientes unificados que contienen la información de consentimiento. Para los perfiles de clientes que ya contienen información de consentimiento, vaya directamente a la sección [usar datos de consentimiento](#use-consent-data).

## <a name="prerequisites"></a>Requisitos previos

La siguiente información debe estar disponible en sus datos de origen para unificar los datos de consentimiento con otros perfiles de clientes:

- Clave alternativa para asignar la información de consentimiento a los perfiles de usuario en Customer Insights. Por ejemplo, una dirección de correo electrónico o un número de teléfono.
- Valor del consentimiento para determinar el estado del consentimiento del cliente.

Considere agregar la siguiente información *opcional*:

- Clave principal para actualizar el estado de consentimiento si un cliente solicita un cambio.
- Tipo de consentimiento, si hay más de una forma de procesar la información del cliente.
- Fecha de consentimiento o cualquier otro tipo de datos relevantes para sus escenarios de consentimiento.

Tabla de ejemplo de una base de datos de consentimiento simple con múltiples opciones de consentimiento:

|Identificador de consentimiento (clave principal)   |Correo electrónico (clave alternativa)  |Opción de consentimiento  |Valor de consentimiento  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Boletín       |  False       |
|2    |  holly@contoso.com       |  Actualizaciones del producto       |  VERDADERO       |
|3    |  frank@contoso.com       |  Boletín       | VERDADERO        |
|4    |  frank@contoso.com       |  Actualizaciones del producto       |  False       |

## <a name="import-and-unify-consent-data"></a>Importar y unificar datos de consentimiento

Puede importar datos de consentimiento de la misma manera que ingiere otras fuentes de datos a Customer Insights. Para obtener más información sobre las fuentes de datos admitidas y cómo importarlas, consulte [Descripción general de los orígenes de datos](data-sources.md).

Para obtener más información sobre cómo unificar sus orígenes de datos, consulte [Descripción general de la unificación de datos](data-unification.md).

## <a name="use-consent-data"></a>Usar datos de consentimiento

Una vez que sus datos de consentimiento sean parte de sus perfiles de cliente unificados, puede usarlos en Customer Insights. Por ejemplo, cree un segmento con una regla para asegurarse de respetar las preferencias de privacidad y protección de datos de sus clientes. Las reglas que respaldan las preferencias de consentimiento se utilizan para excluir a los usuarios de un segmento en función de los atributos del perfil. Agregar una regla a un segmento que excluya los perfiles de clientes que no dieron su consentimiento para contactar.

Con referencia a la tabla de muestra anterior, un segmento podría contener esta regla: `Consent option=Newsletter & Consent value=True`. Esta configuración da como resultado un segmento que respeta las preferencias de contacto para enviar un boletín.

Para obtener más información sobre crear segmentos, consulte [Crear segmentos](segment-builder.md).

Una vez que se crea el segmento, puede usar una de las muchas [opciones de exportación](export-destinations.md) para utilizar el segmento en otras aplicaciones.

## <a name="ensure-updated-consent-status"></a>Garantizar el estado de consentimiento actualizado

Es importante mantener actualizado el estado de consentimiento de sus clientes. La actualización programada en Customer Insights siempre importa el estado más reciente de sus fuentes de datos. Esta información luego se procesa a través de la unificación de datos y da como resultado perfiles de clientes actualizados. Estos perfiles actualizados luego se usan para actualizar segmentos para asegurarse de que trabaja con la información más actualizada.

En otras palabras, asegúrese de que los datos de origen que se importan a Customer Insights siempre tengan la información más reciente.

Para más información, vea [Actualizar segmentos manualmente](segments.md#refresh-segments) o [Configurar una actualización programada](system.md#schedule-tab).
