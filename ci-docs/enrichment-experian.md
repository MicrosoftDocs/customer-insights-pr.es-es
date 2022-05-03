---
title: Enriquecimiento con el enriquecimiento de terceros de Experian
description: Información general sobre el enriquecimiento de Experian de terceros.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f5aa45316b9e0e99c7ba4389353063e9d3ce06c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646507"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquezca los perfiles de los clientes con datos demográficos de Experian (vista previa)

Experian es líder mundial en informes crediticios y servicios de marketing para consumidores y empresas. Con los servicios de enriquecimiento de datos de Experian, puede desarrollar una comprensión más a fondo de sus clientes al enriquecer los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Experian, deben cumplirse los siguientes requisitos previos:

- Tiene una suscripción de Experian activa. Para obtener una suscripción, [póngase en contacto con Experian](https://www.experian.com/marketing-services/contact) directamente. [Más información sobre el enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Una conexión Experian ya ha sido configurada por un administrador *o* tiene permisos de [administrador](permissions.md#admin). También necesita la identificación de usuario, la identificación de parte y el número de modelo para su cuenta de transporte seguro (ST) habilitada para SSH que haya creado Experian por usted.

## <a name="supported-countriesregions"></a>Países/regiones admitidos

Actualmente, solo admitimos el enriquecimiento de perfiles de clientes en los Estados Unidos.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana de Experian.

   > [!div class="mx-imgBorder"]
   > ![Icono de Experian.](media/experian-tile.png "Experian tile")
   > 

1. Seleccione una [conexión](connections.md) en la lista desplegable. Contacte con un administrador si no hay conexión disponible. Si es un administrador, puede crear una conexión seleccionando **Agregar conexión** y eligiendo Experian en la lista desplegable. 

1. Seleccione **Conectar a Experian** para confirmar la selección de conexión.

1.  Seleccione **próximo** y elija el **conjunto de datos Cliente** que desee enriquecer con datos demográficos de Experian. Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. Seleccione **Siguiente** y defina qué tipo de campos de sus perfiles unificados deben usarse para buscar datos demográficos coincidentes de Experian. Es obligatorio al menos uno de los campos **Nombre y dirección**, **Teléfono**, o **Correo electrónico**. Para una mayor precisión de correspondencia, se pueden agregar hasta otros dos campos. Esta selección afectará a los campos de asignación a los que tiene acceso en el siguiente paso.

    > [!TIP]
    > Si se envían más atributos de identificadores de claves enviados a Experian, probablemente se genere un índice de coincidencia más alto.

1. Seleccione **Siguiente** para iniciar la asignación de campos.

1. Definir qué tipo de campos de sus perfiles unificados deben usarse para buscar datos demográficos coincidentes de Experian. Los campos obligatorios están marcados.

1. Proporcione un nombre para el enriquecimiento y un nombre para la entidad de salida.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

## <a name="configure-the-connection-for-experian"></a>Configurar la conexión para Experian 

Debe ser un administrador para configurar las conexiones. Seleccione **Agregar conexión** al configurar un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Experian.

1. Seleccione **Comenzar**.

1. Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.

1. Identifique un identificador de usuario, un identificador de parte de grupo y un número de modelo válidos para su cuenta de transporte seguro de Experian.

1. Revise y proporcione su consentimiento para **Privacidad y cumplimiento de datos** seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración.

1. Después de completar la verificación, seleccione **Guardar**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel de configuración de conexión de Experian.":::

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y de los procesos de enriquecimiento configurados para su cuenta por Experian.

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilite Dynamics 365 Customer Insights para transmitir datos a Experian, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Experian cumple las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE [footer-include](includes/footer-banner.md)]
