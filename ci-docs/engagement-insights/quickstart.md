---
title: Introducción al producto de inicio rápido
description: Experiencia de primera ejecución para configurar la funcionalidad de las conclusiones sobre la interacción.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: eebe51d343f6afbed52a66c52ab6a60eb5cd410367fb2e4409eb8679f357c91e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033928"
---
# <a name="first-run-experience"></a>Experiencia de primera ejecución

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Conclusiones sobre la interacción, una funcionalidad de Dynamics 365 Customer Insights, le permite recopilar y medir el comportamiento de los clientes en su sitio web. Este artículo explica cómo registrarse para obtener conclusiones sobre la interacción, configurar un área de trabajo, agregar miembros y realizar cambios.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>Registrarse para una demostración de las conclusiones sobre la interacción

Debe tener una cuenta de usuario Azure Active Directory de Microsoft activa. 

1. Abra el sitio web [conclusiones sobre la interacción](https://pi.dynamics.com/). 

1. Inicie sesión con una cuenta profesional o educativa.

1. Seleccione su región y use la casilla de verificación para indicar si desea optar por recibir actualizaciones y ofertas por correo electrónico.

1. Revise las **Condiciones de uso de conclusiones sobre la interacción (versión preliminar)** y la **Declaracion de privacidad** y luego seleccione **Explorar la demostración** para aceptarlas.

1. Explore el producto utilizando un conjunto de datos de muestra. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>Configurar su primera área de trabajo en conclusiones sobre la interacción

Un área de trabajo es la forma en que almacena y administra eventos e informes.

Para crear su primera área de trabajo

1. En conclusiones sobre la interacción, seleccione **Conectar sus datos** para iniciar el asistente. 

:::image type="content" source="media/banner.png" alt-text="Página Customer Insights con botón para conectar sus datos.":::

2. Elija el tipo de actividad que desea medir en una nueva área de trabajo. Actualmente, solo está disponible **Actividad del sitio web**. **Actividad de la aplicación** y **Actividad del dispositivo** estarán disponibles en versiones futuras.

1. Seleccione **Siguiente** para confirmar y crear el área de trabajo.

1. Agregue un fragmento de código a su sitio web para comenzar a recibir datos en conclusiones de la interacción. Puede implementar esto de inmediato o compartir el código y las instrucciones con el administrador de su sitio web. Para encontrar el fragmento de código más tarde, vaya a **Administración** > **Área de trabajo** > **Guía de instalación**.

   > [!IMPORTANT]
   > Los datos no se mostrarán en el área de trabajo hasta que el código se haya implementado en su sitio web.

1. Seleccione **Listo** para abrir su nueva área de trabajo. 

## <a name="add-members-to-an-existing-workspace"></a>Agregar miembros a un área de trabajo existente

De forma predeterminada, solo la persona que creó el área de trabajo tiene acceso a ella. Puede agregar otros usuarios de su organización a un área de trabajo existente en cualquier momento.

:::image type="content" source="media/add-members.png" alt-text="Página de miembros con una llamada en el botón Agregar miembros.":::

1. Vaya a **Administración** > **Área de trabajo** > **Miembros**.

2. Seleccione **Agregar miembros**. Utilice el cuadro **Miembros** para agregar a otras personas en su organización. Puede agregar varios miembros a la vez.

3. Seleccione un **Rol** para asignarlo a los nuevos miembros. Actualmente, solo está disponible la opción **Administrador del área de trabajo**. Se agregarán otros roles en versiones futuras.

4. Seleccione **Añadir miembros** para confirmar.

Para eliminar miembros de un espacio de trabajo, seleccione **...** junto a sus nombres en la página **Miembros** y luego seleccione **Borrar** en el menú desplegable.

## <a name="edit-a-workspace"></a>Editar un área de trabajo

Puede editar los detalles de las áreas de trabajo existentes en cualquier momento.

:::image type="content" source="media/change-workspace-settings.png" alt-text="Página de configuración del área de trabajo con una llamada en el nombre y la descripción del área de trabajo.":::

1. Vaya a **Administración** > **Área de trabajo** > **Configuración**.

1. Cambie el **Nombre** para su área de trabajo.

1. Seleccione **Guardar** para aplicar los cambios.

## <a name="add-another-new-workspace"></a>Agregar otra nueva área de trabajo

:::image type="content" source="media/workspace-switcher.png" alt-text="Página de Customer Insights con una llamada en el panel de navegación y una descripción.":::

Puede crear áreas de trabajo adicionales para clasificar sus datos.

1. En el selector de área de trabajo, seleccione **Nueva área de trabajo**.

1. Introduzca un **Nombre** y una **Descripción** opcional.

1. Seleccione **Crear**.

## <a name="switch-between-workspaces"></a>Cambiar entre áreas de trabajo

Para cambiar entre áreas de trabajo, seleccione el selector de áreas de trabajo. También puede crear una nueva área de trabajo o seleccionar **Muestra web** para ver informes y probar funciones con datos de ejemplo. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]