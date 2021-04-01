---
title: Conectarse a entidades en el lago gestionado de Common Data Service
description: Importar datos de un data lake administrado por Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596980"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Conéctese a los datos en un data lake administrado de Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artículo proporciona información sobre cómo los clientes existentes de Dynamics 365 pueden conectarse rápidamente a sus entidades analíticas en el lago gestionado de Common Data Service. Debe ser administrador en la organización de Common Data Service para continuar y ver la lista de entidades disponibles en el lago administrado.

## <a name="important-considerations"></a>Consideraciones importantes

Los datos almacenados en servicios en línea como Azure Data Lake Storage pueden almacenarse en una ubicación diferente de dónde se procesan o almacenan los datos en Dynamics 365 Customer Insights. Al importar o conectarse a datos almacenados en servicios en línea, acepta que los datos pueden transferirse y almacenarse con Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Conectarse a un lago gestionado por Common Data Service

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Seleccione **Agregar origen de datos**.

3. Seleccione **Conectar con Common Data Service** y, a continuación, seleccione **Siguiente**.

4. Escriba un **Nombre** para el origen de datos y seleccione **Siguiente**. Directrices de nomenclatura: 
   - Empiece con una letra.
   - Utilice solo letras y números. No se permiten caracteres especiales ni espacios.
   - Utilice entre 3 y 64 caracteres.

5. Especifique la **Dirección del servidor** de su organización de Common Data Service y seleccione **Iniciar sesión**.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo para introducir la dirección del servidor de Common Data Service](media/enter-CDS-org-details.png)

6. En la lista disponible, seleccione el conjunto de entidades que desea ingerir.    

   > [!NOTE]
   > Si algunas entidades ya están seleccionadas, puede que se utilicen en otras aplicaciones de Dynamics 365 (como Dynamics 365 Sales Insights o Customer Service Insights). No se puede cambiar esta selección. Estas entidades estarán disponibles una vez que se cree el origen de datos.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo que muestra una lista de entidades en la organización de Common Data Service](media/select-analytical-entities.png)

7. Guarde la selección para comenzar a sincronizar las entidades seleccionadas con el lago gestionado por Common Data Service. Encontrará la conexión recién agregada en la página **Orígenes de datos**. Se pondrá en cola para actualizarse y mostrará un recuento de entidades igual a 0 hasta que se hayan sincronizado todas las entidades.

Solo un origen de datos de un entorno puede usar simultáneamente el mismo lago gestionado Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Editar un origen de datos de lago gestionado por Common Data Service

Solo se edita la selección de entidad después de crear el origen de datos. Por ejemplo, si se agregaron entidades adicionales a Common Data Service y desea importarlas también.    
Para conectarse a una instancia de Common Data Service distinta, puede [crear un origen de datos nuevo](#connect-to-a-common-data-service-managed-lake).

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Junto al origen de datos que desea actualizar, seleccione los puntos suspensivos.

3. Seleccione la opción **Editar** de la lista.

4. Seleccione entidades adicionales de la lista de entidades disponibles y, a continuación, seleccione **Guardar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]