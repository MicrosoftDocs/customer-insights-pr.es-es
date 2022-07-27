---
title: Trabajar con cuentas de negocio
description: Obtenga más información sobre cuentas de negocio como público de destino principal en Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 9bf91671b744198b2f37391edc7abf58eca3c820
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053134"
---
# <a name="work-with-business-accounts"></a>Trabajar con cuentas de negocio

Dynamics 365 Customer Insights le permite configurar su entorno para diferentes públicos de destino principales: consumidores individuales (B2C) y cuentas de negocio (B2B). En escenarios B2C, los datos se centran en personas. Para B2B, los públicos de destino principales son cuentas (organizaciones o empresas) y contactos. Este artículo le ayuda a comenzar con un entorno para cuentas comerciales. Enumera las diferencias para las áreas de funciones en Customer Insights, según el enfoque de su entorno. Para obtener más información sobre las diferencias, revise los documentos de las áreas de funciones. 

## <a name="create-an-environment-for-business-accounts"></a>Crear un entorno para cuentas de negocio

Los administradores pueden [crear un entorno en una organización existente](create-environment.md). Un paso en el proceso de creación de un nuevo entorno solicita a los administradores el público de destino principal del entorno. En caso de que sea la configuración inicial después de comprar una licencia, una experiencia guiada ayuda con la creación del primer entorno.

A continuación puede [ingerir datos](data-sources.md) para cuentas de negocio y contactos relacionados como orígenes de datos de todos los orígenes admitidos.

Después de unificar los datos, [especifique jerarquías de cuentas](relationships.md#set-up-account-hierarchies) como parte de la configuración de la relación. También puede [configurar asignaciones semánticas](semantic-mappings.md) para conectar entidades de contacto y de cuenta. 

## <a name="switch-between-primary-target-audience"></a>Cambiar de público de destino principal

Si su organización mantiene entornos para clientes individuales y cuentas de negocio, puede usar el conmutador en el panel izquierdo para elegir el público de destino principal.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Conmutador para cambiar el público de destino principal entre clientes individuales y cuentas de negocio.":::

## <a name="supported-feature-areas"></a>Áreas de características admitidas

- [Actividades](activities.md): Compatibilidad para cuentas y contactos relacionados para crear actividades y mostrarlas en una escala de tiempo.
- [Relaciones](relationships.md): El asistente de actividad ayuda a crear relaciones entre las entidades para que la vista de cuenta pueda mostrar todas las actividades de los contactos. Los contactos pueden desglosarse para ver la vista de contacto y las jerarquías se pueden usar para agregaciones de actividad de la cuenta.
- [Medidas](measures.md): Admite medidas creadas a partir del generador de medidas con un cálculo. Una configuración opcional permite la acumulación de subcuentas al crear medidas.
- [Segmentos](segments.md): Admite segmentos que se crean desde cero con el generador de segmentos. Los nuevos operadores permiten incorporar jerarquías de cuentas al construir segmentos.
- [Ingestión de datos](data-sources.md): Todas las funciones de esta área son las mismas para cuentas de negocio y clientes individuales.
- [Unificación de datos](data-unification.md): Todas las funciones de esta área son las mismas para cuentas de negocio y clientes individuales.
- [Enriquecimiento](enrichment-hub.md): Algunos tipos de enriquecimiento están disponibles solo para escenarios de clientes individuales, mientras que otros están disponibles exclusivamente para cuentas comerciales.
- [Predicciones y modelos predefinidos](predictions-overview.md): La predicción de abandono de transacciones contiene pasos adicionales para cuentas de negocio. Otras predicciones solo están disponibles para clientes individuales.
- [Activación y exportación](export-destinations.md): Las exportaciones están disponibles para cuentas de negocio y clientes individuales. Algunas exportaciones requieren configuración adicional e información de contacto proyectada en los segmentos subyacentes para que sean válidas para las cuentas de negocio.
- [Configuración del sistema](system.md) y [administración de usuarios](permissions.md): Todas las funciones de esta área son las mismas para cuentas de negocio y clientes individuales.

