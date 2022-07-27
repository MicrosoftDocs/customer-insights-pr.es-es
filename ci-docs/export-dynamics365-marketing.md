---
title: Exportar segmentos a Dynamics 365 Marketing (versión preliminar)
description: Aprenda a configurar la conexión y a exportar a Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054637"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exportar segmentos a Dynamics 365 Marketing (versión preliminar)

Use los [segmentos](segments.md) creados para generar campañas y contactar con grupos específicos de clientes con Dynamics 365 Marketing. Para obtener más información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Si está usando las nuevas capacidades de Dynamics 365 Marketing para la orquestación del recorrido del cliente en tiempo real en una organización de Dataverse, no necesita crear una exportación estándar a Dynamics 365 Marketing. Los contactos y segmentos de Customer Insights están disponibles directamente en Dynamics 365 Marketing después de conectar Marketing y Customer Insights. Antes de eliminar las exportaciones existentes, revise la documentación en [cómo conectar Customer Insights y Dynamics 365 Marketing recorrido del cliente orquestación](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Requisito previo para una conexión

- Los registros de contacto deben estar presentes en Dynamics 365 Marketing antes de poder exportar un segmento de Customer Insights a Marketing. Más información sobre cómo ingerir contactos en [Dynamics 365 Marketing usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > La exportación de segmentos de Customer Insights a Marketing no creará nuevos registros de contacto en las instancias de Marketing. Los registros de contacto de Marketing deben ingerirse en Customer Insights y usarse como origen de datos. También deben incluirse en la entidad Cliente unificada para asignar los identificadores de cliente a los identificadores de contacto antes de que se puedan exportar los segmentos.

## <a name="set-up-connection-to-marketing"></a>Configurar conexión a Marketing

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Dynamics 365 Marketing** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. Si no realiza ninguna acción, el valor predeterminado será Administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduzca la dirección URL de Marketing de su organización en el campo **Dirección del servidor**.

1. En la sección **Cuenta de administrador de servidor**, seleccione **Iniciar sesión** y elija una cuenta de Dynamics 365 Marketing.

1. Asigne el campo Id. de contacto de la entidad Cliente al Id. de contacto de Dynamics 365.

1. Seleccione **Guardar** para completar la conexión. 

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Dynamics 365 Marketing. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Elija uno o más segmentos.

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
