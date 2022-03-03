---
title: Exportar eventos refinados
description: Cómo exportar eventos refinados y eventos base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232909"
---
# <a name="export-events"></a>Exportar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un evento representa el comportamiento del usuario. Registra cuando un usuario ve una página (evento de visualización) o interactúa con el contenido (evento de acción). Cuando puede decidir qué propiedades de los datos desea mostrar en un informe, esta vista virtual de los datos se denomina *evento refinado*. Para más información, vea [Crear y modificar eventos](refined-events.md).

- Puede exportar eventos y eventos refinados a un almacenamiento externo. 
- Las exportaciones son un flujo de datos hacia delante. No puede volver a llenar la secuencia. 
- Las exportaciones tienen esquemas fijos. Si agrega propiedades personalizadas a un evento, no se incluirán. Deberá crear una nueva exportación.

## <a name="prerequisites"></a>Requisitos previos

Antes de configurar una exportación, debe tener acceso y una suscripción activa al portal de Azure. Necesitará la información de la cuenta de almacenamiento durante el proceso de exportación. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Crear una cuenta Azure Data Lake Storage Gen 2.

1. Inicie sesión en el portal de Azure y [cree una nueva cuenta de almacenamiento](/azure/storage/common/storage-account-create). 

1. Asegúrse de habilitar el **Espacio de nombres jerárquico** en la pestaña **Avanzado**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Habilitar el espacio de nombres jerárquico en la pestaña Avanzado.":::

1. Una vez que se haya implementado, vaya a la cuenta de almacenamiento recién creada. En el panel de navegación, seleccione **Configuración** > **Claves de acceso**. 

1. Copie el **Nombre de la cuenta** y la **Clave** para utilizarlos al crear una nueva exportación.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Claves de acceso en una cuenta de almacenamiento.":::

## <a name="export-events"></a>Exportar eventos

Hay dos formas de abrir el diálogo **Exportar eventos**: 
- Vaya a **Datos** > **Exportaciones** y seleccione **Nueva exportación**.
- Vaya a **Datos** > **Eventos**, seleccione **Más [...]** junto al evento que desea exportar y seleccione **Exportar** en el menú desplegable. 

:::image type="content" source="media/new-export.png" alt-text="Crear una nueva exportación.":::

Se le guiará a través de los pasos para crear una exportación:

1. Proporcione un **Nombre de exportación** y luego seleccione **Siguiente**.

1. En la lista desplegable **Selección de eventos**, elija los eventos base y los eventos refinados que se van a incluir en la exportación. 

1. En la sección **Estructura de archivo**, seleccione la cadencia (por hora o diaria) para crear nuevos archivos en el almacenamiento de destino, y luego seleccione **Siguiente**. Los eventos se exportan continuamente a medida que llegan.

1. En el diálogo **Elegir formato**, seleccione el formato para su exportación. Elija entre los formatos **Common Data Model**, **CSV** y **JSON**. Para usar la exportación con otras aplicaciones de Dynamics 365, recomendamos el formato **Common Data Model**.

1. En el diálogo **Elegir destino**, especifique la ubicación de Azure Data Lake Storage Gen 2.
    1. **Nombre de la cuenta de ADLS Gen 2** es el nombre de la cuenta de almacenamiento en la que desea guardar la exportación. 
    1. **Ruta de la carpeta** define dónde se debe almacenar la exportación en el sistema de archivos y la estructura del directorio de la cuenta de almacenamiento.
    1. **Clave compartida** está disponible en Azure Portal para la cuenta de almacenamiento.

1. Revise y confirme las selecciones para finalizar.

## <a name="view-and-manage-exports"></a>Ver y administrar exportaciones

Una vez que haya configurado una exportación, vaya a **Datos** > **Exportaciones** para verla. Seleccione **Más [...]** para cualquier exportación existente para editarla o eliminarla.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
