---
title: Conectar datos de Common Data Model a una cuenta de Azure Data Lake
description: Trabajar con datos de Common Data Model usando Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011594"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Conectarse a los datos en Azure Data Lake Storage

Ingerir datos en Dynamics 365 Customer Insights usando su cuenta Azure Data Lake Storage Gen2. La ingesta de datos puede ser completa o incremental.

## <a name="prerequisites"></a>Requisitos previos

- La ingesta de datos admite exclusivamente cuentas Azure Data Lake Storage *Gen2*. No puede usar cuentas de almacenamiento de Data Lake Storage Gen1 para ingerir datos.

- La cuenta de Azure Data Lake Storage debe tener [espacio de nombres jerárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace). Los datos deben almacenarse en un formato de carpeta jerárquica que define la carpeta raíz y tiene subcarpetas para cada entidad. Las subcarpetas pueden tener carpetas de datos completos o de datos incrementales.

- Para autenticarse con una entidad de servicio de Azure, asegúrese de que esté configurada en su inquilino. Para obtener más información, consulte [Conectarse a una cuenta de Azure Data Lake Storage Gen 2 mediante el uso de una entidad de servicio de Azure](connect-service-principal.md).

- El Azure Data Lake Storage al que se va a conectar y del que va a ingerir datos debe estar en la misma región de Azure que el entorno de Dynamics 365 Customer Insights. No se admiten las conexiones a una carpeta de Common Data Model desde un lago de datos en una región de Azure diferente. Para conocer la región de Azure del entorno en vaya a **Administrador** > **Sistema** > **Acerca de** en Customer Insights.

- Los datos almacenados en servicios en línea pueden almacenarse en una ubicación diferente a la que se procesan o almacenan en Dynamics 365 Customer Insights. Al importar o conectarse a datos almacenados en servicios en línea, acepta que los datos pueden transferirse y almacenarse con Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

