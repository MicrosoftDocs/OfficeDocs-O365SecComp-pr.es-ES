---
title: Diseñar un sitio de grupo de SharePoint Online aislado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Resumen: Paso a través del proceso de diseño para sitios de grupo de SharePoint Online aislados.'
ms.openlocfilehash: bd36044eb16b9f6ee3ee9bbb444fe8f4efe2fd63
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345812"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Diseñar un sitio de grupo de SharePoint Online aislado

 **Resumen:** Paso a través del proceso de diseño para sitios de grupo de SharePoint Online aislados.
  
En este artículo se le guiará por las decisiones de diseño clave que se deben realizar antes de crear un sitio de grupo de SharePoint Online aislado.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: Determinar los grupos de SharePoint y los niveles de permisos

Cada sitio de grupo SharePoint Online de forma predeterminada se crea con los siguientes grupos de SharePoint:
  
- \<nombre del sitio > (miembros de)
    
- \<nombre del sitio > visitantes
    
- \<nombre del sitio > propietarios
    
Estos grupos son independientes de grupos de Office 365 y Azure Active Directory (AD) y la base de asignación de permisos para los recursos del sitio.
  
El conjunto de permisos específicos que determina lo que puede hacer un miembro de un grupo de SharePoint en un sitio es un nivel de permisos. Hay tres niveles de permisos de forma predeterminada para un sitio de grupo SharePoint Online: editar, lectura y control total. En la siguiente tabla se muestra la correlación predeterminada de los grupos de SharePoint y niveles de permisos:
  
|**Grupo de SharePoint**|**Nivel de permisos**|
|:-----|:-----|
|\<nombre del sitio > (miembros de)  <br/> |Editar  <br/> |
|\<nombre del sitio > visitantes  <br/> |Lectura  <br/> |
|\<nombre del sitio > propietarios  <br/> |Control total  <br/> |
   
 **Recomendado:** Puede crear grupos de SharePoint adicionales y niveles de permisos. Sin embargo, se recomienda usar los grupos de SharePoint predeterminados y niveles de permisos para el sitio de SharePoint Online aislado.
  
Aquí son los grupos de SharePoint predeterminados y niveles de permisos.
  
