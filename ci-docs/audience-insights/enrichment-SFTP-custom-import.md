---
title: Enriquecimiento con importación personalizada SFTP
description: Información general sobre el enriquecimiento de importación personalizada SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568507"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquezca los perfiles de los clientes con datos personalizados (versión preliminar)

La importación personalizada del Protocolo de transferencia segura de archivos (SFTP) le permite importar datos que no tienen que pasar por el proceso de unificación de datos. Es una forma flexible, segura y fácil de incorporar sus datos. La importación personalizada SFTP se puede utilizar en combinación con la [Exportación SFTP](export-sftp.md) que le permite exportar los datos del perfil del cliente necesarios para el enriquecimiento. Luego, los datos se pueden procesar, enriquecer y la importación personalizada de SFTP se puede utilizar para devolver los datos enriquecidos a la capacidad de información de público de Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

Para configurar la importación personalizada de SFTP, se deben cumplir los siguientes requisitos previos:

- Tiene credenciales de usuario (nombre de usuario y contraseña) para la ubicación SFTP desde donde se importarán los datos.
- Tiene la URL y el número de puerto (generalmente 22) para el host STFP.
- Tiene el nombre de archivo y la ubicación del archivo que se va a importar en el servidor SFTP.
- Hay un archivo *model.json* que especifica el esquema de los datos que se van a importar. Este archivo debe estar en el mismo directorio que el archivo que se va a importar.
- Tiene permisos de [Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuración

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. En el **mosaico de importación personalizada de SFTP Technologies**, seleccione **Enriquecer mis datos**.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de importación personalizado de SFTP](media/SFTP_Custom_Import_tile.png "Mosaico de importación personalizado de SFTP")

1. Seleccione **Comenzar** y proporcione las credenciales y la dirección del servidor SFTP. Por ejemplo, sftp://mysftpserver.com:22.

1. Introduzca el nombre del archivo que contiene los datos y la ruta al archivo en el servidor SFTP si no está en la carpeta raíz.

1. Confirme todas las entradas seleccionando **Conectarse a la importación personalizada**.

   > [!div class="mx-imgBorder"]
   > ![Control flotante de configuración de importación personalizada SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Control flotante de configuración de importación personalizada SFTP")

## <a name="defining-field-mappings"></a>Definición de asignaciones de campos 

El directorio que contiene el archivo que se va a importar en el servidor SFTP también debe contener un archivo *model.json*. Este archivo define el esquema que se utilizará para importar los datos. El esquema tiene que usar [Common Data Model](https://docs.microsoft.com/common-data-model/) para especificar la asignación de campos. Un ejemplo sencillo de un archivo model.json tiene este aspecto:

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

Utilice los datos enriquecidos de sus clientes. Cree [segmentos](segments.md), [medidas](measures.md) y [exporte los datos](export-destinations.md) para brindar experiencias personalizadas a sus clientes.


