---
title: Investigar y responder automáticamente a las amenazas en Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/04/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Empiece a usar la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2c64ea936170524811839db7c593d67bfe11a928
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "36762033"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>Investigar y responder automáticamente a las amenazas en Office 365

## <a name="overview"></a>Información general

[Protección contra amenazas avanzada de Office 365](office-365-atp.md) El plan 2 incluye capacidades de investigación y respuesta automatizadas (AIR) que pueden salvar el tiempo y el esfuerzo del equipo de operaciones de seguridad para tratar las alertas y las amenazas. Lea este artículo para empezar a usar las funcionalidades de AIR en Office 365. Para obtener más información sobre cómo funciona AIR, consulte [Automated Investigation and Response (Air) con Office 365](automated-investigation-response-office.md).

Con AIR, cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y comienza la investigación automatizada. Durante y después de un proceso de investigación automatizado, los administradores y el equipo de operaciones de seguridad pueden:

- [Ver los detalles de una investigación](#view-details-of-an-investigation)

- [Revisión y aprobación de acciones como resultado de una investigación](#review-and-approve-actions) 

- [Ver los detalles de una alerta relacionada con una investigación](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> Debe ser administrador global, administrador de seguridad, operador de seguridad o lector de seguridad para realizar las tareas descritas en este artículo. Para obtener más información, consulte [Microsoft 365 Security Center: roles y permisos](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).

## <a name="view-details-of-an-investigation"></a>Ver los detalles de una investigación

1. Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión. Esto le llevará al centro de seguridad & cumplimiento.

2. Realice una de las acciones siguientes:

    - Vaya al **** > **Panel**de administración de amenazas. Esto le llevará al [Panel de seguridad](security-dashboard.md). Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md). Seleccione un widget, como un **Resumen de investigaciones**.

    - Vaya a **** > **investigaciones**de administración de amenazas. 

    Cualquiera de estos métodos le lleva a una lista de investigaciones.

    ![Página principal de investigación para AIR](media/air-maininvestigationpage.png) 

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** . Se abrirá la página Detalles de la investigación, comenzando con el gráfico de investigación.

    ![Página de gráfico de investigación de aire](media/air-investigationgraphpage.png)

4. Use las distintas pestañas para obtener más información sobre la investigación.

## <a name="review-and-approve-actions"></a>Revisión y aprobación de acciones

En Office 365, las investigaciones automatizadas suelen dar como resultado una o varias acciones recomendadas. Sin embargo, no se lleva a cabo ninguna acción hasta que la aprueba el equipo de operaciones de seguridad. Use el siguiente procedimiento para revisar y aprobar acciones.

1. Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión. 

2. Vaya a **** > **investigaciones**de administración de amenazas.

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** . 

3. En la vista detalles de la investigación, seleccione la ficha **acciones** . Aquí se enumeran las acciones pendientes de aprobación.

4. Seleccione un elemento de la lista.

5. Seleccione **aprobar** para realizar la acción recomendada (o **rechazar** para cerrar la investigación sin emprender ninguna acción).

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Ver los detalles de una alerta relacionada con una investigación

Ciertos tipos de alertas desencadenan la investigación automática en Office 365. Para obtener más información, vea [alertas](automated-investigation-response-office.md#alerts). Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.

1. Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión. Esto le llevará al centro de seguridad & cumplimiento.

2. Vaya a **** > **investigaciones**de administración de amenazas.

3. En la lista de investigaciones, seleccione un elemento en la columna **ID** . 

4. Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.

5. Seleccione un elemento de la lista. Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.

6. Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir**o **notificar a los usuarios**. 

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Usar la API de actividad de administración de Office 365 para soluciones de informes personalizadas o de terceros

Si su organización usa una solución de informes personalizada o una solución de informes de terceros, puede ver información sobre las investigaciones automatizadas en esa solución mediante el uso de la API de actividad de administración 365 de Office.

Use los siguientes recursos para configurar esto:

|Recurso  |Descripción  |
|---------|---------|
|[Información general de las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.         |
|[Introducción a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos de Office 365. Siga los pasos de este artículo para configurarlo.          |
|[Referencia de las API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure AD. Lea este artículo para obtener más información sobre cómo funciona.        |
|[Esquema de la API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.         |

## <a name="next-steps"></a>Pasos siguientes

[Más información acerca de las alertas](alert-policies.md)

[Buscar y investigar manualmente el correo electrónico malintencionado que se entregó en Office 365](investigate-malicious-email-that-was-delivered.md)

[Obtener información sobre AIR en ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará](https://www.microsoft.com/microsoft-365/roadmap?filters=)