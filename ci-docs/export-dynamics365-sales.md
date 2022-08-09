---
title: Exportar segmentos a Dynamics 365 Sales (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196002"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportar segmentos a Dynamics 365 Sales (versión preliminar)

Use sus datos de clientes para crear listas de marketing, realizar un seguimiento de los flujos de trabajo y enviar promociones con Dynamics 365 Sales.

## <a name="prerequisites"></a>Requisitos previos

Los registros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales. Obtenga más información sobre cómo ingerir contactos de [Dynamics 365 Sales usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > La exportación de segmentos de Customer Insights a Sales no creará nuevos registros de contacto en las instancias de Sales. Los registros de contacto de Sales deben ingerirse en Customer Insights y usarse como origen de datos. También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.

## <a name="known-limitations"></a>Limitaciones conocidas

Las exportaciones a Dynamics 365 Sales están limitadas a 100 000 por segmento, lo que puede tardar hasta 3 horas en completarse.

## <a name="set-up-connection-to-sales"></a>Configurar la conexión con Ventas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Añadir conexión** y elija **Dynamics 365 Sales**.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca la dirección URL de Sales de su organización en el campo **Dirección del servidor**.

1. En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Sales.

1. Asigne un campo de id. de cliente al id. de contacto de Dynamics 365.

1. Revise [Privacidad y cumplimiento de datos](connections.md#data-privacy-and-compliance) y seleccione **Acepto**.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaya a **Datos** > **Exportaciones**.

1. Seleccione **Agregar exportación**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Dynamics 365 Sales. Contacte con un administrador si no hay conexión disponible.

1. Escriba un nombre para la exportación.

1. Seleccione el campo Id. de contacto de la entidad cliente que corresponda al id. de contacto de Dynamics 365.

1. Seleccione los segmentos que desea exportar.

1. Seleccione **Guardar**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
