---
title: Protección de archivos de SharePoint Online con Azure Information Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumen: aplique Azure Information Protection para proteger los archivos en un sitio de grupo de SharePoint Online altamente confidencial.'
ms.openlocfilehash: 4be30059192bb954a1c2d07d34ece76bb339d7dc
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999123"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a>Protección de archivos de SharePoint Online con Azure Information Protection

 **Resumen:** Aplique Azure Information Protection para proteger los archivos en un sitio de grupo de SharePoint Online altamente confidencial.
  
Siga los pasos de este artículo para configurar Azure Information Protection para proporcionar cifrado y permisos para archivos. Estos archivos pueden agregarse a una biblioteca de SharePoint configurada para protección altamente confidencial. O bien, puede abrir un archivo directamente desde el sitio y usar al cliente de Azure Information Protection para agregar el cifrado. La protección mediante cifrado y permisos viaja con un archivo, incluso cuando se descarga desde el sitio. 

Estos pasos son parte de una solución más grande para la configuración de protección confidencial para sitios de SharePoint y los archivos de estos sitios. Para obtener más información, consulte [Protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md). 

Usar Azure Information Protection para los archivos de SharePoint Online no es recomendable para todos los clientes, pero es una opción para aquellos que necesitan este nivel de protección de un subconjunto de archivos.

Algunas notas importantes sobre esta solución:
- Cuando se aplica el cifrado de Azure Information Protection a los archivos almacenados en Office 365, el servicio no puede procesar el contenido de estos archivos. No funcionan algunas características de colaboración, como la coautoría, eDiscovery, la búsqueda y Delve. Las directivas de prevención de pérdida de datos (DLP) solo pueden trabajar con los metadatos (incluidas las etiquetas de Office 365), pero no con el contenido de estos archivos (por ejemplo, números de tarjeta de crédito incluidos en los archivos).

- Esta solución requiere que un usuario seleccione la etiqueta que aplica la protección de Azure Information Protection. Si necesita cifrado automático y que SharePoint sea capaz de indexar y comprobar los archivos, puede usar Information Rights Management (IRM) en SharePoint Online. Al configurar una biblioteca de SharePoint para IRM, los archivos se cifrarán automáticamente cuando se descarguen para su edición. IRM de SharePoint incluye limitaciones que podrían influir en su decisión. Para obtener más información, consulte [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).

## <a name="admin-setup"></a>Configuración de administración
Primero, siga las instrucciones que se indican en [Activar Azure RMS desde el Centro de administración de Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) para su suscripción de Office 365.
  
Después, siga estos pasos para configurar Azure Information Protection con una nueva directiva con ámbito y una subetiqueta para la protección y los permisos relacionados con el sitio de grupo de SharePoint Online altamente confidencial.
  
1. Inicie sesión en el centro de administración con una cuenta que tenga el rol de Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
    
2. En una pestaña independiente del explorador, vaya a Azure Portal ([https://portal.azure.com](https://portal.azure.com)).
    
3. Si es la primera vez que configura Azure Information Protection, vea [estas instrucciones](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).

4. En el panel de lista, haga clic en **Más servicios**, escriba **information** y haga clic en **Azure Information Protection**.

5. Haga clic en **Etiquetas**.
    
6. Haga clic con el botón derecho en la etiqueta **Extremadamente confidencial** y después seleccione **Agregar una subetiqueta**.
    
7. Escriba un nombre para la subetiqueta en **Nombre** y una descripción de la subetiqueta en **Descripción**.
    
8. En **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.
    
9. En la sección **Protección**, haga clic en **Azure (clave de nube)**.
    
10. En la hoja **Protección**, en **Configuración de protección**, haga clic en **Agregar permisos**.
    
11. En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **Examinar directorio**.
    
12. En el panel **Usuarios y grupos de AAD**, seleccione el grupo de acceso de miembros del sitio para el sitio de grupo de SharePoint Online extremadamente confidencial y haga clic en **Seleccionar**.
    
13. En **Seleccionar permisos del conjunto predefinido o personalizado**, haga clic en **Personalizar** y después active las casillas **Ver derechos**, **Editar contenido**, **Guardar**, **Responder** y **Responder a todos**.
    
14. Haga clic en **Aceptar** dos veces.
    
15. En la hoja **Subetiqueta**, haga clic en **Guardar** y, después, seleccione **Aceptar**.

16. En la hoja **Azure Information Protection**, haga clic en **Directivas > + Agregar una directiva**.
    
17. Escriba un nombre de la nueva directiva en **Nombre de la directiva** y una descripción en **Descripción**.
    
18. Haga clic en **Seleccionar a qué usuarios o grupos se aplica esta directiva > Usuarios o grupos** y, luego, seleccione el grupo de acceso de los miembros del sitio para su sitio de grupo de SharePoint Online extremadamente confidencial.
    
19. Haga clic en **Seleccionar > Aceptar**.

20. Haga clic en **Agregar o quitar etiquetas**. En el panel **Directiva: Agregar o quitar etiquetas**, haga clic en el nombre de la nueva subetiqueta y, después, haga clic en **Aceptar**.   

21. Haga clic en **Guardar**y después en **Aceptar**.
 
## <a name="client-setup"></a>Instalación del cliente
Ya está listo para empezar a crear documentos y protegerlos con Azure Information Protection y su nueva etiqueta.
  
Necesita [instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en el dispositivo o equipo basado en Windows. Puede generar scripts y automatizar la instalación, o bien los usuarios pueden instalar el cliente de forma manual. Vea los recursos siguientes:
  
- [El lado cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [Instalación del cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [Página de descarga para la instalación manual](https://www.microsoft.com/download/details.aspx?id=53018)
    
Cuando se complete la instalación, los usuarios ejecutarán y, después, iniciarán sesión desde una aplicación de Office (como Microsoft Word) con su cuenta de Office 365. Una nueva barra de **Information Protection** permite a los usuarios seleccionar la nueva etiqueta. Asegúrese de que los usuarios conozcan el sitio de grupo de SharePoint Online y la etiqueta que necesitan usar para proteger sus archivos altamente confidenciales.
  
> [!NOTE]
> Si tiene varios sitios de grupo de SharePoint Online extremadamente confidenciales, deberá crear varias directivas con ámbito de Azure Information Protection que contengan subetiquetas con la configuración anterior, con los permisos de cada subetiqueta establecidos en el grupo de acceso de miembros de sitio de un equipo de grupo concreto de SharePoint Online. 
  
## <a name="adding-permissions-for-external-users"></a>Agregar permisos para usuarios externos
Hay dos maneras de conceder a los usuarios externos el acceso a archivos protegidos con Azure Information Protection. En ambos casos, los usuarios externos necesitan tener una cuenta de Azure AD. Si los usuarios externos no son miembros de una organización que usa Azure AD, pueden obtener una cuenta de Azure AD como usuario individual a través de esta página de suscripción: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Agregar usuarios externos a un grupo de Azure AD que se usa para configurar la protección de una etiqueta. Primero debe agregar la cuenta como un usuario B2B en el directorio. Puede que el [almacenamiento en caché de pertenencia al grupo de Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) tarde un par de horas.  
 - Agregar usuarios externos directamente a la protección de etiqueta. Puede agregar todos los usuarios de una organización (por ejemplo, Fabrikam.com), un usuario o un grupo de Azure AD (como un grupo de finanzas dentro de una organización). Puede agregar, por ejemplo, un grupo de reguladores externo para la protección de una etiqueta.

## <a name="see-also"></a>Consulte también

[Protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md)
  
[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
