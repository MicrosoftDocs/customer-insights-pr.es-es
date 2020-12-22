---
title: Página de inicio en informaciones de público
description: Comience a explorar la aplicación en la página Inicio.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407034"
---
# <a name="create-a-new-environment"></a>Crear un nuevo entorno

## <a name="create-a-trial-environment"></a>Crear un entorno de prueba

Puede registrarse para una prueba en la [página de suscripción de prueba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Las pruebas caducan después de 30 días.

1. Elija la opción **Suscribirse para una prueba gratis** y seleccione **Registrarse ahora**.

1. Proporcione la dirección de correo electrónico de su trabajo o escuela, cuéntenos más sobre usted y seleccione **Siguiente**.

1. Introduzca un **Nombre** para el nuevo entorno. 

1. Seleccione el tipo de prueba.

1. Elija la **Región** para su entorno.

1. Opcionalmente, para administradores de una organización de Dynamics 365: seleccione **Configuración avanzada** y proporcione la URL de su organización para usar características de predicción como el abandono de clientes.

1. Seleccione **Crear**. 

Una vez creado el entorno, verá el entorno **Demo**, que le permite explorar la aplicación con datos ficticios. Puede cambiar los datos de ejemplo para que coincidan con su industria. Seleccione el icono **Configuración** en el encabezado y seleccione **Configuración de demostración**. Además, puede cambiar el tema visual. 

[Cambie al entorno](#change-between-environments) que creó durante el proceso de registro para trabajar con sus propios datos.

## <a name="create-a-new-production-or-sandbox-environment"></a>Cree un nuevo entorno de producción o de espacio aislado

En su entorno, seleccione el icono **Configuración** en el encabezado y seleccione **Nuevo entorno**.

Siga los pasos como si [creara un entorno de prueba](#create-a-trial-environment). Obtenga una opción adicional al seleccionar **Configuración avanzada** para almacenar sus datos en su propio Azure Data Lake. Proporcione su nombre de cuenta y clave de cuenta para establecer una conexión con su Azure Data Lake. De forma predeterminada, los datos se almacenan en el data lake administrado por Customer Insights.

> [!IMPORTANT]
> Al guardar datos en su Azure Data Lake Storage, acepta que los datos se transferirán a la ubicación geográfica adecuada y se almacenarán en ella para esa cuenta de Azure Storage, que puede ser distinta del lugar en el que se almacenan los datos en Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar la página principal

Usted puede [acceder a su entorno de Customer Insights](https://home.ci.ai.dynamics.com/) en la siguiente URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Esta página **Inicio** muestra una descripción general de su base de clientes y métricas clave para realizar un seguimiento del estado de su negocio.

> [!div class="mx-imgBorder"] 
> ![Información en página principal](media/home-page-insights.png "Información en página principal")

En **Segmentos recientes** verá grupos de clientes según los atributos demográficos, de comportamiento o transaccionales que haya definido. [Crear segmentos](segments.md) le ayuda a orientar mejor sus actividades comerciales.

**Medidas recientes** muestra ventanas con [medidas](measures.md). Las medidas son indicadores clave de rendimiento (KPI) que ha definido. Por ejemplo, la probabilidad media de pérdida de clientes o el gasto medio online por cliente.

La sección **Enriquecimientos recientes** enumera los resultados de las ejecuciones de enriquecimiento que se completaron recientemente. Los enriquecimientos agregan información sobre su base de clientes. Por ejemplo, comprendiendo los intereses y las marcas por las que tienen afinidad. Esta información se puede desbloquear usando las funciones de [enriquecimiento](enrichment-microsoft-graph.md) después de completar las fases [mapa](map-entities.md), [coincidencia](match-entities.md) y [combinación](merge-entities.md).

## <a name="change-between-environments"></a>Cambiar entre entornos

Una vez que haya instalado y configurado [orígenes de datos](data-sources.md), le convendrá cambiar de un entorno de demostración a un entorno en vivo. El uso del entorno de producción le permite trabajar con sus propios datos de clientes. Seleccione el control **Entorno** en la esquina superior derecha de la página para cambiar entornos.

> [!div class="mx-imgBorder"] 
> ![Cambiar entorno](media/home-page-environment-switcher.png "Cambiar entorno")

Los administradores pueden crear y administrar [entornos múltiples](manage-environments.md). Mantener más de un entorno puede ser útil si, por ejemplo, su organización opera internacionalmente y necesita segregar datos e información de diferentes maneras.

## <a name="next-step"></a>Paso siguiente

Para ver sus propias ideas en la página de inicio, primero deberá [agregar orígenes de datos](data-sources.md) y [unificar](data-unification.md) sus datos para crear perfiles de clientes.
