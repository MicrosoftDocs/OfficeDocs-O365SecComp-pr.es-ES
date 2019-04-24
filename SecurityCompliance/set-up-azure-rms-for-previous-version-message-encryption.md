---
title: Configurar Azure Rights Management para la versión anterior del Cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: La versión anterior de Office 365 cifrado de mensajes depende de Microsoft Azure Rights Management (anteriormente conocido como Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 89b86035f57699457c86fefb49888b8428f4e01c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266892"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>Configurar Azure Rights Management para la versión anterior del Cifrado de mensajes de Office 365

En este tema se describen los pasos que debe seguir para activar y, a continuación, configurar Azure Rights Management (RMS), parte de Azure Information Protection, para usarlo con la versión anterior de Office 365 cifrado de mensajes (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Este artículo solo se aplica a la versión anterior de OME
Si todavía no ha movido su organización de Office 365 a las nuevas capacidades de OME, pero ya ha implementado OME, la información de este artículo se aplica a su organización. Microsoft recomienda que cree un plan para cambiar a las nuevas funciones de OME en cuanto sea razonable para su organización. Para obtener instrucciones, vea [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md). Si desea obtener más información sobre cómo funcionan las nuevas funciones en primer lugar, consulte [Office 365 Message Encryption](ome.md). En el resto de este artículo se hace referencia al comportamiento OME antes de la publicación de las nuevas capacidades de OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Requisitos previos para usar la versión anterior de Office 365 cifrado de mensajes
<a name="warmprereqs"> </a>

El cifrado de mensajes de Office 365 (OME), incluido el IRM, depende de Azure Rights Management (Azure RMS). Azure RMS es la tecnología de protección usada por Azure Information Protection. Para usar OME, su organización de Office 365 debe incluir una suscripción de Exchange online o Exchange Online Protection que, a su vez, incluya una suscripción de Azure Rights Management.
  
- Si no está seguro de lo que incluye su suscripción, consulte descripciones del servicio de Exchange Online para la [Directiva de mensajes, la recuperación y el cumplimiento](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).

- Si no tiene una suscripción de Azure RMS para Exchange online o Exchange Online Protection, debe comprar una suscripción y activarla primero.

    Para obtener información sobre cómo comprar una suscripción a Azure Rights Management, vea [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). En la sección siguiente encontrará información sobre cómo activar Azure Rights Management.

- Si tiene Azure Rights Management pero no está configurado para Exchange online o Exchange Online Protection, en este artículo se explica cómo activar Azure Rights Management y, a continuación, se describe la mejor forma de configurar OME para trabajar con Azure Rights Management.

- Si ya configuró OME para trabajar con Azure Rights Management para Exchange online o Exchange Online Protection, según cómo se configure, puede que esté listo para empezar a usar OME y sus nuevas funcionalidades inmediatamente. En este artículo se explica cómo determinar si se ha establecido correctamente OME, qué hacer si es necesario cambiar la configuración y qué sucede si se decide no cambiar la configuración. Por ejemplo, para poder usar las nuevas funciones, debe usar Azure RMS con OME. No puede usar las nuevas funciones con Active Directory RMS local.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Activar Azure Rights Management para la versión anterior de OME en Office 365

Debe activar Azure Rights Management para que los usuarios de su organización puedan aplicar la protección de la información a los mensajes que envíen, y abrir los mensajes y archivos que hayan sido protegidos por el servicio Azure Rights Management. Para obtener instrucciones, consulte [Activar Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Una vez que haya completado la activación, regrese aquí y continúe con las tareas de este artículo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configure la versión anterior de OME para usar Azure RMS mediante la importación de dominios de publicación de confianza (TDP)

Un TPD es un archivo XML que contiene información sobre la configuración de la administración de derechos de la organización. Por ejemplo, el TPD contiene información sobre el certificado emisor de licencias de servidor que se usa para la firma y el cifrado de certificados y licencias, las direcciones URL usadas para la concesión de licencias y la publicación, etc. Importe el TPD a su organización de Office 365 mediante Windows PowerShell.
  
> [!IMPORTANT]
> Anteriormente, puede optar por importar TDP del servicio Rights Management de Active Directory (AD RMS) en su organización de Office 365. Sin embargo, si lo hace, impedirá usar las nuevas funciones de OME y no se recomienda. Si su organización de Office 365 está configurada de esta forma, Microsoft le recomienda que cree un plan para migrar desde su implementación local de RMS de Active Directory RMS a Azure Information Protection basado en la nube. Para obtener más información, vea [migración de AD RMS a Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). No podrá usar las nuevas funciones de OME hasta que haya completado la migración a Azure Information Protection.
  
 **Para importar TDP desde Azure RMS**
  
1. [Conéctese a Exchange online mediante PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Elija la URL de uso compartido de claves que corresponda a la ubicación geográfica de su organización de Office 365:

|**Ubicación**|**Dirección URL de ubicación de uso compartido de claves**|
|:-----|:-----|
|Norteamérica  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Unión Europea  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sudamérica  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 Administración Pública (nube de la comunidad de administración pública)  <br/> Esta ubicación de uso compartido de claves de RMS está reservada para los clientes que han adquirido Office 365 para las SKU gubernamentales.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. Para configurar la ubicación de uso compartido de claves, ejecute el cmdlet [set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) de la siguiente manera: 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    Por ejemplo, para configurar la ubicación de uso compartido de claves si su organización se encuentra en Norteamérica:
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. Ejecute el cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con el conmutador-RMSOnline para importar el TPD desde Azure Rights Management: 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    Donde *TPDName* es el nombre que desea usar para el TPD. Por ejemplo, "Contoso North americano TPD". 
    
5. Para comprobar que ha configurado correctamente su organización de Office 365 para usar el servicio Azure Rights Management, ejecute el cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con el modificador-RMSOnline de la siguiente manera: 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    Entre otras cosas, este cmdlet comprueba la conectividad con el servicio Azure Rights Management, descarga el TPD y comprueba su validez.
    
6. Ejecute el cmdlet [set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) como se indica a continuación para deshabilitar las plantillas de Azure Rights Management para que no estén disponibles en Outlook en la web y Outlook: 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. Ejecute el cmdlet [set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) como se indica a continuación para habilitar Azure Rights Management para su organización de correo electrónico basada en la nube y configurarlo para que use el cifrado de mensajes de Azure Rights Management para Office 365: 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. Para comprobar que ha importado correctamente el TPD y que ha habilitado Azure Rights Management, use el cmdlet test-IRMConfiguration para probar la funcionalidad de Azure Rights Management. Para obtener más información, vea "Ejemplo 1" en [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Tengo la versión anterior de OME configurada con Active Directory Rights Management, no Azure Information Protection, ¿qué hago?
<a name="importTPDs"> </a>

Puede seguir usando las reglas de flujo de correo de cifrado de mensajes de Office 365 existentes con Active Directory Rights Management, pero no puede configurar ni usar las nuevas funciones de OME. En su lugar, debe migrar a Azure Information Protection. Para obtener información sobre la migración y qué significa para su organización, vea [migrar de AD RMS a Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Siguientes pasos
<a name="importTPDs"> </a>

Una vez que haya completado la instalación de Azure Rights Management, si desea habilitar las nuevas capacidades de OME, vea [set up New Office 365 Message Encryption Capabilities Built on of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
Una vez que haya configurado la organización para usar las nuevas capacidades de OME, estará listo para [definir reglas de flujo de correo para proteger los mensajes de correo electrónico con nuevas funciones de OME](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Temas relacionados
<a name="importTPDs"> </a>

[Cifrado en Office 365](encryption.md)
  
[Información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md)
  
[¿Qué es Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

