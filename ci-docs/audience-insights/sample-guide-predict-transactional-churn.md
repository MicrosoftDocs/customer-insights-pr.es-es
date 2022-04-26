---
title: Guía de ejemplo de predicción de abandono de transacción
description: Utilice esta guía de ejemplo para probar el modelo de predicción de cancelación de transacción de uso inmediato.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d3465b7eaa17a24e2926b8ea432b33e705931b88
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555380"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guía de ejemplo de predicción de abandono de transacción

Esta guía le llevará por un ejemplo completo de predicción de cancelación de transacción en Customer Insights, utilizando los datos de ejemplo que se proporcionan a continuación. Todos los datos utilizados en esta guía no son datos reales de clientes y forman parte del conjunto de datos Contoso que se encuentra en el entorno *Demostración* de su suscripción a Customer Insights.

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad, que venden a través de su sitio web Contoso Coffee. Su objetivo es saber qué clientes que normalmente compran sus productos de forma regular, dejarán de ser clientes activos en los próximos 60 días. Saber cuál de sus clientes es **probable que cancele**, puede ayudarle a ahorrar esfuerzos de marketing, centrándose en mantenerlos.

## <a name="prerequisites"></a>Requisitos previos

- Al menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Le recomendamos que implemente los siguientes pasos [en un nuevo entorno](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarea 1: ingerir datos

Revise los artículos [acerca de la ingestión de datos](data-sources.md) y la [importación de orígenes de datos usando conectores de Power Query](connect-power-query.md) específicamente. La siguiente información asume que está familiarizado con la ingesta de datos en general. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir datos de clientes de una plataforma de comercio electrónico

1. Cree un origen de datos llamado **Comercio electrónico**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **DateOfBirth**: fecha
   - **CreatedOn**: fecha/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar DoB en Fecha.":::

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**

1. Guarde el origen de datos.

### <a name="ingest-online-purchase-data"></a>Ingerir datos de compras en línea

1. Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**. Elija el conector **Texto/CSV** de nuevo.

1. Introduzca la URL para datos de **Compras en línea** https://aka.ms/ciadclassonline.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **PurchasedOn**: fecha/hora
   - **TotalPrice**: moneda
   
1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommercePurchases**.

1. Guarde el origen de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.

1. Guarde el origen de datos.


## <a name="task-2---data-unification"></a>Tarea 2: unificación de datos

Después de ingerir los datos, ahora comenzamos el proceso **Asignar, Coincidir, Fusionar** para crear un perfil de cliente unificado. Para obtener más información, consulte [Unificación de datos](data-unification.md).

### <a name="map"></a>Asignar

1. Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes. Vaya a **Datos** > **Unificar** > **Mapa**.

1. Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar las fuentes de datos de comercio electrónico y fidelización.":::

1. Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifique LoyaltyId como clave principal.":::

### <a name="match"></a>Coincidir

1. Vaya a la pestaña **Coincidir** y seleccione **Establecer orden**.

1. En la lista desplegable **Principal**, seleccione **eCommerceContacts: eCommerce** como el origen principal en incluya todos los registros.

1. En la lista desplegable **Entidad 2**, seleccione **loyCustomers: LoyaltyScheme** e incluya todos los registros.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifique la coincidencia de comercio electrónico y fidelización.":::

1. Seleccione **Crear nueva regla**

1. Agregue su primera condición con FullName.

   * Para eCommerceContacts, seleccione **FullName** en el menú desplegable.
   * Para loyCustomers, seleccione **FullName** en el menú desplegable.
   * Seleccione el desplegable **Normalizar** y elija **Tipo (teléfono, nombre, dirección...)**.
   * Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.

1. Introduzca el nombre **FullName, Email** para la nueva regla.

   * Agregar una segunda condición para la dirección de correo electrónico seleccionando **Agregar condición**
   * Para la entidad eCommerceContacts, elija **Correo electrónico** en el menú desplegable.
   * Para la entidad loyCustomers, elija **Correo electrónico** en el menú desplegable. 
   * Deje Normalizar en blanco. 
   * Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifique la regla de coincidencia para el nombre y el correo electrónico.":::

7. Seleccione **Guardar** y **Ejecutar**.

### <a name="merge"></a>Fusionar mediante combinación

1. Vaya a la pestaña **Fusionar**.

1. En **ContactId** de la entidad **loyCustomers**, cambie el nombre para mostrar a **ContactIdLOYALTY** para diferenciarlo de los otros id. ingeridos.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="cambie el nombre de contactid a partir del id. de fidelidad.":::

1. Seleccione **Guardar** y **Ejecutar** para iniciar el proceso de fusión.



## <a name="task-3---configure-transaction-churn-prediction"></a>Tarea 3: configurar la predicción de abandono de transacciones

Con los perfiles de clientes unificados en su lugar, ahora podemos ejecutar la predicción de cancelación de suscripción. Para conocer los pasos detallados, consulte el artículo [Predicción de abandono de suscripciones](predict-subscription-churn.md). 

1. Vaya a **Inteligencia** > **Descubrir** y seleccione usar el **Modelo de abandono de clientes**.

1. Seleccione la opción **Transactional** y elija **Comenzar**.

1. Nombre el modelo como **Predicción de cancelación de transacción de comercio electrónico OOB** y la entidad de salida como **OOBeCommerceChurnPrediction**.

1. Defina dos condiciones para el modelo de abandono:

   * **Ventana de predicción**: **al menos 60** dias. Esta configuración define en qué medida en el futuro queremos predecir el abandono de clientes.

   * **Definición de abandono**: **al menos 60** días. La duración sin compra después de la cual un cliente se considera abandonado.

     :::image type="content" source="media/model-levers.PNG" alt-text="Seleccione las palancas de modelo Ventana de predicción y Definición de abandono.":::

1. Seleccione **Historial de compras (obligatorio)** y seleccione **Agregar datos** para el historial de compras.

1. Añada la entidad **eCommercePurchases : eCommerce** y asigne los campos de comercio electrónico a los campos correspondientes requeridos por el modelo.

1. Únase a la entidad **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Únase a entidades de comercio electrónico.":::

1. Seleccione **Siguiente** para establecer la programación del modelo.

   El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se ingieren nuevos datos. En este ejemplo, seleccione **Mensualmente**.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarea 4: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. Ahora puede revisar las explicaciones del modelo de cancelación de suscripción. Para más información, consulte [Revisar un estado de predicción y los resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarea 5: crear un segmento de clientes con alto riesgo de abandono

La ejecución del modelo de producción crea una nueva entidad que puede ver en **Datos** > **Entidades**.   

Puede crear un nuevo segmento basado en la entidad creada por el modelo.

1.  Vaya a **Segmentos**. Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación de un segmento con la salida del modelo.":::

1. Seleccione el punto de conexión **OOBSubscriptionChurnPrediction** y defina el segmento: 
   - Campo: ChurnScore
   - Operador: mayor que
   - Valor: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configure el segmento de cancelación de suscripción.":::

Ahora tiene un segmento que se actualiza dinámicamente y que identifica a los clientes con alto riesgo de abandono para este negocio de suscripción.

Para obtener más información, vea [Crear y administrar segmentos](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
