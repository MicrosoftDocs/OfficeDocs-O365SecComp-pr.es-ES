---
title: Protección de archivos y sitios de SharePoint Online
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 'Resumen: recomendaciones de configuración para proteger archivos en SharePoint Online y Office 365.'
ms.openlocfilehash: 3e41a46d244f88110b87426fe975b3f72e376984
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955233"
---
# <a name="secure-sharepoint-online-sites-and-files"></a>Protección de archivos y sitios de SharePoint Online

 **Resumen:** Recomendaciones de configuración para proteger archivos en SharePoint Online y Office 365.
  
En este artículo, se ofrecen recomendaciones para configurar la protección de archivos y sitios de grupo de SharePoint Online de manera que se equilibre la seguridad con la facilidad de colaboración. En este artículo, se definen cuatro configuraciones distintas, empezando por un sitio público dentro de la organización con las directivas de uso compartido más abiertas. Cada configuración adicional representa un paso significativo para la protección, pero a costa de que el conjunto de usuarios relevante pierda capacidad de obtener acceso a los recursos y colaborar en ellos. Siga estas recomendaciones como punto inicial, y ajuste las configuraciones para adaptarse a las necesidades de su organización. 
  
Las configuraciones que se explican en este artículo concuerdan con las recomendaciones de Microsoft para los tres niveles de protección de datos, identidades y dispositivos:
  
- Protección de base de referencia
    
- Protección confidencial
    
- Protección extremadamente confidencial
    
Para más información sobre estos niveles y capacidades recomendadas para cada nivel, vea los siguientes recursos. 
  
- [Protección de identidades y dispositivos para Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365IDP)
    
