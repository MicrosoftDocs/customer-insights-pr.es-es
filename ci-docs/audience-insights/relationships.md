---
title: Relaciones entre entidades y rutas de entidades
description: Cree y administre relaciones entre entidades de múltiples fuentes de datos.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407050"
---
# <a name="relationships-between-entities"></a>Relaciones entre entidades

Las relaciones ayudan a conectar entidades y generar un gráfico de sus datos cuando las entidades comparten un identificador común (clave externa) al que se puede hacer referencia de una entidad a otra. Las entidades conectadas le permiten definir segmentos y medidas basadas en múltiples orígenes de datos.

Existen dos tipos de relaciones: Relaciones del sistema no editables, que se crean automáticamente, y relaciones personalizadas creadas y configuradas por los usuarios.

Durante los procesos de coincidencia y combinación, las relaciones del sistema se crean detrás de escena en función de la coincidencia inteligente. Estas relaciones ayudan a relacionar los registros del perfil del cliente con los registros de otras entidades correspondientes. El siguiente diagrama ilustra la creación de tres relaciones del sistema cuando la entidad de cliente coincide con entidades adicionales para producir la entidad Perfil de cliente final.

> [!div class="mx-imgBorder"]
> ![Creación de relación](media/relationships-entities-merge.png "Creación de relación")

- La **relación *CustomerToContact*** fue creada entre la entidad Cliente y la entidad Contacto. La entidad Cliente obtiene el campo de clave **Contact_contactId** para relacionarse con el campo de clave de la entidad Contacto **contactId**.
- La **relación _CustomerToContact_** fue creada entre la entidad Cliente y la entidad Cuenta. La entidad Cliente obtiene el campo de clave **Account_accountId** para relacionarse con el campo de clave de la entidad Cuenta **accountId**.
- La **relación _CustomerToWebAccount_** fue creada entre la entidad Cliente y la entidad WebAccount. La entidad Cliente obtiene el campo de clave **WebAccount_webaccountId** para relacionarse con el campo de clave de la entidad WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Crear una relación

Defina relaciones personalizadas en la página **Relaciones**. Cada relación consta de una entidad de origen (la entidad que posee la clave externa) y una entidad de destino (la entidad a la que apunta la clave externa de la entidad de origen).

1. En las informaciones de público, vaya a **Datos** > **Relaciones**.

2. Selecciona **Nueva relación**.

3. En el panel **Agregar relación**, proporcione la siguiente información:

   > [!div class="mx-imgBorder"]
   > ![Escriba los detalles de la relación](media/relationships-add.png "Escriba los detalles de la relación")

   - **Nombre de la relación**: Nombre que refleja el propósito de la relación (por ejemplo, **AccountWebLogs**).
   - **Descripción**: Descripción de la relación.
   - **Entidad de origen**: Seleccione la entidad que se utiliza como origen de la relación (por ejemplo, WebLog).
   - **Cardinalidad** : Seleccione la cardinalidad de los registros de la entidad de origen. Por ejemplo, "muchos" significa que varios registros Weblog están relacionados con una WebAccount.
   - **Campo de clave de origen**: Representa el campo de clave externa en la entidad de origen. Por ejemplo, WebLog tiene el campo de clave externa **accountId**.
   - **Entidad de destino**: Seleccione la entidad que se utiliza como destino de la relación (por ejemplo, WebAccount).
   - **Cardinalidad de destino**: Seleccione la cardinalidad de los registros de la entidad de destino. Por ejemplo, "uno" significa que varios registros Weblog están relacionados con una WebAccount.
   - **Campo de clave de destino** : Este campo representa el campo de clave de la entidad de destino. Por ejemplo, WebAccount tiene el campo de clave **accountId**.

> [!NOTE]
> Solo se admiten relaciones de varios a uno y de uno a uno. Se pueden crear relaciones de varios a varios utilizando dos relaciones de varios a uno y una entidad de vínculo (una entidad que se utiliza para conectar la entidad de origen y la entidad de destino).

## <a name="delete-a-relationship"></a>Eliminar una relación

1. En las informaciones de público, vaya a **Datos** > **Relaciones**.

2. Active las casillas para las relaciones que desee eliminar.

3. Seleccione **Eliminar** en la parte superior de la tabla **Relaciones**.

4. Confirme la eliminación.

## <a name="next-step"></a>Paso siguiente

Las relaciones del sistema y personalizadas se utilizan para crear segmentos basados en varios orígenes de datos que ya no están en desconectados. Para más información, vea [Segmentos](segments.md).
