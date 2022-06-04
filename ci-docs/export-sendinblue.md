---
title: Exportar datos de Customer Insights a Sendinblue
description: Aprenda a configurar la conexión y exportar a Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6d63e0017caa50379426cd5f9b663571b568de7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647639"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segmentos a Sendinblue (versión preliminar)

Exportar segmentos de perfiles de cliente unificados para generar campañas, ofrecer marketing por correo electrónico y aprovechar grupos específicos de clientes con Sendinblue.

## <a name="prerequisites-for-connection"></a>Requisitos previos para una conexión

-   Tiene una [cuenta de Sendinblue](https://www.sendinblue.com/) y las credenciales de administrador correspondientes.
-   Hay listas existentes en Sendinblue y los identificadores correspondientes.
-   Ha [configurado los segmentos](segments.md).
-   Los perfiles de clientes unificados en los segmentos exportados contienen un campo que representa una dirección de correo electrónico.

## <a name="known-limitations"></a>Limitaciones conocidas

- Hasta 1 millón de perfiles de clientes por exportación a Sendinblue.
- La exportación a Sendinblue está limitada a segmentos.
- La exportación de segmentos con un total de 1 millones de perfiles de clientes puede tardar hasta 90 minutos. 
- La cantidad de perfiles de clientes que puede exportar a Sendinblue depende y está limitada por su contrato con Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Configurar la conexión a Sendinblue

1. Vaya a **Administrador** > **Conexiones**.

1. Seleccione **Agregar conexión** y elija **Sendinblue** para configurar la conexión.

1. Asigne a su conexión un nombre reconocible en el campo **Nombre para mostrar**. El nombre y el tipo de conexión describe esta conexión. Recomendamos elegir un nombre que explique el propósito y el objetivo de la conexión.

1. Elija quién puede utilizar esta conexión. De forma predeterminada, solo son administradores. Para obtener más información, vea [Permitir que los colaboradores utilicen una conexión para las exportaciones](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Especifique su **[clave de API de Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**

1. Seleccione **Acepto** para confirmar la **Privacidad y cumplimiento de los datos** y seleccione **Conectar** para inicializar la conexión a Sendinblue.

1. Seleccione **Agregarse como usuario de exportación** y proporcione sus credenciales de Customer Insights.

1. Seleccione **Guardar** para completar la conexión.

## <a name="configure-an-export"></a>Configurar una exportación

Puede configurar esta exportación si tiene acceso a una conexión de este tipo. Para obtener más información, vea [Permisos necesarios para configurar una exportación](export-destinations.md#set-up-a-new-export).

1. Vaya a **Datos** > **Exportaciones**.

1. Para crear una exportación nueva, seleccione **Agregar destino**.

1. En el campo **Conexión para exportación**, elija una conexión de la sección Sendinblue. Si no ve este nombre de sección, es que no hay conexiones de este tipo disponibles para usted.

1. Indique su **Id. de lista de Sendinblue**. 

1. En la sección **Coincidencia de datos**, en el campo **Correo electrónico**, seleccione el campo que representa la dirección de correo electrónico de un cliente. 

1. Opcionalmente, puede exportar **Nombre de pila**, **Apellido**, y **Teléfono** para crear correos electrónicos más personalizados. Seleccione **Agregar atributo** para asignar estos campos.

1. Seleccione los segmentos que desea exportar. 

1. Seleccione **Guardar**.

Guardar una exportación no ejecuta la exportación inmediatamente.

La exportación se ejecuta con cada [actualización programada](system.md#schedule-tab). Tú también puede [exportar datos según las necesidades](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privacidad y cumplimiento de datos

Cuando habilite Dynamics 365 Customer Insights para transmitir datos a Sendinblue, permita la transferencia de datos fuera del límite de cumplimiento para Dynamics 365 Customer Insights, incluyendo los datos potencialmente confidenciales, como los datos personales. Microsoft transferirá dichos datos según sus instrucciones, pero usted es responsable de garantizar que Sendinblue cumple las obligaciones de privacidad o seguridad que pueda tener. Para más información, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Su administrador de Dynamics 365 Customer Insights puede quitar este destino de exportación en cualquier momento para dejar de usar esta funcionalidad.


[!INCLUDE [footer-include](includes/footer-banner.md)]