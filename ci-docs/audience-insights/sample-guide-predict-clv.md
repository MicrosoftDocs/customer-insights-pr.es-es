---
title: Guía de muestra de la predicción del valor de por vida del cliente
description: Utilice esta guía de muestra para probar el modelo de valor de vida útil del cliente predicción.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: c130e5f699f7eb921b69a20bc6d4ba9eab5b2779
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354852"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guía de muestra de la predicción (CLV) del valor de por vida del cliente

Esta guía le explicará un ejemplo de extremo a extremo de la predicción del valor de vida útil del cliente (CLV) en Customer Insights utilizando datos de muestra.

## <a name="scenario"></a>Escenario

Contoso es una empresa que produce café y máquinas de café de alta calidad. Venden los productos a través de su sitio web Contoso Coffee. La empresa quiere comprender el valor (ingresos) que sus clientes pueden generar en los próximos 12 meses. Conocer el valor esperado de sus clientes en los próximos 12 meses les ayudará a dirigir sus esfuerzos de marketing hacia clientes de alto valor.

## <a name="prerequisites"></a>Requisitos previos

- Por lo menos [permisos de colaborador](permissions.md) en información de público.
- Le recomendamos que implemente los siguientes pasos [en un nuevo entorno](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarea 1: ingerir datos

Revise los artículos [acerca de la ingestión de datos](data-sources.md) y la [importación de orígenes de datos usando conectores de Power Query](connect-power-query.md). La siguiente información asume que está familiarizado con la ingesta de datos en general.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir datos de clientes de una plataforma de comercio electrónico

1. Cree un origen de datos llamado **Comercio electrónico**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **CreatedOn**: fecha/hora/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar la fecha de nacimiento a fecha.":::

1. En el campo 'Nombre' del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **eCommerceContacts**

1. **Guarde** el origen de datos.

### <a name="ingest-online-purchase-data"></a>Ingerir datos de compras en línea

1. Agregue otro conjunto de datos al mismo origen de datos **comercio electrónico**. Elija el conector **Texto/CSV** de nuevo.

1. Introduzca la URL para datos de **Compras en línea** https://aka.ms/ciadclassonline.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **PurchasedOn**: fecha/hora
   - **TotalPrice**: moneda

1. En el campo **Nombre** del panel lateral cambie el nombre de su origen de datos de **Consulta** a **eCommercePurchases**.

1. **Guarde** el origen de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir datos de clientes del esquema de fidelización

1. Cree un origen de datos llamado **LoyaltyScheme**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:
   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn**: fecha/hora

1. En el campo **Nombre** del panel de la derecha, cambie el nombre de su origen de datos de **Consulta** a **loyCustomers**.

1. **Guarde** el origen de datos.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir datos de clientes de revisiones del sitio web

1. Cree un origen de datos llamado **Sitio web**, elija la opción de importación y seleccione el conector **Texto/CSV**.

1. Introduzca la URL de los contactos de comercio electrónico https://aka.ms/CI-ILT/WebReviews.

1. Al editar los datos, seleccione **Transformar** y luego seleccione **Usar la primera fila como encabezado**.

1. Actualice el tipo de datos para las columnas que se enumeran a continuación:

   - **ReviewRating**: Número decimal
   - **ReviewDate**: fecha

1. En el campo "Nombre" del panel derecho, cambie el nombre de su origen de datos de **Consulta** a **Reseñas**.

1. **Guarde** el origen de datos.

## <a name="task-2---data-unification"></a>Tarea 2: unificación de datos

Después de ingerir los datos, ahora comenzamos el proceso de unificación de datos para crear un perfil de cliente unificado. Para obtener más información, consulte [Unificación de datos](data-unification.md).

### <a name="map"></a>Asignar

1. Después de ingerir los datos, mapee los contactos de los datos de comercio electrónico y fidelidad con tipos de datos comunes. Vaya a **Datos** > **Unificar** > **Mapa**.

1. Seleccione las entidades que representan el perfil del cliente: **eCommerceContacts** y **loyCustomers**. Después, seleccione **Aplicar**.

   ![unificar las fuentes de datos de comercio electrónico y fidelización.](media/unify-ecommerce-loyalty.png)

1. Seleccione **ContactId** como la clave principal para **eCommerceContacts** y **LoyaltyID** como la clave principal para **loyCustomers**.

   ![Unifique LoyaltyId como clave principal.](media/unify-loyaltyid.png)

1. Seleccione **Guardar**.

### <a name="match"></a>Coincidir

1. Vaya a la pestaña **Coincidir** y seleccione **Establecer orden**.

1. En la lista desplegable **Principal**, seleccione **eCommerceContacts: eCommerce** como el origen principal en incluya todos los registros.

1. En la lista desplegable **Entidad 2**, seleccione **loyCustomers: LoyaltyScheme** e incluya todos los registros.

   ![Unifique la coincidencia de comercio electrónico y fidelización.](media/unify-match-order.png)

1. Seleccione **Agregar regla**

1. Agregue su primera condición con FullName.

   - Para eCommerceContacts, seleccione **FullName** en el menú desplegable.
   - Para loyCustomers, seleccione **FullName** en el menú desplegable.
   - Seleccione el menú desplegable **Normalizar** y elija **Tipo (teléfono, nombre, dirección, ...)**.
   - Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.

1. Introduzca el nombre **FullName, Email** para la nueva regla.

   - Agregar una segunda condición para la dirección de correo electrónico seleccionando **Agregar condición**
   - Para la entidad eCommerceContacts, elija **Correo electrónico** en el menú desplegable.
   - Para la entidad loyCustomers, elija **Correo electrónico** en el menú desplegable.
   - Deje Normalizar en blanco.
   - Conjunto **Nivel de precisión**: **Básico**, y **Valor**: **Alto**.

   ![Unifique la regla de coincidencia para el nombre y el correo electrónico.](media/unify-match-rule.png)

1. Seleccione **Listo**.

1. Seleccione **Guardar** y **Ejecutar**.

### <a name="merge"></a>Combinar

1. Vaya a la pestaña **Fusionar**.

1. En **ContactId** de la entidad **loyCustomers**, cambie el nombre para mostrar a **ContactIdLOYALTY** para diferenciarlo de los otros id. ingeridos.

   ![cambie el nombre de contactid a partir del id. de fidelidad.](media/unify-merge-contactid.png)

1. Seleccione **Guardar** y **Ejecutar fusión y procesos subsiguientes**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tarea 3: configurar el valor de vida útil del cliente predicción

Con los perfiles de cliente unificados en su lugar, ahora podemos ejecutar el valor de vida útil del cliente predicción. Para conocer los pasos detallados, vea [Predicción del valor de vida del cliente](predict-customer-lifetime-value.md).

1. Vaya a **Inteligencia**  > **Predicciones** y seleccione el **Modelo de valor de vida útil**.

1. Revise la información en el panel lateral y seleccione **Comenzar**.

1. Nombre el modelo **OOB eCommerce CLV predicción** y la entidad de salida **OOBeCommerceCLVPrediction**.

1. Defina las preferencias del modelo para el modelo CLV:
   - **Predicción período de tiempo**: **12 meses o 1 año**. Esta configuración define qué tan lejos en el futuro se predecirá el valor de vida útil del cliente.
   - **Clientes activos**: especifique qué significan los clientes activos para su empresa. Establezca el período de tiempo histórico en el que un cliente debe haber tenido al menos una transacción para ser considerado activo. El modelo solo predecirá CLV para clientes activos. Elija entre dejar que el modelo calcule el período de tiempo en función de los datos históricos de transacciones o proporcionar un período de tiempo específico. En esta guía de muestra, **deje que el modelo calcule el intervalo de compra**, que es la opción predeterminada.
   - **Clientes de alto valor**: defina los clientes de alto valor como un percentil de los clientes que más pagan. El modelo utiliza esta entrada para proporcionar resultados que se ajustan a la definición de su negocio de clientes de alto valor. Puede elegir permitir que el modelo defina qué clientes son de alto valor. Utiliza una regla heurística que deriva el percentil. También puede definir clientes de alto valor como un percentil de los clientes futuros que más pagan. En esta guía de muestra, definimos manualmente a los clientes de alto valor como **30% superior de los clientes activos que pagan** y seleccione **Próximo**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Paso de preferencias en la experiencia guiada para el modelo CLV.":::

1. En el paso **Datos necesarios**, seleccione **Agregar datos** para proporcionar los datos del historial de transacciones.

1. Añada la entidad **eCommercePurchases: eCommerce** y asigne los atributos que requiere el modelo:
   - ID de transacción: eCommerce.eCommercePurchases.PurchaseId
   - Fecha de transacción: eCommerce.eCommercePurchases.PurchasedOn
   - Importe de la transacción: eCommerce.eCommercePurchases.TotalPrice
   - Id. del producto: eCommerce.eCommercePurchases.ProductId

1. Seleccione **Siguiente**.

1. Establezca la relación entre la entidad **eCommercePurchases: eCommerce** y **eCommerceContacts: eCommerce**.

1. El paso **Datos adicionales (opcional)** le permite agregar más datos de actividad del cliente. Estos datos pueden ayudar a obtener más información sobre las interacciones de los clientes con su empresa, lo que puede contribuir al CLV. Agregue interacciones clave con el cliente, como registros web, registros servicio al cliente o el historial del programa de recompensas, puede mejorar la precisión de las predicciones. Seleccione **Agregar datos** para incluir más datos de actividad del cliente.

1. Agregue la entidad de actividad del cliente y asigne los nombres de sus campos a los campos correspondientes requeridos por el modelo:
   - Entidad de actividad del cliente: Reviews:Website
   - Clave principal: Website.Reviews.ReviewId
   - Marca de tiempo: Website.Reviews.ReviewDate
   - Evento (nombre de la actividad): Website.Reviews.ActivityTypeDisplay
   - Detalles (cantidad o valor): Website.Reviews.ReviewRating

1. Seleccione **Siguiente** y configure la actividad y la relación entre los datos de la transacción y los datos del cliente:  
   - Tipo de actividad: elegir existente
   - Etiqueta de actividad: Review
   - Etiqueta correspondiente: Website.Reviews.UserId
   - Entidad del cliente: : eCommerceContacts:eCommerce
   - Relación: WebsiteReviews

1. Seleccione **Siguiente** para establecer la programación del modelo.

   El modelo debe entrenarse con regularidad para aprender nuevos patrones cuando se introducen nuevos datos. Para este ejemplo, elija **Mensual**.

1. Después de revisar todos los detalles, seleccione **Guardar y ejecutar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarea 4: revisar los resultados y las explicaciones del modelo

Deje que el modelo complete el entrenamiento y la puntuación de los datos. A continuación, puede revisar los resultados y las explicaciones del modelo CLV. Para más información, consulte [Revisar un estado de predicción y los resultados](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tarea 5: crear un segmento de clientes de alto valor

La ejecución del modelo crea una nueva entidad, que se enumera en **Datos** > **Entidades**. Puede crear un nuevo segmento de clientes basado en la entidad creada por el modelo.

1. Vaya a **Segmentos**. 

1. Seleccione **Nuevo** y elija **Crear desde** > **Inteligencia**.

   ![Creación de un segmento con la salida del modelo.](media/segment-intelligence.png)

1. Seleccione la entidad **OOBeCommerceCLVPrediction** y defina el segmento:
  - Campo: CLVScore
  - Operador: mayor que
  - Valor: 1500

1. Seleccione **Revisar** y **Guardar** el segmento.

Ahora tiene un segmento que identifica a los clientes que se prevé que generarán más de 1500 $ de ingresos en los próximos 12 meses. Este segmento se actualiza dinámicamente si se ingieren más datos.

Para obtener más información, vea [Crear y administrar segmentos](segments.md).
