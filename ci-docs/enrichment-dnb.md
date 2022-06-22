---
title: Enriquecimiento de perfiles de empresa con Dun & Bradstreet
description: Información general sobre el enriquecimiento de terceros de Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953912"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enriquecimiento de perfiles de empresa con Dun & Bradstreet (Vista previa)

Dun & Bradstreet proporciona datos comerciales, análisis e información para las empresas. Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa. Entre los enriquecimientos se incluyen atributos como número DUNS, tamaño de la empresa, su ubicación, su sector y mucho más.

## <a name="prerequisites"></a>Requisitos previos

- Una licencia activa de [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Perfiles de clientes unificados](customer-profiles.md) para compañías.
- Un [proyecto](#set-up-your-dun--bradstreet-project) de Dun & Bradstreet está configurado.
- La [conexión](connections.md) Dun & Bradstreet está [configurada](#configure-a-connection-for-dun--bradstreet) por un Administrador.

## <a name="set-up-your-dun--bradstreet-project"></a>Configurar su proyecto Dun & Bradstreet

Como usuario con licencia de Dun & Bradstreet, puede configurar un proyecto en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Iniciar sesión en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para recuperar credenciales, [restaure su contraseña](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Descargue [nuestro archivo de plantilla csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que se usará para asignar los campos de Customer Insights a los campos de Dun & Bradstreet correspondientes.

1. Cargue el archivo en el paso **Cargar datos** de la experiencia de creación de proyectos de Dun & Bradstreet.

1. Seleccione los puntos horizontales debajo de la **fuente** correspondiente en el proyecto Dun & Bradstreet recién creado para ver las opciones disponibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de pantalla de puntos en un proyecto de Dun & Bradstreet.":::

1. Elija **Obtener detalles S3**. Guarde esta información en un lugar seguro. La necesitará para [configurar la conexión para el enriquecimiento](#configure-a-connection-for-dun--bradstreet) en Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de pantalla de selección de información s3 en un proyecto de Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurar una conexión para Dun & Bradstreet

Debe ser un [Administrador](permissions.md#admin) en Customer Insights y tener las credenciales de Dun & Bradstreet Connect.

1. Seleccione **Añadir conexión** al configurar un enriquecimiento o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en el icono Dun & Bradstreet.

1. Escriba un nombre para la conexión.

1. Proporcione credenciales válidas de Dun & Bradstreet y detalles del proyecto de Dun & Bradstreet *Región, ruta de la carpeta de entrega y nombre de la carpeta de entrega*. Usted [obtiene esta información](#set-up-your-dun--bradstreet-project) del proyecto Dun & Bradstreet.

1. Revise y proporcione su consentimiento para [Privacidad y cumplimiento de datos](#data-privacy-and-compliance) seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración y luego seleccionar **Guardar**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Página de configuración de conexión Dun & Bradstreet":::

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Dun & Bradstreet, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Dun & Bradstreet cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

## <a name="supported-countries-or-regions"></a>Países o regiones compatibles

Actualmente admitimos las siguientes opciones de país/región: Canadá (inglés) o Estados Unidos (inglés).

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana **Datos de la empresa** para Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de pantalla del mosaico de Dun & Bradstreet.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione la conexión y confirme. Contacte con un Administrador si no hay uno disponible.

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos de cliente** y elija el perfil o segmento que desea enriquecer con datos de la empresa de Dun & Bradstreet. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

1. Defina qué tipos de campos de sus perfiles unificados se usan para buscar datos de empresa de Dun & Bradstreet. Es obligatorio al menos uno de los campos **Nombre y dirección**, **Teléfono**, o **Correo electrónico**.

1. Seleccione **Siguiente**

1. Asigne sus campos a los datos de empresa de Dun & Bradstreet. Los campos **número DUNS** o **Nombre de la compañía** y **País** son obligatorios.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel de asignación de campos de Dun & Bradstreet.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un **nombre** para el enriquecimiento y la **Nombre de entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
