---
title: Conector de Power BI
description: Aprenda a usar el conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407009"
---
# <a name="connector-for-power-bi-preview"></a>Conector para Power BI (vista previa)

Cree visualizaciones para sus datos con Power BI Desktop. Genere información adicional y cree informes con sus datos de cliente unificados.

## <a name="prerequisites"></a>Requisitos previos

- Tiene perfiles de cliente unificados.
- La última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalado en su equipo. [Más información acerca de Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar el conector para Power BI

1. En Power BI Desktop, seleccione **Archivo** > **Obtener datos**.

1. Seleccione **Ver más** y busque **Dynamics 365 Customer Insights**

1. Seleccione el resultado y seleccione **Conectar**.

1. **Inicie sesión** con la misma cuenta de organización que usa para Customer Insights y seleccione **Conectar**.
   > [!NOTE]
   > La cuenta que indique en este paso se usa para obtener datos de Customer Insights y no necesita ser la misma en la que inició sesión en Power BI. Para restablecer la cuenta que se utiliza para la recuperación de datos, abra Power BI y vaya a **Archivo** > **Opciones** > **Configuración** > **Configuración de origen de datos**. En la lista de orígenes de datos, seleccione **Inicio de sesión de Dynamics 365 Customer Insights** y seleccione **Borrar permisos**.  

1. En el cuadro de diálogo **Navegador**. puede ver la lista de todos los entornos a los que tiene acceso. Expanda un entorno y abra cualquiera de las carpetas (entidades, medidas, segmentos, enriquecimientos). Por ejemplo, abra la carpeta **Entidades** para ver todas las entidades que puede importar.

   ![Navegador de conectores de Power BI](media/power-bi-navigator.png "Navegador de conectores de Power BI")

1. Seleccione las casillas de verificación junto a las entidades que quiere incluir y **Cargar**. Puede seleccionar varias entidades de múltiples entornos.

1. Verá un cuadro de diálogo de carga mientras se cargan las entidades. Una vez que se hayan cargado todas las entidades seleccionadas, puede utilizar las capacidades de Power BI para visualizar los datos.

## <a name="large-data-sets"></a>Conjuntos de datos de gran tamaño

El conector Customer Insights para Power BI está diseñado para funcionar con conjuntos de datos que contienen hasta 1 millón de perfiles de clientes. La importación de conjuntos de datos más grandes puede funcionar, pero lleva mucho tiempo. Además, el proceso podría agotar un tiempo de espera debido a las limitaciones de Power BI. Para más información, vea [Power BI: Recomendaciones para grandes conjuntos de datos](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Trabajar con un subconjunto de datos

Considere trabajar con un subconjunto de sus datos. Por ejemplo, puede crear [segmentos](segments.md) en lugar de exportar todos los registros de clientes a Power BI.
