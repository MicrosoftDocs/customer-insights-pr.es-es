---
title: Crear y administrar entornos
description: Obtenga información sobre cómo registrarse en el servicio y cómo administrar los entornos.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 65c6a68f550c2873ec30c6ac54f1752d880ce12c
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799656"
---
# <a name="manage-environments"></a>Administrar ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Cambiar entornos

Seleccione el control **Entorno** en la esquina superior derecha de la página para cambiar entornos.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla del control para cambiar de entorno.":::

Los administradores pueden [crear](create-environment.md) y administrar entornos.

## <a name="edit-an-existing-environment"></a>Editar un entorno existente

Puede editar algunos de los detalles de los entornos existentes.

1.  Seleccione el selector **Entorno** en el encabezado de la aplicación.

2.  Seleccione el icono de **Editar**.

3. En el cuadro **Editar entorno** puede actualizar la configuración del entorno.

Para obtener más información sobre la configuración del entorno, consulte [Crear un nuevo entorno](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Conectar con Microsoft Dataverse
   
El paso **Microsoft Dataverse** le permite conectar Customer Insights con su entorno de Dataverse.

Para usar [modelos predicción predefinidos](predictions-overview.md#out-of-box-models), configure el intercambio de datos con Dataverse. O puede habilitar la ingestión de datos desde orígenes de datos locales, proporcionando la dirección URL del entorno de Microsoft Dataverse que administra su organización. Seleccione **Habilitar el uso compartido de datos** para compartir los datos de salida de Customer Insights con una instancia de lago de datos gestionada de Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opciones de configuración para permitir el uso compartido de datos con Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights no admite los siguientes escenarios de uso compartido de datos:
> - Si guarda todos los datos en su propio Azure Data Lake Storage, no podrá habilitar el uso compartido de datos con un lago de datos administrado por Dataverse.
> - Si habilita el uso compartido de datos con Dataverse, no podrá [crear valores pronosticados o faltantes en una entidad](predictions.md).

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

- Orígenes de datos de la carpeta Common Data Model y el lago de datos administrado por Dataverse. Tendrá que crear esos orígenes de datos manualmente con el mismo nombre que en el entorno de origen.

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
