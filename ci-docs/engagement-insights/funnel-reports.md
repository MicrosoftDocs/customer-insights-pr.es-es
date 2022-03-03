---
title: Informes de embudo
description: Cómo utilizar los informes de embudo para comprender cómo el público toma decisiones.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7bb961c5ba8d42f704eefe0dcb22e561367f3efb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226282"
---
# <a name="create-and-manage-funnel-reports"></a>Cree y administre informes de embudo

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En un informe de embudo, se recopila información sobre los pasos que tienen lugar durante un recorrido del cliente a través de su sitio web o aplicación móvil. Le ayuda a comprender cómo un público progresa a través de un proceso e identifica los puntos de entrega. Por ejemplo, puede utilizar un informe de embudo para identificar rutas que están tomando sus clientes antes de realizar una compra. Un informe de embudo proporciona datos para informar las decisiones e identificar las áreas para la optimización y las mejoras de procesos.

## <a name="create-a-funnel-report"></a>Crear un informe de embudo

Para crear un informe de embudo, especifique los pasos que desea incluir y la actividad de cada paso. Una actividad es un [evento](glossary.md) que representa el comportamiento del usuario. El informe de embudo muestra la cantidad de usuarios que completaron cada paso definido. 

1. Vaya a **Embudos** y seleccione **+Nuevo embudo** para iniciar un informe de embudo.

1. En el **Editor de embudo**, en **Pasos**, seleccione **+Agregar paso.** 

1. Introduzca un nombre en **Título del paso**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nuevo informe de embudo.":::

1. Seleccione una **Actividad**. Una actividad registra cuando un usuario visualiza una página (actividad **Visualización**) o interactúa con el contenido (actividad **Acción**).

1. Use **Criterios de paso** para especificar la dimensión de la actividad. Las [dimensiones](dimensions.md) son atributos que pueden describir, filtrar o agrupar datos.

1. Opcionalmente, puede configurar pasos de embudo de múltiples condiciones. Seleccione **Agregar condición** para especificar más dimensiones en un paso. Los criterios adicionales deben utilizar el mismo tipo de actividad. Puede elegir si se conectan varias condiciones con un operador AND u OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor de embudo que muestra la configuración de pasos con pasos de varias condiciones.":::

1. Seleccione **Agregar paso** hasta que complete todos los pasos que desee incluir en el informe.

1. Seleccione **Guardar**, dele un nombre al informe y seleccione **Guardar** de nuevo. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Ejemplo: informe de embudo de la empresa Fourth Coffee

El siguiente escenario ilustra una forma de utilizar un informe de embudo. Una analista de la empresa Fourth Coffee quiere comprender la influencia de una promoción reciente en las tarifas de suscripción. La analista crea un informe de embudo para identificar la actividad del cliente. Abarca desde que los clientes llegan a la página de inicio de la empresa hasta que utilizan el código de promoción de suscripción. La analista crea un informe de embudo con los siguientes pasos:

Paso 1: Clientes que llegan a la página de inicio   
Paso 2: Clientes que realizan una compra   
Paso 3: Clientes que usan el código de promoción para obtener un descuento en una suscripción   
Paso 4: Registro de suscripción   

:::image type="content" source="media/funnel-report-example.png" alt-text="ejemplo de informe de embudo.":::
  
Este embudo le permite ver la cantidad de usuarios que han usado el código de promoción después de una compra única para registrarse en el programa de suscripción.

### <a name="configure-advanced-settings"></a>Configurar opciones avanzadas 

Los informes de embudo le permiten definir un límite en el tiempo que lleva completar un embudo. Por ejemplo, puede establecer el tiempo para completar el embudo en cuatro días. Esta configuración solo contará los registros de suscripción exitosos que ocurrieron dentro de los cuatro días posteriores a la visita de un usuario a la página de inicio.

1. Vaya a **Embudos** para abrir la **Biblioteca de embudos**.

1. Seleccione un nombre para abrir el informe. 

1. En el panel **Editor de embudo**, seleccione **Ajustes avanzados**. 

1. Establezca el tiempo límite de finalización del embudo en **Activado**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor de embudo que muestra configuraciones avanzadas y opciones para limitar el tiempo para completar un embudo.":::

1. Elija la hora a la que debe completarse el embudo en la lista desplegable **Establecer límite a**.

1. Seleccione **Guardar** para aplicar los cambios.


## <a name="cross-channel-funnel-reports"></a>Informes de embudo entre canales 

En las conclusiones sobre la interacción también se recopilar datos de comportamiento de los clientes en su aplicación móvil. Una vez que haya instrumentado su aplicación móvil con el [SDK de Android](get-started-android.md) o [el SDK de iOS](get-started-ios.md) de las conclusiones sobre la interacción , puede crear informes de embudo entre canales. 

### <a name="create-a-cross-channel-funnel-report"></a>Crear un informes de embudo entre canales 

