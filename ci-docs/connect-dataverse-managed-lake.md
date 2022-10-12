---
title: Conéctese a los datos en un data lake administrado de Microsoft Dataverse
description: Importar datos de un data lake administrado por Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609872"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conéctese a los datos en un data lake administrado de Microsoft Dataverse

Los usuarios de Microsoft Dataverse pueden conectarse rápidamente a entidades analíticas en un lago administrado de Microsoft Dataverse. Solo un origen de datos de un entorno puede usar simultáneamente el mismo lago gestionado Dataverse.

> [!NOTE]
> Debe ser administrador en la organización de Dataverse para continuar y ver la lista de entidades disponibles en el lago administrado.

## <a name="prerequisites"></a>Requisitos previos

- Los datos almacenados en servicios en línea como Azure Data Lake Storage pueden almacenarse en una ubicación diferente de dónde se procesan o almacenan los datos en Dynamics 365 Customer Insights. Al importar o conectarse a datos almacenados en servicios en línea, acepta que los datos pueden transferirse y almacenarse con Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

- Solamente están visibles las entidades Dataverse con [Change Tracking](/power-platform/admin/enable-change-tracking-control-data-synchronization) habilitado. Estas entidades se pueden exportar al lago de datos gestionado por Dataverse y utilizarse en Customer Insights. Las tablas de Dataverse predefinidas tienen habilitado el Change Tracking por defecto. Debe activar el Change Tracking para las tablas personalizadas. Para comprobar si una tabla de Dataverse tiene activado el Change Tracking, vaya a [Power Apps](https://make.powerapps.com) > **Datos** > **Tablas**. Encuentre la tabla que le interesa y selecciónela. Vaya a **Configuración** > **Opciones avanzadas** y revise la configuración de **Rastrear cambios**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectarse a un lago gestionado por Dataverse

1. Vaya a **Datos** > **Orígenes de datos**.

1. Seleccione **Agregar origen de datos**.

1. Seleccione **Microsoft Dataverse**.

1. Escriba un **Nombre** para el origen de datos y una **Descripción** opcional.

1. Especifique la **Dirección del servidor** para la organización de Dataverse y seleccione **Iniciar sesión**.

1. Seleccione las tablas que desea ingerir como entidades para Customer Insights de la lista disponible.

   > [!NOTE]
   > Si algunas tablas ya están seleccionadas, probablemente se deba a que otras aplicaciones de Dynamics 365, como Dynamics 365 Sales Insights o Customer Service Insights, las están utilizando. No se puede cambiar esta selección. Estas tablas estarán disponibles como entidades cuando se cree el origen de datos.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Cuadro de diálogo que muestra una lista de entidades en el entorno de Dataverse.":::

1. Guarde su selección para empezar a sincronizar las tablas seleccionadas desde Dataverse. Encontrará la conexión recién agregada en la página **Orígenes de datos**. Se pondrá en cola para actualizarse y mostrará el recuento de entidades como 0 hasta que todas las tablas seleccionadas estén sincronizadas.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

La carga de datos puede llevar tiempo. Una vez completada una actualización, se pueden revisar los datos ingeridos en la página [**Entidades**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar un origen de datos de lago gestionado por Dataverse

Solo se edita la selección de entidad después de crear el origen de datos. Por ejemplo, si se agregaron entidades adicionales a Dataverse y desea importarlas también.
Para conectarse a un lago de datos de Dataverse, debe [crear un origen de datos nuevo](#connect-to-a-dataverse-managed-lake).

1. Vaya a **Datos** > **Orígenes de datos**.

1. Junto al origen de datos que desea actualizar, seleccione **Editar**.

1. Seleccione entidades adicionales de la lista de entidades disponibles.

1. Haga clic en **Guardar** para aplicar los cambios y volver a la página **Orígenes de datos**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Motivos comunes de errores de ingestión o datos dañados

Las siguientes comprobaciones se ejecutan en los datos ingeridos para exponer registros dañados:

- El valor de un campo no coincide con el tipo de datos de su columna.
- Los campos contienen caracteres que hacen que las columnas no coincidan con el esquema esperado. Por ejemplo: comillas con formato incorrecto, comillas sin escape o caracteres de nueva línea.
- Si hay columnas datetime/date/datetimeoffset, su formato debe especificarse en el modelo si no sigue el formato ISO estándar.

### <a name="schema-or-data-type-mismatch"></a>Discrepancia de esquema o tipo de datos

Si los datos no se ajustan al esquema, los registros se clasifican como corruptos. Corrija los datos de origen o el esquema y vuelva a ingerir los datos.

### <a name="datetime-fields-in-the-wrong-format"></a>Campos de fecha y hora en un formato incorrecto

Los campos de fecha y hora de la entidad no están en formato ISO o en-US. El formato de fecha y hora predeterminado en Customer Insights es el formato en-US. Todos los campos de fecha y hora de una entidad deben tener el mismo formato. Customer Insights admite otros formatos siempre que se realicen anotaciones o características en el nivel de fuente o entidad en el modelo o manifest.json. Por ejemplo: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  En un manifest.json, el formato de fecha y hora se puede especificar en el nivel de entidad o en el nivel de atributo. En el nivel de entidad, use "exhibitsTraits" en la entidad en *.manifest.cdm.json para definir el formato de fecha y hora. En el nivel de atributo, use "appliedTraits" en el atributo en el nombre de entidad.cdm.json.

**Manifest.json a nivel de entidad**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json a nivel de atributo**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
