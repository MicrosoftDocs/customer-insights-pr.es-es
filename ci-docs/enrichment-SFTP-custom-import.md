---
title: Enriquezca los perfiles de los clientes con FTP custom import (vista previa)
description: Información general sobre el enriquecimiento de importación personalizada SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195817"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Enriquezca los perfiles de los clientes con FTP custom import (vista previa)

La importación personalizada del Protocolo de transferencia segura de archivos (SFTP) le permite importar datos que no tienen que pasar por el proceso de unificación de datos. Es una forma flexible, segura y fácil de incorporar sus datos. La importación personalizada SFTP se puede utilizar en combinación con la [Exportación SFTP](export-sftp.md) que le permite exportar los datos del perfil del cliente necesarios para el enriquecimiento. Luego, los datos se pueden procesar y enriquecer, y se puede usar la importación personalizada de SFTP para devolver los datos enriquecidos a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

- Se conoce el nombre del archivo y la ubicación (ruta) del archivo que se importará en el host SFTP.

- Un archivo *model.json* que especifica el esquema de Common Date Model para los datos que se van a importar está disponible. Este archivo debe estar en el mismo directorio que el archivo que se va a importar.

- Una [conexión](connections.md) SFTP está [configurada](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Ejemplo de esquema de archivo

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurar la conexión para la importación personalizada de SFTP

Debe ser un [Administrador](permissions.md#admin) en Customer Insights y tener las credenciales de usuario, la URL y el número de puerto de la ubicación SFTP desde la que desea importar los datos.

1. Seleccione **Agregar conexión** cuando configure un enriquecimiento o vaya a **Administración** > **Conexiones** y seleccione **Configurar** en la ventana de Importación personalizada.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Página de configuración de conexión de Importación personalizada":::

1. Escriba un nombre para la conexión.

1. Especifique un nombre de usuario y contraseña y una dirección URL de host válidos para el servidor SFTP en el que residen los datos que se importarán.

1. Revise y proporcione su consentimiento para [Privacidad y cumplimiento de datos](#data-privacy-and-compliance) seleccionando **Estoy de acuerdo**.

1. Seleccione **Verificar** para validar la configuración y luego seleccionar **Guardar**.

### <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilita Dynamics 365 Customer Insights para transmitir datos usando Custom Import, permite la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluidos los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que los datos cumplan con las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este enriquecimiento en cualquier momento para dejar de usar esta funcionalidad.

## <a name="configure-the-import"></a>Configurar la importación

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana **Importar SFTP personalizado**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ventana de importación personalizada de SFTP.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Seleccione la conexión. Contacte con un administrador si no hay conexión disponible.

1. Seleccione el **Conjunto de datos del cliente** y elija el perfil o segmento que quiere enriquecer. La entidad *Cliente* enriquece todos sus perfiles de cliente mientras que un segmento solo enriquece perfiles de cliente contenidos en ese segmento.

1. Seleccione **Siguiente**.

1. Introduzca la **Ruta** y **Nombre de archivo** del archivo de datos que quiera importar.

1. Seleccione **Siguiente**.

1. Proporcione un **nombre** para el enriquecimiento y la **Nombre de entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Ejecutar** para iniciar el proceso de enriquecimiento o cerrar para volver a la página **Enriquecimientos**.

## <a name="view-enrichment-results"></a>Ver los resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
