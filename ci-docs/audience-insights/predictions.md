---
title: Completar datos parciales usando predicciones
description: Utilice predicciones para completar datos incompletos del cliente.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3100acf383d85c00a6ff0a8ebc54e038bd813427
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732453"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Complete sus datos parciales con predicciones (obsoleto)

> [!IMPORTANT]
> Esta característica estará **obsoleta** a partir del **5 de noviembre de 2021**. Las implementaciones actuales seguirán funcionando hasta que se elimine la función, pero no podrá crear nuevas integraciones con las instrucciones a continuación.

Las predicciones le permiten crear fácilmente valores de predicción que pueden mejorar su comprensión de un cliente. En la página **Inteligencia** > **Predicciones**, puede seleccionar **Mis predicciones** para ver las predicciones que ha configurado en otras partes de las informaciones de público y poder personalizarlas aún más.

> [!NOTE]
> No puede usar esta característica si su entorno usa almacenamiento de Azure Data Lake Gen 2.
>
> La característica de predicciones utiliza medios automatizados para evaluar datos y realizar predicciones basadas en esos datos, y por lo tanto, tiene capacidad de ser utilizada como método de generación de perfiles, de acuerdo con la definición de ese término en el Reglamento General de Protección de Datos ("RGPD"). El uso de esta función por parte del cliente para procesar datos puede estar sujeto al RGPD u otras leyes o regulaciones. Usted es responsable de garantizar que el uso de Dynamics 365 Customer Insights, incluidas las predicciones, cumple con todas las leyes y regulaciones aplicables, incluidas las leyes relacionadas con la privacidad, los datos personales, los datos biométricos, la protección de datos y la confidencialidad de las comunicaciones.

## <a name="prerequisites"></a>Requisitos previos

Antes de que su organización pueda usar la característica de predicciones, se deben cumplir los siguientes requisitos previos:

