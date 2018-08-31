---
title: Cómo Exchange Online protege su información confidencial de correo electrónico
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
description: Además de la confianza centro de Office 365 que proporciona seguridad, privacidad y cumplimiento información para Office 365, es posible que desee saber cómo ayuda Office 365 protege secretos proporcionar en sus centros de datos. Se usa una tecnología llamada Administrador de clave distribuida (DKM).
ms.openlocfilehash: a8fe1a2c9393958a391ec69a9a476a06de8c7576
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536720"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Cómo Exchange Online protege su información confidencial de correo electrónico

Este artículo describe cómo Microsoft protege su información confidencial de correo electrónico en sus centros de datos.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>¿Cómo se protege la información confidencial proporcionada por el usuario?

Además de la confianza centro de Office 365 que proporciona [seguridad, privacidad y la información de cumplimiento para Office 365](https://go.microsoft.com/fwlink/?linkid=874644), es posible que desee saber cómo ayuda Office 365 protege secretos proporcionar en sus centros de datos. Se usa una tecnología llamada Administrador de clave distribuida (DKM).
  
El administrador de claves distribuidas (DKM) es una funcionalidad de cliente que usa un conjunto de claves secretas para cifrar y descifrar información. Solo los miembros de un grupo de seguridad específico de los Servicios de dominio de Active Directory pueden tener acceso a dichas claves para descifrar los datos cifrados por el DKM. En Exchange Online, solo determinadas cuentas de servicio bajo las cuales se ejecutan procesos de Exchange forman parte del grupo de seguridad. Como parte del procedimiento operativo estándar en el centro de datos, ningún humano tiene credenciales que forman parte de este grupo de seguridad y, por lo tanto, nadie tiene acceso a las claves que pueden descifrar la información confidencial.
  
Para depuración, solución de problemas o fines de auditoria, un administrador del centro de datos debe solicitar acceso con privilegios elevados para obtener credenciales temporales que forman parte del grupo de seguridad. Este proceso requiere varios niveles de aprobación legal. Si se concede acceso, toda la actividad se registra y se audita. Además, solo se otorga acceso durante un determinado intervalo de tiempo, que caduca automáticamente una vez concluido.
  
Para brindar protección adicional, la tecnología del DKM incluye sustitución de claves y archivado automáticos. Esto también garantiza el acceso al contenido anterior sin tener que recurrir a la misma clave de forma indefinida.

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>¿De qué forma Exchange Online usa el DKM?

Microsoft usa el DKM para cifrar la información confidencial en centros de datos de Exchange Online. Por ejemplo:
  
- Credenciales de cuentas de correo electrónico de cuentas conectadas. Las cuentas conectadas son cuentas de terceros, como las de Hotmail, Gmail y Yahoo!.
    
- Claves de raíz (RMS) del servicio de administración de derechos. Estos son claves de cliente que están que bien importar desde RMS de Azure o desde las implementaciones de servicios de dominio de Active Directory RMS de local del cliente que se usan para cifrar y descifrar mensajes de correo electrónico con RMS o Office 365 Message Encryption (OME).
    
## <a name="related-topics"></a>Temas relacionados

[Cifrado en Office 365](encryption.md)
  
[Información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md)
  
[Service assurance en la seguridad de Office 365 &amp; centro de cumplimiento](https://go.microsoft.com/fwlink/?linkid=874645)
  