- [Soluciones de protección de archivos en Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#BKMK_O365fileprotect)
    
## <a name="capability-overview"></a>Introducción a las capacidades

Las recomendaciones para sitios de grupo de SharePoint Online abarcan toda una variedad de capacidades de Microsoft 365. En la ilustración siguiente, se muestran las configuraciones recomendadas para cuatro sitios de grupo de SharePoint Online.

![Configuración recomendada para sitios de SharePoint](media/SharePoint-site-configurations.png)

Como se muestra:
  
- La protección de base de referencia incluye dos opciones para los sitios de grupo de SharePoint Online: un sitio público y un sitio privado. Los sitios públicos son aquellos visibles y accesibles por cualquier persona de la organización. Los sitios privados solo pueden detectarlos y acceder a ellos los miembros del sitio. Estas dos configuraciones de sitio permiten compartir fuera del grupo. 
    
- Los sitios para protección confidencial y extremadamente confidencial son sitios privados con acceso limitado solamente a los miembros de grupos específicos.
    
- Las [etiquetas de retención](labels.md) proporcionan una manera de clasificar los archivos en los sitios. Cada sitio de grupo de SharePoint Online está configurado para etiquetar automáticamente los archivos de bibliotecas de documentos con una etiqueta de retención predeterminada para el sitio. Las etiquetas de este ejemplo son Interno público, Privado, Confidencial y Extremadamente confidencial, que se corresponden con las cuatro configuraciones de sitio. Los usuarios pueden cambiar las etiquetas, pero esta configuración garantiza que todos los archivos reciben una etiqueta predeterminada.
    
- Las directivas de [prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) se configuran para que las etiquetas de retención Confidencial y Extremadamente confidencial puedan advertir o prevenir a los usuarios cuando intentan enviar estos tipos de archivo fuera de la organización.
    
- Si es necesario para su escenario, puede usar [etiquetas de confidencialidad](sensitivity-labels.md) para proteger archivos confidenciales con cifrado y permisos. Para los clientes de Azure Information Protection, puede usar las etiquetas de Azure Information Protection en el Centro de cumplimiento de Microsoft 365 y las etiquetas se sincronizarán con el portal de Azure en caso de que decida realizar una configuración adicional o avanzada. Las etiquetas de Azure Information Protection y etiquetas de confidencialidad de Office 365 son totalmente compatibles entre sí. Esto significa que, por ejemplo, si tiene contenido con la etiqueta de Azure Information Protection, no tendrá que volver a clasificar o cambiar las etiquetas de su contenido. No todos los clientes necesitan este nivel de protección. 
    
## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a>Configuración de todos los inquilinos para SharePoint Online y OneDrive para la Empresa

SharePoint Online y OneDrive para la Empresa incluyen opciones de configuración de todos los inquilinos que afectan a todos los sitios y usuarios. Algunas de estas opciones también se pueden ajustar en el nivel de sitio para que sea más restrictivo (pero no para que lo sea menos). En esta sección se describe la configuración de todos los inquilinos que afecta a la seguridad y la colaboración. 
  
### <a name="sharing"></a>Uso compartido

Para esta solución, se recomienda la siguiente configuración de todos los inquilinos:
  
- Mantenga la directiva de uso compartido predeterminada, que permite compartir con todos los tipos de cuenta, incluso de forma anónima.
    
- Establezca la expiración de los vínculos anónimos, si así lo quiere.
    
- Establezca en Interno el tipo de vínculo predeterminado para el uso compartido. De esta manera se previene la pérdida accidental de datos fuera de la organización.
    
Aunque pueda parecer contradictorio permitir el uso compartido externo, este enfoque proporciona más control sobre el uso compartido de archivos en comparación con el envío de archivos por correo electrónico. SharePoint Online y Outlook funcionan conjuntamente para proporcionar una colaboración segura en los archivos. 
  
- De manera predeterminada, Outlook comparte un vínculo a un archivo en lugar de enviar el archivo por correo electrónico. 
    
- Con SharePoint Online y OneDrive para la Empresa, es muy fácil compartir vínculos a archivos con colaboradores que se encuentran tanto dentro como fuera de la organización.
    
También tiene controles que ayudan a regir el uso compartido externo. Por ejemplo, puede:
  
- Deshabilitar un vínculo de invitado anónimo.
    
- Revocar el acceso de usuario a un sitio.
    
- Ver quién tiene acceso a un sitio o documento específico.
    
- Establecer la expiración de vínculos anónimos de uso compartido (configuración de inquilino).
    
- Limitar quién puede compartir fuera de la organización (configuración de inquilino).
    
### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Combinar el uso compartido externo con la prevención de pérdida de datos (DLP)

Si no permite el uso compartido externo, los usuarios con necesidades empresariales encontrarán métodos y herramientas alternativas. Microsoft recomienda combinar el uso compartido externo con directivas DLP para proteger archivos confidenciales y altamente confidenciales.
  
### <a name="device-access-settings"></a>Configuración de acceso a dispositivos

La configuración de acceso a dispositivos para SharePoint Online y OneDrive para la Empresa permite determinar si el acceso está limitado solo al explorador (no se pueden descargar archivos) o el acceso está bloqueado. Para obtener más información, consulte [Controlar el acceso desde dispositivos no administrados](https://docs.microsoft.com/es-ES/sharepoint/control-access-from-unmanaged-devices). 

Para usar la configuración de acceso de dispositivo con las directivas de acceso condicional recomendadas en Azure Active Directory, vea [Recomendaciones de directivas para la protección de sitios y archivos de SharePoint](https://docs.microsoft.com/es-ES/microsoft-365/enterprise/sharepoint-file-access-policies).
  
### <a name="onedrive-for-business"></a>OneDrive para la Empresa

Revise esta configuración para decidir si quiere cambiar la configuración predeterminada para los sitios de OneDrive para la Empresa. Actualmente, las configuraciones de acceso a dispositivos y de uso compartido están duplicadas desde el centro de administración de SharePoint Online y se aplican a ambos entornos.
  
## <a name="sharepoint-team-site-configuration"></a>Configuración del sitio de grupo de SharePoint

En la tabla siguiente se resume la configuración para cada uno de los sitios de grupo que se han descrito en este artículo. Use estas configuraciones como punto de partida y ajuste los tipos de sitio y las configuraciones para satisfacer las necesidades de la organización. No todas las organizaciones necesitan todos los tipos de sitio. El número de organizaciones que necesita una protección extremadamente confidencial es muy reducido.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
||**Protección de base de referencia n.º 1** <br/> |**Protección de base de referencia n.º 2** <br/> |**Protección confidencial** <br/> |**Extremadamente confidencial** <br/> |
|Descripción  <br/> |Colaboración y detección abierta dentro de la organización.  <br/> |Grupo y sitio privado con uso compartido permitido fuera del grupo.  <br/> |Sitio aislado, en el que se definen niveles de acceso según la pertenencia a grupos específicos. Solo se permite el uso compartido a los miembros del sitio. DLP avisa a los usuarios cuando intentan enviar archivos fuera de la organización.  <br/> |Sitio aislado + cifrado de archivos y permisos con Azure Information Protection. DLP impide a los usuarios enviar archivos fuera de la organización.  <br/> |
|Sitio de grupo público o privado  <br/> |Público  <br/> |Private  <br/> |Private  <br/> |Private  <br/> |
|¿Quién tiene acceso?  <br/> |Todos los usuarios de la organización, incluidos los usuarios B2B y usuarios invitados.  <br/> |Solo los miembros del sitio. Otros usuarios pueden pedir acceso.  <br/> |Solo los miembros del sitio. Otros usuarios pueden pedir acceso.  <br/> |Solo los miembros. Otros usuarios no pueden pedir acceso.  <br/> |
|Controles de uso compartido en el nivel de sitio  <br/> |Uso compartido permitido con cualquier usuario. Configuración predeterminada.  <br/> |Uso compartido permitido con cualquier usuario. Configuración predeterminada.  <br/> |Los miembros no pueden compartir el acceso al sitio.  <br/> Los usuarios que no son miembros pueden pedir acceso al sitio, pero estas solicitudes deben ser supervisadas por un administrador del sitio.  <br/> |Los miembros no pueden compartir el acceso al sitio.  <br/> Los usuarios que no son miembros no pueden pedir acceso al sitio o al contenido.  <br/> |
|Controles de acceso a dispositivos en el nivel de sitio  <br/> |Sin controles adicionales.  <br/> |Sin controles adicionales.  <br/> |Impide a los usuarios descargar archivos en dispositivos no compatibles o que no están unidos a ningún dispositivo. Esto permite solamente el acceso de explorador desde los demás dispositivos.  <br/> |Impedir quela descarga de archivos en dispositivos de dominios no combinados o no compatibles.  <br/> |
|Etiquetas de retención  <br/> |Interno público  <br/> |Private  <br/> |Confidencial  <br/> |Extremadamente confidencial  <br/> |
|Directivas DLP  <br/> |||Advierten a los usuarios cuando se envían archivos etiquetados como Confidenciales fuera de la organización.  <br/> Para bloquear el uso compartido externo de tipos de datos confidenciales, como números de tarjeta de crédito u otros datos personales, puede configurar directivas DLP adicionales para estos tipos de datos (incluidos los tipos de datos personalizados que configure).  <br/> |Impiden a los usuarios enviar archivos etiquetados como Extremadamente confidencial fuera de la organización. Permiten a los usuarios anular esto si proporcionan una justificación que incluya el nombre del usuario con el que van a compartir el archivo.  <br/> |
|Etiquetas de confidencialidad  <br/> ||||Use las etiquetas de confidencialidad para cifrar y conceder permisos a los archivos automáticamente. Las etiquetas de confidencialidad usan Azure Information Protection para cifrar archivos. Esta protección viaja con los archivos en caso de que estos se pierdan.  <br/> Office 365 no puede leer los archivos cifrados con Azure Information Protection. Además, las directivas DLP solo funcionan con los metadatos (incluidas las etiquetas), pero no con los contenidos de sus archivos (como los números de tarjetas de crédito dentro de los archivos).  <br/> |
   
Para conocer los pasos para implementar los cuatro tipos distintos de sitios de grupo de SharePoint Online en esta solución, vea [Implementar sitios de SharePoint Online para tres niveles de protección](deploy-sharepoint-online-sites-for-three-tiers-of-protection.md). Para conocer los pasos para crear un entorno de desarrollo y pruebas, vea [Proteger sitios de SharePoint Online en un entorno de desarrollo y pruebas](secure-sharepoint-online-sites-in-a-dev-test-environment.md). 
  
## <a name="office-365-retention-labels"></a>Etiquetas de retención de Office 365

Se recomienda usar etiquetas de retención para entornos con datos confidenciales. Después de configurar y publicar las etiquetas de retención:
  
- Aplicar una etiqueta predeterminada a una biblioteca de documentos en un sitio de grupo de SharePoint Online, para que todos los documentos en esa biblioteca obtengan la etiqueta predeterminada. 
    
- Aplicar etiquetas a contenido automáticamente si coincide con condiciones específicas.
    
- Puede aplicar directivas DLP basadas en etiquetas de retención.
    
- Permitir que las personas de la organización apliquen manualmente una etiqueta al contenido de grupos de Outlook en la Web, Outlook 2010 y versiones posteriores, OneDrive para la Empresa, SharePoint Online y Office 365. A menudo, los usuarios son los que mejor saben con qué tipo de contenido están trabajando, por lo que pueden clasificarlo y aplicar la directiva DLP adecuada.
    
![Configuración recomendada para sitios de SharePoint](media/7fed0126-ab4a-4480-922c-681970642339.png)
  
Como se muestra, esta solución incluye la creación de las siguientes etiquetas de retención:
  
- Extremadamente confidencial
    
- Confidencial
    
- Private
    
- Interno público
    
Estas etiquetas se asignan a los sitios recomendados en las ilustraciones y los gráficos antes citados en este artículo. Esta solución recomienda configurar las directivas DLP para evitar la filtración de archivos etiquetados como “Confidencial” y “Extremadamente confidencial” a miembros ajenos a la organización.
  
Para consultar los pasos necesarios para configurar etiquetas de retención y directivas DLP en esta solución, consulte [Protección de archivos de SharePoint Online con etiquetas de retención y DLP](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md).
  
## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad 

Si existe una justificación para sus circunstancias de seguridad, puede usar las etiquetas de confidencialidad para aplicar protección a los archivos donde quiera que vayan. Las etiquetas de confidencialidad en el Centro de cumplimiento de Microsoft 365 y las etiquetas de Azure Information Protection son las mismas. Para esta solución, se recomienda usar una directiva con ámbito de Azure Information Protection y una subetiqueta de la etiqueta Extremadamente confidencial para conceder permisos y cifrar los archivos que deben protegerse con el máximo nivel de seguridad. 
  
Tenga en cuenta que, cuando se aplica el cifrado de Azure Information Protection a los archivos almacenados en Office 365, el servicio no puede procesar el contenido de estos archivos. No funcionan algunas características de colaboración, como la coautoría, eDiscovery, la búsqueda y Delve. Las directivas DLP solo pueden trabajar con los metadatos (incluidas las etiquetas de retención), pero no con el contenido de estos archivos (por ejemplo, números de tarjeta de crédito incluidos en los archivos).

Para obtener más información, vea [Información general sobre las etiquetas de retención](sensitivity-labels.md).

    
### <a name="adding-permissions-for-external-users"></a>Agregar permisos a usuarios externos

Hay dos maneras de conceder a los usuarios externos el acceso a archivos protegidos con Azure Information Protection. En ambos casos, los usuarios externos necesitan tener una cuenta de Azure AD. Si los usuarios externos no son miembros de una organización que usa Azure AD, pueden obtener una cuenta de Azure AD como usuario individual a través de esta página de suscripción: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).
  
- Agregar usuarios externos a un grupo de Azure AD que se usa para configurar la protección de una etiqueta
    
     Primero necesita agregar la cuenta como un usuario B2B en el directorio. Puede que el [almacenamiento en caché de pertenencia a grupos de Azure Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare#group-membership-caching-by-azure-rights-management) tarde un par de horas en completarse. Con este método, los permisos se conceden a todos los archivos existentes protegidos que tengan la etiqueta (incluso los archivos protegidos antes de que se agregara un usuario al grupo de Azure AD).
    
- Agregar usuarios externos directamente a la protección de etiqueta
    
     Puede agregar todos los usuarios de una organización (por ejemplo, Fabrikam.com), un grupo de Azure AD (por ejemplo, un grupo de finanzas dentro de una organización) o un usuario individual. Por ejemplo, puede agregar un equipo externo de reguladores para la protección de una etiqueta. Con este método, se conceden permisos solo a los archivos protegidos con la etiqueta después de que se haya agregado la entidad externa a la protección.
    
### <a name="deploying-and-using-azure-information-protection"></a>Implementación y uso de Azure Information Protection

Para consultar los pasos necesarios para configurar Azure Information Protection en esta solución, vea [Protección de archivos de SharePoint Online con Azure Information Protection](protect-sharepoint-online-files-with-azure-information-protection.md).
  
## <a name="see-also"></a>Vea también

[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Proteger sitios de SharePoint Online en un entorno de desarrollo y pruebas](secure-sharepoint-online-sites-in-a-dev-test-environment.md)



