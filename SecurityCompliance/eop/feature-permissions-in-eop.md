---
title: Permisos de características en EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Los permisos necesarios para hacer tareas de administración en Microsoft Exchange Online Protection (EOP) varían en función de la característica que se administre.
ms.openlocfilehash: 08753d537982e49e735a1f81796f4709882c2be9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256258"
---
# <a name="feature-permissions-in-eop"></a>Permisos de características en EOP

Los permisos necesarios para hacer tareas de administración en Microsoft Exchange Online Protection (EOP) varían en función de la característica que se administre. 
  
Para configurar EOP debe ser un administrador global de Office 365 o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización).
  
## <a name="exchange-online-protection-permissions"></a>Permisos de Protección en línea de Exchange

Para ver los permisos necesarios para administrar características de EOP, vea la siguiente tabla. Si una característica enumera más que un grupo de roles, solo tiene que estar asignado a uno de los grupos de roles para usarla.
  
|**Feature**|**Permisos necesarios**|
|:-----|:-----|
|Antimalware  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Administración de higiene](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Contra correo electrónico no deseado  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Administración de higiene](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Reglas de flujo de correo  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](http://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx) <br/> |
|Dominios  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> |
|Protección contra amenazas avanzada (ATP)  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Administración de higiene](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Conectores de Office 365  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> |
|Seguimiento de mensajes  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> |
|Configuración de la organización  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> |
|Cuarentena  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Usuarios, contactos y grupos de roles  <br/> |[Administración de organizaciones](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Grupos de distribución y grupos de seguridad  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx) <br/> |
|Ver informes  <br/> |[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx): los usuarios tienen acceso a los informes de protección de correo.  <br/> [View-Only Recipients](http://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx): los usuarios tienen acceso a los informes de protección de correo.  <br/> [Compliance Management](http://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx): los usuarios tienen acceso a informes de protección de correo e informes de prevención de pérdida de datos (DLP) (si la suscripción tiene capacidades DLP).  <br/> |
   

