---
title: Usar perfiles unificados en Dynamics 365 Marketing
description: Aprenda a integrar perfiles y segmentos unificados con Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833329"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Trabaje con perfiles de clientes unificados en Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) eleva las experiencias de los clientes, lo que le permite organizar recorridos personalizados orquestados en todos los puntos de contacto para fortalecer las relaciones y ganar fidelidad. La aplicación Dynamics 365 Marketing funciona a la perfección con Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams y otros productos, y le permite tomar decisiones mejores y más rápidas, con la potencia de los datos y la IA.

Al conectar los datos de Customer Insights con Marketing, puede:

- Dirigirse a perfiles y segmentos de clientes unificados. Esto le permite interactuar con cada cliente, independientemente de la ubicación de los datos del cliente.
- Basar contenido dinámico (como tokens personalizados) en correos electrónicos, SMS y notificaciones push en medidas como el estado de fidelización, la fecha de renovación de la suscripción, la cuenta primaria o cualquier otra medida que haya capturado en el perfil de Customer Insights unificado.
- Cargar los datos de Marketing en Customer Insights y combinarlos con datos de los clientes de otros orígenes.
- Aplicar limpieza, enriquecimiento y herramientas de coincidencia aproximada de datos de Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Usar perfiles de clientes enriquecidos en marketing en tiempo real

El marketing en tiempo real le permite crear [desencadenadores personalizados](/dynamics365/marketing/real-time-marketing-custom-triggers) que inician recorridos de clientes basados en cualquier acción del cliente. Cuanto más personalizados sean sus datos, más relevantes y personalizados serán sus recorridos. Esto es lo que hace que la combinación de Marketing y Customer Insights sea tan poderosa. Puede [unificar datos](data-unification.md) de cualquier origen y luego usarlos para impulsar recorridos de clientes hiperpersonalizados.

Más información: [Usar perfiles y segmentos de Customer Insights en marketing en tiempo real](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Use segmentos unificados con recorridos de clientes salientes

Customer Insights le permite refinar datos de muchos orígenes y combinarlos en segmentos de clientes agregados. Al [conectar Customer Insights con el marketing saliente](export-dynamics365-marketing.md), estos segmentos aparecerán automáticamente *y* se actualizarán automáticamente en el diseñador de recorridos del cliente.

Más información: [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Extraer datos de su propio Azure Data Lake Storage

No está limitado al almacenamiento en la nube si desea utilizar los datos de Customer Insights con Marketing. Si ya tiene su propio Azure Data Lake Storage configurado, puede conectarse con Customer Insights y luego compartir los datos con la aplicación Marketing tal como lo haría con una configuración basada en la nube.

Más información: [Habilitar el intercambio de datos con Dataverse desde su propio Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
