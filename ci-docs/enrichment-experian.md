---
title: Enriquecimiento con el enriquecimiento de terceros de Experian
description: Información general sobre el enriquecimiento de Experian de terceros.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954108"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquezca los perfiles de los clientes con datos demográficos de Experian (vista previa)

Experian es líder mundial en informes crediticios y servicios de marketing para consumidores y empresas. Con los servicios de enriquecimiento de datos de Experian, puede desarrollar una comprensión más a fondo de sus clientes al enriquecer los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.

## <a name="supported-countriesregions"></a>Países/regiones admitidos

Actualmente, solo admitimos el enriquecimiento de perfiles de clientes en los Estados Unidos.

## <a name="prerequisites"></a>Requisitos previos

- Una suscripción activa de Experian. Para obtener una suscripción, [póngase en contacto con Experian](https://www.experian.com/marketing-services/contact) directamente. [Más información sobre el enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Una [conexión](connections.md) de Experian [configurada](#configure-the-connection-for-experian) por un administrador.

- Identificación de usuario Experian, la identificación de parte y el número de modelo para su cuenta de transporte seguro (ST) habilitada para SSH que haya creado Experian por usted.

## <a name="configure-the-connection-for-experian"></a>Configurar la conexión para Experian

Debe ser un [Administrador](permissions.md#admin) en Customer Insights y tener un Identificador de usuario, Grupo y Número de modelo de Experian.

1. Seleccione **Agregar conexión** al configurar un enriquecimiento o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel de configuración de conexión de Experian.":::

1. Ingrese un nombre para la conexión y una identificación de usuario válida, identificación de parte y número de modelo para su Cuenta Transporte Seguro Experian.

1. Revise y proporcione su consentimiento para [Privacidad y cumplimiento de datos](#data-privacy-and-compliance) seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración y luego seleccionar **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilite Dynamics 365 Customer Insights para transmitir datos a Experian, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Experian cumple las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en el mosaico **Datos demográficos** de Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian icono de identidad en la página de información general de enriquecimiento.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione la conexión. Contacte con un Administrador si no hay uno disponible.

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos de cliente** y elija el perfil o segmento que desea enriquecer con datos demográficos de Experian. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla cuando se elige el conjunto de datos del cliente.":::

1. Defina qué tipos de campos de sus perfiles unificados se usan para buscar datos demográficos de Experian. Es obligatorio al menos uno de los campos **Nombre y dirección**, **Teléfono**, o **Correo electrónico**. Para una mayor precisión de coincidencia, agregue otros campos. Seleccione **Siguiente**.

1. Asigne sus campos a los datos demográficos de Experian.

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un **nombre** para el enriquecimiento y la **Nombre de entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **Número de clientes enriquecidos por campo** proporciona un desglose de la cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
