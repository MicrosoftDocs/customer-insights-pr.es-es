---
title: Visión general del enriquecimiento de datos (vista previa)
description: Utilice las capacidades de Microsoft y otros servicios de terceros para enriquecer los datos de sus clientes.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304540"
---
# <a name="data-enrichment-preview-overview"></a>Visión general del enriquecimiento de datos (vista previa)

Utilice datos de orígenes como Microsoft y otros socios para enriquecer los datos de clientes. Los enriquecimientos de terceros se configuran mediante [conexiones](connections.md), que un administrador configura con credenciales y proporciona consentimiento para transferencias de datos. Los administradores y los colaboradores pueden usar las conexiones para configurar enriquecimientos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Múltiples enriquecimientos del mismo tipo

La entidad que se va a enriquecer se especifica durante la configuración del enriquecimiento, lo que le permite enriquecer solo un subconjunto de sus perfiles. Por ejemplo, enriquezca los datos solo para un segmento específico. Puede configurar varios enriquecimientos del mismo tipo y reutilizar la misma conexión. Algunos enriquecimientos tendrán límites en el número de enriquecimientos del mismo tipo que se pueden crear. Los límites y el uso actual se pueden ver en cada mosaico en la pestaña **Descubrir** ficha de la página **Enriquecimiento**.

## <a name="enrich-data-sources-before-unification"></a>Enriquecer los orígenes de datos antes de la unificación

