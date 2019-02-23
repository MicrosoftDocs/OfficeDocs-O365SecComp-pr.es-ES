---
title: Cómo Exchange Online protege su información confidencial de correo electrónico
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Además del centro de confianza de Office 365, que proporciona información de seguridad, privacidad y cumplimiento para Office 365, es posible que quiera saber cómo Office 365 ayuda a proteger secretos que proporcione en sus centros de datos. Usamos una tecnología denominada administrador de claves distribuidas (DKM).
ms.openlocfilehash: ba4c661899273f5e07c2468631298f5500d0e32f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218080"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Cómo Exchange Online protege su información confidencial de correo electrónico

Este artículo describe cómo Microsoft protege su información confidencial de correo electrónico en sus centros de datos.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>¿Cómo se protege la información confidencial proporcionada por el usuario?

Además del centro de confianza de Office 365, que proporciona [información de seguridad, privacidad y cumplimiento para office 365](https://go.microsoft.com/fwlink/?linkid=874644), es posible que quiera saber cómo Office 365 ayuda a proteger secretos que proporcione en sus centros de datos. Usamos una tecnología denominada administrador de claves distribuidas (DKM).
  
El administrador de claves distribuidas (DKM) es una funcionalidad de cliente que usa un conjunto de claves secretas para cifrar y descifrar información. Solo los miembros de un grupo de seguridad específico de los Servicios de dominio de Active Directory pueden tener acceso a dichas claves para descifrar los datos cifrados por el DKM. En Exchange Online, solo determinadas cuentas de servicio bajo las cuales se ejecutan procesos de Exchange forman parte del grupo de seguridad. Como parte del procedimiento operativo estándar en el centro de datos, ningún humano tiene credenciales que forman parte de este grupo de seguridad y, por lo tanto, nadie tiene acceso a las claves que pueden descifrar la información confidencial.
  
Para depuración, solución de problemas o fines de auditoria, un administrador del centro de datos debe solicitar acceso con privilegios elevados para obtener credenciales temporales que forman parte del grupo de seguridad. Este proceso requiere varios niveles de aprobación legal. Si se concede acceso, toda la actividad se registra y se audita. Además, solo se otorga acceso durante un determinado intervalo de tiempo, que caduca automáticamente una vez concluido.
  
Para brindar protección adicional, la tecnología del DKM incluye sustitución de claves y archivado automáticos. Esto también garantiza el acceso al contenido anterior sin tener que recurrir a la misma clave de forma indefinida.

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>¿De qué forma Exchange Online usa el DKM?

Microsoft usa el DKM para cifrar la información confidencial en centros de datos de Exchange Online. Por ejemplo:
  
- Credenciales de cuentas de correo electrónico de cuentas conectadas. Las cuentas conectadas son cuentas de terceros, como las de Hotmail, Gmail y Yahoo!.
    
- Claves raíz del servicio Rights Management (RMS). Estas son claves de cliente que se importan de Azure RMS o de las implementaciones de RMS de servicios de dominio de Active Directory locales del cliente que se usan para cifrar y descifrar correos electrónicos con RMS o el cifrado de mensajes de Office 365 (OME).
    
## <a name="related-topics"></a>Temas relacionados

[Cifrado en Office 365](encryption.md)
  
[Información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md)
  
[Garantía del servicio en el centro de &amp; seguridad y cumplimiento de Office 365](https://go.microsoft.com/fwlink/?linkid=874645)
  

