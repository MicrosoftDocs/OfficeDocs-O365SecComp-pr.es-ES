---
title: Configurar Azure Rights Management para el Cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 'Cifrado de mensajes de Office 365 depende de Microsoft Azure Rights Management (anteriormente conocido como Windows Azure Active Directory Rights Management). '
ms.openlocfilehash: 99c8de49330cf99545d28d81e0c99c2138797356
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536246"
---
# <a name="set-up-azure-rights-management-for-office-365-message-encryption"></a>Configurar Azure Rights Management para el Cifrado de mensajes de Office 365

En este tema se describe los pasos que debe seguir para poder activar y, a continuación, establecer la seguridad de Azure Rights Management (RMS), parte de la protección de la información de Azure, para su uso con Office 365 Message Encryption (OME).
  
## <a name="prerequisites-for-using-office-365-message-encryption"></a>Requisitos previos para usar el cifrado de mensajes de Office 365
<a name="warmprereqs"> </a>

Office 365 Message Encryption (OME), incluidos IRM, depende de Azure Rights Management (RMS Azure). RMS Azure es la tecnología de protección usada por la protección de la información de Azure. Para usar OME, la organización de Office 365 debe incluir una suscripción a Exchange Online o Exchange Online Protection que, a su vez, incluye una suscripción de Azure Rights Management.
  
- Si no está seguro de lo que incluye su suscripción, consulte las descripciones de servicio Exchange Online para [Directiva de mensajes, recuperación y cumplimiento de normas](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).
    
- Si no tiene una suscripción de Azure RMS para Exchange Online o Exchange Online Protection, debe adquirir una suscripción y activarlo en primer lugar.
    
    Para obtener información acerca de cómo adquirir una suscripción a Azure Rights Management, vea [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). La siguiente sección proporciona información acerca de cómo activar Azure Rights Management.
    
- Si tiene Azure Rights Management, pero no se ha configurado para Exchange Online o Exchange Online Protection, este artículo explica cómo activar Azure Rights Management y, a continuación, el se describe la mejor forma de configurar OME para que funcione con Azure Rights Management.
    
- Si ya ha configurado OME para que funcione con Azure Rights Management para Exchange Online o Exchange Online Protection, función de la configuración de seguridad, es posible que listo para empezar a utilizar OME y sus nuevas capacidades de inmediato. Este artículo explica cómo determinar si se ha configurado OME correctamente, qué hacer si necesita cambiar el programa de instalación y ¿qué sucede si no desea cambiar el programa de instalación. Por ejemplo, para poder usar las nuevas capacidades, debe usar RMS de Azure con OME. No puede usar las nuevas capacidades con un RMS de Active Directory local activa.
    
## <a name="activate-azure-rights-management-for-ome-in-office-365"></a>Activar Azure Rights Management para OME en Office 365
<a name="activatewarm"> </a>

Es necesario activar Azure Rights Management para que pueden aplicar la protección de información a los mensajes que envían los usuarios de su organización y abrir los mensajes y los archivos que han sido protegidos por el servicio de administración de derechos de Azure. Para obtener instrucciones, vea [Activar Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Una vez que haya completado la activación, regrese aquí y continuar con las tareas de este artículo.
  
## <a name="set-up-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configurar OME para usar RMS de Azure mediante la importación de dominios de publicación de confianza (publicación)
<a name="importTPDs"> </a>

Un TPD es un archivo XML que contiene información sobre la configuración de administración de derechos de la organización. Por ejemplo, el TPD contiene información sobre el certificado de emisor de licencias de servidor (SLC) utilizado para firmar y cifrar certificados y licencias, usan para emitir licencias y publicar las direcciones URL y así sucesivamente. Importar el TPD a la organización de Office 365 con Windows PowerShell.
  
> [!IMPORTANT]
> Anteriormente, podría elegir importar la publicación desde el servicio de administración de derechos de Active Directory (AD RMS) en la organización de Office 365. Sin embargo, si lo hace, se impide utilice las nuevas capacidades OME y no se recomienda. Si su organización es actualmente de Office 365 configurada de esta forma, Microsoft recomienda que cree un plan para migrar desde su RMS de Active Directory local activa a la protección de la información basada en la nube Azure. Para obtener más información, consulte [migración de AD RMS para protección de la información de Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). No podrá usar las nuevas capacidades OME hasta que haya completado la migración de protección de la información de Azure. 
  
 **Para importar la publicación de RMS de Azure**
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Elija la dirección URL de la clave de uso compartido que corresponde a la ubicación geográfica de su organización de Office 365:
    
|**Ubicación**|**Clave de uso compartido de dirección URL de la ubicación**|
|:-----|:-----|
|Norteamérica  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Unión Europea  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sudamérica  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 Administración Pública (nube de la comunidad de administración pública)  <br/> Esta ubicación de uso compartido de claves de RMS está reservada para los clientes que han adquirido Office 365 para las SKU de gobierno.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. Configure la ubicación de uso compartido de clave ejecutando el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) como se indica a continuación: 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    Por ejemplo, para configurar la clave de ubicación de uso compartido si su organización se encuentra en América del Norte:
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. Ejecute el cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con el modificador - RMSOnline para importar el TPD desde Azure Rights Management: 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    Donde *TPDName* es el nombre que desea usar para el TPD. Por ejemplo, "Contoso norteamericanos TPD". 
    
5. Para comprobar que se haya configurado correctamente su organización de Office 365 para usar el servicio de administración de derechos de Azure, ejecute el cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con el modificador - RMSOnline como sigue: 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    Entre otras cosas, este cmdlet comprueba la conectividad con el servicio de administración de derechos de Azure, descarga el TPD y comprueba su validez.
    
6. Ejecute el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) como se indica a continuación para deshabilitar las plantillas de Azure Rights Management esté disponible en Outlook en la web y de Outlook: 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. Ejecute el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) como se indica a continuación para habilitar Azure Rights Management para la organización de correo electrónico basada en la nube y configurarlo para usar Azure Rights Management Office 365 para cifrado de mensajes: 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. Para comprobar que ha importado el TPD y habilitado Azure Rights Management, use el cmdlet Test-IRMConfiguration para probar la funcionalidad de Azure Rights Management. Para obtener información detallada, vea "Ejemplo 1" en [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).
    
## <a name="i-have-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Tengo OME configurado con Active Directory Rights Management no protección de información de Azure, ¿qué puedo hacer?
<a name="importTPDs"> </a>

Puede continuar usar las reglas de flujo de correo de cifrado de mensajes de Office 365 existentes con Active Directory Rights Management, pero no se puede configurar o usar las nuevas capacidades OME. En su lugar, debe migrar a la protección de la información de Azure. Para obtener información sobre la migración y lo que significa para su organización, consulte [migración de AD RMS para protección de la información de Azure](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Pasos siguientes
<a name="importTPDs"> </a>

Una vez que haya completado el programa de instalación de Azure Rights Management, si desea habilitar las nuevas capacidades OME, vea [Configurar nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
Después de que ha configurado la organización para usar las nuevas capacidades OME, estará listo para [definir las reglas de flujo de correo para proteger los mensajes de correo electrónico con nuevas capacidades OME](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Temas relacionados
<a name="importTPDs"> </a>

[Cifrado en Office 365](encryption.md)
  
[Información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md)
  
[¿Qué es Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

