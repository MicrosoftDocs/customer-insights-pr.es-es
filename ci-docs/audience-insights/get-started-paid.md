---
title: Crear y configurar una licencia de pago de Customer Insights
description: Pasos para obtener una suscripción con licencia de Dynamics 365 Customer Insights y configurarla.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650514"
---
# <a name="get-started-with-a-paid-subscription"></a>Introducción a la suscripción de pago

En este artículo se explica cómo crear un entorno nuevo después de que su organización haya adquirido una suscripción a Dynamics 365 Customer Insights. Si desea adquirir Customer Insights, nuestras opciones de contacto se muestra en el [sitio web de Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Si desea probar el servicio y sus características, consulte [Configurar un entorno de prueba](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Crear un entorno en una organización existente

Tras adquirir una licencia de suscripción de Customer Insights, el administrador global del inquilino de Microsoft 365 recibirá un correo electrónico que le invitará a crear el entorno. Vaya a [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) para empezar. 

Customer Insights no incluye licencias por usuario, por lo que no aparecerá en el área Licencias. Si busca la licencia en el centro de administración de Microsoft 365, vaya a **Sus productos**. 

> [!NOTE]
> Las organizaciones pueden crear *dos* entornos para cada licencia de Customer Insights. Si su organización compra más de una licencia, [contacte con nuestro equipo de soporte técnico](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar el número de entornos disponibles. Para obtener más información sobre la capacidad y la capacidad complementaria, descargue la [Guía de licencias de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Para crear un entorno:

1. En cuadro de diálogo **Crear un entorno**, seleccione **Nuevo entorno**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuadro de diálogo para crear un nuevo entorno de Customer Insights.":::

   Recomendamos comenzar a configurar un entorno desde cero. Sin embargo, si es administrador o miembro de un entorno de prueba, puede [copiar datos de otro entorno](manage-environments.md#copy-the-environment-configuration) eligiendo **Copiar desde entorno existente**. Verá una lista de todos los entornos disponibles de su organización desde los que puede copiar datos.

1. Especifique los detalles siguientes:
   - **Nombre**: el nombre para este entorno. Este campo ya se ha cumplimentado si ha copiado un entorno existente, pero puede modificarlo.
   - **Región**: la región en la que se implementa y hospeda el servicio.
   - **Tipo**: seleccione si desea crear un entorno de producción o de espacio aislado. Los entornos de espacio aislado no permiten la actualización de datos programada y están pensados para la implementación previa y las pruebas.
   
1. De manera opcional, puede seleccionar **Configuración avanzada**:

   - **Guardar todos los datos en**: Especifica dónde desea almacenar los datos de salida generados a partir de Customer Insights. Tendrá dos opciones: **Almacenamiento de Customer Insights** (Azure Data Lake administrado por el equipo de Customer Insights) y **Azure Data Lake Storage** (su propio Azure Data Lake Storage). De forma predeterminada, la opción de almacenamiento de Customer Insights está seleccionada.

     > [!NOTE]
     > Al guardar datos en Azure Data Lake Storage, acepta que los datos se transferirán a la ubicación geográfica adecuada y se almacenarán en ella para esa cuenta de almacenamiento de Azure, que puede ser distinta del lugar en el que se almacenan los datos en Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Actualmente, las entidades ingeridas desde flujos de datos de Power BI siempre se almacenan en un Data Lake administrado por Microsoft Dataverse. 
     > 
     > Solo admitimos cuentas de Azure Data Lake Storage de la misma región de Azure que seleccionó al crear el entorno. 
     > 
     > Solo admitimos cuentas de Azure Data Lake Storage que tienen habilitado el espacio de nombres jerárquico.


   - Para la opción Azure Data Lake Storage, puede elegir entre una opción basada en recursos y una opción basada en suscripción para la autenticación. Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md). El nombre del **Contenedor** no se puede cambiar y será `customerinsights`.
   
   - Si quieres usar [modelos listos para usar](predictions-overview.md#out-of-box-models), configurar el intercambio de datos con Microsoft Dataverse o habilitar la ingesta de datos de los orígenes de datos locales, especifique la dirección URL del entorno de Microsoft Dataverse en **Configurar el intercambio de datos con Microsoft Dataverse y habilitar funcionalidad adicional**. Seleccione **Habilitar el uso compartido de datos** para compartir los datos de salida de Customer Insights con una instancia de Data Lake gestionada de Microsoft Dataverse.

     > [!NOTE]
     > - El uso compartido de datos con una instancia de Data Lake gestionada de Microsoft Dataverse no se admite en estos momentos cuando almacene todos los datos en su propia instancia de Azure Data Lake Storage.
     > - La [predicción de valores que faltan en una entidad](predictions.md) actualmente no es compatible cuando habilita el uso compartido de datos con Data Lake gestionada de Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opciones de configuración para permitir el uso compartido de datos con Microsoft Dataverse.":::

   Cuando se hayan completado los procesos del sistema, como la ingesta de datos, el sistema crea las carpetas correspondientes en la cuenta de almacenamiento que especificó. Los archivos de datos y los archivos model.json se crean y se agregan a carpetas cuyo nombre se basa en el del proceso.

   Si crea varios entornos de Customer Insights y elige guardar las entidades de salida de esos entornos en su cuenta de almacenamiento, se crearán carpetas separadas para cada entorno, con ci_<environmentid> en el contenedor.

1. Seleccione **Crear** para configurar un entorno. 

## <a name="configure-an-environment"></a>Configurar un entorno

Revise los siguientes artículos que le ayudarán a comenzar a configurar Customer Insights. 

- [Agregar más usuarios y asignar permisos](permissions.md).
- [Ingerir los orígenes de datos](data-sources.md) y ejecutarlos a través del [proceso de unificación de datos](data-unification.md) para obtener [perfiles de cliente unificados](customer-profiles.md).
- [Enriquecer los perfiles de cliente unificados](enrichment-hub.md) o [ejecutar modelos predictivos](predictions-overview.md).
- Crear [segmentos](segments.md) para agrupar clientes y KPI de revisión de [medidas](measures.md).
- Configurar [conexiones](connections.md) y [exportaciones](export-destinations.md) para procesar subconjuntos de los datos en otras aplicaciones.
