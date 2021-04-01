---
title: Relaciones entre entidades y rutas de entidades
description: Cree y administre relaciones entre entidades de múltiples fuentes de datos.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595233"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="51e64-103">Relaciones entre entidades</span><span class="sxs-lookup"><span data-stu-id="51e64-103">Relationships between entities</span></span>

<span data-ttu-id="51e64-104">Las relaciones ayudan a conectar entidades y generar un gráfico de sus datos cuando las entidades comparten un identificador común (clave externa) al que se puede hacer referencia de una entidad a otra.</span><span class="sxs-lookup"><span data-stu-id="51e64-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="51e64-105">Las entidades conectadas le permiten definir segmentos y medidas basadas en múltiples orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="51e64-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="51e64-106">Existen dos tipos de relaciones:</span><span class="sxs-lookup"><span data-stu-id="51e64-106">There are two types of relationships.</span></span> <span data-ttu-id="51e64-107">Relaciones del sistema no editables, que se crean automáticamente, y relaciones personalizadas creadas y configuradas por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="51e64-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="51e64-108">Durante los procesos de coincidencia y combinación, las relaciones del sistema se crean detrás de escena en función de la coincidencia inteligente.</span><span class="sxs-lookup"><span data-stu-id="51e64-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="51e64-109">Estas relaciones ayudan a relacionar los registros del perfil del cliente con los registros de otras entidades correspondientes.</span><span class="sxs-lookup"><span data-stu-id="51e64-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="51e64-110">El siguiente diagrama ilustra la creación de tres relaciones del sistema cuando la entidad de cliente coincide con entidades adicionales para producir la entidad Perfil de cliente final.</span><span class="sxs-lookup"><span data-stu-id="51e64-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="51e64-111">![Creación de relación](media/relationships-entities-merge.png "Creación de relación")</span><span class="sxs-lookup"><span data-stu-id="51e64-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="51e64-112">La **relación *CustomerToContact*** fue creada entre la entidad Cliente y la entidad Contacto.</span><span class="sxs-lookup"><span data-stu-id="51e64-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="51e64-113">La entidad Cliente obtiene el campo de clave **Contact_contactId** para relacionarse con el campo de clave de la entidad Contacto **contactId**.</span><span class="sxs-lookup"><span data-stu-id="51e64-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="51e64-114">La **relación *CustomerToContact*** fue creada entre la entidad Cliente y la entidad Cuenta.</span><span class="sxs-lookup"><span data-stu-id="51e64-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="51e64-115">La entidad Cliente obtiene el campo de clave **Account_accountId** para relacionarse con el campo de clave de la entidad Cuenta **accountId**.</span><span class="sxs-lookup"><span data-stu-id="51e64-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="51e64-116">La **relación *CustomerToWebAccount*** fue creada entre la entidad Cliente y la entidad WebAccount.</span><span class="sxs-lookup"><span data-stu-id="51e64-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="51e64-117">La entidad Cliente obtiene el campo de clave **WebAccount_webaccountId** para relacionarse con el campo de clave de la entidad WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="51e64-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="51e64-118">Crear una relación</span><span class="sxs-lookup"><span data-stu-id="51e64-118">Create a relationship</span></span>

<span data-ttu-id="51e64-119">Defina relaciones personalizadas en la página **Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="51e64-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="51e64-120">Cada relación consta de una entidad de origen (la entidad que posee la clave externa) y una entidad de destino (la entidad a la que apunta la clave externa de la entidad de origen).</span><span class="sxs-lookup"><span data-stu-id="51e64-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="51e64-121">En las informaciones de público, vaya a **Datos** > **Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="51e64-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="51e64-122">Selecciona **Nueva relación**.</span><span class="sxs-lookup"><span data-stu-id="51e64-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="51e64-123">En el panel **Agregar relación**, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="51e64-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="51e64-124">![Escriba los detalles de la relación](media/relationships-add.png "Escriba los detalles de la relación")</span><span class="sxs-lookup"><span data-stu-id="51e64-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="51e64-125">**Nombre de la relación**: Nombre que refleja el propósito de la relación (por ejemplo, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="51e64-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="51e64-126">**Descripción**: Descripción de la relación.</span><span class="sxs-lookup"><span data-stu-id="51e64-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="51e64-127">**Entidad de origen**: Seleccione la entidad que se utiliza como origen de la relación (por ejemplo, WebLog).</span><span class="sxs-lookup"><span data-stu-id="51e64-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="51e64-128">**Cardinalidad** : Seleccione la cardinalidad de los registros de la entidad de origen.</span><span class="sxs-lookup"><span data-stu-id="51e64-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="51e64-129">Por ejemplo, "muchos" significa que varios registros Weblog están relacionados con una WebAccount.</span><span class="sxs-lookup"><span data-stu-id="51e64-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="51e64-130">**Campo de clave de origen**: Representa el campo de clave externa en la entidad de origen.</span><span class="sxs-lookup"><span data-stu-id="51e64-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="51e64-131">Por ejemplo, WebLog tiene el campo de clave externa **accountId**.</span><span class="sxs-lookup"><span data-stu-id="51e64-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="51e64-132">**Entidad de destino**: Seleccione la entidad que se utiliza como destino de la relación (por ejemplo, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="51e64-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="51e64-133">**Cardinalidad de destino**: Seleccione la cardinalidad de los registros de la entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="51e64-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="51e64-134">Por ejemplo, "uno" significa que varios registros Weblog están relacionados con una WebAccount.</span><span class="sxs-lookup"><span data-stu-id="51e64-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="51e64-135">**Campo de clave de destino** : Este campo representa el campo de clave de la entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="51e64-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="51e64-136">Por ejemplo, WebAccount tiene el campo de clave **accountId**.</span><span class="sxs-lookup"><span data-stu-id="51e64-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="51e64-137">Solo se admiten relaciones de varios a uno y de uno a uno.</span><span class="sxs-lookup"><span data-stu-id="51e64-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="51e64-138">Se pueden crear relaciones de varios a varios utilizando dos relaciones de varios a uno y una entidad de vínculo (una entidad que se utiliza para conectar la entidad de origen y la entidad de destino).</span><span class="sxs-lookup"><span data-stu-id="51e64-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="51e64-139">Eliminar una relación</span><span class="sxs-lookup"><span data-stu-id="51e64-139">Delete a relationship</span></span>

1. <span data-ttu-id="51e64-140">En las informaciones de público, vaya a **Datos** > **Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="51e64-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="51e64-141">Active las casillas para las relaciones que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="51e64-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="51e64-142">Seleccione **Eliminar** en la parte superior de la tabla **Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="51e64-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="51e64-143">Confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="51e64-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="51e64-144">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="51e64-144">Next step</span></span>

<span data-ttu-id="51e64-145">Las relaciones del sistema y personalizadas se utilizan para crear segmentos basados en varios orígenes de datos que ya no están en desconectados.</span><span class="sxs-lookup"><span data-stu-id="51e64-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="51e64-146">Para más información, vea [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="51e64-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]