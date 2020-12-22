---
title: Crear y administrar entornos
description: Obtenga información sobre cómo registrarse en el servicio y cómo administrar los entornos.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644154"
---
# <a name="manage-environments"></a>Administrar entornos

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artículo explica cómo crear una nueva organización y cómo aprovisionar un entorno.

## <a name="sign-up-and-create-an-organization"></a>Registrarse y crear una organización

1. Vaya al sitio web de [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Seleccione **Comenzar**.

3. Elija su escenario de registro preferido y seleccione el vínculo correspondiente.

4. Acepte los términos y condiciones y seleccione **Continuar** para empezar a crear la organización.

5. Una vez creado el entorno, se le redirigirá a [Customer Insights](https://home.ci.ai.dynamics.com).

6. Use el entorno de demostración para explorar la aplicación o cree un nuevo entorno siguiendo los pasos de la siguiente sección.

7. Después de especificar la configuración del entorno, seleccione **Crear**.

8. Iniciará sesión después de que el entorno se haya creado correctamente.

## <a name="create-an-environment-in-an-existing-organization"></a>Crear un entorno en una organización existente

Hay dos formas de crear un entorno nuevo. Puede especificar una configuración completamente nueva o copiar algunos valores de configuración de un entorno existente.

Para crear un entorno:

1. Seleccione el símbolo **Configuración** en el encabezado de la aplicación.

1. Seleccione **Nuevo entorno**.

   > [!div class="mx-imgBorder"]
   > ![Configuración del entorno](media/environment-settings-dialog.png)

1. En el diálogo **Crear un nuevo entorno**, seleccione **Nuevo ambiente**.

   Si quiere [copiar datos del entorno actual](#additional-considerations-for-copy-configuration-preview), seleccione **Copiar desde entorno existente**. Verá una lista de todos los entornos disponibles de su organización desde los que puede copiar datos.

1. Especifique los detalles siguientes:
   - **Nombre**: el nombre para este entorno. Este campo ya se ha cumplimentado si ha copiado un entorno existente, pero puede modificarlo.
   - **Región**: la región en la que se implementa y hospeda el servicio.
   - **Tipo**: Seleccione si desea crear un entorno de producción o de espacio aislado.

2. De manera opcional, puede seleccionar **Configuración avanzada**:

   - **Guardar todos los datos en**: Especifica dónde desea almacenar los datos de salida generados a partir de Customer Insights. Tendrá dos opciones: **Almacenamiento de Customer Insights** (un Azure Data Lake administrado por el equipo de Customer Insights) y **Azure Data Lake Storage Gen2** (su propio Azure Data Lake Storage). De forma predeterminada, la opción de almacenamiento de Customer Insights está seleccionada.

   > [!NOTE]
   > Al guardar datos en Azure Data Lake Storage, acepta que los datos se transferirán a la ubicación geográfica adecuada y se almacenarán en ella para esa cuenta de almacenamiento de Azure, que puede ser distinta del lugar en el que se almacenan los datos en Dynamics 365 Customer Insights. [Obtenga más información en el Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)
   >
   > Actualmente, las entidades ingeridas siempre se almacenan en el lago de datos administrados de Customer Insights.
   > Solo admitimos cuentas de almacenamiento de Azure Data Lake Gen2 de la misma región de Azure que seleccionó al crear el entorno.
   > Solo admitimos cuentas de almacenamiento habilitadas para cuentas de Espacio de nombres jerárquicos (HNS) de Azure Data Lake Gen2.

   - Para la opción de Azure Data Lake Storage Gen2, puede elegir entre usar una opción basada en recursos y una opción basada en suscripción para la autenticación. Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md). El nombre del **Contenedor** no se puede cambiar y será "customerinsights".
   
   - Si quiere usar [predicciones](predictions.md), introduzca la URL de instancia de Common Data Service en el campo **Dirección del servidor**, en **Usar predicciones**.

   Cuando ejecuta procesos, como la ingestión de datos o la creación de segmentos, las carpetas correspondientes se crearán en la cuenta de almacenamiento que especificó anteriormente. Se crearán archivos de datos y archivos model.json, y se agregarán a las subcarpetas correspondientes según el proceso que se ejecute.

   Si crea varios entornos de Customer Insights y elige guardar las entidades de salida de esos entornos en su cuenta de almacenamiento, se crearán carpetas separadas para cada entorno, con ci_<environmentid> en el contenedor.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Consideraciones adicionales para la configuración de copia (vista previa)

Se copian los siguientes valores de configuración:

- Configuración de características
- Orígenes de datos ingeridos/importados
- Configuración de unificación de datos (asignación, coincidencia, combinación)
- Segmentos
- Medidas
- Relaciones
- Actividades
- Índice de Buscar y filtrar
- Exportar destinos
- Actualización programada
- Enriquecimientos
- Administración de modelos
- Asignaciones de roles

Los siguientes valores de configuración *no* se copian:

- Perfiles de clientes.
- Credenciales del origen de datos. Debe especificar las credenciales para cada origen de datos y actualizar los orígenes de datos manualmente.
- Orígenes de datos de la carpeta de Common Data Model y del lago gestionado por Common Data Service. Tendrá que crear esos orígenes de datos manualmente con el mismo nombre que en el entorno de origen.

Al copiar un entorno, verá un mensaje de confirmación de que se ha creado el nuevo entorno. Seleccione **Ir a orígenes de datos** para ver la lista de orígenes de datos.

Todos los orígenes de datos mostrarán un estado de **Credenciales necesarias**. Edite los orígenes de datos e introduzca las credenciales para actualizarlas.

> [!div class="mx-imgBorder"]
> ![Orígenes de datos copiados](media/data-sources-copied.png)

Después de actualizar los orígenes de datos, vaya a **Datos** > **Unificar**. Aquí encontrará configuraciones del entorno de origen. Edítelos si es necesario o seleccione **Ejecutar** para iniciar el proceso de unificación de datos y crear la entidad de cliente unificado.

Cuando se haya completado la unificación de datos, vaya a **Medidas** y **Segmentos** para actualizarlos también.

## <a name="edit-an-existing-environment"></a>Editar un entorno existente

Puede editar algunos de los detalles de los entornos existentes.

1. Vaya a **Administración** > **Sistema** > **Acerca de**.

2. Seleccione **Editar**.

3. Puede actualizar **Nombre para mostrar** del entorno, pero no puede cambiar la **Región** o el **Tipo**.

4. Si un entorno está configurado para almacenar datos en Azure Data Lake Storage Gen2, puede actualizar la **Clave de cuenta**. Sin embargo, no puede cambiar el **Nombre de cuenta** o el nombre de **Contenedor**.

5. Opcionalmente, puede actualizar desde una conexión basada en clave de cuenta a una conexión basada en recursos o basada en suscripción. Una vez actualizado, no puede volver a la clave de cuenta después de la actualización. Para más información, consulte [Conectar la información de público a una cuenta de Azure Data Lake Storage Gen2 con una entidad de servicio de Azure](connect-service-principal.md). No puede cambiar la información de **Contenido** al actualizar la conexión.

## <a name="reset-an-existing-environment"></a>Restablecimiento de un entorno existente

Puede restablecer un entorno a un estado vacío si desea eliminar todas las configuraciones y eliminar los datos ingeridos.

1.  Vaya a **Administración** > **Sistema** > **Acerca de**.

2.  Seleccione **Restablecer**. 

3.  Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Restablecer**.


## <a name="delete-an-existing-environment"></a>Eliminar un entorno existente

1. Vaya a **Administración** > **Sistema** > **Acerca de**.

1. Seleccione **Eliminar**.

1. Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Eliminar**.
