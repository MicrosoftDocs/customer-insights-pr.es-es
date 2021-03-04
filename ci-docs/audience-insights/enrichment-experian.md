---
title: Enriquecimiento con el enriquecimiento de terceros Experian
description: Información general sobre el enriquecimiento de terceros de Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269581"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquezca los perfiles de los clientes con datos demográficos de Experian (vista previa)

Experian es un líder mundial en informes crediticios y servicios de marketing para consumidores y empresas. Con los servicios de enriquecimiento de datos de Experian, puede desarrollar una comprensión más profunda de sus clientes enriqueciendo los perfiles de sus clientes con datos demográficos como el tamaño del hogar, los ingresos y más.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Experian deben cumplirse los siguientes requisitos previos:

- Tener una suscripción de Experian activa. Para obtener una suscripción, [póngase en contacto con Experian](https://www.experian.com/marketing-services/contact) directamente. [Más información sobre el enriquecimiento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Uste tiene el ID. de usuario, el ID. de parte y el número de modelo para su cuenta de transporte seguro (ST) habilitada por SSH que Experian creó para usted.
- Tiene permisos de [Administrador](permissions.md#administrator) en la información de público.

## <a name="configuration"></a>Configuración

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana de Experian.

   > [!div class="mx-imgBorder"]
   > ![Ventana de Experian](media/experian-tile.png "Ventana de Experian")

1. Seleccione **Comenzar** e ingrese el ID. de usuario, ID. de parte y número de modelo para su cuenta de transporte seguro de Experian. Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**. Confirme todas las entradas seleccionando **Aplicar**.

## <a name="map-your-fields"></a>Asignar sus campos

1.  Seleccione **Agregar datos** y elija el **Conjunto de datos de cliente** que desee enriquecer con datos demográficos de Experian. Puede seleccionar la entidad **Cliente** para enriquecer todos los perfiles de sus clientes o seleccionar una entidad de segmento para enriquecer solo los perfiles de clientes contenidos en ese segmento.

1. Seleccione sus identificadores clave en **Nombre y dirección**, **Correo electrónico**, o **Teléfono** para enviar a Experian para la resolución de identidad.

   > [!TIP]
   > Más atributos de identificadores clave enviados a Experian probablemente produzcan una tasa de coincidencia más alta.

1. Seleccione **Siguiente** y asigne los atributos correspondientes desde su entidad de cliente unificada para los campos de identificador de clave seleccionados.

1. Seleccione **Agregar atributo** para asignar atributos adicionales que le gustaría enviar a Experian.

1.  Seleccione **Guardar** para completar la asignación de campos.

    > [!div class="mx-imgBorder"]
    > ![Asignación de campos de Experian](media/experian-field-mapping.png "Asignación de campos de Experian")

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento dependerá del tamaño de los datos de sus clientes y de los procesos de enriquecimiento configurados para su cuenta por Experian.

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte los datos](export-destinations.md) para entregar experiencias personalizadas a sus clientes.

## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Experian cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]