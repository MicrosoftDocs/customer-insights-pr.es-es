---
title: Preguntas más frecuentes de la prueba - Dynamics 365 Customer Insights
description: Soluciones a preguntas comunes relacionadas con la administración y la configuración de la versión de prueba de Customer Insights. Aprenda a resolver problemas específicos de la plataforma y la aplicación.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 46a67e58f79029246029e2d06789525c2131f100
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011908"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Preguntas frecuentes sobre la versión de prueba de Dynamics 365 Customer Insights

## <a name="sign-up"></a>Registro

### <a name="what-are-the-system-requirements-for-the-trial"></a>¿Cuáles son los requisitos del sistema para la prueba?

Esta aplicación es un servicio basado en la nube que no requiere software especial más allá de un explorador web actualizado, aunque se aplican algunas restricciones. Para obtener la mejor experiencia de prueba, evite acceder al sitio de prueba en modo incógnito y elija la ubicación de prueba más cercana a usted. [Más información acerca de los requisitos de aplicaciones web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>¿Cómo puedo registrarme para la prueba sin un inquilino de Microsoft 365?

Puede ingresar una dirección de correo electrónico que no sea del trabajo y crearemos una cuenta y un inquilino para usted.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>¿Puedo registrarme en varias aplicaciones de Dynamics 365, como Sales, Marketing y Customer Service?

Sí, puede hacerlo. Para ver todas las pruebas disponibles, [visite la página del centro de prueba](https://dynamics.microsoft.com/dynamics-365-free-trial). Puede usar la misma cuenta de correo electrónico para registrarse en diferentes pruebas. Sin embargo, no es posible tener varias aplicaciones en el mismo sitio de prueba. Cada prueba se realizará en una organización y una URL diferentes. Los datos de ejemplo no se compartirán entre aplicaciones.

## <a name="trial-app"></a>Aplicación de prueba

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>No recibí el correo electrónico con los detalles de la prueba después de registrarme, ¿qué debo hacer?

Cuando se registre para la prueba, recibirá un correo electrónico con los detalles de la prueba. Si no ve el correo electrónico en su bandeja de entrada, revise su carpeta de correo no deseado. Alternativamente, utilice los siguientes pasos para acceder a su aplicación:

1. Vaya al sitio de prueba y seleccione **Probar gratis**.
1. Ingrese la dirección de correo electrónico que utilizó para registrarse en la prueba. Será redirigido a su aplicación de prueba.

### <a name="how-do-i-add-more-users-to-a-trial"></a>¿Cómo agrego más usuarios a una prueba?

Para agregar usuarios, vaya al [Centro de administración de Microsoft 365](https://admin.microsoft.com) utilizando la cuenta de administrador de la prueba. Siga las [instrucciones del centro de administración](/microsoft-365/admin/add-users/add-users) para agregar usuarios hasta el límite de la licencia de prueba. Si el usuario que está agregando ya tiene una cuenta de Microsoft 365, asígnele un rol de seguridad apropiado en la organización de prueba. Para más información, consulte [Asignar un rol de seguridad a un usuario](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>¿Cuántos usuarios puedo agregar a mi entorno de prueba?

Puede agregar un número ilimitado de usuarios al entorno de prueba.

### <a name="how-do-i-reset-the-trial-environment"></a>¿Cómo restablezco el entorno de la versión de prueba?

No puede restablecer el entorno de la versión de prueba. Sin embargo, puede esperar a que finalice el período de prueba y luego registrarse nuevamente para una nueva prueba.

## <a name="trial-expiration-and-extension"></a>Caducidad y ampliación del período de prueba

### <a name="how-do-i-extend-the-trial"></a>¿Cómo puedo ampliar la duración de la versión de prueba?

Puede extender la prueba en la aplicación directamente. Puede extender su prueba una vez.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>¿Puedo convertir la versión de prueba en una licencia de pago?

Por lo general, recomendamos comenzar de cero con sus propios datos al actualizar a la versión de pago de Customer Insights. 

Opcionalmente, si solo usa Customer Insights, puede copiar sus datos desde un entorno de prueba si compra Customer Insights. Debe ser el administrador de la versión de prueba de Customer Insights y el administrador global de su inquilino de Microsoft 365 o administrador de Dynamics 365 en su organización para migrar la configuración de un entorno de prueba a un entorno de pago.

Cuando inicie sesión por primera vez en su instancia de pago de Customer Insights, se le pedirá que cree un entorno nuevo. En este proceso, puede optar por copiar la configuración de un entorno existente y migrar la mayoría de las opciones de configuraciones. Si tiene los permisos mencionados anteriormente, el entorno de prueba se mostrará en esta lista. Para obtener más información, consulte [Copiar la configuración del entorno](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>¿Cuáles son los límites y las cuotas de la prueba?

- No puede usar su propia cuenta de Azure Data Lake Storage para almacenar datos de salida durante una prueba de Customer Insights. Sin embargo, puede ingerir datos de una cuenta de Data Lake Storage.
- Puede almacenar hasta 3 GB de datos en el entorno de Dataverse que se aprovisiona automáticamente cuando inicia una prueba de Customer Insights.

## <a name="customer-insights-specific-questions"></a>Customer Insights: preguntas específicas

### <a name="how-do-i-start-using-the-trial"></a>¿Cómo empiezo a utilizar la versión de prueba?

Después de registrarse para la prueba, llegará a la pantalla principal de la aplicación. La pantalla principal proporciona enlaces a guías de usuario y tutoriales. Para obtener más información, visite los enlaces en [Recursos adicionales](trial-signup.md#additional-resources) en la página de registro de la versión de prueba.

### <a name="what-features-are-available-in-the-trial"></a>¿Qué funciones están disponibles en la versión de prueba?

La mayoría de las funciones de las capacidades de Customer Insights están disponibles en la versión de prueba.

Las características siguientes **no están disponibles**:

- No puede crear nuevos entornos que usen su propia cuenta de Azure Data Lake Storage.
- No puede eliminar el entorno de la prueba.

### <a name="how-long-does-the-trial-last"></a>¿Cuál es la duración de la prueba?

La prueba de Customer Insights dura 30 días. Puede extender la prueba una vez después de 23 días cuando inicie sesión en su entorno de prueba.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>¿Cómo elimino datos de ejemplo de la prueba?

No puede eliminar los datos de ejemplo de la prueba.
