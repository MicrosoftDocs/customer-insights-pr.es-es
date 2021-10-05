---
title: Crear y configurar una versión de prueba de Customer Insights
description: Pasos para obtener una suscripción de prueba de Dynamics 365 Customer Insights y configurarla.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558846"
---
# <a name="set-up-a-trial-environment"></a>Configurar un entorno de prueba 

Una versión de prueba de Dynamics 365 Customer Insights permite revisar la funcionalidad esencial y obtener más información sobre las distintas características. Una vez caducada, se eliminará la suscripción de prueba. Los entornos de prueba los crean usuarios individuales que pasan a ser los administradores de esos entornos de prueba creados. Pueden invitar a más usuarios a la prueba y configurar las distintas características.

## <a name="create-a-trial-environment"></a>Crear un entorno de prueba

Puede registrarse para una prueba en la [página de suscripción de prueba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Elija la opción **Suscribirse para una prueba gratis** y seleccione **Registrarse ahora**.

1. Especifique su dirección de correo electrónico profesional o educativa, cuéntenos más sobre usted y seleccione **Empezar**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Cuadro de diálogo para registrarse para obtener una instancia de prueba:":::

1. Revise los términos y condiciones y seleccione **Continuar** para confirmar.

1. Introduzca un **Nombre** para el nuevo entorno. 

1. Establezca el **Tipo** de entorno como **Prueba**.

1. En el campo **Seleccionar una demostración del sector**, puede elegir opcionalmente un conjunto de datos concreto del sector. También puede [cambiar a una demostración del sector](#use-industry-specific-demo-data-sets-in-audience-insights) posteriormente y empezar con el conjunto de datos predeterminado.

1. Elija la **Región** para su entorno.

1. Opcionalmente, si es el administrador de una organización de Dynamics 365, seleccione **Configuración avanzada** y proporcione la dirección URL de su organización para usar características de predicción, como la predicción del abandono de clientes. 

1. Seleccione **Crear**. 

La configuración del entorno tarda un momento. Una vez completada, se le redirigirá al entorno de demostración o a la demostración del sector que haya elegido en el paso anterior. Ahora puede explorar la aplicación con datos de demostración de solo lectura. Para agregar sus propios datos al entorno, consulte [Crear datos de demostración específicos del escenario en su propio entorno](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Captura de pantalla de un entorno de prueba recién creado.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Utilizar conjuntos de datos de demostración específicos del sector en conclusiones del público

Conectar orígenes de datos reales es uno de los pasos esenciales para aprovechar las posibilidades que ofrece Customer Insights. Para probar características sin interferir con sus propios datos, puede utilizar opcionalmente datos de demostración específicos del sector. Hay un par de conjuntos de datos de demostración disponibles para los siguientes sectores: 

-   Automoción
-   Banca
-   Bienes de consumo
-   Administración Pública
-   Atención sanitaria
-   Hostelería
-   Seguros
-   Fabricación
-   Servicios profesionales
-   Venta directa

### <a name="see-industry-specific-demo-data-in-trials"></a>Ver datos de demostración específicos del sector en las pruebas

Para obtener una versión de solo lectura de Customer Insights adaptada a un sector o escenario concreto, empiece en el entorno de demostración. 
 
1.  En las conclusiones del público, elija el entorno **Demostración** en el selector de entornos.

2.  En **Inicio**, elija una opción del menú desplegable Seleccionar una demostración del sector.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Elegir un sector para el entorno de prueba.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Crear datos de demostración específicos del escenario en su propio entorno

Como administrador, seleccione el selector de entorno del encabezado de la aplicación para crear un entorno nuevo. En el nuevo entorno puede configurar sus propios orígenes de datos y la aplicación de acuerdo con sus requisitos. 

1.  En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2.  Para importar sus propios orígenes de datos, vaya a la [guía de ingesta de datos](data-sources.md).     
   Si prefiere trabajar con datos de ejemplo que le permitan probar la ingesta de datos, puede ingerir los datos de demostración del sector en su entorno. Elija la opción **Importar desde el centro de datos** y siga los pasos que se indican a continuación.

3.  Seleccione la tarjeta de sector adecuada para su escenario. 

4.  Revise (y, opcionalmente, actualice) el nombre sugerido del origen de datos. 

5.  Seleccione **Siguiente** para ingerir los datos de ejemplo. 

Ahora puede utilizar los datos ingeridos para adaptar Customer Insights a su escenario. Para ver un entorno específico de los datos de demostración ingeridos, elija la opción **Demostración de <Industry>** en el selector de entorno.

## <a name="limitations-in-trials"></a>Limitaciones en las versiones de prueba

- Las versiones de prueba están activas durante 30 días de forma predeterminada. Sin embargo, puede ampliar la duración después del día 23, al iniciar sesión en la versión de prueba.
- No puede usar su propia cuenta de almacenamiento de Azure Data Lake para almacenar datos de salida durante una prueba. Sin embargo, puede ingerir datos de una cuenta de almacenamiento de Data Lake.
- Puede almacenar hasta 3 GB de datos en el entorno de Dataverse que se aprovisiona automáticamente cuando inicia una prueba de Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copiar datos de una versión de prueba a una suscripción de pago

Por lo general, recomendamos comenzar de cero con sus propios datos al actualizar a la versión de pago de Customer Insights. 

Opcionalmente, puede copiar sus datos desde un entorno de prueba si adquiere Customer Insights. Debe ser administrador de la versión de prueba de Customer Insights y administrador global de su inquilino de Microsoft 365, o administrador de Dynamics 365 en su organización para poder migrar la configuración de un entorno de prueba a un entorno de pago. 

Cuando inicie sesión por primera vez en su instancia de pago de Customer Insights, se le pedirá que cree un entorno nuevo. En este proceso, puede optar por copiar la configuración de un entorno existente y migrar la mayoría de las opciones de configuraciones. Si tiene los permisos mencionados anteriormente, el entorno de prueba se mostrará en esta lista. Para obtener más información, consulte [Copiar la configuración del entorno](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Pasos siguientes

Revise los siguientes artículos que le ayudarán a comenzar a configurar Customer Insights. 

- [Agregar más usuarios y asignar permisos](permissions.md).
- [Ingerir los orígenes de datos](data-sources.md) y ejecutarlos a través del [proceso de unificación de datos](data-unification.md) para obtener [perfiles de cliente unificados](customer-profiles.md).
- [Enriquecer los perfiles de cliente unificados](enrichment-hub.md) o [ejecutar modelos predictivos](predictions-overview.md).
- Crear [segmentos](segments.md) para agrupar clientes y KPI de revisión de [medidas](measures.md).
- Configurar [conexiones](connections.md) y [exportaciones](export-destinations.md) para procesar subconjuntos de los datos en otras aplicaciones.
