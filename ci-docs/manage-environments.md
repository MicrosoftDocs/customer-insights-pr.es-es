---
title: Administrar ambientes
description: Aprenda a administrar los entornos existentes de Customer Insights como administrador.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588833"
---
# <a name="manage-environments"></a>Administrar ambientes

Los administradores [crean](create-environment.md) y administran entornos. Pueden cambiar algunas configuraciones en entornos existentes. Los ajustes de negocio, tipo, región, opción de almacenamiento y Dataverse se fijan después de crear el entorno. Si desea cambiar esta configuración, [restablezca el entorno](#reset-an-existing-environment-preview) o [cree un nuevo entorno](create-environment.md).

## <a name="edit-an-existing-environment"></a>Editar un entorno existente

Edite los detalles de un entorno existente, como el nombre o la configuración del entorno predeterminado.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el icono de **Editar**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icono para editar la configuración del entorno.":::

1. En el panel **Editar entorno** puede actualizar la configuración del entorno.

1. Seleccione **Revisar y terminar**, luego **Actualizar** para aplicar los cambios.

## <a name="change-the-owner-of-an-environment"></a>Cambiar el propietario de un entorno

Varios usuarios pueden tener permisos de administrador, pero solo un usuario es el propietario de un entorno. De forma predeterminada, es el administrador el que crea un entorno inicialmente. Como administrador de un entorno, puede asignar la propiedad a otro usuario con permisos de administrador.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el icono de **Editar**.

1. En el panel **Editar entorno**, vaya al paso **Información básica**.

1. En el campo **Cambiar propietario del entorno**, elija el nuevo propietario del entorno.  

1. Seleccione **Revisar y terminar**, luego **Actualizar** para aplicar los cambios.

## <a name="claim-ownership-of-an-environment"></a>Reclamar la propiedad de un entorno

Si la cuenta de usuario del propietario se elimina o suspende, el entorno no tendrá propietario. Cualquier usuario administrador puede reclamar la propiedad y convertirse en el nuevo propietario. El administrador propietario puede seguir siendo propietario del entorno o [cambiar la propiedad a otro administrador](#change-the-owner-of-an-environment).

Para reclamar la propiedad, seleccione el botón **Asumir la propiedad** que se muestra en la parte superior de cada página en Customer Insights cuando el propietario original deja la organización.

## <a name="reset-an-existing-environment-preview"></a>Restablecer un entorno existente (versión preliminar)

Como propietario de un entorno, puede restablecer el entorno a un estado vacío si desea eliminar todas las configuraciones y los datos ingeridos.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el entorno que desea restablecer y seleccione los puntos suspensivos verticales (&vellip;).

1. Elija **Restablecer (vista previa)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Control para restablecer un entorno.":::

1. Elija si desea restablecer todo el entorno, todo excepto los orígenes de datos o cualquier cosa que esté configurada sobre Unified Customer Profile.

1. Para confirmar, especifique el nombre del entorno y seleccione **Restablecer**.

## <a name="delete-an-existing-environment"></a>Eliminar un entorno existente

Como propietario de un entorno, puede eliminarlo.

> [!IMPORTANT]
> La eliminación de un entorno no elimina la conexión con un entorno de Dataverse. Si planear conectar el mismo entorno de Dataverse a un nuevo entorno de Customer Insights en el futuro, debe [eliminar una conexión existente a un entorno de Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el entorno que desea eliminar y seleccione los puntos suspensivos verticales (&vellip;). 

1. Elija **Borrar**.

   :::image type="content" source="media/delete-environment.png" alt-text="Control para eliminar el entorno.":::

1. Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Eliminar**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
