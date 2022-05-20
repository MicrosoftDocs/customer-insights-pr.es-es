---
title: Crear entornos en Customer Insights
description: Pasos para crear entornos con una suscripción con licencia para Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c64ac94a7e0e743d3c13e32e394cc5d409420622
ms.sourcegitcommit: c00441bc60b978e25f930b06c9d97b46fe462538
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712923"
---
# <a name="create-an-environment-in-customer-insights"></a>Crear un entorno en Customer Insights

En este artículo se explica cómo crear un entorno nuevo después de que su organización haya adquirido una suscripción a Dynamics 365 Customer Insights. 

Las organizaciones pueden crear varios entornos para cada licencia de Customer Insights. Si su organización adquiere más de una licencia, [póngase en contacto con nuestro equipo de soporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar el número de entornos disponibles. Para obtener más información sobre la capacidad y la capacidad adicional, consulte la [Guía de licencias de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Si desea probar el servicio, consulte [Configurar un entorno de prueba](trial-signup.md).

## <a name="create-a-new-environment"></a>Crear un nuevo entorno

Después de comprar una licencia de suscripción para Customer Insights, el administrador global del inquilino de Microsoft 365 recibe un correo electrónico que lo invita a crear el entorno. Vaya a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para empezar. 

Una experiencia guiada le ayuda a través de los pasos para recopilar toda la información necesaria para un nuevo entorno. Necesita [permisos de administrador](permissions.md) en Customer Insights para crear o gestionar entornos.

1. Abra el selector de entorno y seleccione **+ Nuevo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccionar el selector de entornos.":::

1. Siga la experiencia guiada que se describe en las siguientes secciones.

### <a name="step-1-provide-environment-information"></a>Paso 1: proporcione información sobre el entorno

En el paso **Información básica**, elija si desea crear un entorno desde cero o [copiar datos de otro entorno](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuadro de diálogo para crear un nuevo entorno de Customer Insights.":::

Especifique los detalles siguientes:
   - **Nombre**: el nombre para este entorno. Este campo ya se ha cumplimentado si ha copiado un entorno existente, pero puede modificarlo.
   - **Elija su negocio**: Elija el público principal para el nuevo entorno. Puede trabajar con consumidores individuales (B2C) o [cuentas empresariales](work-with-business-accounts.md) (B2B).
   - **Tipo**: seleccione si desea crear un entorno de producción o de espacio aislado. Los entornos de espacio aislado no permiten la actualización de datos programada y están pensados para la implementación previa y las pruebas. Los entornos de espacio aislado utilizan el mismo público principal que el entorno de producción que está seleccionado actualmente.
   - **Región**: la región en la que se implementa y hospeda el servicio.

### <a name="step-2-configure-data-storage"></a>Paso 2: Configurar almacenamiento de datos

En el paso **Almacenamiento de datos**, elija dónde almacenar los datos de Customer Insights.

Tendrá dos opciones: **Almacenamiento de Customer Insights** (lago de datos de Azure administrado por el equipo de Customer Insights) y **Azure Data Lake Storage** (su propio Azure Data Lake Storage). De forma predeterminada, la opción de almacenamiento de Customer Insights está seleccionada.

:::image type="content" source="media/data-storage-environment.png" alt-text="Elija el Azure Data Lake Storage para almacenar sus datos.":::

Al guardar datos en Azure Data Lake Storage, usted acepta que los datos se transferirán y almacenarán en la ubicación geográfica adecuada para esa cuenta de almacenamiento de Azure. Esta ubicación puede diferir de dónde se almacenan los datos en Dynamics 365 Customer Insights. Obtenga más información en el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights actualmente admite lo siguiente:  
> - Las cuentas de Azure Data Lake Storage de la misma región de Azure que seleccionó al crear el entorno.
> - Las cuentas de Azure Data Lake Storage que sean de 2.ª generación y tengan el *espacio de nombres jerárquico* habilitado. Las cuentas de almacenamiento de Azure Data Lake de 1.ª generación no son compatibles.

Para la opción Azure Data Lake Storage, puede elegir entre una opción basada en recursos y una opción basada en suscripción para la autenticación. Para obtener más información, consulte [Conectarse a una cuenta de Azure Data Lake Storage mediante el uso de una entidad de servicio de Azure](connect-service-principal.md). Un contenedor llamado `customerinsights` tiene que existir en la cuenta de almacenamiento.

Cuando se completan procesos del sistema, como ingestión de datos, el sistema crea las carpetas correspondientes en la cuenta de almacenamiento que especificó. Los archivos de datos y los archivos *model.json* se crean y se agregan a carpetas cuyo nombre se basa en el del proceso.

Si crea varios entornos de Customer Insights y elige guardar las entidades de salida de esos entornos en su cuenta de almacenamiento, Customer Insights crea carpetas independientes para cada entorno con `ci_environmentID` en el contenedor.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Paso 3: Conéctese a Microsoft Dataverse
   
El paso **Microsoft Dataverse** le permite conectar Customer Insights con su entorno de Dataverse.

Proporcione su propio entorno de Microsoft Dataverse para compartir datos (perfiles e insights) con aplicaciones empresariales basadas en Dataverse, como Dynamics 365 Marketing o aplicaciones basadas en modelos en Power Apps. Deje este campo vacío si no tiene su propio entorno de Dataverse y le proporcionaremos uno.

La conexión a su entorno de Dataverse también le permite [ingerir datos de los orígenes de datos locales usando flujos de datos de Power Platform y puertas de enlace](data-sources.md#add-data-from-on-premises-data-sources).

> [!IMPORTANT]
> 1. Customer Insights y Dataverse tienen que estar en la misma región para permitir el intercambio de datos.
> 1. Debe tener un rol de administrador global en el entorno de Dataverse. Compruebe si este entorno de [Dataverse está asociado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a ciertos grupos de seguridad y asegúrese de que se le agregue a esos grupos.
> 1. Ningún entorno existente de Customer Insights ya está asociado con ese entorno de Dataverse. Aprenda cómo [quitar una conexión existente a un entorno de Dataverse](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="intercambio de datos con Microsoft Dataverse habilitado automáticamente para nuevas instancias netas.":::

Para obtener más información sobre cómo habilitar el uso compartido de datos con Microsoft Dataverse desde su propio Azure Data Lake Storage, consulte [Conectar a Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights no admite los siguientes escenarios de uso compartido de datos:
- Si habilita el uso compartido de datos con Dataverse, no podrá [crear valores pronosticados o faltantes en una entidad](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Paso 4: Finalizar la configuración

En el paso **Revisar**, revise todos los ajustes especificados. Cuando todo parezca completo, seleccione **Crear** para configurar el entorno. 

También puede cambiar la mayoría de las configuraciones más tarde. Para más información, consulte [Administrar entornos](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabajar con su nuevo entorno

Revise los siguientes artículos para ayudarle a comenzar a configurar Customer Insights: 

- [Agregar más usuarios y asignar permisos](permissions.md).
- [Ingerir los orígenes de datos](data-sources.md) y ejecutarlos a través del [proceso de unificación de datos](data-unification.md) para obtener [perfiles de cliente unificados](customer-profiles.md).
- [Enriquecer los perfiles de cliente unificados](enrichment-hub.md) o [ejecutar modelos predictivos](predictions-overview.md).
- [Crear segmentos](segments.md) para agrupar clientes y [medidas](measures.md) para revisar los KPI.
- [Configurar conexiones](connections.md) y [exportaciones](export-destinations.md) para procesar subconjuntos de los datos en otras aplicaciones.
