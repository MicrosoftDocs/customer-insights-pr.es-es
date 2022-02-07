---
title: Conectarse a tablas en Microsoft Dataverse
description: Importar datos de un data lake administrado por Microsoft Dataverse.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
---

# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conéctese a los datos en un data lake administrado de Microsoft Dataverse



Este artículo proporciona información sobre cómo los usuarios de Dataverse pueden conectarse rápidamente a entidades analíticas en un lago gestionado por Microsoft Dataverse. 

> [!NOTE]
> Debe ser administrador en la organización de Dataverse para continuar y ver la lista de entidades disponibles en el lago administrado.

## <a name="important-considerations"></a>Consideraciones importantes

Los datos almacenados en servicios en línea como Azure Data Lake Storage pueden almacenarse en una ubicación diferente de dónde se procesan o almacenan los datos en Dynamics 365 Customer Insights. Al importar o conectarse a datos almacenados en servicios en línea, acepta que los datos pueden transferirse y almacenarse con Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectarse a un lago gestionado por Dataverse

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Seleccione **Agregar origen de datos**.

3. Seleccione **Microsoft Dataverse** y luego **Siguiente**.

4. Escriba un **Nombre** para el origen de datos y seleccione **Siguiente**. 

5. Especifique la **Dirección del servidor** para la organización de Dataverse y seleccione **Iniciar sesión**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Pantalla del paso de ingesta de datos donde un usuario puede especificar la dirección URL del entorno de Dataverse.":::

6. Seleccione las tablas que desea ingerir como entidades para las conclusiones del público de la lista disponible.    

   > [!NOTE]
   > Si algunas tablas ya están seleccionadas, probablemente se deba a que otras aplicaciones de Dynamics 365, como Dynamics 365 Sales Insights o Customer Service Insights, las están utilizando. No se puede cambiar esta selección. Estas tablas estarán disponibles como entidades cuando se cree el origen de datos.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Cuadro de diálogo que muestra una lista de entidades en el entorno de Dataverse.":::

7. Guarde su selección para empezar a sincronizar las tablas seleccionadas desde Dataverse. Encontrará la conexión recién agregada en la página **Orígenes de datos**. Se pondrá en cola para actualizarse y mostrará el recuento de entidades como 0 hasta que todas las tablas seleccionadas estén sincronizadas.

Solo un origen de datos de un entorno puede usar simultáneamente el mismo lago gestionado Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar un origen de datos de lago gestionado por Dataverse

Solo se edita la selección de entidad después de crear el origen de datos. Por ejemplo, si se agregaron entidades adicionales a Dataverse y desea importarlas también.    
Para conectarse a un lago de datos de Dataverse, debe [crear un origen de datos nuevo](#connect-to-a-dataverse-managed-lake).

1. En informaciones del público, vaya a **Datos** > **Orígenes de datos**.

2. Junto al origen de datos que desea actualizar, seleccione los puntos suspensivos.

3. Seleccione la opción **Editar** de la lista.

4. Seleccione entidades adicionales de la lista de entidades disponibles y, a continuación, seleccione **Guardar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
