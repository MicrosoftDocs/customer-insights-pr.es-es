---
title: Trabajar con datos de Customer Insights en Microsoft Dataverse
description: Aprenda a conectar Customer Insights y Microsoft Dataverse y comprenda las entidades de salida que se exportan a Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153425"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabajar con datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece la opción de hacer que las entidades de salida estén disponibles como [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integración permite compartir datos fácilmente y el desarrollo personalizado a través de un enfoque de código bajo / sin código. Las [entidades de salida](#output-entities) están disponibles como tablas en un entorno de Dataverse. Puede usar los datos para cualquier otra aplicación basada en tablas de Dataverse. Estas tablas permiten escenarios como flujos de trabajo automatizados a través de Power Automate o crear aplicaciones con Power Apps.

La conexión a su entorno de Dataverse también le permite [ingerir datos de los orígenes de datos locales usando flujos de datos de Power Platform y puertas de enlace](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Requisitos previos

- Los entornos de Customer Insights y Dataverse deben estar alojados en la misma región.
- Debe tener un rol de administrador global en el entorno de Dataverse. Compruebe si este entorno de [Dataverse está asociado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a ciertos grupos de seguridad y asegúrese de que se le agregue a esos grupos.
- Ningún otro entorno de Customer Insights está asociado con ese entorno de Dataverse al que desea conectarse. Aprenda cómo [quitar una conexión existente a un entorno de Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Un entorno de Microsoft Dataverse solo puede conectarse a una única cuenta de almacenamiento. Solo se aplica si configura el entorno para [usar Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Derecho de capacidad de almacenamiento de Dataverse

Una suscripción a Customer Insights le da derecho a capacidad adicional para la [capacidad de almacenamiento de Dataverse](/power-platform/admin/capacity-storage) existente en la organización. La capacidad adicional depende de la cantidad de perfiles que use su suscripción.

**Ejemplo**:

Supóngase que obtiene 15 GB de almacenamiento de base de datos y 20 GB de almacenamiento de archivos por cada 100 000 perfiles de clientes. Si su suscripción incluye 300 000 perfiles de clientes, su capacidad de almacenamiento total sería de 45 GB (3 x 15 GB) de almacenamiento de base de datos y 60 GB de almacenamiento de archivos (3 x 20 GB). Del mismo modo, si tiene una suscripción B2B con 30 000 cuentas, su capacidad de almacenamiento total sería de 45 GB (3 x 15 GB) de almacenamiento de base de datos y 60 GB de almacenamiento de archivos (3 x 20 GB).

La capacidad de registro no es incremental ni fija para su organización.

Para obtener más información sobre los derechos de capacidad detallados, consulte la [Guía de licencias de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Conectar un entorno de Dataverse a Customer Insights

El paso de **Microsoft Dataverse** le permite conectar Customer Insights con su entorno de Dataverse mientras [crea un entorno de Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="intercambio de datos con Microsoft Dataverse habilitado automáticamente para nuevos entornos netos.":::

Los administradores pueden configurar Customer Insights para conectar un entorno de Dataverse existente. Al proporcionar la URL del entorno de Dataverse, se conecta a su nuevo entorno de Customer Insights. Después de establecer la conexión entre Customer Insights y Dataverse, no cambie el nombre de la organización para el entorno de Dataverse. El nombre de la organización se utiliza en la URL de Dataverse y un nombre cambiado interrumpe la conexión con Customer Insights.

Si no desea utilizar un entorno de Dataverse existente, el sistema crea un nuevo entorno para los datos de Customer Insights en su inquilino. [Los administradores de Power Platform puede controlar quién puede crear entornos](/power-platform/admin/control-environment-creation). Cuando está configurando un nuevo entorno de Customer Insights y el administrador ha deshabilitado la creación de entornos de Dataverse para todos excepto los administradores, es posible que no pueda crear un nuevo entorno.

**Habilite el uso compartido de datos** con Dataverse seleccionando la casilla de verificación para compartir datos.

Si usa su propia cuenta de Data Lake Storage, también necesita el **Identificador de permisos**. Para obtener más información sobre cómo obtener el identificador de permisos, revise la siguiente sección.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habilitar el intercambio de datos con Dataverse desde su propio Azure Data Lake Storage (Vista previa)

La habilitación del uso compartido de datos con Microsoft Dataverse cuando el entorno [usa su propia cuenta de Azure Data Lake Storage](own-data-lake-storage.md) requiere alguna configuración adicional. El usuario que configura el entorno de Customer Insights debe tener como mínimo permisos de **Lector de datos de Storage Blob** en el contenedor de *CustomerInsights* de la cuenta de Azure Data Lake Storage.

1. Cree dos grupos de seguridad en su suscripción de Azure: un grupo de seguridad **Lector** y un grupo de seguridad **Colaborador** y establezca el servicio Microsoft Dataverse como propietario de ambos grupos de seguridad.
2. Administre la lista de control de acceso (ACL) en el contenedor de CustomerInsights en su cuenta de almacenamiento a través de estos grupos de seguridad. Agregue el servicio Microsoft Dataverse y cualquier aplicación empresarial basada en Dataverse como Dynamics 365 Marketing para el grupo de seguridad **Lector** con permisos de **solo lectura**. Agregue *solamente* la aplicación Customers Insights al grupo de seguridad **Colaborador** para otorgar a ambos permisos de **lectura y escritura** para escribir perfiles e información.

### <a name="limitations"></a>Limitaciones

Existen dos limitaciones al usar Dataverse con su propia cuenta de Azure Data Lake Storage:

- Hay una asignación de uno a uno entre una organización de Dataverse y una cuenta de Azure Data Lake Storage. Una vez que una organización de Dataverse está conectada a una cuenta de almacenamiento, no puede conectarse a otra cuenta de almacenamiento. Esta limitación impide que un Dataverse rellene varias cuentas de almacenamiento.
- El uso compartido de datos no funcionará si se necesita una configuración de Azure Private Link para obtener acceso a su cuenta de Azure Data Lake Storage porque está detrás de un firewall. Actualmente Dataverse no admite la conexión a puntos finales privados a través de Private Link.

### <a name="set-up-powershell"></a>Configurar PowerShell

Para ejecutar los scripts de PowerShell, primero tiene que configurar PowerShell como corresponde.

1. Instale la versión más reciente de [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. En su PC, seleccione la tecla de Windows en su teclado, busque **Windows PowerShell** y seleccione **Ejecutar como Administrador**.
   1. En la ventana de PowerShell que se abre, introduzca `Install-Module AzureAD`.
2. Importe tres módulos.
    1. En la ventana PowerShell, escriba `Install-Module -Name Az.Accounts` y siga los pasos.
    1. Repita para `Install-Module -Name Az.Resources` y `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Pasos de configuración

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
        - Este script de PowerShell agrega el control de acceso basado en roles para el servicio Microsoft Dataverse y cualquier aplicaciones empresarial basada en Dataverse. También actualiza la Lista de control de acceso (ACL) en el contenedor de Customer Insights para los grupos de seguridad creados con el script `CreateSecurityGroups.ps1`. El grupo Colaborador tendrá permiso *rwx* y el grupo Lector tendrá solo permiso *r-x*.
        - Ejecute este script de PowerShell en Windows PowerShell proporcionando el Id. de suscripción de Azure que contiene su Azure Data Lake Storage, el nombre de la cuenta de almacenamiento, el nombre del grupo de recursos y los valores de Id. del grupo de seguridad Lector y Colaborador. Abra el script de PowerShell en un editor para revisar información adicional y la lógica implementada.
        - Copie la cadena de resultados después de ejecutar correctamente el script. La cadena de resultados deberá tener un aspecto similar al siguiente: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Escriba la cadena de resultados copiada del paso anterior en el campo **Identificador de permisos** del paso de configuración del entorno para Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opciones de configuración para habilitar el uso compartido de datos desde su propia cuenta Azure Data Lake Storage con Microsoft Dataverse.":::

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

Si la eliminación de la conexión falla debido a las dependencias, deberá eliminarlas también. Para obtener más información, consulte [Eliminación de dependencias](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entidades de salida

Algunas entidades de salida de Customer Insights están disponibles como tablas en Dataverse. Las secciones siguientes describen el esquema esperado de estas tablas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecimiento](#enrichment)
- [Predicción](#prediction)
- [Suscripción de segmento](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Esta tabla contiene el perfil de cliente unificado de Customer Insights. El esquema para un perfil de cliente unificado depende de las entidades y atributos utilizados en el proceso de unificación de datos. Un esquema de perfil de cliente generalmente contiene un subconjunto de los atributos de la [Definición de Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La tabla AlternateKey contiene claves de las entidades que participaron en el proceso de unificación.

|Column  |Tipo  |Descripción  |
|---------|---------|---------|
|DataSourceName    |String         | Nombre del origen de datos. Por ejemplo: `datasource5`        |
|EntityName        | String        | Nombre de la entidad en Customer Insights. Por ejemplo: `contact1`        |
|AlternateValue    |String         |Id. alternativo que se asigna al Id. de cliente. Ejemplo: `cntid_1078`         |
|KeyRing           | Texto de varias líneas        | Valor JSON  </br> Muestra: [{"dataSourceName":" datasource5 ",</br>"entityName": "contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Id. del perfil de cliente unificado.         |
|AlternateKeyId     | GUID         |  GUID determinista de AlternateKey basado en msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Ejemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta tabla contiene actividades de los usuarios que están disponibles en Customer Insights.

| Column            | Tipo        | Descripción                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Id. del perfil de cliente                                                                      |
| ActivityId        | String      | ID interno de la actividad del cliente (clave principal)                                       |
| SourceEntityName  | String      | Nombre de la entidad de origen                                                                |
| SourceActivityId  | String      | Clave principal de la entidad de origen                                                       |
| ActivityType      | String      | Tipo de actividad semántica o nombre de la actividad personalizada                                        |
| ActivityTimeStamp | DATETIME    | Marca de tiempo de actividad                                                                      |
| Puesto             | String      | Título o nombre de la actividad                                                               |
| Descripción       | String      | Descripción de actividad                                                                     |
| Dirección URL               | String      | Enlace a una URL externa específica de la actividad                                         |
| SemanticData      | Cadena JSON | Incluye una lista de pares clave-valor para campos de mapeo semántico específicos para el tipo de actividad |
| RangeIndex        | String      | Marca de tiempo Unix utilizada para ordenar la línea de tiempo de la actividad y las consultas de rango efectivo |
| mydynci_unifiedactivityid   | GUID | ID interno de la actividad del cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta tabla contiene los datos de salida de las medidas basadas en atributos del cliente.

| Column             | Tipo             | Descripción                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Id. del perfil de cliente        |
| Medidas           | Cadena JSON      | Incluye una lista de pares clave-valor para el nombre y los valores de la medida para el cliente dado | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Id. del perfil de cliente |


### <a name="enrichment"></a>Enriquecimiento

Esta tabla contiene el resultado del proceso de enriquecimiento.

| Column               | Tipo             |  Descripción                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Id. del perfil de cliente                                 |
| EnrichmentProvider   | String           | Nombre del proveedor del enriquecimiento                                  |
| EnrichmentType       | String           | Tipo de enriquecimiento                                      |
| Valores               | Cadena JSON      | Lista de atributos producidos por el proceso de enriquecimiento |
| msdynci_enrichmentid | GUID             | GUID determinista generado a partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predicción

Esta tabla contiene el resultado de predicciones de modelo.

| Column               | Tipo        | Descripción                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Id. del perfil de cliente                                  |
| ModelProvider        | String      | Nombre del proveedor del modelo                                      |
| No                | String      | Nombre del modelo                                                |
| Valores               | Cadena JSON | Lista de atributos producidos por el modelo |
| msdynci_predictionid | GUID        | GUID determinista generado a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Suscripción de segmento

Esta tabla contiene información de suscripción de segmento de los perfiles de cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Id. del perfil de cliente        |
| SegmentProvider      | String       | Aplicación que publica los segmentos.      |
| SegmentMembershipType | String       | Tipo de cliente en el registro de suscripción de este segmento. Admite varios tipos, como cliente, contacto o cuenta. Predeterminado: Cliente  |
| Segmentos       | Cadena JSON  | Lista de segmentos únicos de los que el perfil del cliente es miembro      |
| msdynci_identifier  | String   | Identificador único del registro de suscripción de segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista generado por `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