![Los grupos y niveles de permisos predeterminados de SharePoint de un sitio de SharePoint Online.](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: Asignar permisos a los usuarios con los grupos de acceso

Puede asignar permisos a los usuarios mediante la adición de su cuenta de usuario o un grupo de Office 365 o Azure AD de que la cuenta de usuario es un miembro, a los grupos de SharePoint. Una vez agregado, las cuentas de usuario de Office 365, ya sea directamente o indirectamente a través de la pertenencia a un grupo de Office 365 o Azure AD, se asigna el nivel de permisos asociado con el grupo de SharePoint.
  
Uso de los grupos de SharePoint de forma predeterminada como un ejemplo:
  
- Los miembros de la ** \<nombre del sitio > miembros** grupo de SharePoint, que puede incluir los grupos y cuentas de usuario, se asigna el nivel de permisos **Editar**
    
- Los miembros de la ** \<nombre del sitio > visitantes** grupo de SharePoint, que puede incluir los grupos y cuentas de usuario, tienen asignado el nivel de permiso de **lectura**
    
- Los miembros de la ** \<nombre del sitio > propietarios** grupo de SharePoint, que puede incluir los grupos y cuentas de usuario, se asigna el nivel de permiso **control total**
    
 **Recomendado:** Aunque puede administrar los permisos a través de las cuentas de usuario individuales, se recomienda que utilice un único grupo de Azure AD, conocido como un grupo de acceso, en su lugar. Esto simplifica la administración de permisos a través de la pertenencia al grupo de acceso, en lugar de cuentas de administración de la lista de usuario para cada grupo de SharePoint.
  
Los grupos de AD Azure para Office 365 son diferentes de los grupos de Office 365. Grupos de Azure AD aparecen en el centro de administración de Office con su conjunto de **tipo de** **seguridad** y no tienen una dirección de correo electrónico. Grupos de Azure AD pueden administrarse dentro de:
  
- Windows Server Active Directory (AD)
    
    Estos son los grupos que se han creado en la infraestructura de Windows Server AD local y se sincronizan con su suscripción de Office 365. En el centro de administración de Office, estos grupos tienen un **estado** de **Synched con Active Directory**.
    
- Office 365
    
    Estos son los grupos que se han creado mediante el centro de administración de Office, el portal de Azure o Microsoft PowerShell. En el centro de administración de Office, estos grupos tienen un **estado** de **la nube**.
    
 **Recomendado:** Si está utilizando Windows Server AD local y sincronizar con su suscripción de Office 365, realizar el usuario y la administración de grupo con Windows Server AD.
  
Para los sitios de equipo de SharePoint Online aislados, la estructura de grupo recomendado tiene este aspecto:
  
|**Grupo de SharePoint**|**Grupo de Azure access basada en AD**|**Nivel de permisos**|
|:-----|:-----|:-----|
|\<nombre del sitio > (miembros de)  <br/> |\<nombre del sitio > (miembros de)  <br/> |Editar  <br/> |
|\<nombre del sitio > visitantes  <br/> |\<nombre del sitio > visores  <br/> |Lectura  <br/> |
|\<nombre del sitio > propietarios  <br/> |\<nombre del sitio > administradores  <br/> |Control total  <br/> |
   
 **Recomendado:** Aunque se pueden usar Office 365 o Azure AD grupos como miembros de grupos de SharePoint, se recomienda usar grupos de Azure AD. Azure grupos de AD, administrados a través de Windows Server AD o Office 365, proporcionan más flexibilidad para utilizar grupos anidados para asignar permisos.
  
Aquí es el valor predeterminado configurados para usar grupos de Azure access basada en AD los grupos de SharePoint.
  
![Uso de grupos de acceso como miembros de grupos de sitio de SharePoint Online predeterminados.](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
Al diseñar los grupos de tres acceso, tenga en cuenta lo siguiente:
  
- Debería haber solo unos pocos miembros en el ** \<nombre del sitio > administradores** grupo de acceso, correspondiente a un número pequeño de administradores de SharePoint Online que están administrando el sitio de grupo.
    
- La mayoría de los miembros de su sitio se encuentran en el ** \<nombre del sitio > miembros** o ** \<nombre del sitio > visores** tener acceso a grupos. Debido a que los miembros en el sitio la ** \<nombre del sitio > (miembros)** grupo de acceso tienen la capacidad para eliminar o modificar los recursos en el sitio, considere detenidamente su pertenencia al grupo. En caso de duda, agregar el miembro del sitio para la ** \<nombre del sitio > visores** grupo de acceso.
    
Este es un ejemplo de los grupos de SharePoint y los grupos de acceso para un sitio aislado denominado ProyectoX.
  
![Un ejemplo del uso de grupos de acceso de un sitio de SharePoint Online denominado ProjectX.](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: Utilice las anidadas grupos de Azure AD

Para un proyecto que se limita a un número reducido de personas, un único nivel de grupos de Azure access basada en AD agregado a los grupos de SharePoint del sitio quepan la mayoría de los escenarios. Sin embargo, si tiene un gran número de personas y a aquellas personas ya miembros de establecimiento de los grupos de Azure AD, puede asignar más fácilmente los permisos de SharePoint mediante el uso de grupos anidados o grupos que contienen otros grupos como miembros.
  
Por ejemplo, en el que desea crear un sitio de equipo online aislado de SharePoint para la colaboración entre los ejecutivos de las ventas, marketing, ingeniería, legal y compatibilidad departamentos y esos ya en sus propios grupos con la cuenta de usuario de ejecutivos pertenencia a. En lugar de crear un nuevo grupo para los nuevos miembros del sitio y realizar todas las cuentas de usuario individuales de ejecutivos en ella, coloque los grupos de ejecutivos existentes para cada departamento en el nuevo grupo.
  
 Si va a compartir entre varias organizaciones de una suscripción a Office 365, un único nivel de pertenencia al grupo de un sitio aislado para una organización es posible que a ser difícil de administrar debido al gran número de cuentas de usuario. En este caso, puede usar grupos de Azure AD para cada organización que contienen los grupos dentro de sus organizaciones para administrar los permisos anidados.
  
Para usar grupos de Azure AD anidados:
  
1. Identifique o cree los grupos de Azure AD que contendrá las cuentas de usuario y agregar las cuentas de usuario apropiadas como miembros.
    
2. Crear el grupo de Azure access basada en AD de contenedor que va a contener otros grupos de Azure AD y agregar esos grupos como miembros.
    
3.  Para el nivel de acceso para el grupo de acceso de contenedor apropiado, identifique el grupo de SharePoint y el nivel de permiso correspondiente.
    
> [!NOTE]
> No puede usar los grupos anidados de Office 365. 
  
Este es un ejemplo de Azure AD anidado grupos para el grupo de acceso de miembro ProyectoX.
  
![Un ejemplo del uso de los grupos de acceso anidados para el grupo de acceso de los miembros del sitio ProjectX.](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Debido a que todas las cuentas de usuario en la investigación, ingeniería y proyecto de clientes potenciales equipos están diseñados para ser miembros del sitio, es más fácil agregar sus grupos de Azure AD al grupo de acceso de los miembros de ProyectoX.
  
## <a name="next-step"></a>Paso siguiente

Cuando esté listo para crear y configurar un sitio aislado en producción, vea [implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Consulte también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)
  
[Administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)



