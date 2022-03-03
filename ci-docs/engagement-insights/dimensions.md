---
title: Ver y crear dimensiones
description: Cómo crear, editar y eliminar dimensiones.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d35c72f73d2f3e202ae3c5a5ef26e9db89360084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226328"
---
# <a name="view-and-create-dimensions"></a>Ver y crear dimensiones

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Una dimensión es un atributo de un evento que puede describir, filtrar o agrupar datos. Si está ejecutando una promoción de marketing en su sitio web, puede utilizar dimensiones para clasificar a los visitantes por usuarios nuevos y recurrentes.  

La información sobre la participación incluye dimensiones listas para usar (OOB) para las propiedades del evento. A continuación se muestran algunos ejemplos:

- Nombre del explorador
- Nombre de página
- Modelo de dispositivo
- Sistema operativo
- País

## <a name="view-dimensions"></a>Ver dimensiones

Las dimensiones se basan en propiedades de eventos existentes. Cuando utiliza el código de seguimiento para obtener información sobre la participación, las dimensiones del sistema se crean automáticamente.

1. Vaya a **Datos** en el panel de navegación izquierdo. 
1. Seleccione **Dimensiones** para ver una lista de todas las dimensiones en el área de trabajo. 
   > [!NOTE]
   > Las dimensiones generadas por el sistema son de solo lectura. No puede editarlas. Solo puede crear y editar dimensiones personalizadas.

## <a name="create-a-dimension"></a>Crear una dimensión

Además de las dimensiones generadas por el sistema, los administradores del entorno y del espacio de trabajo pueden crear dimensiones personalizadas. Las dimensiones personalizadas se basan en las propiedades predeterminadas de los eventos base o pueden usar [propiedades personalizadas de un evento](advanced-SDK-implementation.md).

1. Vaya a **Datos** > **Dimensiones**.
1. Seleccione **Nueva dimensión**.

   :::image type="content" source="media/add-dimension.png" alt-text="Agregar una dimensión a un evento.":::

1. En el panel **Crear una dimensión**, seleccione una propiedad en la que basar la dimensión. La lista de propiedades mostrará todas las propiedades del espacio de trabajo no asignadas a una dimensión.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Crear una nueva dimensión.":::
      
3. Indique un nombre para el cuadro **Nombre para mostrar**. Opcionalmente puede agregar una **Descripción**.
4. Seleccione **Crear flujo** para guardar la dimensión. Puede tardar hasta un minuto antes de que pueda usar la dimensión en un [informe personalizado](custom-reports.md) o [segmento](segments.md). 

## <a name="edit-a-dimension"></a>Editar una dimensión

Puede cambiar el nombre y la descripción de una dimensión. Solo puede editar dimensiones creadas por el usuario, pero no puede editar las dimensiones del sistema.


1. Vaya a **Datos** > **Dimensiones**.
1. Seleccione la dimensión que desea eliminar.
1. En el panel **Editar dimensión**, actualice la dimensión.
1. Seleccione **Aplicar** para guardar los cambios.

## <a name="delete-a-dimension"></a>Eliminar una dimensión

Solo puede eliminar las dimensiones creadas por el usuario, pero no puede eliminar las dimensiones del sistema.

Eliminar una dimensión es permanente. Los informes y segmentos que utilizan una dimensión eliminada dejarán de funcionar. 

1. Vaya a **Datos** > **Dimensiones**.
1. Seleccione la dimensión que desea eliminar.
1. En el panel **Editar dimensión**, seleccione **Eliminar dimensión**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Eliminar una dimensión de un evento.":::

1. Introduzca **CONFIRMAR ELIMINACIÓN** (en mayúsculas) para confirmar la eliminación. 
1. Seleccione **Eliminar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
