---
title: Enriquecer los perfiles de la empresa con datos empresariales mejorados
description: Enriquezca y normalice los datos de la empresa con los modelos de Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054269"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Enriquecer los perfiles de la empresa con datos empresariales mejorados

Utilice los modelos de Microsoft y los datos compilados de la empresa para corregir, complementar y estandarizar los perfiles de su empresa. Usaremos el [formato de Common Data Model](/common-data-model/schema/core/applicationcommon/account) para una mejor precisión y conocimientos.

Tú también puede [enriquecer datos de empresas en orígenes de datos](data-sources-enrichment.md) para mejorar la precisión de coincidencia en el proceso de unificación de datos.

Para las empresas públicas en los Estados Unidos, se encuentra disponible información como ingresos, cotizaciones bursátiles, industria y más.  

## <a name="how-we-enhance-company-data"></a>Cómo mejoramos los datos de empresa

Nuestro modelo pasa por un proceso de dos pasos para mejorar un perfil de empresa. Primero, normaliza el nombre de la empresa. Por ejemplo, *Microsoft Corp* será corregido y estandarizado para *Microsoft Corporation*. Intenta encontrar una coincidencia en los datos compilados de la empresa de Microsoft. Si se encuentra una coincidencia, enriquecemos el perfil de la empresa con información de los datos de nuestra empresa compilados, incluido el nombre de la empresa.

### <a name="example"></a>Ejemplo

Es posible que la información de su empresa no siga un formato estandarizado y contenga errores ortográficos. El modelo intenta solucionar estos problemas y crear información coherente.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limitaciones

El modelo no hace lo siguiente:

- Confirme la identidad de la empresa. No verificamos si la entrada es una organización existente o si una empresa usa la salida como su nombre estándar.
- Cobertura integral de empresas a nivel mundial. Los datos de la empresa compilados de Microsoft tienen cobertura global, pero ofrecen la mayor cobertura en Australia, Canadá, Reino Unido y Estados Unidos.
- Estandarice las direcciones de las empresas a nivel mundial. Actualmente admitimos la estandarización de direcciones en estos países o regiones: Australia, Canadá, Francia, Alemania, Italia, Japón, Reino Unido y Estados Unidos.
- Garantizar la exactitud o actualidad de los datos. Como la información empresarial cambia a menudo, no podemos garantizar que los datos mejorados de la empresa proporcionados sean siempre exactos o estén actualizados.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana **Datos de la empresa mejorados**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Mosaico de enriquecimiento en el centro de enriquecimiento para datos de la empresa.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos del cliente** y elija el perfil o segmento que quiere enriquecer. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

1. Seleccione qué tipo de campos de los perfiles de su empresa deben usarse para hacer coincidir con los datos de la empresa compilados por Microsoft. Esta selección afectará a los campos de asignación a los que tiene acceso en el siguiente paso.

1. Seleccione **Siguiente**.

1. Asigne sus campos de empresa a los datos de empresa de Microsoft. Para mayor precisión de coincidencia, agregue más campos.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Paso de mapeo de datos al configurar el enriquecimiento de una empresa.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un **nombre** para el enriquecimiento y la **entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="view-enrichment-results"></a>Ver los resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Tarjeta de descripción general

El mosaico **Vista general de cambios de clientes** muestra detalles sobre la cobertura del enriquecimiento

- **Compañías procesadas y cambiadas**: el número de perfiles de compañías que se enriquecieron con éxito.
- **Compañías procesadas y no cambiadas**: el número de perfiles de compañías de clientes que se reconocieron pero no cambiaron. Esto suele suceder cuando los datos de entrada son válidos y no se pueden mejorar mediante el enriquecimiento.
- **Compañías no procesadas y no cambiadas**: el número de perfiles de compañías de clientes que no se reconocieron. Por lo general, para datos de entrada que no son válidos o no son compatibles con el enriquecimiento.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