- La entidad de servicio de Customer Insights debe tener uno de los siguientes roles para acceder a la cuenta de almacenamiento. Para más información, consulte [Otorgar permisos a la entidad de servicio para acceder a la cuenta de almacenamiento](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Lector de datos de blobs de almacenamiento
  - Propietario de datos de blobs de almacenamiento
  - Colaborador de datos de blob de almacenamiento

- Los datos en su Data Lake Storage deben seguir el estándar de Common Data Model para el almacenamiento de sus datos y tener el manifiesto de modelo de datos común para representar el esquema de los archivos de datos (*.csv o *.parquet). El manifiesto debe proporcionar los detalles de las entidades, como columnas de entidad y tipos de datos, y la ubicación del archivo de datos y el tipo de archivo. Para obtener más información, consulte [El manifiesto de Common Data Model](/common-data-model/sdk/manifest). Si el manifiesto no está presente, los usuarios administradores con acceso Storage Blob Data Owner o Storage Blob Data colaborador pueden definir el esquema al ingerir los datos.

## <a name="connect-to-azure-data-lake-storage"></a>Conectar con Azure Data Lake Storage

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione **Agregar origen de datos**.

1. Seleccione **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Cuadro de diálogo para introducir detalles de conexión para Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Escriba un **Nombre** para el origen de datos y una **Descripción** opcional. El nombre identifica de forma única el origen de datos y se hace referencia en los procesos posteriores y no se puede cambiar.

1. Elija una de las siguientes opciones para **Conecte su almacenamiento usando**. Para obtener más información, consulte [Conectar Customer Insights a una cuenta de Azure Data Lake Storage Gen 2 mediante el uso de una entidad de servicio de Azure](connect-service-principal.md).

   - **Recurso Azurel**: introduzca el **Identificador de recurso**. Opcionalmente, si desea ingerir datos de una cuenta de almacenamiento a través de Azure Private Link, seleccione **Habilitar Private Link**. Para obtener más información, consulte [Private Links](security-overview.md#private-links-tab).
   - **Suscripción Azure**: seleccione **Suscripción** y luego el **Grupo de recursos** y **Cuenta de almacenamiento**. Opcionalmente, si desea ingerir datos de una cuenta de almacenamiento a través de Azure Private Link, seleccione **Habilitar Private Link**. Para obtener más información, consulte [Private Links](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Necesita uno de los siguientes roles para el contenedor o la cuenta de almacenamiento para crear el origen de datos:
   >
   >  - El Lector de datos de Storage Blob es suficiente para leer desde una cuenta de almacenamiento e incorporar los datos a Customer Insights. 
   >  - Se requiere el propietario o el colaborador de datos de Storage Blob Storage si desea editar los archivos de manifiesto directamente en Customer Insights.  
  
1. Elige el nombre del **Contenedor** que contiene los datos y el esquema (archivo model.json o manifest.json) para importar datos y seleccione **Siguiente**.
   > [!NOTE]
   > Cualquier archivo model.json o manifest.json asociado con otro origen de datos del entorno no se mostrará en la lista. Sin embargo, el mismo archivo model.json o manifest.json se puede utilizar para orígenes de datos en varios entornos.

1. Para crear un nuevo esquema, vaya a [Crear un nuevo archivo de esquema](#create-a-new-schema-file).

1. Para usar un esquema existente, vaya a la carpeta que contiene el archivo model.json o manifest.cdm.json. Puede buscar dentro de un directorio para encontrar el archivo.

1. Seleccione el archivo json y, a continuación, **Siguiente**. Aparece una lista de entidades disponibles.

   :::image type="content" source="media/review-entities.png" alt-text="Cuadro de diálogo de una lista de entidades para seleccionar":::

1. Seleccione las entidades que desee incluir.

   :::image type="content" source="media/ADLS_required.png" alt-text="Cuadro de diálogo que muestra Obligatorio para la clave principal":::

   > [!TIP]
   > Para editar las entidades en una interfaz de edición JSON, seleccione **Mostrar más** > **Editar archivo de esquema**. Realice los cambios y seleccione **Guardar**.

1. Para entidades seleccionadas que requieren ingesta incremental, **Obligatorio** aparece debajo de **Actualización incremental**. Para cada una de estas entidades, consulte [Configurar una actualización incremental para orígenes de datos de Azure Data Lake](incremental-refresh-data-sources.md).

1. Para entidades seleccionadas donde no se ha definido una clave principal, **Obligatorio** aparece debajo de **Clave primaria**. Para cada una de estas entidades:
   1. Seleccione **Obligatorio**. El panel **Editar entidad** aparece.
   1. Elija la **Clave principal**. La clave principal es un atributo exclusivo de la entidad. Para que un atributo pueda ser una clave principal válida, no debe incluir valores duplicados, no deben faltar valores ni debe haber valores nulos. Los atributos de tipo de datos de cadena, entero y GUID se admiten como claves principales.
   1. Opcionalmente, cambie el patrón de partición.
   1. Seleccione **Cerrar** para guardar y cerrar el panel.

1. Seleccione el número de **Atributos** para cada entidad incluida. Aparece la página **Administrar atributos**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Cuadro de diálogo para seleccionar el perfilado de datos.":::

   1. Cree nuevos atributos, edite o elimine atributos existentes. Puede cambiar el nombre, el formato de datos o agregar un tipo semántico.
   1. Para habilitar el análisis y otras capacidades, seleccione **Perfilado de datos** para toda la entidad o para atributos específicos. De forma predeterminada, ninguna entidad está habilitada para la creación de perfiles de datos.
   1. Seleccione **Listo**.

1. Seleccione **Guardar**. La página **Orígenes de datos** se abre y muestra el nuevo origen de datos en estado **Actualizando**.

### <a name="create-a-new-schema-file"></a>Cree un nuevo archivo de esquema

1. Seleccione **Nuevo archivo de esquema**.

1. Especifique un nombre para el archivo y seleccione **Guardar**.

1. Seleccione **Nueva entidad**. El panel **Nueva entidad** aparece.

1. Introduzca el nombre de la entidad y elija la **Ubicación de los archivos de datos**.
   - **Múltiples archivos .csv o .parquet**: vaya a la carpeta raíz, seleccione el tipo de patrón e ingrese la expresión.
   - **Archivos individuales .csv o .parquet**: busque el archivo .csv o .parquet y selecciónelo.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Cuadro de diálogo para crear una nueva entidad con la ubicación de los archivos de datos resaltada.":::

1. Seleccione **Guardar**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Cuadro de diálogo para definir o generar automáticamente atributos.":::

1. Seleccione **definir los atributos** para agregar manualmente los atributos, o seleccione **generarlos automáticamente**. Para definir los atributos, ingrese un nombre, seleccione el formato de datos y el tipo semántico opcional. Para atributos generados automáticamente:

   1. Después de que los atributos se generen automáticamente, seleccione **Revisar atributos**. Aparece la página **Administrar atributos**.

   1. Asegúrese de que el formato de datos sea correcto para cada atributo.

   1. Para habilitar el análisis y otras capacidades, seleccione **Perfilado de datos** para toda la entidad o para atributos específicos. De forma predeterminada, ninguna entidad está habilitada para la creación de perfiles de datos.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Cuadro de diálogo para seleccionar el perfilado de datos.":::

   1. Seleccione **Listo**. Aparece la página **Seleccionar entidades**.

1. Continúe agregando entidades y atributos, si corresponde.

1. Después de agregar todas las entidades, seleccione **Incluir** para incluir las entidades en la ingestión origen de datos.

   :::image type="content" source="media/ADLS_required.png" alt-text="Cuadro de diálogo que muestra Obligatorio para la clave principal":::

1. Para entidades seleccionadas que requieren ingesta incremental, **Obligatorio** aparece debajo de **Actualización incremental**. Para cada una de estas entidades, consulte [Configurar una actualización incremental para orígenes de datos de Azure Data Lake](incremental-refresh-data-sources.md).

1. Para entidades seleccionadas donde no se ha definido una clave principal, **Obligatorio** aparece debajo de **Clave primaria**. Para cada una de estas entidades:
   1. Seleccione **Obligatorio**. El panel **Editar entidad** aparece.
   1. Elija la **Clave principal**. La clave principal es un atributo exclusivo de la entidad. Para que un atributo pueda ser una clave principal válida, no debe incluir valores duplicados, no deben faltar valores ni debe haber valores nulos. Los atributos de tipo de datos de cadena, entero y GUID se admiten como claves principales.
   1. Opcionalmente, cambie el patrón de partición.
   1. Seleccione **Cerrar** para guardar y cerrar el panel.

1. Seleccione **Guardar**. La página **Orígenes de datos** se abre y muestra el nuevo origen de datos en estado **Actualizando**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Editar un origen de datos Azure Data Lake Storage

Puede actualizar la opción *Conéctese a la cuenta de almacenamiento usando*. Para obtener más información, consulte [Conectar Customer Insights a una cuenta de Azure Data Lake Storage Gen 2 mediante el uso de una entidad de servicio de Azure](connect-service-principal.md). Para conectarse a un contenedor diferente de su cuenta de almacenamiento o cambiar el nombre de la cuenta, [cree una nueva conexión de origen de datos](#connect-to-azure-data-lake-storage).

1. Vaya a **Datos** > **Orígenes de datos**.

1. Junto al origen de datos que desea actualizar, seleccione **Editar**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Cuadro de diálogo para editar Azure Data Lake origen de datos.":::

1. Cambie cualquiera de la información siguiente:

   - **Description**
   - **Conecte su almacenamiento usando** e información de conexión. No puede cambiar la información de **Contenido** al actualizar la conexión.
      > [!NOTE]
      > Se debe asignar uno de los siguientes roles a la cuenta de almacenamiento o al contenedor:
        > - Lector de datos de blobs de almacenamiento
        > - Propietario de datos de blobs de almacenamiento
        > - Colaborador de datos de blob de almacenamiento

   - **Habilitar Private Link** si desea ingerir datos de una cuenta de almacenamiento a través de Azure Private Link. Para obtener más información, consulte [Private Links](security-overview.md#private-links-tab).

1. Seleccione **Siguiente**.
1. Cambie cualquiera de las siguientes:
   - Navegue a un archivo model.json o manifest.json diferente con un conjunto diferente de entidades del contenedor.
   - Para agregar entidades adicionales para ingerir, seleccione **Nueva entidad**.
   - Para eliminar cualquier entidad ya seleccionada si no hay dependencias, seleccione la entidad y **Borrar**.
      > [!IMPORTANT]
      > Si hay dependencias en el archivo model.json o manifest.json existente y el conjunto de entidades, verá un mensaje de error y no podrá seleccionar un archivo model.json o manifest.json diferente. Elimine esas dependencias antes de cambiar el archivo model.json o manifest.json o cree un nuevo origen de datos con el archivo model.json o manifest.json que desea utilizar para evitar eliminar las dependencias.
   - Para cambiar la ubicación del archivo de datos o la clave principal, seleccione **Editar**.
   - Para cambiar los datos de ingesta incremental, consulte [Configurar una actualización incremental para orígenes de datos de Azure Data Lake](incremental-refresh-data-sources.md)

1. Seleccione **Atributos** para agregar o cambiar atributos, o para habilitar la creación de perfiles de datos. A continuación, seleccione **Hecho**.

1. Haga clic en **Guardar** para aplicar los cambios y volver a la página **Orígenes de datos**.