1. Su organización tiene una instancia [configurada en Microsoft Dataverse](/ai-builder/build-model#prerequisites) y está en la misma organización que Customer Insights.

2. Su entorno de conclusiones del público está conectado a su instancia de Dataverse.

Para obtener más información, consulte [Crear un nuevo entorno](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Crear una predicción en la entidad de cliente

1. En las informaciones de público, vaya a **Datos** > **Entidades**.

2. Seleccione la entidad **Cliente**.

3. En la entidad **Customer: CustomerInsights**, seleccione la pestaña **Campos**.

4. Busque el nombre del atributo para el que desea predecir valores y, a continuación, seleccione el icono **Información general** en la columna **Resumen**.
   > [!div class="mx-imgBorder"]
   > ![Icono de visión general.](media/intelligence-overviewicon.png "Icono de visión general")

5. Si hay una alta tasa de valores que faltan para el atributo, seleccione **Predecir valores que faltan** para continuar con la predicción.
   > [!div class="mx-imgBorder"]
   > ![Estado de resumen con el botón predecir valores que faltan.](media/intelligence-overviewpredictmissingvalues.png "Estado de resumen con el botón predecir valores que faltan")

6. Proporcione un **Nombre para mostrar** y un **Nombre de entidad de salida** para los resultados de la predicción.

7. Una lista de opciones rellenada previamente mostrará dónde puede asignar los valores a una categoría de predicción. En este caso, las únicas opciones de categoría serán 0 o 1, ya que se asignan a la naturaleza verdadera/falsa o binaria de la predicción. En la columna Categoría, asigne los valores de campo que desea clasificar como "0" en la predicción final a "0" y los elementos que desea clasificar como "1" en la predicción final a "1".
   > [!div class="mx-imgBorder"]
   > ![Ejemplo que muestra valores de campo asignados a categorías.](media/intelligence-categorymapping.png "Ejemplo que muestra valores de campo asignados a categorías")

8. Seleccione **Listo** y se procesará la predicción. El procesamiento llevará algún tiempo, dependiendo del tamaño y la complejidad de los datos. Los resultados estarán disponibles en una nueva entidad basada en el **Nombre de entidad de salida** de la predicción que ha creado.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Crear una predicción al crear un segmento

Predecir los valores que faltan para un atributo elegido específico también es posible al crear un segmento. En concreto, cuando crea rápidamente un segmento basado en la entidad de cliente unificada o en la entidad Customer_Measure.

Como parte de este flujo, elegirá un atributo específico en el que basar el segmento, como Satisfacción del cliente o Importe de la compra. Al crear el segmento, el sistema sugerirá un método para predecir los valores que faltan para este atributo.

1. En las informaciones de público, vaya a **Segmentos** y seleccione el mosaico **Perfiles**.

2. Elija un **Campo** para crear un segmento y seleccione un **Operador** y, a continuación, seleccione **Revisar**.

3. Proporcione un **Nombre** y un **Nombre para mostrar** para el segmento.

4. Seleccione **Guardar**.

5. Si el segmento que ha creado tiene datos incompletos en el campo de origen, puede elegir predecir los valores que faltan.
   > [!div class="mx-imgBorder"]
   > ![Botón Predicción.](media/segments-predictoption.png "Botón Predicción")

6. Proporcione un **Nombre para mostrar** y un **Nombre de entidad de salida** para los resultados de la predicción.

7. Seleccione **Listo**. La predicción se generará en breve en una nueva entidad con el nombre que proporcionó para el **Nombre de entidad de salida**.

## <a name="view-a-prediction"></a>Ver una predicción

1. En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.

2. Seleccione la predicción que desea revisar.

3. Seleccione los puntos suspensivos en la columna **Acciones** y elija **Ver**.

4. Verá una serie de puntos de datos en la vista de la predicción.
   > [!div class="mx-imgBorder"]
   > ![Página de predicciones.](media/intelligence-predictionsviewpage.png "Página de predicciones")

   - **Valores de predicción** muestra la asignación que creó durante la fase de asignación de valor de campo a categoría. Estos son los valores del conjunto de datos que se han asignado a una categoría específica.
   -**Principales influencias** son los factores del conjunto de datos que probablemente influyeron en la confianza de la predicción de que el valor de campo se asignara a una categoría específica.
   - **Rendimiento** indica el acierto de las predicciones. Seleccione el vínculo para obtener más información.
   - **Vista previa** muestra ejemplos del conjunto de datos de salida desde la predicción y la probabilidad, o nuestra confianza, del valor de predicción, donde 0 es incierto, y 1 es cierto.

## <a name="update-a-prediction"></a>Actualizar una predicción

1. En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.

2. Seleccione la predicción que desea actualizar y seleccione el icono **Actualizar**.

3. La predicción se programará para su procesamiento. Puede ver la hora en que se actualizó por última vez en la columna **Actualizado** de la página **Predicciones**.

## <a name="edit-a-prediction"></a>Editar una predicción

Después de crear una predicción, puede personalizar el modelo en el AI Builder para aumentar la eficacia del modelo.  

1. En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.

2. Seleccione la predicción que desea editar.

3. Seleccione los puntos suspensivos en la columna **Acciones** y elija **Ver**.

4. Seleccione **Personalizar en AI Builder**.

5. Actualice el modelo en AI Builder. [Obtener más información sobre cómo administrar modelos en AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

La siguiente ejecución de la predicción usará el modelo actualizado que ha creado.

> [!NOTE]
> Los nuevos modelos creados en AI Builder no se mostrarán en las informaciones de público a menos que el modelo se haya creado a partir de las experiencias enumeradas anteriormente.

## <a name="remove-a-prediction"></a>Quitar una predicción

1. En las informaciones de público, vaya a **Inteligencia** > **Predicciones** > **Mis predicciones**.

2. Seleccione la predicción que desee eliminar.

3. Seleccione los puntos suspensivos en la columna **Acciones** y elija **Eliminar**.

4. Confirme la eliminación.

## <a name="troubleshooting"></a>Solución de problemas

Si no puede completar el proceso de Dataverse de conexión debido a un error, puede intentar completar el proceso manualmente. Hay dos problemas conocidos que pueden producirse en el proceso de conexión:

- La solución de complemento de tarjeta de cliente no está instalada.
    1. Complete las instrucciones para [instalar y configurar la solución](customer-card-add-in.md).

- No se otorgan permisos de aplicaciones.
    1. Vaya a [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Seleccione **Entornos**.
    1. Seleccione los puntos suspensivos junto al entorno al que desea agregar el permiso y seleccione **Configuración**.
    1. Expanda **Usuarios + permisos** y seleccione **Usuarios**.
    1. Seleccione sucesivamente **+ Nuevo** y **Usuario**.
    1. Seleccione **Usuario de la aplicación** si aún no está seleccionado e introduzca la siguiente información:
        - **Nombre de usuario:** cihelp@microsoft.com
        - **Id. de aplicación:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nombre de pila:** Cliente
        - **Apellidos:** Insights
        - **Correo electrónico principal:** cihelp@microsoft.com
    1. Seleccione **Guardar y cerrar**.
    1. Seleccione el usuario que acaba de crear.
    1. Seleccione **Administrar roles** en la barra de menús superior.
    1. Seleccione **Administrador del sistema** y luego seleccione **Aceptar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
