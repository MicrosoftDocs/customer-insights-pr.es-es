---
title: Cómo crear un nuevo entorno
description: Pasos para crear entornos en Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245624"
---
# <a name="how-to-create-a-new-environment"></a>Cómo crear un nuevo entorno

Después de [comprar una licencia de suscripción para Dynamics 365 Customer Insights](paid-license.md), el administrador global del inquilino de Microsoft 365 recibe un correo electrónico que le invita a crear el entorno. Vaya a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para empezar. En este escenario, puede ir directamente al [Paso 1: Proporcionar información básica](#step-1-provide-basic-information).

Después de crear el primer entorno, el Administrador global del inquilino de Microsoft 365 puede [agregar usuarios de su organización como administradores](permissions.md). En el futuro, estos administradores podrán administrar usuarios y entornos. Si su organización adquiere más de una licencia de Customer Insights, [póngase en contacto con nuestro equipo de soporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar el número de entornos disponibles. Para obtener más información sobre la capacidad y la capacidad adicional, consulte la [Guía de licencias de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Si desea probar el servicio, consulte [Configurar un entorno de prueba](trial-signup.md).

## <a name="prerequisites"></a>Requisitos previos

Necesita [permisos de administrador](permissions.md) en Customer Insights para crear o gestionar entornos.

## <a name="start-the-environment-creation-process"></a>Iniciar el proceso de creación del entorno

1. Abra el selector de entorno y seleccione **+ Nuevo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccionar el selector de entornos.":::

1. Siga la experiencia guiada descrita en las siguientes secciones para proporcionar toda la información necesaria para un nuevo entorno. Si configuró un entorno anteriormente, también puede [copiar la configuración](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Paso 1: Proporcionar información básica

En el paso **Información básica**, elija si desea crear un entorno desde cero o [copiar datos de otro entorno](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuadro de diálogo para crear un nuevo entorno de Customer Insights.":::

Especifique los detalles siguientes:

- **Nombre**: el nombre para este entorno. Este campo ya se ha cumplimentado si ha copiado un entorno existente, pero puede modificarlo. Si tiene más de un entorno de trabajo, proporcione a cada uno un nombre fácilmente identificable.
- **Elija su negocio**: Elija el público principal para el nuevo entorno. Puede trabajar con consumidores individuales (B2C) o [cuentas empresariales](work-with-business-accounts.md) (B2B). Si su organización hace negocios principalmente con individuos, como un minorista o una cafetería, elija consumidores individuales. En caso de que su principal público sean otras empresas, como un fabricante de automóviles o una papelera, elija cuentas comerciales.
- **Tipo**: seleccione si desea crear un entorno de producción o de espacio aislado. Los entornos de espacio aislado no permiten la actualización de datos programada y están pensados para la implementación previa y las pruebas. Los entornos de espacio aislado utilizan el mismo público principal que el entorno de producción que está seleccionado actualmente.
- **Región**: la región en la que se implementa y hospeda el servicio. Para [usar su propia cuenta de Azure Data Lake Storage](own-data-lake-storage.md) o [conectarse a una organización de Microsoft Dataverse existente](customer-insights-dataverse.md), el entorno de Customer Insights debe estar en la misma región.

## <a name="step-2-configure-data-storage"></a>Paso 2: Configurar almacenamiento de datos

En el paso **Almacenamiento de datos**, elija dónde almacenar los datos de Customer Insights.

Puede elegir entre dos opciones:

- **Almacenamiento de Customer Insights**: el equipo de Customer Insights administra el almacenamiento de datos. Es la opción predeterminada y, a menos que existan requisitos específicos para almacenar datos en su propia cuenta de almacenamiento, recomendamos usar esta opción.
- **Azure Data Lake Storage**: Especifique su propia cuenta de Azure Data Lake Storage para almacenar los datos y tener control total sobre dónde se almacenan. Para obtener más información, consulte [Usar su propia cuenta de Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Elija la opción preferida para almacenar sus datos.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Paso 3: Conéctese a Microsoft Dataverse

El paso **Microsoft Dataverse** le permite conectar Customer Insights con su entorno de Dataverse. Comparta datos con Dataverse para usarlos con aplicaciones empresariales basadas en Dataverse, como Dynamics 365 Marketing o aplicaciones basadas en modelos en Power Apps.

Deje este campo vacío si no tiene su propio entorno de Dataverse y crearemos uno para usted.

Para obtener más información, consulte [Trabajar con datos de Customer Insights en Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="intercambio de datos con Microsoft Dataverse habilitado automáticamente para nuevos entornos netos.":::

### <a name="step-4-finalize-the-settings"></a>Paso 4: Finalizar la configuración

En el paso **Revisar**, revise todos los ajustes especificados. Cuando todo parezca completo, seleccione **Crear** para configurar el entorno.

Puede cambiar algunas de las configuraciones más tarde. Para más información, consulte [Administrar entornos](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabajar con su nuevo entorno

Revise los siguientes artículos para ayudarle a comenzar a configurar Customer Insights:

- [Agregar más usuarios y asignar permisos](permissions.md).
- [Ingerir los orígenes de datos](data-sources.md) y ejecutarlos a través del [proceso de unificación de datos](data-unification.md) para obtener [perfiles de cliente unificados](customer-profiles.md).
- [Enriquecer los perfiles de cliente unificados](enrichment-hub.md) o [ejecutar modelos predictivos](predictions-overview.md).
- [Crear segmentos](segments.md) para agrupar clientes y [medidas](measures.md) para revisar los KPI.
- [Configurar conexiones](connections.md) y [exportaciones](export-destinations.md) para procesar subconjuntos de los datos en otras aplicaciones.

## <a name="copy-the-environment-configuration"></a>Copiar el entorno de configuración

Como administrador, puede optar por copiar la configuración de un entorno existente cuando crea uno nuevo.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de las opciones de configuración en la configuración del entorno.":::

Verá una lista de todos los entornos disponibles de su organización desde los que puede copiar datos.

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

## <a name="set-up-a-copied-environment"></a>Configure un entorno copiado

Cuando copia la configuración del entorno, debe realizar algunos pasos adicionales para confirmar las credenciales:

- Perfiles de clientes. Primero, autentique e ingiera sus fuentes de datos y ejecute la unificación de datos para recrear los perfiles de los clientes.
- Credenciales del origen de datos. Debe proporcionar las credenciales para cada origen de datos para autenticar y actualizar los orígenes de datos manualmente.
- Orígenes de datos de la carpeta Common Data Model y Dataverse. Debe crear estos orígenes de datos manualmente con el mismo nombre que en el entorno de origen.
- Secretos de conexión que se utilizan para exportaciones y enriquecimientos. Tiene que volver a autenticar las conexiones y luego reactivar enriquecimientos y exportaciones.

Verá un mensaje de confirmación cuando se haya creado el entorno copiado. Seleccione **Ir a orígenes de datos** para ver la lista de orígenes de datos.

Todos los orígenes de datos mostrarán un estado de **Credenciales necesarias**. Edite los orígenes de datos e introduzca las credenciales para actualizarlas.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orígenes de datos que se copiaron y necesitan autenticación.":::

Después de actualizar los orígenes de datos, vaya a **Datos** > **Unificar**. Aquí encontrará configuraciones del entorno de origen. Edítelos si es necesario o seleccione **Ejecutar** para iniciar el proceso de unificación de datos y crear la entidad de cliente unificado.

Cuando se haya completado la unificación de datos, vaya a **Medidas** y **Segmentos** para actualizarlos también.

Antes de reactivar exportaciones y enriquecimientos, vaya a **Administración** > **Conexiones** para volver a autenticar las conexiones en su nuevo entorno.

[!INCLUDE [footer-include](includes/footer-banner.md)]
