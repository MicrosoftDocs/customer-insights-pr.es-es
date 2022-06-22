---
title: Enriquezca los perfiles de los clientes con datos de ubicación de Azure Maps
description: Información general sobre el enriquecimiento propio con Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953649"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enriquecimiento de perfiles de clientes con Azure Maps (versión preliminar)

Azure Maps proporciona datos y servicios centrados en la ubicación para brindar experiencias basadas en datos geoespaciales con inteligencia de ubicación integrada. Los servicios de enriquecimiento de datos de Azure Maps mejoran la precisión de la información de ubicación de sus clientes. Aporta capacidades como la normalización de direcciones y la extracción de latitud y longitud a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

- Debe disponer de una suscripción activa de Azure Maps. Para obtener una suscripción, [suscríbase o consiga una prueba gratuita](https://azure.microsoft.com/services/azure-maps/).

- Una [conexión](connections.md) a Azure Maps [configurada](#configure-the-connection-for-azure-maps) por un administrador.

## <a name="configure-the-connection-for-azure-maps"></a>Configurar la conexión para Azure Maps

Debe ser un [Administrador](permissions.md#admin) en Customer Insights y tener una clave de API de Azure Maps activa.

1. Seleccione **Agregar conexión** al configurar un enriquecimiento, o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Página de configuración de conexión de Azure Maps.":::

1. Introduzca un nombre para la conexión y una clave de API de Azure Maps válida.

1. Revise y proporcione su consentimiento para [Privacidad y cumplimiento de datos](#data-privacy-and-compliance) seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración y luego seleccionar **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Al habilitar Dynamics 365 Customer Insights para transmitir datos a Azure Maps, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Azure Maps cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para obtener más información, vaya a [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en el mosaico **Ubicación** de Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Mosaico de Azure Maps.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione la conexión. Contacte con un administrador si no hay conexión disponible.

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos de cliente** y elija el perfil o segmento que desea enriquecer con datos de Microsoft. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

1. Defina qué tipo de campos de sus perfiles unificados usar para la coincidencia: la dirección principal y/o secundaria. Puede especificar una asignación de campo para ambas direcciones y enriquecer los perfiles para ambas direcciones por separado. Por ejemplo, para una dirección particular y una dirección comercial. Seleccione **Siguiente**.

1. Asigne sus campos al datos de ubicación de Azure Maps. Los campos **Calle 1** y **Código postal** son obligatorios para la dirección primaria y/o secundaria seleccionadas. Para mayor precisión de coincidencia, agregue más campos.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Asignación de atributos de Azure Maps.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Revise la **Configuración avanzada** que ofrece la máxima flexibilidad para manejar casos de uso avanzados. Sin embargo, normalmente no es necesario cambiar los siguientes valores predeterminados.

   - **Tipo de direcciones**: la mejor coincidencia de dirección es devuelta incluso si está incompleta. Para obtener solo direcciones completas, por ejemplo, direcciones que incluyen el número de casa, desmarque todas las casillas de verificación excepto **Direcciones de puntos** .
   - **Idioma**: las direcciones se devuelven en el idioma según la región de la dirección. Para aplicar un idioma de dirección estandarizado, seleccione el idioma en el menú desplegable. Por ejemplo, seleccionando **Inglés** devuelve **Copenhague, Dinamarca** en vez de **København, Dinamarca**.
   - **Número máximo de resultados**: número de resultados por dirección.

1. Seleccione **Siguiente**.

1. Proporcione un **nombre** para el enriquecimiento y la **Nombre de entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **Número de clientes enriquecidos por campo** proporciona un desglose de la cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
