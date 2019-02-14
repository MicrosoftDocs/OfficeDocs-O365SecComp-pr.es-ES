---
title: Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection: M365-security-compliance
description: Integrar la protección de amenaza avanzada de Office 365 con Windows Defender avanzada protección contra amenazas para ver información más detallada de administración de amenaza.
ms.openlocfilehash: f8f5f50af10fb668aa67b68604e95e8dd19c9e69
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995211"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender

Si forma parte del equipo de seguridad de su organización, puede integrar características de protección de amenaza avanzada de Office 365 y amenaza con protección de amenaza avanzada de Windows Defender. Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están en riesgo cuando investigue las amenazas en Office 365. Por ejemplo, una vez que se habilita la integración, podrá ver una lista de los equipos que se usan por los destinatarios de un mensaje de correo electrónico detectado, así como el modo en muchas alertas recientes esos equipos tienen en la protección de amenaza avanzada de Windows Defender.
  
En la siguiente imagen se muestra la ficha **dispositivos** que verá cuándo tiene la integración de la protección de amenaza avanzada de Windows Defender habilitada: 
  
![Cuando Windows Defender ATP está habilitada, puede ver una lista de las máquinas con las alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo para un dispositivo, su página se abre en el portal de protección de amenaza avanzada de Windows Defender.
  
## <a name="requirements"></a>Requisitos

- Su organización debe tener información sobre amenazas de Office 365 y Windows Defender ATP.
    
- Debe ser un administrador Global de Office 365 o tener un rol de administrador de seguridad (por ejemplo, el Administrador de seguridad) asignado en la [seguridad &amp; centro de cumplimiento](https://protection.office.com). (Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md))
    
- Debe tener acceso a información sobre amenazas de Office 365 y el portal de protección de amenaza avanzada de Windows Defender.
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>Para integrar información sobre amenazas de Office 365 con Windows Defender ATP

Integración de Office 365 amenaza inteligencia con protección de amenaza avanzada de Windows Defender se configura mediante el uso de ambos la seguridad de Office 365 & centro de cumplimiento de normas y el portal de protección de amenaza avanzada de Windows Defender.
  
1. Como un administrador global de Office 365 o un administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela para Office 365. 
    
2. Elija **administración de amenaza** \> **Explorer**.<br>![Explorador en el menú de administración de amenaza](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. En la esquina superior derecha de la pantalla, elija **Configuración de WDATP**.
    
4. En el cuadro de diálogo de conexión de Windows Defender ATP, activar conectar a ATP de Windows.<br>![Conexión de Windows Defender ATP](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Habilitar la conexión en la protección de amenaza avanzada de Windows Defender. Cómo [usar el portal de protección de amenaza avanzada de Windows Defender](https://go.microsoft.com/fwlink/?linkid=859690).

  
## <a name="related-topics"></a>Temas relacionados

[Inteligencia sobre amenazas de Office 365](office-365-ti.md)
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  