1. Siga los pasos para [crear un informe de embudo](#create-a-funnel-report).    

1. Para realizar un seguimiento de cómo sus clientes interactúan con su marca tanto en su sitio web como en su aplicación móvil o bien, en varios sitios web, utilice el conmutador de área de trabajo para crear pasos de embudo con datos de otros espacios de trabajo. En **Editor de embudo**, en **Pasos** seleccione de qué área de trabajo deben provenir los datos para el paso de embudo.

## <a name="manage-funnel-reports"></a>Administrar informes de embudo

Puede revisar los informes de embudo para analizar datos, realizar un seguimiento del rendimiento y recopilar información.

> [!NOTE]
> - Los informes de embudo de conclusiones sobre la interacción actualmente admiten escenarios en los que todos los usuarios del embudo son anónimos o todos los usuarios están autenticados. 
> - Los datos históricos en los informes de embudo están disponibles durante los últimos 30 días.

### <a name="view-funnel-reports"></a>Ver informes de embudo

1. Vaya a **Embudos** para abrir la **Biblioteca de embudos**.
1. Seleccione un nombre para abrir el informe.    

### <a name="see-the-data-collected-for-a-report"></a>Ver los datos recopilados para un informe   

Para ver información sobre una fase,

- elija un paso en el informe.

:::image type="content" source="media/funnel-step-data.png" alt-text="datos del embudo.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Cambiar el intervalo de fechas del informe de embudo

1. Vaya a **Embudos** para abrir la **Biblioteca de embudos**.

1. Seleccione un nombre para abrir el informe.

1. Abra el **Intervalo de tiempo** y seleccione un nuevo período de tiempo de la lista o un **Intervalo de fechas fijo** para especificar un rango de fechas.

## <a name="edit-or-delete-funnel-reports"></a>Editar o eliminar informes de embudo

Puede cambiar el nombre de un informe de embudo, eliminarlo o modificar los pasos del informe.

### <a name="rename-or-delete-a-funnel-report"></a>Cambiar el nombre o eliminar un informe de embudo

1. Vaya a **Embudos** para abrir la **Biblioteca de embudos**. 

1. Seleccione **Más** junto al informe que desea cambiar y seleccione **Editar nombre** o **Borrar**.

### <a name="edit-a-funnel-step"></a>Editar un paso de embudo  

1. Vaya a **Embudos** para abrir la **Biblioteca de embudos**. 

1. Seleccione un nombre para abrir el informe.

1. Seleccione el paso que desea editar.

1. Seleccione **Editar**.

1. En el **Editor de embudo**, actualice la información que desea cambiar.  

1. Seleccione **Guardar**.

### <a name="reorder-a-funnel-step"></a>Reordenar un paso de embudo

1. Vaya a **Embudos** para abrir la **Biblioteca de embudos**. 

1. Seleccione un nombre para abrir el informe.

1. Seleccione el paso que desea reordenar.

1. Seleccione **Mover** y, después, **Arriba**, **Abajo**, **A la parte superior** o **A la parte inferior** para mover el paso.

### <a name="delete-a-funnel-step"></a>Eliminar un paso de embudo

1. Vaya a **Embudos** para abrir la **Biblioteca de embudos**. 

1. Seleccione un nombre para abrir el informe.

1. Seleccione el paso que desee eliminar y seleccione **Eliminar**.

## <a name="funnel-insights"></a>Conclusiones del embudo 

Las conclusiones de involucración ahora ofrecen información sobre el embudo para los clientes. Utilice la información del embudo para obtener una visión más profunda del comportamiento del cliente en los pasos del informe del embudo. Cuando crea y guarda un nuevo informe de embudo, las estadísticas del embudo se generan automáticamente para su informe. 

:::image type="content" source="media/funnel-insights.png" alt-text="Conclusiones del embudo.":::

> [!NOTE]
> Las estadísticas del embudo solo se pueden generar para los pasos del embudo que **no** incluir dimensiones personalizadas. Para generar estadísticas de embudo para todos los pasos de su embudo, use las dimensiones de estadísticas de participación listas para usar para crear sus pasos de embudo. 

Puede ver información sobre el embudo de conversión de las siguientes categorías, tanto en el nivel principal como en el de los pasos: 

 - Tasa de conversión
 -    La tasa de conversión entre Checkout y Buy es 22 %.
 - Tiempo de transición 
 -    El tiempo medio de transición entre Cart y Checkout es de 23 minutos. 
 - Tiempo de finalización 
 -    La cantidad media de tiempo que tardan los clientes en completar el embudo es de 47 minutos. 

Utilice esta información para explorar más profundamente el comportamiento del cliente y comprender mejor los puntos de abandono y las conversiones para su informe de embudo. 

Para comparar estadísticas en diferentes pasos, seleccione **Ver desglose de pasos** o **Comparar con otros pasos** de las tarjetas de información. Estos mostrarán un gráfico de barras que compara métricas para cada paso del embudo. 

Las conclusiones del embudo se vuelven a calcular cada 24 horas o al **Guardar** el informe de embudo. 

> [!NOTE]
> Para ver las estadísticas del embudo, debe guardar su informe cada vez que realice cambios. 

