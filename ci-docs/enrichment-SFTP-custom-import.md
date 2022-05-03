---
title: Enriquecimiento con importación personalizada SFTP
description: Información general sobre el enriquecimiento de importación personalizada SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f52d24cbe793bee7948ad2af31059cd3edf40f94
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646547"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquezca los perfiles de los clientes con datos personalizados (versión preliminar)

La importación personalizada del Protocolo de transferencia segura de archivos (SFTP) le permite importar datos que no tienen que pasar por el proceso de unificación de datos. Es una forma flexible, segura y fácil de incorporar sus datos. La importación personalizada SFTP se puede utilizar en combinación con la [Exportación SFTP](export-sftp.md) que le permite exportar los datos del perfil del cliente necesarios para el enriquecimiento. Luego, los datos se pueden procesar y enriquecer, y se puede usar la importación personalizada de SFTP para devolver los datos enriquecidos a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

Para configurar la importación personalizada de SFTP, se deben cumplir los siguientes requisitos previos:

- Tiene el nombre del archivo y la ubicación (ruta) del archivo que se va a importar en el host SFTP.
- Hay un archivo *model.json* que especifica [el esquema de Common Data Model](/common-data-model/) para que los datos se importen. Este archivo debe estar en el mismo directorio que el archivo que se va a importar.
- Una conexión SFTP ya ha sido configurada por un administrador *o* tiene permisos de [administrador](permissions.md#admin). Necesitará las credenciales de usuario, la dirección URL y el número de puerto para la ubicación SFTP desde la que desea importar los datos.


## <a name="configure-the-import"></a>Configurar la importación

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. En la **ventana de importación personalizada de SFTP**, seleccione **Enriquecer mis datos** y, luego, seleccione **Comenzar**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ventana de importación personalizada de SFTP.":::

1. Seleccione una [conexión](connections.md) en la lista desplegable. Contacte con un administrador si no hay conexión disponible. Si es un administrador, puede crear una conexión seleccionando **Agregar conexión** y eligiendo **Importación personalizada de SFTP** en la lista desplegable.

1. Seleccione **Conectar a importación personalizada** para confirmar la conexión seleccionada.

1.  Seleccione **Siguiente** y especifique la **Ruta** y el **Nombre del archivo** del archivo de datos que desea importar.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de pantalla al especificar la ubicación de los datos.":::

1. Seleccione **Siguiente** y elija el cliente conjunto de datos. Puede ser todos los perfiles de clientes o un segmento.

1. Seleccione **Siguiente** y proporcione un nombre para el enriquecimiento y un nombre para la entidad de salida. 

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurar la conexión para la importación personalizada de SFTP 

Debe ser un administrador para configurar las conexiones. Seleccione **Agregar conexión** cuando configure un enriquecimiento *o* vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Importación personalizada.

1. Indique un nombre para la conexión el cuadro **Nombre ara mostrar**.

1. Especifique un nombre de usuario y contraseña y una dirección URL de host válidos para el servidor SFTP en el que residen los datos que se importarán.

1. Revise y proporcione su consentimiento para la **Privacidad y cumplimiento de datos**. Para ello, active la casilla **Acepto**.

1. Seleccione **Verificar** para validar la configuración.

1. Una vez que se ha completado la verificación, la conexión se puede guardar seleccionando **Guardar**.

   > [!div class="mx-imgBorder"]
   > ![Página de configuración de conexión de Experian.](media/enrichment-SFTP-connection.png "Página de configuración de conexión de Experian")


## <a name="defining-field-mappings"></a>Definición de asignaciones de campos 

El directorio que contiene el archivo que se va a importar en el servidor SFTP también debe contener un archivo *model.json*. Este archivo define el esquema que se utilizará para importar los datos. El esquema tiene que usar [Common Data Model](/common-data-model/) para especificar la asignación de campo. Un ejemplo sencillo de un archivo model.json tiene este aspecto:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Resultados del enriquecimiento

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar** desde la barra de comandos. También puede dejar que el sistema ejecute el enriquecimiento automáticamente como parte de una [actualización programada](system.md#schedule-tab). El tiempo de procesamiento dependerá del tamaño de los datos a importar y de la conexión al servidor SFTP.

Una vez que se completa el proceso de enriquecimiento, puede revisar los datos de enriquecimiento personalizados recién importados en **Mis enriquecimientos**. Además, encontrará la hora de la última actualización y el número de perfiles enriquecidos.

Puede acceder a una vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
