---
title: Usar la propia cuenta de Azure Data Lake Storage Gen2
author: mukeshpo
description: Conozca los requisitos para usar su propia cuenta de Azure Data Lake Storage para almacenar datos de Customer Insights.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833931"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Usar la propia cuenta de Azure Data Lake Storage Gen2

Dynamics 365 Customer Insights le proporciona la opción de almacenar todos sus datos en [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Al guardar datos en Data Lake Storage, usted acepta que los datos se transfieran y almacenen en la ubicación geográfica adecuada para esa cuenta de almacenamiento de Azure. Para obtener más información, consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Los administradores de Customer Insights pueden [crear entornos](create-environment.md) y [especificar la opción de almacenamiento de datos](create-environment.md#step-2-configure-data-storage) en el proceso.

## <a name="prerequisites-to-use-your-storage-account"></a>Requisitos previos para usar su cuenta de almacenamiento

- Las cuentas de Azure Data Lake Storage deben estar en la misma región de Azure que seleccionó al crear el entorno de Customer Insights. Puede comprobar la región del entorno de Customer Insights en **Administración** > **Sistema** > **Acerca de**.
- Data Lake Storage debe ser Gen2 y debe tener un [espacio de nombres jerárquico habilitado](/azure/storage/blobs/create-data-lake-storage-account). Las cuentas de almacenamiento Gen1 no son compatibles.
- Un contenedor llamado `customerinsights` tiene que existir en la cuenta de almacenamiento. Debe crearlo antes de usar su propio Data Lake Storage en Customer Insights. El administrador que configure el entorno de Customer Insights necesita el rol de colaborador de datos de Storage Blob o Propietario de datos de Storage Blob en la cuenta de almacenamiento o en el contenedor de `customerinsights`. Para obtener más información sobre la asignación de permisos en una cuenta de almacenamiento, consulte [Crear una cuenta de almacenamiento](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Conectar Customer Insights con su cuenta de almacenamiento

Cuando cree un nuevo entorno, asegúrese de que exista la cuenta de Data Lake Storage y de que se cumplan todos los requisitos previos.

1. En el paso **Almacenamiento de datos** durante la creación del entorno, ajuste **Guardar datos de salida** en **Azure Data Lake Storage Gen2**.
1. Seleccione cómo **Conectarse al almacenamiento**. Puede elegir entre una opción basada en recursos y una opción basada en suscripción para la autenticación. Para obtener más información, consulte [Conectarse a una cuenta de Azure Data Lake Storage mediante el uso de una entidad de servicio de Azure](connect-service-principal.md).
   - Para la **Suscripción a Azure**, elija **Suscripción**, **Grupo de recursos** y **Cuenta de almacenamiento** que contiene el contenedor de `customerinsights`.
   - Para la **Clave de cuenta**, proporcione el **Nombre de cuenta** y la **Clave de cuenta** para la cuenta de Data Lake Storage. El uso de este método de autenticación implica que se le informe si su organización rota las claves. Debe [actualizar la configuración del entorno](manage-environments.md#edit-an-existing-environment) con la nueva clave cuando se gira.

Cuando se completan procesos del sistema, como ingestión de datos, el sistema crea las carpetas correspondientes en la cuenta de almacenamiento. Los archivos de datos y los archivos *model.json* se crean y se agregan a carpetas cuyo nombre se basa en el del proceso.

Si crea varios entornos de Customer Insights y elige guardar las entidades de salida de esos entornos en su cuenta de almacenamiento, Customer Insights crea carpetas independientes para cada entorno con `ci_environmentID` en el contenedor.
