---
title: Bot para Microsoft Teams
description: Busque perfiles de clientes unificados en Microsoft Teams con la ayuda de un bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407037"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot de Teams para Dynamics 365 Customer Insights (versión preliminar)

Conéctese con Microsoft Teams para permitir que un bot busque perfiles de clientes unificados en los canales de Teams.

> [!div class="mx-imgBorder"]
> ![Bot de Teams mostrando un registro de cliente](media/teams-bot.png "Bot de Teams mostrando un registro de cliente")

## <a name="prerequisites"></a>Requisitos previos

Para preparar y configurar el bot deben cumplirse los siguientes requisitos previos:

- Hay al menos un [origen de datos agregado](data-sources.md).
- Se ha completado la instancia de [proceso de unificación](data-unification.md).
- Se han agregado campos a [índice de búsqueda y filtro](search-filter-index.md).
- Customer Insights y Teams están en la misma organización.

## <a name="configure-the-bot"></a>Configurar el bot

1. En las informaciones de público, vaya a **Administrador** > **Destinos de exportación**.
1. En el icono de Microsoft Teams, seleccione **Configurar**.
1. Se le redirigirá al área **Aplicaciones** en equipos. También puede abrir Teams y seleccionar **Aplicaciones** en la esquina inferior izquierda u [obtenerlo de AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directamente.
1. Busque **Customer Insights** y seleccione la aplicación.
1. Seleccione **Agregar**.
1. Después de iniciar sesión en Customer Insights dentro de Teams, verá un mensaje de bienvenida y podrá empezar.

## <a name="things-you-can-do-with-the-bot"></a>Cosas que puede hacer con el bot

El bot proporciona capacidades de búsqueda para perfiles de clientes unificados.

- Escriba **buscar** seguido de un nombre, dirección de correo electrónico o cualquier otro campo del perfil de cliente unificado que se haya agregado al índice de búsqueda y filtrado.

  Obtendrá una tarjeta con hasta 15 campos del perfil de cliente resultante. Múltiples coincidencias devuelven una lista de resultados en la que puede seleccionar un perfil. Puede agregar el término de búsqueda entre comillas dobles para buscar una coincidencia exacta.

- Si su organización mantiene varios entornos de Customer Insights en la misma organización, puede introducir **switchinstance** para elegir el entorno al que desea conectar el bot.

- Escriba **ayuda** para ver una lista de comandos disponibles para el bot.  
