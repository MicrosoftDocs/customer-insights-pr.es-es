---
title: Ver informes de datos
description: Utilice los informes disponibles para ver la actividad en tiempo real en su sitio web.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036669"
---
# <a name="view-reports"></a>Ver informes

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe es una colección de visualizaciones de datos, que utiliza los datos recopilados a través del SDK, que le ayudan a medir y comprender el comportamiento del usuario. Los conocimientos sobre la interactuación de Dynamics 365 Customer Insights incluyen informes listos para usar (OOB) para proyectos web y móviles.  

## <a name="web-reports"></a>Informes web

Puede acceder a los informes web en **Descubrir** en el panel de navegación izquierdo.

:::image type="content" source="media/report-menu.png" alt-text="Navegación que muestra la lista de informes disponibles.":::

### <a name="real-time-usage-report"></a>Informe de uso en tiempo real

El informe **Uso en tiempo real** proporciona una descripción general de la actividad actual en su sitio web que se actualiza automáticamente cada minuto. Utilice el uso en tiempo real para supervisar el impacto de las campañas de marketing, eventos de prensa y otros escenarios en el tráfico de su sitio.

### <a name="key-metrics-reports"></a>Informes de métricas clave

- **Vistas de página** enumera las visitas a la página para páginas individuales junto con el número total de vistas de la página durante el plazo de tiempo seleccionado.

- **Visitas** muestra información sobre el número de visitas y la duración de la visita.

- **Visitantes** informa sobre los visitantes únicos nuevos y recurrentes a su sitio.

### <a name="content-reports"></a>Informes de contenido

- **Vínculos** muestra información sobre el número y el tipo de clics.

- **Paginas de salida** enumera los enlaces en los que los visitantes hicieron clic para salir de su sitio.

### <a name="traffic-sources-reports"></a>Informes de fuentes de tráfico

- **Referencias** enumera los dominios y las direcciones URL que remitieron a los visitantes a su sitio.

- **Códigos de seguimiento** ofrece detalles sobre los códigos de seguimiento en los enlaces que llevaron a los visitantes a su sitio.

### <a name="visitor-profiles-reports"></a>Informes de perfiles de visitantes

- **Dispositivos** enumera los dispositivos físicos que se utilizaron para acceder a su sitio.

- **SO y navegadores** proporciona información sobre los sistemas operativos y los navegadores que se estaban ejecutando al acceder a su sitio.

- **Ubicaciones** muestra información sobre los visitantes por país, región y ciudad.

- **Idiomas** enumera las vistas de página según los idiomas preferidos de los visitantes.

## <a name="mobile-reports"></a>Informes móviles

Los informes móviles se agrupan en categorías de usuarios, aplicaciones y utilización en tiempo real. Puede acceder a los informes móviles en **Descubrir** en el panel de navegación izquierdo.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interfaz de usuario de conocimientos sobre la interacción que muestra el informe de utilización en tiempo real con los datos en gráficos y listas.":::   

### <a name="real-time-usage"></a>Uso en tiempo real

**Utilización en tiempo real** proporciona una descripción general de la actividad actual en su aplicación móvil que se actualiza automáticamente cada minuto. Utilice la utilización en tiempo real para supervisar la cantidad de usuarios y sesiones actualmente activos en su aplicación y las vistas de la pantalla superior.

### <a name="app-reports"></a>Informes de aplicación

- **Vistas de pantalla** enumera las vistas de pantalla para pantallas individuales en una aplicación y el número total de vistas de pantalla durante un plazo de tiempo seleccionado. Puede ver las vistas de pantalla por nombre de pantalla o por título de pantalla.

- **Sesiones** muestra información sobre el número de sesiones y la duración de la sesión.

- **Frecuencia de retorno** agrupa recuentos de sesiones por el número de días desde la última sesión.

- **Usuarios** muestra los usuarios nuevos y recurrentes en su aplicación móvil.

- **Eventos** enumera todos los eventos recopilados de su aplicación, además del recuento total para cada evento.

### <a name="user-reports"></a>Informes de usuario

- **Versiones de la aplicación** enumera las versiones de su aplicación móvil en uso por su base de usuarios.

- **Dispositivos y versiones de SO** proporciona conocimientos sobre los dispositivos y sistemas operativos que ejecutan su aplicación móvil.

- **Ubicaciones** muestra información sobre los usuarios de la aplicación por país, región y ciudad.

## <a name="filter-by-time-or-value"></a>Filtrar por tiempo o valor

Puede seleccionar período de tiempo o valor en un informe web o móvil para centrarse en un valor o plazo de tiempo. 

- Para seleccionar un plazo de tiempo, seleccione **Más [...]** en la lista desplegable del informe. La selección de intervalo de tiempo está deshabilitada para un informe de uso en tiempo real; el intervalo de tiempo para un informe de uso en tiempo real es "ahora".

- En la mayoría de los informes, seleccione un valor en un gráfico o lista para filtrar el informe por el valor seleccionado.

[!INCLUDE[footer-include](../includes/footer-banner.md)]