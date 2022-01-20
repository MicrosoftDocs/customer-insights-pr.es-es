---
title: Mejora de datos de empresa
description: Enriquezca y normalice los datos de la empresa con los modelos de Microsoft.
ms.date: 12/16/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 616efe723313a6fbec7f1c7219c236a8f0aab3b2
ms.sourcegitcommit: e141a6a34a985cca68f03082a700ed27f2f3c0c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2021
ms.locfileid: "7927603"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Enriquecimiento de los perfiles de la empresa con datos empresariales mejorados

Utilice los modelos de Microsoft y los datos compilados de la empresa para corregir, complementar y estandarizar los perfiles de su empresa. Usaremos el [formato de Common Data Model](/common-data-model/schema/core/applicationcommon/account) para una mejor precisión y conocimientos.

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

Existen algunas limitaciones con los datos mejorados. Los elementos de la lista siguiente no son compatibles con el modelo.

1.  Confirme la identidad de la empresa. No verificamos si la entrada es una organización existente o si una empresa usa la salida como su nombre estándar.
2.  Cobertura integral de empresas a nivel mundial. Los datos de la empresa compilados de Microsoft tienen cobertura global, pero ofrecen la mayor cobertura en Australia, Canadá, Reino Unido y Estados Unidos.
3.  Estandarice las direcciones de las empresas a nivel mundial. Actualmente admitimos la estandarización de direcciones en estos países o regiones: Australia, Canadá, Francia, Alemania, Italia, Japón, Reino Unido y Estados Unidos.
4.  Garantizar la exactitud o actualidad de los datos. Como la información empresarial cambia a menudo, no podemos garantizar que los datos mejorados de la empresa proporcionados sean siempre exactos o estén actualizados.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento**.

1. Seleccione **Enriquecer mis datos** en la ventana **Datos de la empresa mejorados**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Mosaico de enriquecimiento en el centro de enriquecimiento para datos de la empresa.":::

1. Selecciona el **Conjunto de datos de clientes** y elija la entidad que contiene las direcciones que desea enriquecer. Puede seleccionar la entidad *Cliente* para enriquecer direcciones en todos sus perfiles de clientes o seleccionar una entidad de segmento para enriquecer direcciones solo en perfiles de clientes contenidos en ese segmento.

1. Seleccione qué tipo de campos de los perfiles de su empresa deben usarse para hacer coincidir con los datos de la empresa compilados por Microsoft. Esta selección afectará a los campos de asignación a los que tiene acceso en el siguiente paso.

1.  Asigne los campos de la empresa desde su entidad de cliente unificada. Cuantos más identificadores y campos clave mapee, mayor será la probabilidad de una tasa de coincidencia más alta.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Paso de mapeo de datos al configurar el enriquecimiento de una empresa.":::

1. Seleccione **Siguiente** para completar la asignación de campos.

1. Proporcione un nombre para el enriquecimiento y la entidad de salida.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento depende del tamaño de los datos de sus clientes.

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de los perfiles de clientes recién enriquecidos en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

### <a name="overview-card"></a>Tarjeta de descripción general

La tarjeta de descripción general muestra detalles sobre la cobertura del enriquecimiento. 

* **Clientes procesados y cambiados**: el número de perfiles de clientes que se enriquecieron con éxito.

* **Clientes procesados y no cambiados**: el número de perfiles de clientes que se reconocieron pero no cambiaron. Por lo general, sucede cuando los datos de entrada son válidos y no se pueden mejorar mediante el enriquecimiento.

* **Clientes no procesados y no cambiados**: el número de perfiles que no se reconocieron. Por lo general, para datos de entrada que no son válidos o no son compatibles con el enriquecimiento.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
