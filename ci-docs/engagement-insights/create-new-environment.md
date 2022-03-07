---
title: Crear un nuevo entorno
description: El propósito de un entorno y cómo crear uno nuevo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648138"
---
# <a name="create-a-new-environment"></a>Crear un nuevo entorno 

## <a name="overview"></a>Introducción

Un entorno es un espacio donde gestiona sus áreas de trabajo y conexiones. La forma en que usa los entornos depende de su organización y su caso de uso. Por ejemplo, puede crear:

- Un solo entorno.
- Entornos separados de prueba y de producción.
- Entornos separados para equipos o departamentos específicos de su organización que contienen eventos relevantes para cada público.
- Entornos separados para diferentes ramas del mundo de su empresa.
- Conexiones a las funcionalidades de las conclusiones del público de Customer Insights.

## <a name="create-a-new-environment"></a>Crear un nuevo entorno

1. En el lado derecho del banner principal, seleccione el selector de entornos y luego **+Nuevo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Seleccionar el selector de entornos.":::

1. En el panel **Configuración**, escriba un **Nombre del entorno**.

1. Elija el **Tipo** de cuenta, dependiendo de su tipo de plan.

1. Elija la **Región** y seleccione **Siguiente**. 

1. Escriba un **Nombre del área de trabajo**, que le permite recopilar datos para sitios web o aplicaciones específicos. Para obtener más información, consulte [Crear un área de trabajo](create-workspace.md).

1. Elija el **Tipo de área de trabajo** (Web o móvil) que desea crear. 

1. Seleccione **Mostrar configuración avanzada** para habilitar o deshabilitar estas configuraciones opcionales:

   - Active **Desconocido a conocido** para asociar eventos web con usuarios que se autenticaron previamente. Para más información, vea [Reconocer eventos web de visitantes previamente autenticados](unknown-to-known.md)
   - Active **Filtrar tráfico de bots** para quitar el tráfico web de los bots para esta área de trabajo. 

1. Seleccione **Completo** cuando haya terminado. 

1. Instale el fragmento de código para comenzar a recibir datos y luego seleccione **Finalizar** para crear el área de trabajo. Para obtener más información, consulte [Información general para desarrolladores](developer-resources.md).

> [!NOTE]
> Ahora puede agregar miembros y asignar su nivel de permiso desde la lista **Rol**. Para obtener más información, consulte [Roles y permisos](user-roles.md). 

Para obtener más información, consulte [Gestionar entornos y áreas de trabajo](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Trabajar con su nuevo entorno

- [Cree un área de trabajo](../engagement-insights/create-workspace.md) y añada miembros.
- [Agregue código a su sitio web](../engagement-insights/instrument-website.md) o [aplicación móvil](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Ver un [informe en tiempo real](../engagement-insights/view-reports.md) o crear [informes personalizados](../engagement-insights/custom-reports.md).
- [Cree eventos refinados](../engagement-insights/refined-events.md) para exportar.
- [Exporte los datos](../engagement-insights/export-events.md) a Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
