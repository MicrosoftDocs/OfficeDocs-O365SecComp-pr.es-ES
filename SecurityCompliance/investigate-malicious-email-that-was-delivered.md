---
title: Buscar e investigar el correo electrónico malintencionado que se entregó (Office 365 información sobre amenazas)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
description: Obtenga información sobre cómo usar la información sobre amenazas para buscar e investigar el correo electrónico malintencionado.
ms.openlocfilehash: b6d4f8a5d1fcfce4461b91796b1264f94d1eb4d1
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014922"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a>Buscar e investigar el correo electrónico malintencionado que se entregó (Office 365 información sobre amenazas)

[Información sobre amenazas de Office 365](office-365-ti.md) le permite investigar las actividades que los usuarios correr el riesgo y tomar medidas para proteger a su organización. Por ejemplo, si son parte del equipo de seguridad de su organización, puede encontrar e investigar los mensajes de correo electrónico sospechosos que se entregaron a los usuarios. Puede hacerlo mediante [El Explorador de amenaza](get-started-with-ti.md#threat-explorer).
  
> [!NOTE]
> Información sobre amenazas de Office 365 está disponible en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, información sobre amenazas de Office 365 puede adquirirse como un complemento. (Como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Agregar suscripciones**.) Para obtener más información, vea [Descripción del servicio Office 365 plataforma: seguridad de Office 365 &amp; centro de cumplimiento](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento de Office 365 para profesionales](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
## <a name="before-you-begin"></a>Antes de comenzar...

Asegúrese de que se cumplen los siguientes requisitos:
  
- Su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md) y [asignar licencias a los usuarios de Office 365 para la empresa](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
- [Registro de auditoría de Office 365](turn-audit-log-search-on-or-off.md) está activado para la organización. 
    
- Su organización tiene las directivas definidas para contra correo no deseado, anti-malware, contra suplantación de identidad y así sucesivamente. Vea [administración de la seguridad de Office 365 de amenazas &amp; centro de cumplimiento](threat-management.md).
    
- Es un administrador global de Office 365, o tiene el Administrador de seguridad o la función de búsqueda y purgar asignado en la seguridad &amp; centro de cumplimiento. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Trabaja con mensajes de correo electrónico sospechosos

Los atacantes malintencionados se puede enviar correo a los usuarios para probar y phishing sus credenciales y obtener acceso a su información confidencial corporativa! Con el fin de evitar esto, debe usar los servicios de protección de amenaza ofrecidos por Office 365, como Exchange Online Protection y avanzada de protección contra amenazas. Sin embargo, hay veces cuando un atacante podría enviar correo a los usuarios que contiene una dirección URL y realizar sólo posterior en ese punto de la dirección URL a contenido malintencionado (malware, etcetera). Como alternativa, los clientes pueden obtener demasiado tarde que un usuario en su organización se ha puesto en peligro y, mientras que el usuario se ve comprometido, un atacante utiliza esa cuenta para enviar correo electrónico a otros usuarios de su compañía. Como parte de la limpieza de estos dos escenarios, es posible que desee quitar mensajes de correo electrónico de las bandejas de entrada del usuario. En estas situaciones, puede aprovechar el Explorador de amenaza para buscar y quitar los mensajes de correo electrónico!
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Buscar y eliminar el correo electrónico sospechoso que se entregó

> [!TIP]
> [Explorador de amenaza](get-started-with-ti.md#threat-explorer) (también denominada Explorador), es un informe eficaces que puede servir para varios propósitos, por ejemplo, buscar y eliminar mensajes, que identifica la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una mayor investigación. El siguiente procedimiento se centra en usar el explorador para buscar y eliminar el correo electrónico malintencionado de buzones de correo de los destinatarios. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. Esto le llevará a la seguridad &amp; centro de cumplimiento. 
    
2. En el panel de navegación izquierdo, elija **administración de amenaza** \> **Explorer**.
    
3. En el menú Ver, elija **todos los correos electrónicos**.<br/>![Use el menú Ver para elegir entre correo electrónico y los informes de contenido](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Tenga en cuenta las etiquetas que aparecen en el informe, como **entregados**, **desconocido**o **entrega a no deseado**.<br/>![Explorador de amenaza que muestra datos para todos los correos electrónicos](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Dependiendo de las acciones que se tomaron en mensajes de correo electrónico para su organización, es posible que vea etiquetas adicionales, como **bloqueado** o **se reemplazó**.)
    
5. En el informe, elija **entregado** para ver solo los correos electrónicos que ha terminado en las bandejas de entrada de los usuarios.<br/>![Al hacer clic en "Entregar a no deseado" quita esos datos de vista](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Debajo del gráfico, revise la lista de **correo electrónico** debajo del gráfico.<br/>![Debajo del gráfico, ver una lista de los mensajes de correo electrónico que se han detectado](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. En la lista, elija un elemento para ver más detalles acerca de ese mensaje de correo electrónico. Por ejemplo, puede hacer clic en la línea de asunto para ver información sobre el remitente, los destinatarios, datos adjuntos y otros mensajes de correo electrónico similar.<br/>![Puede ver información adicional acerca de un elemento, incluidos los detalles y los datos adjuntos](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. Después de ver información acerca de los mensajes de correo electrónico, seleccione uno o más elementos en la lista para activar **+ acciones**.
    
9. Use la lista **+ acciones** para aplicar una acción, como **mover a eliminar** los elementos. Esto eliminará los mensajes seleccionados de los buzones de los destinatarios.<br/>![Cuando se selecciona uno o más mensajes de correo electrónico, puede elegir entre varias acciones disponibles](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>Temas relacionados

[Inteligencia sobre amenazas de Office 365](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Visualización de informes para la protección de amenaza avanzada de Office 365](view-reports-for-atp.md)
  

