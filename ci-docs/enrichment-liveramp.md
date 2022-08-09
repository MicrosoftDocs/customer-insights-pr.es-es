---
title: Enriquecer los perfiles de los clientes con datos de identidad de LiveRamp (versión preliminar)
description: Enriquezca los perfiles de los clientes con datos de LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196369"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquecer los perfiles de los clientes con datos de identidad de LiveRamp (versión preliminar)

LiveRamp proporciona resolución de identidad fuera de línea determinista y consolidación de datos de clientes. Puede asignar identificadores personales en sus datos de cliente al gráfico de identidad de AbiliTec y recibir id. de AbiliTec. A continuación, puede utilizar estos id. para una mejor unificación de los datos de sus clientes.

## <a name="supported-countriesregions"></a>Países/regiones admitidos

Actualmente admitimos el enriquecimiento de perfiles de clientes con datos de LiveRamp solo en los Estados Unidos.

## <a name="prerequisites"></a>Requisitos previos

- Una suscripción activa de LiveRamp. Para obtener una suscripción, comuníquese con su equipo de cuenta de LiveRamp o [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para más información.

- Una suscripción activa de AbiliTec con id. y secreto de cliente para acceder a la API. Para obtener más información, consulte [Centro de desarrollo de API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- La [conexión](connections.md) LiveRamp está [configurada](#configure-the-connection-for-liveramp) por un Administrador.

## <a name="configure-the-connection-for-liveramp"></a>Configurar la conexión para LiveRamp

Debe ser un [Administrador](permissions.md#admin) en Customer Insights y tener un secreto e ID de cliente de LiveRamp activos.

1. Seleccione **Añadir conexión** al configurar un enriquecimiento o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en el icono LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Panel de configuración para configurar la conexión al servicio AbiliTec de LiveRamp ":::

1. Ingrese un nombre para la conexión y una ID de cliente LiveRamp válida y un secreto.

1. Revise y proporcione su consentimiento para [Privacidad y cumplimiento de datos](#data-privacy-and-compliance) seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración y luego seleccionar **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que LiveRamp cumpla con las obligaciones de privacidad o seguridad que pueda tener. Para obtener más información, revise la [declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana **Identidad** de LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Icono de identidad en la página de información general de enriquecimiento ":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione la conexión. Contacte con un administrador si no hay conexión disponible.

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos de cliente** y elija el perfil o segmento que desea enriquecer con datos de identidad de LiveRamp. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

1. Defina qué tipos de campos de sus perfiles unificados se usan para buscar datos de identidad de LiveRamp. Al menos uno de los campos **Nombre y dirección**, **Teléfono** o **Correo electrónico** es obligatorio. Para una mayor precisión de coincidencia, agregue otros campos. Seleccione **Siguiente**.

1. Asigne sus campos a los datos de identificación de LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opciones de asignación de datos para el enriquecimiento de LiveRamp.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un **nombre** para el enriquecimiento y la **Nombre de entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="view-enrichment-results"></a>Ver los resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

El **Número de clientes enriquecidos por campo** proporciona un desglose de la cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Pasos siguientes

Utilice los datos enriquecidos de sus clientes. Utilice los id. de AbiliTec para consolidar los perfiles de los clientes en una vista basada en personas.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
