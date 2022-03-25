---
title: Enriquezca los perfiles de los clientes con datos de ubicación de Azure Maps
description: Información general sobre el enriquecimiento propio con Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376667"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enriquecimiento de perfiles de clientes con Azure Maps (versión preliminar)

Azure Maps proporciona datos y servicios centrados en la ubicación para brindar experiencias basadas en datos geoespaciales con inteligencia de ubicación integrada. Los servicios de enriquecimiento de datos de Azure Maps mejoran la precisión de la información de ubicación de sus clientes. Aporta capacidades como la normalización de direcciones y la extracción de latitud y longitud a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

Para configurar el enriquecimiento de datos de Azure Maps, se deben cumplir los siguientes requisitos previos:

- Tener una suscripción de Azure Maps activa. Para obtener una suscripción, puede [registrarse u obtener una prueba gratis](https://azure.microsoft.com/services/azure-maps/).

- Tiene disponible una [conexión](connections.md) de Azure Maps *o* tiene permisos de [Administrador](permissions.md#admin) y una clave de API de Azure Maps activa.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento**. 

1. En el icono **Ubicación**, seleccione **Enriquecer mis datos**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Mosaico de Azure Maps.":::

1. Seleccione una [conexión](connections.md) en la lista desplegable. Póngase en contacto con un administrador si no hay ninguna conexión de Azure Maps disponible. Si es administrador, puede [configurar la conexión para Azure Maps](#configure-the-connection-for-azure-maps). 

1. Seleccione **Siguiente** para confirmar la selección.

1. Elija **Conjunto de datos de cliente** que desea enriquecer con datos de ubicación de Azure Maps. Puede seleccionar la entidad **Cliente** para enriquecer todos sus perfiles de cliente, o seleccionar una entidad de segmento para enriquecer la dirección solo en los perfiles de cliente contenidos en ese segmento.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Captura de pantalla al elegir el conjunto de datos de cliente.":::

1. Elija si desea asignar campos a la dirección principal y/o secundaria. Puede especificar una asignación de campo para ambas direcciones y enriquecer los perfiles para ambas direcciones por separado, por ejemplo, para una dirección particular y una comercial. Seleccione **Siguiente**.

1. Defina qué tipo de campos de sus perfiles unificados utilizar para buscar datos de ubicación coincidentes desde Azure Maps. Los campos **Calle 1** y **Código postal** son obligatorios para la dirección principal o secundaria seleccionadas. Para una mayor precisión de coincidencia, puede agregar más campos.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Página de configuración de enriquecimiento de Azure Maps.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Evalúe si desea modificar la **Configuración avanzada**. Estos ajustes se proporcionan para brindar la máxima flexibilidad para manejar casos de uso avanzados, pero los valores predeterminados serán adecuados en la mayoría de los casos:
   - **Tipo de direcciones**: el comportamiento predeterminado es que el enriquecimiento devolverá la mejor coincidencia de dirección incluso si está incompleto. Para obtener solo direcciones completas, por ejemplo, direcciones que incluyen el número de casa, desmarque todas las casillas de verificación excepto **Direcciones de puntos** . 
   - **Idioma**: de forma predeterminada, las direcciones se devuelven en el idioma de la región a la que se ha determinado que pertenece la dirección. Para aplicar un idioma de dirección estandarizado, seleccione el idioma en el menú desplegable. Por ejemplo, si se selecciona **Inglés**, devolverá **Copenhague, Dinamarca** en lugar de **København, Danmark**.

1. Escriba un nombre para el enriquecimiento.

1. Revise sus opciones y, a continuación, seleccione **Guardar enriquecimiento**.

## <a name="configure-the-connection-for-azure-maps"></a>Configurar la conexión para Azure Maps

Debe ser administrador de conclusiones del público para configurar conexiones. Seleccione **Agregar conexión** al configurar un enriquecimiento, o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Azure Maps.

1. En el cuadro **Nombre para mostrar**, introduzca un nombre para la conexión.

1. Proporcione una clave de API de Azure Maps válida.

1. Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.

1. Seleccione **Verificar** para validar la configuración.

1. Después de completar la verificación, seleccione **Guardar**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Página de configuración de conexión de Azure Maps.":::

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y de los tiempos de respuesta de la API.

Una vez completado el proceso de enriquecimiento, puede revisar los datos de perfiles de clientes recién enriquecidos en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Al habilitar Dynamics 365 Customer Insights para transmitir datos a Azure Maps, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Azure Maps cumpla las obligaciones de privacidad o seguridad que pueda tener. Para obtener más información, vaya a [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
