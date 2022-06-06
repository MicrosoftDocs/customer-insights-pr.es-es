---
title: Cómo administrar entornos
description: Aprenda a administrar los entornos existentes de Customer Insights como administrador".
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833513"
---
# <a name="how-to-manage-environments"></a>Cómo administrar entornos

Los administradores [crean](create-environment.md) y administran entornos. Pueden cambiar algunas configuraciones en entornos existentes. Los ajustes de negocio, tipo, región, opción de almacenamiento y Dataverse se fijan después de crear el entorno. Si desea cambiar esta configuración, restablezca el entorno o cree un nuevo entorno.

## <a name="edit-an-existing-environment"></a>Editar un entorno existente

Puede editar algunos de los detalles de los entornos existentes.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el icono de **Editar**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icono para editar la configuración del entorno.":::

1. En el cuadro **Editar entorno** puede actualizar la configuración del entorno.

Para comenzar con un entorno nuevo, consulte [Crear un nuevo entorno](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Cambiar el propietario de un entorno

Varios usuarios pueden tener permisos de administrador, pero solo un usuario es el propietario de un entorno. De forma predeterminada, es el administrador el que crea un entorno inicialmente. Como administrador de un entorno, puede asignar la propiedad a otro usuario con permisos de administrador.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el icono de **Editar**.

1. En el cuadro de diálogo **Editar entorno**, vaya al paso **Información básica**.

1. En el campo **Cambiar propietario del entorno**, elija el nuevo propietario del entorno.  

1. Seleccione **Revisar y terminar**, luego **Actualizar** para aplicar los cambios.

## <a name="claim-ownership-of-an-environment"></a>Reclamar la propiedad de un entorno

Si la cuenta de usuario del propietario se elimina o suspende, el entorno no tendrá propietario. Todo usuario administrador puede reclamar la propiedad y convertirse en el nuevo propietario. Pueden seguir siendo propietarios del entorno o [cambiar la propiedad a otro administrador](#change-the-owner-of-an-environment).

Para reclamar la propiedad, seleccione el botón **Asumir la propiedad** que se muestra en la parte superior de cada página en Customer Insights cuando el propietario original deja la organización.

## <a name="reset-an-existing-environment-preview"></a>Restablecer un entorno existente (versión preliminar)

Como propietario de un entorno, puede restablecer el entorno a un estado vacío si desea eliminar todas las configuraciones y los datos ingeridos.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el entorno que desea restablecer y seleccione los puntos suspensivos verticales (&vellip;).

1. Elija la opción **Restablecer**.

   :::image type="content" source="media/reset-environment.png" alt-text="Control para restablecer un entorno.":::

1. Elija si desea restablecer todo el entorno, todo excepto los orígenes de datos o cualquier cosa que esté configurada sobre Unified Customer Profile.

1. Para confirmar, especifique el nombre del entorno y seleccione **Restablecer**.

## <a name="delete-an-existing-environment"></a>Eliminar un entorno existente

Como propietario de un entorno, puede eliminar un entorno que administre.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el entorno que desea restablecer y seleccione los puntos suspensivos verticales (&vellip;). 

1. Elija la opción **Eliminar**.

   :::image type="content" source="media/delete-environment.png" alt-text="Control para eliminar el entorno.":::

1. Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Eliminar**.

> [!IMPORTANT]
> La eliminación de un entorno no elimina la conexión con un entorno de Dataverse. Si planear conectar el mismo entorno de Dataverse a un nuevo entorno de Customer Insights en el futuro, deberá eliminar esa conexión. Aprenda a [eliminar una conexión existente a un entorno de Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
