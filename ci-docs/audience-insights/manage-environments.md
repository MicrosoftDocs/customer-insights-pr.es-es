---
title: Crear y administrar entornos
description: Obtenga información sobre cómo registrarse en el servicio y cómo administrar los entornos.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492025"
---
# <a name="manage-environments"></a>Administrar ambientes

## <a name="switch-environments"></a>Cambiar entornos

Seleccione el control **Entorno** en la esquina superior derecha de la página para cambiar entornos.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla del control para cambiar de entorno.":::

Los administradores pueden [crear](create-environment.md) y administrar entornos.

## <a name="edit-an-existing-environment"></a>Editar un entorno existente

Puede editar algunos de los detalles de los entornos existentes.

1.  Seleccione el selector **Entorno** en el encabezado de la aplicación.

2.  Seleccione el icono de **Editar**.

3. En el cuadro **Editar entorno** puede actualizar la configuración del entorno.

Para obtener más información sobre la configuración del entorno, consulte [Crear un nuevo entorno](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Conectar con Microsoft Dataverse
   
El paso **Microsoft Dataverse** le permite conectar Customer Insights con su entorno de Dataverse. 

Proporcione su propio entorno de Microsoft Dataverse para compartir datos (perfiles e insights) con aplicaciones empresariales basadas en Dataverse, como Dynamics 365 Marketing o aplicaciones basadas en modelos en Power Apps.

Para usar [modelos predicción predefinidos](predictions-overview.md#out-of-box-models), configure el intercambio de datos con Dataverse. O puede habilitar la ingestión de datos desde orígenes de datos locales, proporcionando la dirección URL del entorno de Microsoft Dataverse que administra su organización.

Habilitar el intercambio de datos con Microsoft Dataverse al seleccionar la casilla de verificación de intercambio de datos desencadenará una actualización completa única de sus orígenes de datos y todos los demás procesos.

> [!IMPORTANT]
> 1. Customer Insights y Dataverse tienen que estar en la misma región para permitir el intercambio de datos.
> 1. Debe tener un rol de administrador global en el entorno de Dataverse. Compruebe si este entorno de [Dataverse está asociado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a ciertos grupos de seguridad y asegúrese de que se le agregue a esos grupos.
> 1. Ningún entorno existente de Customer Insights ya está asociado con ese entorno de Dataverse. Aprenda cómo [quitar una conexión existente a un entorno de Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opciones de configuración para permitir el uso compartido de datos con Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habilitar el intercambio de datos con Dataverse desde su propio Azure Data Lake Storage (Vista previa)

Si su entorno está configurado para usar su propio Azure Data Lake Storage para almacenar datos de Customer Insights, activar la compartición de datos con Microsoft Dataverse requiere alguna configuración extra.

1. Cree dos grupos de seguridad en su suscripción de Azure: un grupo de seguridad **Lector** y un grupo de seguridad **Colaborador** y establezca el servicio Microsoft Dataverse como propietario de ambos grupos de seguridad.
2. Administre la lista de control de acceso (ACL) en el contenedor de CustomerInsights en su cuenta de almacenamiento a través de estos grupos de seguridad. Agregue el servicio Microsoft Dataverse y cualquier aplicación empresarial basada en Dataverse como Dynamics 365 Marketing para el grupo de seguridad **Lector** con permisos de **solo lectura**. Agregue *solamente* la aplicación Customers Insights al grupo de seguridad **Colaborador** para otorgar a ambos permisos de **lectura y escritura** para escribir perfiles e información.
   
#### <a name="prerequisites"></a>Requisitos previos

Para ejecutar los scripts de PowerShell, debe importar los siguientes tres módulos. 

1. Instale la versión más reciente de [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. En su PC, seleccione la tecla de Windows en su teclado, busque **Windows PowerShell** y seleccione **Ejecutar como Administrador**.
   1. En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.
2. Importe tres módulos.
    1. En la ventana PowerShell, escriba `Install-Module -Name Az.Accounts` y siga los pasos. 
    1. Repita para `Install-Module -Name Az.Resources` y `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Pasos de configuración

1. Descargue los dos scripts de PowerShell que necesita para ejecutar desde nuestro [repositorio de GitHub para ingenieros](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Necesita permisos de *administración de inquilinos* para ejecutar este script de PowerShell. 
       - Este script de PowerShell crea dos grupos de seguridad en su suscripción de Azure. Uno para el grupo Lector y otro para el grupo colaborador y haga que el servicio Microsoft Dataverse sea el propietario de estos dos grupos de seguridad.
       - Ejecute este script de PowerShell en Windows PowerShell proporcionando el Id. de suscripción de Azure que contiene su Azure Data Lake Storage. Abra el script de PowerShell en un editor para revisar información adicional y la lógica implementada.
       - Guarde ambos valores de Id. de grupo de seguridad generados por este script porque los usaremos en el script `ByolSetup.ps1`.
       
        > [!NOTE]
        > La creación de grupos de seguridad se puede deshabilitar en su inquilino. En ese caso, se necesitaría una configuración manual y su administrador de Azure AD tendría que[ habilitar la creación de grupos de seguridad](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Necesita permisos de *Propietario de datos de Storage Blob* en el nivel de contenedor/cuenta de almacenamiento para ejecutar este script o este script creará uno para usted. Su asignación de roles se puede eliminar manualmente después de ejecutar con éxito el script.
        - Este script de PowerShell agrega el control de acceso basado en permisos (RBAC) necesario para el servicio Microsoft Dataverse y cualquier aplicaciones empresarial basada en Dataverse. También actualiza la Lista de control de acceso (ACL) en el contenedor de Customer Insights para los grupos de seguridad creados con el script `CreateSecurityGroups.ps1`. El grupo Colaborador tendrá permiso *rwx* y el grupo Lector tendrá solo permiso *r-x*.
        - Ejecute este script de PowerShell en Windows PowerShell proporcionando el Id. de suscripción de Azure que contiene su Azure Data Lake Storage, el nombre de la cuenta de almacenamiento, el nombre del grupo de recursos y los valores de Id. del grupo de seguridad Lector y Colaborador. Abra el script de PowerShell en un editor para revisar información adicional y la lógica implementada.
        - Copie la cadena de resultados después de ejecutar correctamente el script. La cadena de resultados deberá tener un aspecto similar al siguiente: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Escriba la cadena de resultados copiada del paso anterior en el campo **Identificador de permisos** del paso de configuración del entorno para Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opciones de configuración para habilitar el uso compartido de datos desde su propia cuenta Azure Data Lake Storage con Microsoft Dataverse.":::

Customer Insights no admite los siguientes escenarios de uso compartido de datos:
- Si habilita el uso compartido de datos con Dataverse, no podrá [crear valores pronosticados o faltantes en una entidad](predictions.md).
- Si habilita el uso compartido de datos con Dataverse, no podrá ver ningún informe opcional integrado de PowerBI en su entorno de Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Quite una conexión existente a un entorno de Dataverse

Al conectarse a un entorno de Dataverse, el mensaje de error **Esta organización de CDS ya está adjunta a otra instancia de Customer Insights** significa que el entorno de Dataverse ya se utiliza en un entorno de Customer Insights. Puede quitar la conexión existente como un Administrador global en el entorno de Dataverse. Puede tomar un par de horas completar los cambios.

1. Vaya a [Power Apps](https://make.powerapps.com).
1. Seleccione el entorno desde el selector de entornos.
1. Vaya a **Soluciones**
1. Desinstale o quite la solución que lleva por nombre complemento de tarjeta de cliente **Dynamics 365 Customer Insights (versión preliminar)**.

O 

1. Abra su entorno de Dataverse.
1. Vaya a **Configuración avanzada** > **Soluciones**.
1. Desinstale la solución **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Copiar el entorno de configuración

Como administrador, puede optar por copiar la configuración de un entorno existente cuando crea uno nuevo. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla de las opciones de configuración en la configuración del entorno.":::

Verá una lista de todos los entornos disponibles de su organización desde los que puede copiar datos.

Se copian los siguientes valores de configuración:

- Fuentes de datos ingeridas e importadas
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

## <a name="set-up-a-copied-environment"></a>Configure un entorno copiado

Cuando copia la configuración del entorno, los siguientes datos *no* se copian:

- Perfiles de clientes.
- Credenciales del origen de datos. Debe especificar las credenciales para cada origen de datos y actualizar los orígenes de datos manualmente.
- Orígenes de datos de la carpeta Common Data Model y el lago de datos administrado por Dataverse. Tendrá que crear esos orígenes de datos manualmente con el mismo nombre que en el entorno de origen.
- Secretos de conexión que se utilizan para exportaciones y enriquecimientos. Tiene que volver a autenticar las conexiones y luego reactivar enriquecimientos y exportaciones. 

Al copiar un entorno, verá un mensaje de confirmación de que se ha creado el nuevo entorno. Seleccione **Ir a orígenes de datos** para ver la lista de orígenes de datos.

Todos los orígenes de datos mostrarán un estado de **Credenciales necesarias**. Edite los orígenes de datos e introduzca las credenciales para actualizarlas.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orígenes de datos que se copiaron y necesitan autenticación.":::

Después de actualizar los orígenes de datos, vaya a **Datos** > **Unificar**. Aquí encontrará configuraciones del entorno de origen. Edítelos si es necesario o seleccione **Ejecutar** para iniciar el proceso de unificación de datos y crear la entidad de cliente unificado.

Cuando se haya completado la unificación de datos, vaya a **Medidas** y **Segmentos** para actualizarlos también.

Antes de reactivar exportaciones y enriquecimientos, vaya a **Administración** > **Conexiones** para volver a autenticar las conexiones en su nuevo entorno.

## <a name="change-the-owner-of-an-environment"></a>Cambiar el propietario de un entorno

Si bien varios usuarios pueden tener permisos de administrador en Customer Insights, solo un usuario es el propietario de un entorno. De forma predeterminada, es el administrador el que crea un entorno inicialmente. Como administrador de un entorno, puede asignar la propiedad a otro usuario con permisos de administrador.

1. Seleccione el selector **Entorno** en el encabezado de la aplicación.

1. Seleccione el icono de **Editar**.

1. En el cuadro de diálogo **Editar entorno**, vaya al paso **Información básica**.

1. En el campo **Cambiar propietario del entorno**, elija el nuevo propietario del entorno.  

1. Seleccione **Revisar y terminar**, luego **Actualizar** para aplicar los cambios. 

## <a name="claim-ownership-of-an-environment"></a>Reclamar la propiedad de un entorno

Si el propietario de un entorno deja la organización o se elimina su cuenta de usuario, el entorno no tendrá propietario. Un usuario con permisos de administrador puede reclamar la propiedad y convertirse en el nuevo propietario. Pueden seguir siendo propietarios del entorno o [cambiar la propiedad a otro administrador](#change-the-owner-of-an-environment). 

Para reclamar la propiedad, seleccione el botón **Asumir la propiedad** que se muestra en la parte superior de cada página en Customer Insights cuando el propietario original deja la organización.

## <a name="reset-an-existing-environment"></a>Restablecimiento de un entorno existente

Como propietario de un entorno, puede restablecer el entorno a un estado vacío si desea eliminar todas las configuraciones y los datos ingeridos.

1.  Seleccione el selector **Entorno** en el encabezado de la aplicación. 

2.  Seleccione el entorno que desee restablecer y seleccione los puntos suspensivos (**...**). 

3. Elija la opción **Restablecer**. 

4.  Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Restablecer**.

## <a name="delete-an-existing-environment"></a>Eliminar un entorno existente

Como propietario de un entorno, puede eliminar un entorno que administre.

1.  Seleccione el selector **Entorno** en el encabezado de la aplicación.

2.  Seleccione el entorno que desee restablecer y seleccione los puntos suspensivos (**...**). 

3. Elija la opción **Eliminar**. 

4.  Para confirmar la eliminación, introduzca el nombre del entorno y seleccione **Eliminar**.

> [!NOTE]
> Eliminar un entorno no elimina la asociación a un entorno de Dataverse. Aprenda a [quitar una conexión existente a un entorno de Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
