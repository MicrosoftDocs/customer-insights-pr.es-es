---
title: Bot de Teams para Dynamics 365 Customer Insights (versión preliminar)
description: Busque perfiles de clientes unificados en Microsoft Teams con la ayuda de un bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195863"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot de Teams para Dynamics 365 Customer Insights (versión preliminar)

Conéctese con Microsoft Teams para permitir que un bot busque perfiles de clientes unificados en los canales de Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot de Teams mostrando un registro de cliente":::

## <a name="prerequisites"></a>Requisitos previos

- Hay al menos un [origen de datos agregado](data-sources.md).
- Se ha completado la instancia de [proceso de unificación](data-unification.md).
- Se han agregado campos al [índice de búsqueda y filtro](search-filter-index.md).
- Customer Insights y Teams están en la misma organización.
- Su entorno tiene el público de destino principal configurado para clientes individuales. No se admiten las cuentas empresariales.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurar el bot

1. Vaya a **Administrador** > **Conexiones**.
1. En el icono de Microsoft Teams, seleccione **Configurar**.
1. Se le redirigirá al área **Aplicaciones** en equipos. También puede abrir Teams y seleccionar **Aplicaciones** en la esquina inferior izquierda u [obtenerlo de AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directamente.
1. Busque **Customer Insights** y seleccione la aplicación.
1. Seleccione **Agregar**.
1. Inicie sesión en Customer Insights, en Teams. Aparece un mensaje de bienvenida.

## <a name="things-you-can-do-with-the-bot"></a>Cosas que puede hacer con el bot

El bot proporciona capacidades de búsqueda para perfiles de clientes unificados.

- Escriba **buscar** seguido de un nombre, dirección de correo electrónico o cualquier otro campo del perfil de cliente unificado que se haya agregado al índice de búsqueda y filtrado.

  Obtendrá una tarjeta con hasta 15 campos del perfil de cliente resultante. Múltiples coincidencias devuelven una lista de resultados en la que puede seleccionar un perfil. Para buscar una coincidencia exacta, agregue el término de búsqueda entre comillas dobles.

- Si su organización mantiene varios entornos de Customer Insights en la misma organización, introduzca **switchinstance** para elegir el entorno al que desea conectar el bot.

- Escriba **ayuda** para ver una lista de comandos disponibles para el bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]