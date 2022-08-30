---
title: Crear un nuevo entorno
description: Pasos para crear entornos en Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304288"
---
# <a name="create-a-new-environment"></a>Crear un nuevo entorno

Después de [comprar una licencia de suscripción para Dynamics 365 Customer Insights](paid-license.md), el administrador global del inquilino de Microsoft 365 recibe un correo electrónico que le invita a crear el entorno. Vaya a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para empezar. En este escenario, empiece con el [Paso 1: Proporcionar información básica](#step-1-provide-basic-information).

Después de crear el primer entorno, el Administrador global del inquilino de Microsoft 365 puede [agregar usuarios de su organización como administradores](permissions.md). Estos administradores podrán administrar después usuarios y entornos. Si su organización adquiere más de una licencia de Customer Insights, [póngase en contacto con nuestro equipo de soporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar el número de entornos disponibles. Para obtener más información sobre la capacidad y la capacidad adicional, consulte la [Guía de licencias de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Una vez que tenga la capacidad de crear entornos adicionales, vaya a [Iniciar el proceso de creación del entorno](#start-the-environment-creation-process).

> [!TIP]
> Si desea probar el servicio, consulte [Configurar un entorno de prueba](trial-signup.md).

## <a name="prerequisites"></a>Requisitos previos

Permisos de [administrador](permissions.md) en Customer Insights

## <a name="start-the-environment-creation-process"></a>Iniciar el proceso de creación del entorno

1. Abra el selector de entorno y seleccione **+ Nuevo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccionar el selector de entornos.":::

1. Siga la experiencia guiada descrita en las siguientes secciones para proporcionar toda la información necesaria para un nuevo entorno.

## <a name="step-1-provide-basic-information"></a>Paso 1: Proporcionar información básica

1. Elija si desea crear un entorno desde cero o copiar datos de otro entorno. [Copiar datos de otro entorno](#copy-the-environment-configuration) requiere pasos adicionales.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuadro de diálogo para crear un nuevo entorno de Customer Insights.":::

1. Especifique los detalles siguientes:

   - **Nombre**: el nombre para este entorno. Este campo ya se ha cumplimentado si ha copiado un entorno existente, pero puede modificarlo.
   - **Elija su negocio**: público principal del nuevo entorno: consumidores individuales (B2C) o [cuentas de negocio](work-with-business-accounts.md) (B2B). Si su organización hace negocios principalmente con individuos, como un minorista o una cafetería, elija consumidores individuales. Si su principal público son otras empresas, como un fabricante de automóviles o una papelera, elija cuentas comerciales.
   - **Tipo**: tipo de entorno (producción o espacio aislado). Los entornos de espacio aislado no permiten la actualización de datos programada y están pensados para la implementación previa y las pruebas. Los entornos de espacio aislado utilizan el mismo público principal que el entorno de producción que está seleccionado actualmente.
   - **Región**: la región en la que se implementa y hospeda el servicio. Para [usar su propia cuenta de Azure Data Lake Storage](own-data-lake-storage.md) o [conectarse a una organización de Microsoft Dataverse existente](customer-insights-dataverse.md), el entorno de Customer Insights debe estar en la misma región.

1. Seleccione **Siguiente**.

## <a name="step-2-configure-data-storage"></a>Paso 2: Configurar almacenamiento de datos

1. Elija si almacenar los datos de Customer Insights:

   - **Almacenamiento de Customer Insights**: el almacenamiento de datos se gestiona automáticamente. Es la opción predeterminada y, a menos que existan requisitos específicos para almacenar datos en su propia cuenta de almacenamiento, recomendamos usar esta opción.
   - **Azure Data Lake Storage**: su propia cuenta de Azure Data Lake Storage para almacenar los datos y tener control total sobre dónde se almacenan. Siga los pasos en [Utilizar su propia cuenta de Azure Data Lake Storage](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Elija la opción preferida para almacenar sus datos.":::

1. Seleccione **Siguiente**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Paso 3: Conéctese a Microsoft Dataverse

Si tiene un entorno de Dataverse, conecte Customer Insights. Comparta datos con Dataverse para usarlos con aplicaciones empresariales basadas en Dataverse, como Dynamics 365 Marketing o aplicaciones basadas en modelos en Power Apps.

1. Siga los pasos en [Trabajar con datos de Customer Insights en Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="intercambio de datos con Microsoft Dataverse habilitado automáticamente para nuevos entornos netos.":::

1. Seleccione **Siguiente**.

## <a name="step-4-finalize-the-settings"></a>Paso 4: Finalizar la configuración

Revise la configuración especificada. Cuando todo parezca completo, seleccione **Crear** para configurar el entorno.

Para cambiar algunos de los ajustes más adelante, consulte [Administrar entornos](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabajar con su nuevo entorno

Revise los siguientes artículos para ayudarle a comenzar a configurar Customer Insights:

- [Agregar más usuarios y asignar permisos](permissions.md).
- [Ingerir los orígenes de datos](data-sources.md) y ejecutarlos a través del [proceso de unificación de datos](data-unification.md) para obtener [perfiles de cliente unificados](customer-profiles.md).
- [Enriquecer los perfiles de cliente unificados](enrichment-hub.md) o [ejecutar modelos predictivos](predictions-overview.md).
- [Crear segmentos](segments.md) para agrupar clientes y [medidas](measures.md) para revisar los KPI.
- [Configurar conexiones](connections.md) y [exportaciones](export-destinations.md) para procesar subconjuntos de los datos en otras aplicaciones.

## <a name="copy-the-environment-configuration"></a>Copiar el entorno de configuración

Como administrador, si elige copiar la configuración de un entorno existente, seleccione de la lista de todos los entornos disponibles en su organización.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de las opciones de configuración en la configuración del entorno.":::

Se copian los siguientes valores de configuración:

- Orígenes de datos importados mediante Power Query
- Configuración de unificación de datos
- Segmentos
- Medidas
- Relaciones
- Actividades
- Índice de Buscar y filtrar
- Exportaciones
- Actualizar programación
- Enriquecimientos
- Modelos de predicción
- Asignaciones de roles

### <a name="set-up-a-copied-environment"></a>Configure un entorno copiado

Al copiar la configuración del entorno, verá un mensaje de confirmación de que se ha creado el entorno copiado. Realice los pasos siguientes para confirmar las credenciales.

1. Seleccione **Ir a orígenes de datos** para ver la lista de orígenes de datos. Todos los orígenes de datos muestran el estado de **Credenciales necesarias**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orígenes de datos que se copiaron y necesitan autenticación.":::

1. Edite los orígenes de datos e introduzca las credenciales para actualizarlas. Los orígenes de datos de la carpeta Common Data Model y Dataverse deben crearse manualmente con el mismo nombre que en el entorno de origen.

1. Después de actualizar los orígenes de datos, vaya a **Datos** > **Unificar**. Aquí encontrará configuraciones del entorno de origen. Edítelos si es necesario o seleccione **Unificar** > **Unificar perfiles y dependencias de clientes** para iniciar el proceso de unificación de datos y crear la entidad de cliente unificado.

   > [!TIP]
   > Para cuentas y contactos, seleccione **Unificar cuentas** > **Unificar perfiles y dependencias**.

1. Cuando se haya completado la unificación de datos, vaya a **Medidas** y **Segmentos** para actualizarlos.

1. Vaya a **Administración** > **Conexiones** para volver a autenticar las conexiones en su nuevo entorno.

1. Vaya a **Datos** > **Enriquecimiento** y **Datos** > **Exportaciones** para reactivarlos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
