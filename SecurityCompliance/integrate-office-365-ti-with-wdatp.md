---
title: Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Microsoft defender
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integre Office 365 Advanced Threat Protection con la protección contra amenazas avanzada de Microsoft defender para ver información más detallada sobre la administración de amenazas.
ms.openlocfilehash: 5ab849b833f71868d9b08fd1af76ee6d904f5d59
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852812"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Microsoft defender

Si forma parte del equipo de seguridad de su organización, puede integrar la [protección contra amenazas avanzada de Office 365](office-365-atp.md) y las características de investigación y respuesta relacionadas con la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection). Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están expuestos a riesgos cuando esté investigando amenazas en Office 365. Por ejemplo, una vez habilitada la integración, podrá ver una lista de equipos usados por los destinatarios de un mensaje de correo electrónico detectado, así como el número de alertas recientes que tienen esos equipos en la protección contra amenazas avanzada de Microsoft defender.
  
La siguiente imagen muestra la pestaña **dispositivos** que verá cuando tenga habilitada la integración de Microsoft defender ATP:
  
![Si ATP de Microsoft defender está habilitada, puede ver una lista de equipos con alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro dispositivos y uno de ellos tiene una alerta. Al hacer clic en el vínculo de un dispositivo se abre su página en el centro de seguridad de Microsoft defender.
  
## <a name="requirements"></a>Requisitos

- Su organización debe tener Office 365 ATP plan 2 (o Office 365 E5) y ATP de Microsoft defender.
    
- Debe ser administrador global de Office 365 o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en [el &amp; centro de seguridad y cumplimiento](https://protection.office.com). (Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md))
    
- Debe tener acceso a [exploradores (o detecciones en tiempo real)](threat-explorer.md) en el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Para integrar Office 365 ATP con Microsoft defender ATP

Integración de Office 365 ATP con Microsoft defender ATP se configura mediante el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.
  
1. Como administrador global de Office 365 o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365.
    
2. Elija **Threat Management** \> **Explorer**.<br>![Explorador en el menú de administración de amenazas](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. En la esquina superior derecha de la pantalla, elija **WDATP de configuración**.
    
4. En el cuadro de diálogo conexión ATP de Windows Defender, Active conectarse a ATP de Windows.<br>![Conexión ATP de Microsoft defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Habilite la conexión en el centro de seguridad de Microsoft defender.

  
## <a name="related-topics"></a>Temas relacionados

[Respuesta y investigación de amenazas de Office 365](office-365-ti.md)
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  

