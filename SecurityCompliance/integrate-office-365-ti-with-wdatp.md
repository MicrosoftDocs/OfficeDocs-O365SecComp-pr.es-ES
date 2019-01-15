---
title: Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Integrar la protección de amenaza avanzada de Office 365 con Windows Defender avanzada protección contra amenazas para ver información más detallada de administración de amenaza.
ms.openlocfilehash: 48e879c1d41b5aa662f5128e234be91eb8225e7b
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014772"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>Integrar la inteligencia de amenazas de Office 365 con la protección contra amenazas avanzada de Windows Defender

Si forma parte del equipo de seguridad de su organización, puede integrar Office 365 con Defender avanzada amenaza protección (ATP) de Windows. Esto puede ayudarle a comprender rápidamente si los equipos de los usuarios están en riesgo cuando investigue las amenazas en Office 365. Por ejemplo, una vez que se habilita la integración, podrá ver una lista de los equipos que se usan por los destinatarios de un mensaje de correo electrónico detectado, así como el modo en muchas alertas recientes esos equipos tienen en Windows Defender ATP.
  
En la siguiente imagen se muestra la ficha **dispositivos** que verá cuándo tiene integración de Windows Defender ATP habilitada: 
  
![Cuando Windows Defender ATP está habilitada, puede ver una lista de las máquinas con las alertas.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico tienen cuatro máquinas y uno tiene una alerta en Windows Defender ATP. Al hacer clic en el vínculo a una máquina, se abre la página de la máquina en Windows Defender ATP en una nueva ficha.
  
## <a name="requirements"></a>Requisitos

- Su organización debe tener información sobre amenazas de Office 365 y Windows Defender ATP.
    
- Debe ser un administrador global de Office 365 o tener un rol de administrador de seguridad asignado en la [seguridad &amp; centro de cumplimiento](https://protection.office.com). (Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md))
    
- Debe tener acceso a información sobre amenazas de Office 365 y el portal de Windows Defender ATP.
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>Para integrar información sobre amenazas de Office 365 con Windows Defender ATP

Integración de inteligencia de amenaza de Office 365 con Windows Defender ATP se configura en Office 365 y en el portal de Windows Defender ATP.
  
1. Como un global de Office 365 o un administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela para Office 365. 
    
2. Elija **administración de amenaza** \> **el Explorador de amenaza**.
    
3. En el menú **más** , elija **Configuración de WDATP**.
    
4. Seleccione **conectarse a Windows ATP**.
    
Después de haber cambiado la configuración de Office 365, debe habilitar la conexión desde Windows Defender ATP. Para ello, vea [utilizar el portal de protección de amenaza avanzada de Windows Defender](https://go.microsoft.com/fwlink/?linkid=859690).
  
## <a name="related-topics"></a>Temas relacionados

[Inteligencia sobre amenazas de Office 365](office-365-ti.md)
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  

