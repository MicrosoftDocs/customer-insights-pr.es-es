---
title: Conectar datos de Common Data Model a una cuenta de Azure Data Lake
description: Trabajar con datos de Common Data Model usando Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643479"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Conectarse a una carpeta de Common Data Model mediante una cuenta de Azure Data Lake

Este artículo proporciona información sobre cómo ingerir datos de una carpeta de Common Data Model usando su cuenta de Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Consideraciones importantes

- Los datos de su Azure Data Lake deben seguir el estándar de Common Data Model. Otros formatos no son compatibles en este momento.

- La ingestión de datos admite solo cuentas de almacenamiento de Azure Data Lake *Gen2*. No puede usar cuentas de almacenamiento de Azure Data Lake Gen1 para ingerir datos.

- Para autenticarse con una entidad de servicio de Azure, asegúrese de que esté configurada en su inquilino. Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md).

- El Azure Data Lake desde el que desea conectar e ingerir datos debe estar en la misma región de Azure que el entorno Dynamics 365 Customer Insights. No se admiten las conexiones a una carpeta de Common Data Model desde un lago de datos en una región de Azure diferente. Para conocer la región de Azure del entorno, vaya a **Administrador** > **Sistema** > **Acerca de** en la información de público.

- Los datos almacenados en servicios en línea pueden almacenarse en una ubicación diferente a la que se procesan o almacenan en Dynamics 365 Customer Insights. Al importar o conectarse a datos almacenados en servicios en línea, acepta que los datos pueden transferirse y almacenarse con Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Conectar a una carpeta de Common Data Model

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

1. Seleccione **Agregar origen de datos**.

1. Seleccione **Conectarse a una carpeta de Common Data Model**, introduzca un **Nombre** como origen de datos y seleccione **Siguiente**.

1. Puede elegir entre usar una opción basada en recursos y una opción basada en suscripción para la autenticación. Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md). Introduzca la información del **Contenedor** y seleccione **Siguiente**.
   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo para introducir detalles de conexión para Azure Data Lake](media/enter-new-storage-details.png)

1. En el diálogo **Seleccionar una carpeta de Common Data Model**, seleccione el archivo model.json del que importar datos y seleccione **Siguiente**.
   > [!NOTE]
   > Cualquier archivo model.json asociado con otro origen de datos del entorno no se mostrará en la lista.

1. Obtendrá una lista de entidades disponibles en el archivo model.json seleccionado. Puede revisar y seleccionar de la lista de entidades disponibles y seleccionar **Guardar**. Todas las entidades seleccionadas se ingerirán desde el nuevo origen de datos.
   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo que muestra una lista de entidades de un archivo model.json](media/review-entities.png)

8. Indique en qué entidades de datos desea habilitar la generación de perfiles de datos y seleccione **Guardar**. La generación de perfiles de datos habilita el análisis y otras capacidades. Puede seleccionar la entidad completa, que selecciona todos los atributos de la entidad, o seleccionar ciertos atributos de su elección. De forma predeterminada, ninguna entidad está habilitada para la creación de perfiles de datos.
   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo que muestra un perfil de datos](media/dataprofiling-entities.png)

9. Después de guardar sus selecciones, se abre la página **Orígenes de datos**. Ahora debería ver la conexión de la carpeta de Common Data Model como origen de datos.

> [!NOTE]
> Un archivo model.json solo se puede asociar con un origen de datos en el mismo entorno. Sin embargo, el mismo archivo model.json se puede utilizar para orígenes de datos en varios entornos.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editar un origen de datos de carpeta de Common Data Model

Puede actualizar la clave de acceso para la cuenta de almacenamiento que contiene la carpeta Common Data Model. También puede cambiar el archivo model.json. Para conectarse a un contenedor diferente de su cuenta de almacenamiento o cambiar el nombre de la cuenta, [cree una nueva conexión de origen de datos](#connect-to-a-common-data-model-folder).

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Junto al origen de datos que desea actualizar, seleccione los puntos suspensivos.

3. Seleccione la opción **Editar** de la lista.

4. Opcionalmente, actualice la **Clave de acceso** y seleccione **Siguiente**.

   ![Diálogo para editar y actualizar una clave de acceso para un origen de datos existente](media/edit-access-key.png)

5. Opcionalmente, puede actualizar desde una conexión de clave de cuenta a una conexión basada en recursos o basada en suscripción. Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md). No puede cambiar la información de **Contenido** al actualizar la conexión.
   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo para introducir detalles de conexión para Azure Data Lake](media/enter-existing-storage-details.png)

6. Opcionalmente, elija un archivo model.json diferente con un conjunto diferente de entidades del contenedor.

7. Opcionalmente, puede seleccionar entidades adicionales para ingerir. También puede quitar cualquier entidad ya seleccionada si no hay dependencias.

   > [!IMPORTANT]
   > Si hay dependencias en el archivo model.json existente y el conjunto de entidades, verá un mensaje de error y no podrá seleccionar un archivo model.json diferente. Elimine esas dependencias antes de cambiar el archivo model.json o cree un nuevo origen de datos con el archivo model.json que desee usar para evitar eliminar las dependencias.

8. Opcionalmente, puede seleccionar atributos o entidades adicionales para habilitar la creación de perfiles de datos o deshabilitar los ya seleccionados.   
