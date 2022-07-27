---
title: Enriquezca los perfiles de los clientes con datos de Microsoft Office 365 (vista previa)
description: Utilice datos de propiedad de Microsoft Office para enriquecer los perfiles de sus clientes con datos de interacción.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055695"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Enriquezca los perfiles de los clientes con datos de Microsoft Office 365 (vista previa)

Usar datos de Microsoft Office 365 para enriquecer los perfiles de su cuenta de cliente con información sobre los compromisos a través de aplicaciones de Office 365. Los datos de participación consisten en el correo electrónico y la actividad de la reunión, que se agrega a nivel de cuenta. Por ejemplo, la cantidad de correos electrónicos de una cuenta comercial o la cantidad de reuniones con la cuenta. No se ponen a disposición datos sobre usuarios individuales.

## <a name="supported-countries-or-regions"></a>Países o regiones compatibles

Actualmente admitimos las siguientes regiones: Reino Unido, Europa, América del Norte.

## <a name="prerequisites"></a>Requisitos previos

- Una licencia activa de Office 365 cloud.
- [Perfiles de clientes unificados](customer-profiles.md) basados en [cuentas de negocio](work-with-business-accounts.md).
- Una [organización asociada de Microsoft Dataverse](create-environment.md#step-3-connect-to-microsoft-dataverse) en su entorno de Customer Insights.
- Permisos de [administrador](permissions.md#admin).
- Consentimiento de su administrador de inquilinos de Office 365 para usar datos de Office 365 para proporcionar **Perspectivas para la organización** dentro de las aplicaciones de Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurar el enriquecimiento

1. Vaya a **Datos** > **Enriquecimiento** y seleccione la pestaña **Descubrir**.

1. Seleccione **Enriquecer mis datos** en la ventana **Involucración de cuenta**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Ventana de interacción con cuenta.":::

1. Revise el resumen y luego seleccione **Siguiente**.

1. Introduzca las direcciones de correo electrónico de su organización para las cuales se agregarán los datos de Office. Solo los datos de las direcciones de correo electrónico enumeradas se procesan para la comunicación relevante. Una práctica recomendada es utilizar grupos de correo electrónico, por ejemplo, *Equipo de ventas de EE. UU.*, que se gestionan fácilmente en Office 365. El número de direcciones de correo electrónico en los grupos se resuelve y se muestra. La cantidad total de direcciones de correo electrónico debe ser de al menos 2 y no puede exceder las 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Direcciones de correo electrónico de participación de la cuenta.":::

1. Revisar y dar su consentimiento para [Admistrador de consentimiento de inquilino de Office 365](#office-365-tenant-administrator-consent) seleccionando **Estoy de acuerdo**.

1. Seleccione **Siguiente**.

1. Seleccione el **Conjunto de datos del contacto** y elija el perfil que quiere enriquecer. Seleccione **Siguiente**.

1. Asigne el campo de dirección de correo electrónico de contacto y seleccione **Siguiente**.

1. Proporcione un **nombre** para el enriquecimiento y la **entidad de salida**.

1. Seleccione **Guardar enriquecimiento** después de revisar sus opciones.

1. Seleccione **Cerrar** para volver a la página **Enriquecimientos**.

### <a name="office-365-tenant-administrator-consent"></a>Consentimiento del administrador del inquilino de Office 365

Se requiere el consentimiento del administrador del inquilino de Office 365 para activar el enriquecimiento. Se envía un correo electrónico a los administradores de inquilinos de Office 365 cuando se guarda el enriquecimiento, lo que les pide que revisen y den su consentimiento para permitir que las aplicaciones de Dynamics 365 utilicen los datos de Office 365 para proporcionar **Perspectivas para la organización**. El administrador del inquilino de Office 365 también puede dar su consentimiento directamente en su consola de administración de Office 365, seleccionando **Perspectivas para la organización**.

## <a name="running-the-enrichment-for-the-first-time"></a>Ejecutar el enriquecimieneto por primera vez

Cuando se inicia el enriquecimiento por primera vez, después de que el administrador del inquilino de Office 365 ha dado su consentimiento, comienza la descarga de datos de Office 365. Este proceso lleva algo de tiempo. Se programará la primera ejecución de enriquecimiento con un retraso de seis horas. Puede ver la cantidad de días que cubren los datos en la página de descripción general de la participación de la cuenta después de que finaliza el enriquecimiento. Con un gran volumen de datos, vuelva a ejecutar el enriquecimiento después de unos días. Asegura que los datos estén completos durante todo el período de tiempo, que es un año.

Según el tamaño de los datos de Office, es posible que la ejecución de enriquecimiento demore varias horas en completarse.

Cuando ejecuta un enriquecimiento, Microsoft procesará los datos dentro del límite de cumplimiento de Office 365 para crear información agregada, que luego se agrega a su entorno de Customer Insights. No hay datos a nivel individual (por ejemplo, el cuerpo de cualquier correo electrónico o invitación de calendario) disponible para los usuarios de Customer Insights.

Para iniciar el proceso de enriquecimiento, seleccione **Ejecutar**.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Ver los resultados del enriquecimiento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Esta es la entidad de *Office*. La *Office_UserEntity* contiene los id. de Active Directory para las direcciones de correo electrónico que se eligieron durante la configuración del enriquecimiento.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Vista previa de resultados después de ejecutar el proceso de enriquecimiento.":::

Todos los datos se agregan hasta el nivel de la cuenta. El sistema calcula un puntaje de participación, que varía de 0 a 100, para cada cuenta. La puntuación de participación proporciona una medida compuesta de la participación de la cuenta a través de correos electrónicos y reuniones en relación con sus otras cuentas. La siguiente lista contiene los datos agregados que proporciona el enriquecimiento de la participación de la cuenta:

| Datos                                                                              | Nombre columna                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Puntuación de interacción                                                                  |  EngagementScore                         |
| Número de correos electrónicos a la cuenta                                                       |  NoOfEmails_ToAccount                    |
| Número de correos electrónicos de la cuenta                                                     |  NoOfEmails_FromAccount                  |
| Número de reuniones iniciadas por la cuenta                                           |  NoOfMeetings_FromAccount                |
| Número de reuniones iniciadas por la organización                                 |  NoOfMeetings_ToAccount                  |
| Número de personas de su organización en reuniones con cuenta                  |  NoOfContactsInvolved_Meetings           |
| Número de personas de su organización en conversaciones por correo electrónico con la cuenta       |  NoOfContactsInvolved_Emails             |
| Número de personas de reuniones de la cuenta con su organización                  |  NoOfAccountContactsInvolved_Meetings    |
| Número de personas de la cuenta en conversaciones por correo electrónico con su organización       |  NoOfAccountContactsInvolved_Emails      |
| Fecha de inicio del compromiso (primer correo electrónico o reunión en los datos)                        |  EngagementStartDate                     |
| Días desde el último correo                                                             |  DaysSinceLastEmail                      |
| Días trascurridos desde la última reunión                                                           |  DaysSinceLastMeeting                    |
| Duración media de las reuniones                                                      |  AverageDuration_Of_Meetings             |
| Duración promedio de las respuestas por correo electrónico desde la cuenta                                    |  AverageDuration_Of_AccountEmailReplies  |
| Fecha de inicio de agregación                                                            |  AggregationStartDate                    |
| Nivel de agregación (año, mes o semana)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Vea datos de enriquecimiento en la tarjeta del cliente

La participación de la cuenta también se puede ver en las tarjetas de clientes individuales. Vaya a **Clientes** y seleccione un perfil de cliente. En la tarjeta del cliente, encontrará el puntaje de participación de la cuenta, el número total de correos electrónicos y el número total de reuniones acumuladas durante el último año. También encontrará gráficos que muestran el correo electrónico y el historial de reuniones.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Tarjeta de cliente con datos enriquecidos.":::

## <a name="next-steps"></a>Pasos siguientes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Por ejemplo, un segmento que contiene todos los clientes que tienen un valor superior a 60 para *días desde el último correo electrónico* y *días desde la última reunión*. Ese segmento contiene cuentas obsoletas que puede intentar reactivar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
