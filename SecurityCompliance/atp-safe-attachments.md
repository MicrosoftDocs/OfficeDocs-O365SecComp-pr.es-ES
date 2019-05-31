---
title: Datos adjuntos seguros de ATP de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
description: La característica datos adjuntos seguros proporciona comprobación del tiempo de los datos adjuntos de correo electrónico. Usar datos adjuntos seguros para proteger a su organización de archivos malintencionados envíe o reciba mensajes de correo electrónico.
ms.openlocfilehash: d2e83b602df6195d2b0e5a2762b8076d0b2bef75
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590573"
---
# <a name="office-365-atp-safe-attachments"></a>Datos adjuntos seguros de ATP de Office 365

## <a name="overview-of-office-365-atp-safe-attachments"></a>Información general sobre datos adjuntos seguros de ATP de Office 365

Los datos adjuntos seguros de ATP (junto con [vínculos seguros ATP](atp-safe-links.md)) forman parte de la [protección contra amenazas avanzada de Office 365](office-365-atp.md) (ATP). La característica de datos adjuntos seguros de ATP comprueba si los datos adjuntos de correo son malintencionados y, después, toma medidas para proteger la organización. La característica de datos adjuntos seguros de ATP protege a su organización de acuerdo con [las directivas de datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) que establecen los administradores globales o de seguridad de Office 365. 
  
La protección ATP también se puede ampliar a archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams. Para obtener más información, consulte [protección contra amenazas avanzada de Office 365 para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).
  
## <a name="how-to-get-atp-safe-attachments"></a>Cómo obtener datos adjuntos seguros de ATP

En primer lugar, asegúrese de que la suscripción incluye [protección contra amenazas avanzada](office-365-atp.md). ATP se incluye en en las suscripciones, como [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education A5, etc. Si su organización tiene una suscripción de Office 365 que no incluye ATP de Office 365, puede comprar ATP como complemento. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 

A continuación, asegúrese de que las directivas de datos adjuntos seguros de ATP estén definidas. (Consulte [configurar las directivas de datos adjuntos seguros de Office 365 ATP](set-up-atp-safe-attachments-policies.md)) Las características de datos adjuntos seguros de ATP están activas cuando:
  
- Las directivas de datos adjuntos seguros de ATP están configuradas. (Consulte [configurar las directivas de datos adjuntos seguros ATP en Office 365](set-up-atp-safe-attachments-policies.md).)

- Los usuarios han iniciado sesión en Office 365 con su cuenta profesional o educativa. (Consulte [iniciar sesión en Office u office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

Para definir (o editar) las directivas de ATP, debe tener asignado un rol apropiado. En la tabla siguiente se describen algunos ejemplos:

|Role  |Dónde y cómo se asigna  |
|---------|---------|
|Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
|Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Cómo saber si está disponible la protección de datos adjuntos seguros de ATP

Una vez que haya [definido (o revisado) las directivas de datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md), una buena forma de ver cómo funciona el servicio es viendo los [informes para la protección contra amenazas avanzada](view-reports-for-atp.md).
  
En la tabla siguiente se describen algunos escenarios de ejemplo. En todos estos casos, suponemos que la organización tiene una suscripción de Office 365 que incluye protección contra amenazas avanzada.
  
|**Escenario de ejemplo**|**¿Se aplica la protección de datos adjuntos seguros ATP en este caso?**|
|:-----|:-----|
|La organización de Pat tiene Office 365 Enterprise E5, pero nadie ha definido ninguna directiva para los datos adjuntos seguros de ATP todavía.  <br/> |No. Aunque la característica está disponible, se debe definir al menos una directiva de datos adjuntos seguros ATP para que la protección de datos adjuntos seguros de ATP esté en su lugar.  <br/> |
|Lee es un empleado del Departamento de ventas de contoso. La organización de Lee tiene una directiva de datos adjuntos seguros ATP que solo se aplica a los empleados de finanzas.  <br/> |No. En este caso, los empleados de finanzas tendrían la protección de datos adjuntos seguros ATP, pero otros empleados, incluido el Departamento de ventas, no deberían hasta que se definan las directivas que incluyen dichos grupos.  <br/> |
|Ayer, un administrador de Office 365 en la organización de Jean configuró una directiva de datos adjuntos seguros ATP que se aplica a todos los empleados. Anteriormente, Jean recibió un mensaje de correo electrónico que incluye datos adjuntos.  <br/> |Sí. En este ejemplo, Jean tiene una licencia para la protección contra amenazas avanzada y se ha definido una directiva de datos adjuntos seguros de ATP que incluye Jean. Por lo general, la nueva Directiva tarda unos 30 minutos en surtir efecto en los centros de recursos; como se ha pasado un día en este caso, la Directiva debe estar en vigor.  <br/> |
|La organización de Carlos tiene Office 365 Enterprise E5 con las directivas de datos adjuntos seguros ATP en su lugar para todos los usuarios de la organización. Chris recibe un correo electrónico con datos adjuntos y reenvía el mensaje a otros usuarios que están fuera de la organización.  <br/> |ATP la protección de datos adjuntos seguros está en su lugar para los mensajes que Chris recibe. Si las organizaciones de los destinatarios también tienen directivas de datos adjuntos seguros de ATP, el mensaje que se envía a Carlos estaría sujeto a esas directivas cuando llegue el mensaje reenviado.  <br/> |
|La organización de Pablo tiene directivas de datos adjuntos seguros de ATP y se ha activado [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) . Jamie presupone que todos los archivos en SharePoint Online se han examinado y que se pueden abrir o descargar de forma segura.  <br/> |ATP la protección de datos adjuntos seguros está en su lugar de acuerdo con las directivas definidas; sin embargo, esto no significa que se analicen todos los archivos de SharePoint Online, OneDrive para la empresa o Microsoft Teams. (Para obtener más información, consulte [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)).  <br/> |

## <a name="submitting-files-for-malware-analysis"></a>Enviar archivos para el análisis de malware

- Si recibe un archivo que quiere pedir a Microsoft que analice, visita [Enviar un archivo para el análisis de malware](https://aka.ms/wdsi/submit).

- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que desea enviar a Microsoft para su análisis, use el [complemento de mensajes de informe](enable-the-report-message-add-in.md).