Puede enriquecer los datos de sus clientes antes de la unificación de datos para ayudar a aumentar la calidad de una coincidencia de datos. Para obtener más información, consulte [Enriquecer orígenes de datos](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Crear un enriquecimiento

Debe tener [permisos](permissions.md) de Colaborador o Administrador para crear o editar enriquecimientos.

Vaya a **Datos** > **Enriquecimiento**. La pestaña **Descubrir** muestra todas las opciones de enriquecimiento admitidas.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página del centro de enriquecimiento.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuales (B2C)](#tab/b2c)

- [Identidad AbiliTec](enrichment-liveramp.md) proporcionada por LiveRamp AbiliTec
- [Marcas](enrichment-microsoft.md) proporcionadas por Microsoft
- [Datos demográficos](enrichment-experian.md) proporcionados por Experian
- [Direcciones mejoradas](enrichment-enhanced-addresses.md) proporcionadas por Microsoft
- [Intereses](enrichment-microsoft.md) proporcionados por Microsoft
- [Datos de ubicación](enrichment-azure-maps.md) proporcionados por Microsoft Azure Maps
- [Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies
- [Datos personalizados SFTP](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)

# <a name="business-accounts-b-to-b"></a>[Cuentas empresariales (B2B)](#tab/b2b)

- [Datos de participación de la cuenta](enrichment-office.md) proporcionados por Microsoft
- [Datos de la empresa](enrichment-dnb.md) proporcionados por Dun & Bradstreet
- [Datos de empresa](enrichment-leadspace.md) proporcionados por Leadspace
- [Direcciones mejoradas](enrichment-enhanced-addresses.md) proporcionadas por Microsoft
- [Datos de la empresa mejorados](enrichment-enhanced-company-data.md) proporcionado por Microsoft
- [Datos de ubicación](enrichment-azure-maps.md) proporcionados por Microsoft Azure Maps
- [Datos de ubicación](enrichment-here.md) proporcionados por HERE Technologies
- [Datos personalizados SFTP](enrichment-SFTP-custom-import.md) a través del protocolo seguro de transferencia de archivos (SFTP)

---

## <a name="manage-existing-enrichments"></a>Administrar enriquecimientos existentes

Vaya a **Datos** > **Enriquecimiento**. En la pestaña **Mis enriquecimientos** vea los enriquecimientos configurados, su estado, el número de clientes enriquecidos y la última vez que se actualizaron los datos. Puede ordenar la lista de enriquecimientos por cualquier columna o usar el cuadro de búsqueda para encontrar el enriquecimiento que desea administrar.

Seleccione el enriquecimiento para ver las acciones disponibles.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opciones para administrar enriquecimientos en la lista de enriquecimientos.":::

- **Vea** los detalles de enriquecimiento con el número de perfiles de clientes enriquecidos.
- **Edite** la configuración de enriquecimiento.
- [**Ejecutar**](#run-or-refresh-enrichments) el enriquecimiento para actualizar los perfiles de los clientes con los datos más recientes. Ejecute o desactive varios enriquecimientos a la vez seleccionándolos en la lista.
- **Activar** o **Desactivar** un enriquecimiento. Los enriquecimientos inactivos no se actualizarán durante una [actualización programada](schedule-refresh.md).
- **Eliminar** el enriquecimiento.

También puede crear [segmentos](segments.md) o [medidas](measures.md) de enriquecimientos.

## <a name="run-or-refresh-enrichments"></a>Ejecutar o actualizar enriquecimientos

Una vez que se ejecutan, los enriquecimientos se pueden actualizar en un programa automático o actualizarse manualmente a pedido.

1. Para actualizar manualmente uno o más enriquecimientos, selecciónelos y elija **Ejecutar**. A [programar una actualización automática](schedule-refresh.md), vaya a **Administración** > **Sistema** > **Programar**. El tiempo de procesamiento depende del tamaño de los datos de sus clientes.

1. Opcionalmente, [vea el progreso del proceso de enriquecimiento](#see-the-progress-of-the-enrichment-process).

1. Una vez finalizado el proceso de enriquecimiento, vaya a **Mis enriquecimientos** para revisar los datos de perfiles de clientes recientemente enriquecidos, la hora de la última actualización y la cantidad de perfiles enriquecidos.

1. Seleccione el enriquecimiento para ver [resultados de enriquecimiento](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Ver el progreso del proceso de enriquecimiento

Puede encontrar detalles sobre el procesamiento de un enriquecimiento, incluido su estado y posibles problemas mientras se actualiza o después de que se completa una actualización. Comprenda qué procesos están involucrados para actualizar un enriquecimiento y cuánto tiempo tomó ejecutar los procesos. El estado de enriquecimiento es compatible con Experian, Leadspace, HERE Technologies, SFTP Import y Azure Maps.

1. Vaya a **Datos** > **Enriquecimiento**.
1. En la pestaña **Mis enriquecimientos**, seleccione el estado del enriquecimiento para abrir un panel lateral.
1. En el panel **Detalles de progreso**, expanda la sección **Enriquecimientos**.
1. En el enriquecimiento cuyo progreso desea ver, seleccione **Ver detalles**.
1. En el panel **Detalles de la tarea**, seleccione **Mostrar detalles** para ver los procesos que intervienen en la actualización del enriquecimiento y su estado.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Ver los resultados del enriquecimiento

Después de completar una ejecución de enriquecimiento, puede revisar los resultados del enriquecimiento.

1. Vaya a **Datos** > **Enriquecimiento**.
1. En la pestaña **Mis enriquecimientos**, seleccione el enriquecimiento que desea ver.

Todos los enriquecimientos muestran información básica, como la cantidad de perfiles enriquecidos y la cantidad de perfiles enriquecidos a lo largo del tiempo. El mosaico **Vista previa de clientes enriquecidos** muestra un ejemplo de la entidad de enriquecimiento generada. Para ver una vista detallada, seleccione **Ver más** y seleccione la pestaña **Datos**.

:::image type="content" source="media/enrichments-results.png" alt-text="Página de resultados de enriquecimiento.":::

Si está disponible, el **Número de clientes enriquecidos por campo** proporciona un desglose de la cobertura de cada campo enriquecido.

Algunos enriquecimientos también muestran información específica del tipo de enriquecimiento. Para obtener más información, consulte la documentación relacionada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
