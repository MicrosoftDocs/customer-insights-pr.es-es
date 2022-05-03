---
title: Enriquecimiento de perfiles de empresa con Dun & Bradstreet
description: Información general sobre el enriquecimiento de terceros de Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653730"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enriquecimiento de perfiles de empresa con Dun & Bradstreet (vista previa)

Dun & Bradstreet proporciona datos comerciales, análisis e información para las empresas. Permite a los clientes con perfiles de clientes unificados enriquecer sus datos de empresa. Entre los enriquecimientos se incluyen atributos como número DUNS, tamaño de la empresa, su ubicación, su sector y mucho más.

## <a name="prerequisites"></a>Requisitos previos

Para configurar un enriquecimiento Dun & Bradstreet, deben cumplirse los siguientes requisitos previos:

- Tener una licencia activa de [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Usted tiene [perfiles de clientes unificados](customer-profiles.md) para empresas.
- La [conexión](connections.md) Dun & Bradstreet está configurado por un Administrador. Puede crearla si tiene permisos de [Administrador](permissions.md#admin) y las credenciales de Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Configuración de su proyecto Dun & Bradstreet

Como usuario con licencia de Dun & Bradstreet, puede configurar un proyecto en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Iniciar sesión en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para recuperar credenciales, [restaure su contraseña](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Descargue [nuestro archivo de plantilla csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que se usará para asignar los campos de información audiencia a los campos de Dun & Bradstreet correspondientes. 

1. Cargue el archivo en el paso **Cargar datos** de la experiencia de creación de proyectos de Dun & Bradstreet. 

1. Seleccione los puntos horizontales debajo de la **fuente** correspondiente en el proyecto Dun & Bradstreet recién creado para ver las opciones disponibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de pantalla de puntos en un proyecto de Dun & Bradstreet.":::

1. Elija **Obtener detalles S3**. Guarde esta información en un lugar seguro. La necesitará para [configurar la conexión para el enriquecimiento](#configure-a-connection-for-dun--bradstreet) en las informaciones de audiencia. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de pantalla de selección de información s3 en un proyecto de Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. En las informaciones de público, vaya a **Datos** > **Enriquecimiento**.

1. Seleccione **Enriquecer mis datos** en el mosaico de Dun & Bradstreet y seleccione **Comenzar**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de pantalla del mosaico de Dun & Bradstreet.":::

1. Seleccione una [conexión](connections.md) en la lista desplegable. Contacte con un administrador si no hay conexión disponible. Si es un Administrador, puede crear una conexión. Seleccione **Añadir conexión** y elija **Dun & Bradstreet**. 

1. Seleccione **Conéctese a Dun & Bradstreet** para confirmar la conexión.

1. Seleccione **Siguiente** y elija el **Conjunto de datos de cliente** que desea enriquecer con datos de compañía de Dun & Bradstreet. Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes unificados contenidos en ese segmento.

1. Seleccione **Siguiente** y defina qué campos de sus perfiles unificados se usan para buscar datos de empresa coincidentes de Dun & Bradstreet. Los campos **número DUNS** o **Nombre de la compañía** y **País** son obligatorios. El campo del país o región admite [códigos de país de dos o tres letras](https://www.iso.org/iso-3166-country-codes.html), nombre del país o región en inglés, nombre del país o región en idioma nativo y prefijo de teléfono. Algunas variantes comunes de países o regiones incluyen:

   * EE. UU.: Estados Unidos de América, Estados Unidos, EE. UU., América.
   * CA: Canadá.
   * GB: Reino Unido, UK, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda del Norte, Reino Unido de Gran Bretaña.
   * AU: Australia, Commonwealth de Australia.
   * FR: Francia, República francesa.
   * DE: Alemania, alemán, Deutschland, Alemania, República Federal de Alemania, República de Alemania.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel de asignación de campos de Dun & Bradstreet.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un nombre para el enriquecimiento y seleccione **Guardar enriquecimiento** después de revisar sus opciones.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurar una conexión para Dun & Bradstreet 

Debe ser un administrador para configurar las conexiones. Seleccione **Añadir conexión** al configurar un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en el icono Dun & Bradstreet.

1. Seleccione **Comenzar**. 

1. Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.

1. Proporcione credenciales válidas de Dun & Bradstreet y detalles del proyecto de Dun & Bradstreet *Región, ruta de la carpeta de entrega y nombre de la carpeta de entrega*. Usted [obtiene esta información](#setting-up-your-dun--bradstreet-project) del proyecto Dun & Bradstreet.

1. Revise y proporcione su consentimiento para **Privacidad y cumplimiento de datos** seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración.

1. Después de completar la verificación, seleccione **Guardar**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Página de configuración de conexión Dun & Bradstreet":::

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Después de actualizar el enriquecimiento, puede revisar los datos de la empresa recién enriquecidos en [Mis enriquecimientos](enrichment-hub.md). Puede encontrar la hora de la última actualización y la cantidad de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Dun & Bradstreet, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Dun & Bradstreet cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](includes/footer-banner.md)]
