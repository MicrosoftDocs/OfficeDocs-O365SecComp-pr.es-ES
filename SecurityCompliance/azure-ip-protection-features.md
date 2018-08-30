---
title: Características de protección de protección de la información de Azure implantar a los inquilinos existentes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
description: Para ayudar a con el paso inicial de protección de la información, iniciar julio de 2018 todos los inquilinos de protección de la información de Azure optan habrá las características de protección de protección de la información de Azure activado de forma predeterminada. Las características de protección de protección de la información de Azure eran conocidas anteriormente en Office 365 como administración de derechos o RMS de Azure. Si su organización tiene un plan de servicio de Office E3 o un plan de servicio superior ahora obtendrá una ventaja de protección de la información a través de la protección de la información de Azure cuando se desplegar estas características.
ms.openlocfilehash: be0200da3032dccbcf54e67f3bdfbac800b65526
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535926"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Características de protección de protección de la información de Azure implantar a los inquilinos existentes de Office 365

Para ayudar a con el paso inicial de protección de la información, iniciar julio de 2018 todos los inquilinos de protección de la información de Azure optan habrá las características de protección de protección de la información de Azure activado de forma predeterminada. Las características de protección de protección de la información de Azure eran conocidas anteriormente en Office 365 como administración de derechos o RMS de Azure. Si su organización tiene un plan de servicio de Office E3 o un plan de servicio superior ahora obtendrá una ventaja de protección de la información a través de la protección de la información de Azure cuando se desplegar estas características.
  
## <a name="changes-beginning-july-1-2018"></a>Cambios a partir del 1 de julio de 2018

Iniciar el 1 de julio de 2018, Microsoft habilitará la capacidad de protección en Azure protección de la información para todos los inquilinos de Office 365 que tienen uno de los siguientes planes de suscripción:
  
- Office 365 cifrado de mensajes se ofrece como parte de Office 365 E3 y E5, Microsoft E3 y E5, Office 365 A1, A3 y A5 y Office 365 G3 y G5. No necesita licencias adicionales para recibir las nuevas capacidades de protección con tecnología de protección de la información de Azure. 
    
- También puede agregar planes de Azure información protección Plan 1 a los siguientes elementos para recibir las nuevas capacidades de Office 365 Message Encryption: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Premium de negocio de Office 365, o Office 365 Enterprise E1.
    
- Debe tener licencia para debe estar cubierto por la característica de cada usuario al sacar provecho de cifrado de mensajes de Office 365.
    
- Para obtener la lista completa, consulte las [descripciones del servicio de Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) para Office 365 Message Encryption. 
    
Los administradores de inquilinos pueden comprobar el estado de protección en el portal de administrador de Office 365. 
  
![Captura de pantalla que muestra que rights management en Office 365 está activada.](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>¿Por qué ponemos este cambio?

Cifrado de mensajes de Office 365 aprovecha las capacidades de protección de protección de la información de Azure. En el centro de las mejoras recientes al cifrado de mensajes de Office 365 y nuestras inversiones más amplias para protección de la información en Microsoft 365, estamos facilitando más fácil para las organizaciones a activar y usar nuestras capacidades de protección, como tradicionalmente, cifrado tecnologías han sido difíciles de configurar. Al activar las características de protección de protección de la información de Azure de forma predeterminada, puede empezar rápidamente a proteger sus datos confidenciales.
  
## <a name="does-this-impact-me"></a>¿Esto influye en mí?

Si la organización de Office 365 ha adquirido una licencia de Office 365 optan, a continuación, el inquilino se verán afectado por este cambio.
  
 **Importante!** Si usa Active Directory Rights Management Services (AD RMS) en su entorno local, debe optar por no este cambio inmediatamente o migrar a la protección de la información de Azure antes de que se implantar este cambio en los próximos 30 días. Para obtener información sobre cómo voluntaria, vea "usar AD RMS, cómo se puede participar out?" más adelante en este artículo. Si lo prefiere migrar, vea [migrar de AD RMS a la protección de la información de Azure.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>¿Puedo usar protección de la información de Azure con Active Directory Rights Management Services (AD RMS)?

No. No es un escenario de implementación compatibles. Sin realizar los pasos adicionales de voluntaria, algunos equipos podrían iniciar automáticamente mediante el servicio de administración de derechos de Azure y también conectar con el clúster de AD RMS. En este escenario no es compatible y tiene resultados no confiables, por lo que es importante que anular este cambio en los próximos 30 días antes de que se desplegar estas nuevas características. Para obtener información sobre cómo voluntaria, vea "usar AD RMS, cómo se puede participar out?" más adelante en este artículo. Si lo prefiere migrar, vea [migrar de AD RMS a la protección de la información de Azure.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>¿Cómo saber si estoy usando AD RMS?

Use estas instrucciones de [preparación del entorno de Azure Rights Management cuando haya también Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) para comprobar si ha implementado AD RMS: 
  
1. Aunque es opcional, la mayoría de las implementaciones de AD RMS publica el punto de conexión de servicio (SCP) en Active Directory para que los equipos del dominio pueden descubrir el clúster de AD RMS. 
  
Usar el Editor ADSI para ver si tienen un SCP publicado en Active Directory: CN = Configuration [nombre del servidor], CN = Servicios, CN = RightsManagementServices, CN = SCP
    
2. Si no está utilizando un SCP, equipos de Windows que se conectan a un clúster de AD RMS deben configurarse para la detección del servicio de cliente o licencias de redirección mediante el registro de Windows: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation o HKEY_ LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
Para obtener más información acerca de estas configuraciones del registro, vea [Habilitar detección de servicio de cliente mediante el registro de Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) y [redirigir el tráfico del servidor de licencias](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>¿Usar AD RMS, cómo excluir?

Para anular el cambio próximo, siga estos pasos:
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Ejecute el cmdlet Set-IRMConfiguration mediante la siguiente sintaxis:
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>¿Qué puede esperar después de que se ha realizado este cambio?

Una vez que esto está habilitado, siempre que todavía no ha optado por deshabilitarlo, puede empezar a usar la nueva versión de Office 365 mensaje cifrado que se presentó en [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) y aprovecha las capacidades de cifrado y protección de la información de Azure Protección. 
  
![Captura de pantalla que muestra un OME había protegida mensaje en Outlook en el web.](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
Para obtener más información acerca de las nuevas mejoras, consulte [Cifrado de mensajes de Office 365](ome.md).
  

