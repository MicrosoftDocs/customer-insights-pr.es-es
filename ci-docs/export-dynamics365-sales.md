---
title: Exportar segmentos a Dynamics 365 Sales (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081814"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportar segmentos a Dynamics 365 Sales (versión preliminar)

Use sus datos de clientes para crear listas de marketing, realizar un seguimiento de los flujos de trabajo y enviar promociones con Dynamics 365 Sales.

## <a name="known-limitations"></a>Limitaciones conocidas

- Las exportaciones a Dynamics 365 Sales están limitadas a 100 000 miembros por segmento.
- Las exportaciones de segmentos a Dynamics 365 Sales pueden tardar hasta 3 horas en completarse. 

## <a name="prerequisite-for-connection"></a>Requisito previo para una conexión

1. Los registros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales. Obtenga más información sobre cómo ingerir contactos de [Dynamics 365 Sales usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > La exportación de segmentos de Customer Insights a Sales no creará nuevos registros de contacto en las instancias de Sales. Los registros de contacto de Sales deben ingerirse en Customer Insights y usarse como origen de datos. También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.

## <a name="set-up-the-connection-to-sales"></a>Configurar la conexión con Sales

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Dynamics 365 Sales** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca la dirección URL de Sales de su organización en el campo **Dirección del servidor**.

1. En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Sales.

1. Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Dynamics 365 Sales. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Elija uno o más segmentos.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
