---
title: Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Windows Defender
ms.author: deniseb
author: denisebmsft
manager: laurawi
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
description: Integrar la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Windows Defender para ver información más detallada acerca de la administración de amenazas.
ms.openlocfilehash: f6ea4309d3eb7a4ccd4987d221398d0f15994388
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077256"
---
# <a name="integrate-office-365-advanced-threat-protection-with-windows-defender-advanced-threat-protection"></a>Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Windows Defender

Si forma parte del equipo de seguridad de su organización, puede integrar la protección contra amenazas avanzada de Office 365 y las características de investigación y respuesta relacionadas con la protección contra amenazas avanzada de Windows Defender. Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están expuestos a riesgos cuando esté investigando amenazas en Office 365. Por ejemplo, una vez habilitada la integración, podrá ver una lista de las máquinas que usan los destinatarios de un mensaje de correo electrónico detectado, así como el número de alertas recientes que tienen esos equipos en la protección contra amenazas avanzada de Windows Defender.
  
La siguiente imagen muestra la pestaña **dispositivos** que verá cuando tenga habilitada la integración de la protección contra amenazas avanzada de Windows Defender: 
  
![Si ATP de Windows Defender está habilitada, puede ver una lista de equipos con alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro dispositivos y uno de ellos tiene una alerta. Al hacer clic en el vínculo de un dispositivo se abre su página en el portal de protección contra amenazas avanzada de Windows Defender.
  
## <a name="requirements"></a>Requisitos

- Su organización debe tener Office 365 Advanced Threat Protection Plan 2 (u Office 365 E5) y ATP de Windows Defender.
    
- Debe ser administrador global de Office 365 o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en [el &amp; centro de seguridad y cumplimiento](https://protection.office.com). (Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md))
    
- Debe tener acceso al explorador de amenazas de Office 365 en el centro de seguridad & cumplimiento y el portal de protección contra amenazas avanzada de Windows Defender.
    
## <a name="to-integrate-office-365-advanced-threat-protection-with-windows-defender-atp"></a>Para integrar la protección contra amenazas avanzada de Office 365 con ATP de Windows Defender

Integración de Office 365 avanzada protección contra amenazas con la protección contra amenazas avanzada de Windows Defender se configura mediante el centro de seguridad & cumplimiento y el portal de protección contra amenazas avanzada de Windows Defender.
  
1. Como administrador global de Office 365 o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. 
    
2. Elija **Threat Management** \> **Explorer**.<br>![Explorador en el menú de administración de amenazas](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. En la esquina superior derecha de la pantalla, elija **WDATP de configuración**.
    
4. En el cuadro de diálogo conexión ATP de Windows Defender, Active conectarse a ATP de Windows.<br>![Conexión ATP de Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Habilitar la conexión en la protección contra amenazas avanzada de Windows Defender. Consulte [usar el portal de protección contra amenazas avanzada de Windows Defender](https://go.microsoft.com/fwlink/?linkid=859690).

  
## <a name="related-topics"></a>Temas relacionados

[Respuesta y investigación de amenazas de Office 365](office-365-ti.md)
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  

