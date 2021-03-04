---
title: Página de inicio en informaciones de público
description: Comience a explorar la aplicación en la página Inicio.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477062"
---
# <a name="create-a-new-environment"></a>Crear un nuevo entorno

## <a name="create-a-trial-environment"></a>Crear un entorno de prueba

Puede registrarse para una prueba en la [página de suscripción de prueba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Las pruebas caducan después de 30 días.

1. Elija la opción **Suscribirse para una prueba gratis** y seleccione **Registrarse ahora**.

1. Proporcione la dirección de correo electrónico de su trabajo o escuela, cuéntenos más sobre usted y seleccione **Siguiente**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Cuadro de diálogo para registrarse para obtener una instancia de prueba:":::

1. Introduzca un **Nombre** para el nuevo entorno. 

1. Seleccione el tipo de prueba.

1. Elija la **Región** para su entorno.

1. Opcionalmente, para administradores de una organización de Dynamics 365: seleccione **Configuración avanzada** y proporcione la URL de su organización para usar características de predicción como el abandono de clientes.

1. Seleccione **Crear**. 

Una vez creado el entorno, verá el entorno **Demo**, que le permite explorar la aplicación con datos ficticios. Puede cambiar los datos de ejemplo para que coincidan con su industria. Seleccione el icono **Configuración** en el encabezado y seleccione **Configuración de demostración**. Además, puede cambiar el tema visual. 

[Cambie al entorno](#switch-environments) que creó durante el proceso de registro para trabajar con sus propios datos.

## <a name="create-a-new-production-or-sandbox-environment"></a>Cree un nuevo entorno de producción o de espacio aislado

En su entorno, seleccione el selector **Entornos** en el encabezado de la aplicación y seleccione **Nuevo**.

Siga los pasos como si [creara un entorno de prueba](#create-a-trial-environment). De forma predeterminada, los datos se almacenan en el data lake administrado por Customer Insights. Obtenga una opción adicional al seleccionar **Configuración avanzada** para almacenar sus datos en su propio Azure Data Lake. Proporcione su nombre de cuenta y clave de cuenta para establecer una conexión con su Azure Data Lake. 

> [!IMPORTANT]
> Al guardar datos en su Azure Data Lake Storage, acepta que los datos se transferirán a la ubicación geográfica adecuada y se almacenarán en ella para esa cuenta de Azure Storage, que puede ser distinta del lugar en el que se almacenan los datos en Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar la página principal

Puede [acceder a las informaciones de público de Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) en la siguiente URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
La página **Inicio** muestra una descripción general de los segmentos, las medidas y los datos de enriquecimiento (si están configurados) después de completar las etapas de [asignación](map-entities.md), [correspondencia](match-entities.md) y [combinación](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Información en página principal](media/home-page-insights.png "Información en página principal")

En **Segmentos recientes** verá grupos de clientes según los atributos demográficos, de comportamiento o transaccionales que haya definido. La [creación de segmentos](segments.md) le ayuda a agrupar su base de clientes y orientar mejor sus actividades comerciales.

Las **Medidas recientes** muestran iconos con [indicadores clave de rendimiento (KPI)](measures.md) que ha definido. Por ejemplo, la probabilidad promedio de que un cliente abandone o el gasto promedio en línea por cliente.

La sección **Enriquecimientos recientes** enumera los resultados de las ejecuciones de enriquecimiento que se completaron recientemente. Los [enriquecimientos](enrichment-hub.md) agregan información sobre su base de clientes. Por ejemplo, comprendiendo los intereses y las marcas por las que tienen afinidad.

## <a name="switch-environments"></a>Cambiar entornos

Seleccione el control **Entorno** en la esquina superior derecha de la página para cambiar entornos.

> [!div class="mx-imgBorder"] 
> ![Cambiar entorno](media/home-page-environment-switcher.png "Cambiar entorno")

Los administradores pueden crear y administrar [entornos múltiples](manage-environments.md). Mantener más de un entorno puede ser útil si, por ejemplo, su organización opera internacionalmente y necesita segregar datos e información de diferentes maneras.

## <a name="next-step"></a>Paso siguiente

Para ver sus propias ideas en la página de inicio, primero deberá [agregar orígenes de datos](data-sources.md) y [unificar](data-unification.md) sus datos para crear perfiles de clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]