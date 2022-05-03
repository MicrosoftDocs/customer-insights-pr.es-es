---
title: Conector de Power BI
description: Aprenda a usar el conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647849"
---
# <a name="connector-for-power-bi-preview"></a>Conector para Power BI (vista previa)

Cree visualizaciones para sus datos con Power BI Desktop. Genere información adicional y cree informes con sus datos de cliente unificados.

## <a name="prerequisites"></a>Requisitos previos

- Tiene perfiles de cliente unificados.
- La última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada en su ordenador. [Más información acerca de Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar el conector para Power BI

1. En Power BI Desktop, seleccione **Archivo** > **Obtener datos**.

1. Seleccione **Ver más** y busque **Dynamics 365 Customer Insights**

1. Seleccione **Conectar**.

1. **Inicie sesión** con la misma cuenta de organización que usa para Customer Insights y seleccione **Conectar**.
   > [!NOTE]
   > La cuenta que indique en este paso se usa para obtener datos de Customer Insights y no necesita ser la misma en la que inició sesión en Power BI. Para restablecer la cuenta que se utiliza para la recuperación de datos, abra Power BI y vaya a **Archivo** > **Opciones** > **Configuración** > **Configuración de origen de datos**. En la lista de orígenes de datos, seleccione **Inicio de sesión de Dynamics 365 Customer Insights** y seleccione **Borrar permisos**.  

1. En el cuadro de diálogo **Navegador**. puede ver la lista de todos los entornos a los que tiene acceso. Expanda un entorno y abra cualquiera de las carpetas (entidades, medidas, segmentos, enriquecimientos). Por ejemplo, abra la carpeta **Entidades** para ver todas las entidades que puede importar.

   ![Navegador de conectores de Power BI.](media/power-bi-navigator.png "Navegador de conectores de Power BI")

1. Seleccione las casillas de verificación junto a las entidades que quiere incluir y **Cargar**. Puede seleccionar varias entidades de múltiples entornos.

1. Verá un cuadro de diálogo de carga mientras se cargan las entidades. Una vez que se hayan cargado todas las entidades seleccionadas, puede utilizar las capacidades de Power BI para visualizar los datos.

## <a name="large-data-sets"></a>Conjuntos de datos de gran tamaño

El conector Customer Insights para Power BI está diseñado para funcionar con conjuntos de datos que contienen hasta 1 millón de perfiles de clientes. La importación de conjuntos de datos más grandes puede funcionar, pero lleva mucho tiempo. Además, el proceso podría agotar un tiempo de espera debido a las limitaciones de Power BI. Para más información, vea [Power BI: Recomendaciones para grandes conjuntos de datos](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Trabajar con un subconjunto de datos

Considere trabajar con un subconjunto de sus datos. Por ejemplo, puede crear [segmentos](segments.md) en lugar de exportar todos los registros de clientes a Power BI.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>El entorno de Customer Insights no aparece en Power BI

Entornos que tienen más de una [relación](relationships.md) definida entre dos entidades idénticas en Customer Insights no estará disponible en el conector Power BI.

Puede identificar y eliminar las relaciones duplicadas.

1. Vaya a **Datos** > **Relaciones** en el entorno en el que te estás perdiendo en Power BI.
2. Identifique relaciones duplicadas:
   - Compruebe si hay más de una relación definida entre las mismas dos entidades.
   - Compruebe si existe una relación creada entre dos entidades que están incluidas en el proceso de unificación. Existe una relación implícita definida entre todas las entidades incluidas en el proceso de unificación.
3. Elimine las relaciones duplicadas identificadas que haya.

Después de eliminar las relaciones duplicadas, intente volver a configurar el conector de Power BI. El entorno debería estar disponible ahora.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Errores en los campos de fecha al cargar entidades en Power BI Desktop

Al cargar entidades que contienen campos con un formato de fecha como MM/DD/AAAA, puede encontrar errores debidos a formatos de configuración regional no coincidentes. Este desajuste ocurre cuando su archivo Power BI Desktop está configurado en una configuración regional diferente al inglés (Estados Unidos), porque los campos de fecha en Customer Insights se guardan en formato de EE. UU.

El archivo de Power BI Desktop tiene una configuración regional única, que se aplica al recuperar datos. Para que se interpreten correctamente estos campos de fecha, establezca la configuración regional del archivo .BPI en inglés (Estados Unidos). [Aprenda a cambiar la configuración regional de un archivo de Power BI Desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
