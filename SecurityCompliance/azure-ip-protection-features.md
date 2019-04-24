---
title: Características de protección de Azure Information Protection que se implementan en inquilinos de Office 365 existentes
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
description: Para ayudarle con el paso inicial de protección de la información, a partir de julio de 2018 todos los inquilinos elegibles de Azure Information Protection tendrán las características de protección de Azure Information Protection activadas de forma predeterminada. Las características de protección de Azure Information Protection se conocían anteriormente en Office 365 como Rights Management o Azure RMS. Si su organización tiene un plan de servicio de Office E3 o un plan de servicio más alto, ahora obtendrá una ventaja para proteger la información a través de Azure Information Protection cuando implementamos estas características.
ms.openlocfilehash: 2484f9b335a6698894046aaf429fdad68d82491e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243991"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Características de protección de Azure Information Protection que se implementan en inquilinos de Office 365 existentes

Para ayudarle con el paso inicial de protección de la información, a partir de julio de 2018 todos los inquilinos elegibles de Azure Information Protection tendrán las características de protección de Azure Information Protection activadas de forma predeterminada. Las características de protección de Azure Information Protection se conocían anteriormente en Office 365 como Rights Management o Azure RMS. Si su organización tiene un plan de servicio de Office E3 o un plan de servicio más alto, ahora obtendrá una ventaja para proteger la información a través de Azure Information Protection cuando implementamos estas características.
  
## <a name="changes-beginning-july-1-2018"></a>Cambios a partir del 1 de julio de 2018

A partir del 1 de julio de 2018, Microsoft habilitará la capacidad de protección de Azure Information Protection para todos los inquilinos de Office 365 que tengan uno de los siguientes planes de suscripción:
  
- El cifrado de mensajes de Office 365 se ofrece como parte de Office 365 E3 y E5, Microsoft E3 y E5, Office 365 a1, a3 y A5, y Office 365 G3 y G5. No necesita licencias adicionales para recibir las nuevas capacidades de protección de Azure Information Protection. 
    
- También puede Agregar el plan 1 de Azure Information Protection a los siguientes planes para recibir las nuevas capacidades de cifrado de mensajes de Office 365: Plan 1 de Exchange Online, Exchange Online plan 2, Office 365 F1, Office 365 empresa Essentials, Office 365 empresa Premium o Office 365 Enterprise E1.
    
- Cada usuario que se beneficie de Office 365 el cifrado de mensajes debe disponer de una licencia que abarque la característica.
    
- Para obtener la lista completa, consulte descripciones del [servicio de Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) para el cifrado de mensajes de Office 365. 
    
Los administradores de espacios empresariales pueden comprobar el estado de protección en el portal de administración de Office 365. 
  
![Captura de pantalla que muestra que se activa la administración de derechos en Office 365.](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>¿Por qué hemos hecho este cambio?

El cifrado de mensajes de Office 365 aprovecha las capacidades de protección de Azure Information Protection. En el corazón de las recientes mejoras en el cifrado de mensajes de Office 365 y nuestras inversiones más amplias en la protección de la información en Microsoft 365, estamos facilitando a las organizaciones la activación y uso de nuestras capacidades de protección, como históricamente, el cifrado las tecnologías han sido difíciles de configurar. Al activar las características de protección de Azure Information Protection de forma predeterminada, puede empezar rápidamente a proteger los datos confidenciales.
  
## <a name="does-this-impact-me"></a>¿Esto afecta a mí?

Si su organización de Office 365 ha adquirido una licencia válida de Office 365, su inquilino se verá afectado por este cambio.
  
 **RELEVANCIA!** Si usa Active Directory Rights Management Services (AD RMS) en su entorno local, debe optar por rechazar este cambio inmediatamente o migrar a Azure Information Protection antes de implementar este cambio en los próximos 30 días. Para obtener información sobre cómo rechazar la suscripción, vea "utilizo AD RMS, ¿cómo puedo no participar?". más adelante en este artículo. Si prefiere realizar la migración, vea [migración de AD RMS a Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>¿Puedo usar Azure Information Protection con Active Directory Rights Management Services (AD RMS)?

No. No se trata de un escenario de implementación admitido. Sin tener en consideración los pasos adicionales de cancelación, algunos equipos podrían empezar a usar automáticamente el servicio Azure Rights Management y conectarse también a su clúster de AD RMS. Este escenario no es compatible y tiene resultados no confiables, por lo que es importante que rechace este cambio en los próximos 30 días antes de implementar estas características nuevas. Para obtener información sobre cómo rechazar la suscripción, vea "utilizo AD RMS, ¿cómo puedo no participar?". más adelante en este artículo. Si prefiere realizar la migración, vea [migración de AD RMS a Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>¿Cómo sé si estoy usando AD RMS?

Siga estas instrucciones [para preparar el entorno de Azure Rights Management cuando también tiene Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) para comprobar si ha implementado AD RMS: 
  
1. Aunque es opcional, la mayoría de las implementaciones de AD RMS publican el punto de conexión de servicio (SCP) en Active Directory para que los equipos del dominio puedan detectar el clúster de AD RMS. 
  
Use ADSI Edit para ver si tiene un SCP publicado en Active Directory: CN = configuración [nombre del servidor], CN = servicios, CN = RightsManagementServices, CN = SCP
    
2. Si no usa un SCP, los equipos con Windows que se conecten a un clúster de AD RMS deben configurarse para la detección de licencias o la redirección del servicio del lado cliente mediante el registro de Windows: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation o HKEY_ LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
Para obtener más información acerca de estas configuraciones del registro, vea habilitación de [la detección de servicios del lado cliente mediante el registro de Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) y redireccionamiento del [tráfico del servidor de licencias](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Utilizo AD RMS, ¿cómo puedo no participar?

Para no participar en el próximo cambio, siga estos pasos:
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Ejecute el cmdlet Set-IRMConfiguration con la siguiente sintaxis:
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>¿Qué puedo esperar después de que se haya realizado este cambio?

Una vez habilitado, si no ha optado por usted, puede empezar a usar la nueva versión del cifrado de mensajes de Office 365 que se anunció en el [encendido de Microsoft encendido 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) y aprovecha las capacidades de cifrado y protección de Azure Information. Protege. 
  
![Captura de pantalla que muestra un mensaje protegido de OME en Outlook en la Web.](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
Para obtener más información acerca de las nuevas mejoras, consulte [Office 365 Message Encryption](ome.md).
  

