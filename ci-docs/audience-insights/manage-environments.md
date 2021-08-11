---
title: Crear y administrar entornos
description: Obtenga información sobre cómo registrarse en el servicio y cómo administrar los entornos.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683494"
---
# <a name="manage-environments"></a>Administrar ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Cambiar entornos

Seleccione el control **Entorno** en la esquina superior derecha de la página para cambiar entornos.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla del control para cambiar de entorno.":::

Los administradores pueden [crear](get-started-paid.md) y administrar entornos.

## <a name="edit-an-existing-environment"></a>Editar un entorno existente

Puede editar algunos de los detalles de los entornos existentes.

1.  Seleccione el selector **Entorno** en el encabezado de la aplicación.

2.  Seleccione el icono de **Editar**.

3. En el cuadro **Editar entorno**, puede actualizar la opción **Nombre para mostrar** del entorno, pero no puede cambiar **Región** o **Tipo**.

4. Si un entorno está configurado para almacenar datos en Azure Data Lake Storage, puede actualizar la **Clave de cuenta**. Sin embargo, no puede cambiar el **Nombre de cuenta** o el nombre de **Contenedor**.

5. Opcionalmente, puede actualizar desde una conexión basada en clave de cuenta a una conexión basada en recursos o basada en suscripción. Una vez actualizado, no puede volver a la clave de cuenta después de la actualización. Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md). No puede cambiar la información de **Contenido** al actualizar la conexión.

6. Opcionalmente, puede proporcionar una dirección URL del entorno Microsoft Dataverse en **Configurar el uso compartido de datos con Microsoft Dataverse y habilitar funcionalidades adicionales**. Estas funcionalidades incluyen el uso compartido de datos con aplicaciones y soluciones basadas en Microsoft Dataverse, la ingesta de datos de orígenes datos locales, o el uso de [predicciones](predictions.md). Seleccione **Habilitar el uso compartido de datos** para compartir los datos de salida de Customer Insights con una instancia de Data Lake gestionada de Microsoft Dataverse.

   > [!NOTE]
   > - El uso compartido de datos con una instancia de Data Lake gestionada de Microsoft Dataverse no se admite en estos momentos cuando almacene todos los datos en su propia instancia de Azure Data Lake Storage.
   > - Actualmente no se admiten la [predicción de valores que faltan en una entidad](predictions.md) ni los informes de PowerBI Embedded en las conclusiones para el público (si están habilitados en el entorno) al habilitar el uso compartido de datos con el lago de datos administrado por Microsoft Dataverse .

   Tras habilitar el uso compartido de datos con Microsoft Dataverse, comenzará una actualización completa de los orígenes de datos y otros procesos. Si los procesos están actualmente en ejecución, no verá la opción para habilitar el uso compartido de datos con Microsoft Dataverse. Espere a que se completen esos procesos o cancelarlos para habilitar el uso compartido de datos. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opciones de configuración para permitir el uso compartido de datos con Microsoft Dataverse.":::
   
   Cuando ejecuta procesos, como la ingestión de datos o la creación de segmentos, las carpetas correspondientes se crearán en la cuenta de almacenamiento que especificó anteriormente. Los archivos de datos y los archivos model.json se crearán y agregarán a las subcarpetas respectivas, según el proceso que ejecute.

## <a name="copy-the-environment-configuration"></a>Copiar el entorno de configuración

Al crear un entorno nuevo, puede optar por copiar la configuración de un entorno existente. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de las opciones de configuración en la configuración del entorno.":::

Verá una lista de todos los entornos disponibles de su organización desde los que puede copiar datos.

Se copian los siguientes valores de configuración:

- Fuentes de datos ingeridas e importadas
- Configuración de unificación de datos (asignación, coincidencia, combinación)
- Segmentos
- Medidas
- Relaciones
- Actividades
- Índice de Buscar y filtrar
- Exportar destinos
- Actualización programada
- Enriquecimientos
- Administración de modelos
- Asignaciones de roles

El flujo de datos *no* se copia:

- Perfiles de clientes.
- Credenciales del origen de datos. Debe especificar las credenciales para cada origen de datos y actualizar los orígenes de datos manualmente.
- Orígenes de datos de la carpeta Common Data Model y el Data Lake gestionado de Dataverse. Tendrá que crear esos orígenes de datos manualmente con el mismo nombre que en el entorno de origen.

Al copiar un entorno, verá un mensaje de confirmación de que se ha creado el nuevo entorno. Seleccione **Ir a orígenes de datos** para ver la lista de orígenes de datos.

Todos los orígenes de datos mostrarán un estado de **Credenciales necesarias**. Edite los orígenes de datos e introduzca las credenciales para actualizarlas.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orígenes de datos que se copiaron y necesitan autenticación.":::

Después de actualizar los orígenes de datos, vaya a **Datos** > **Unificar**. Aquí encontrará configuraciones del entorno de origen. Edítelos si es necesario o seleccione **Ejecutar** para iniciar el proceso de unificación de datos y crear la entidad de cliente unificado.

Cuando se haya completado la unificación de datos, vaya a **Medidas** y **Segmentos** para actualizarlos también.

## <a name="reset-an-existing-environment"></a>Restablecimiento de un entorno existente

Como administrador, puede restablecer un entorno a un estado vacío si desea eliminar todas las configuraciones y eliminar los datos ingeridos.

1.  Seleccione el selector **Entorno** en el encabezado de la aplicación. 

2.  Seleccione el entorno que desee restablecer y seleccione los puntos suspensivos (**...**). 

3. Elija la opción **Restablecer**. 

4.  Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Restablecer**.

## <a name="delete-an-existing-environment"></a>Eliminar un entorno existente

Como administrador, puede eliminar un entorno que administre.

1.  Seleccione el selector **Entorno** en el encabezado de la aplicación.

2.  Seleccione el entorno que desee restablecer y seleccione los puntos suspensivos (**...**). 

3. Elija la opción **Eliminar**. 

4.  Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
