---
title: Diseñar un sitio de grupo de SharePoint Online aislado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Resumen: paso a paso del proceso de diseño de sitios de grupo de SharePoint Online aislados.'
ms.openlocfilehash: 09748fcc22a4a48efc4346ff75a225db612a0ef4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257194"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Diseñar un sitio de grupo de SharePoint Online aislado

 **Resumen:** Recorra el proceso de diseño de sitios de grupo de SharePoint Online aislados.
  
Este artículo le guiará por las decisiones de diseño clave que debe tomar antes de crear un sitio de grupo de SharePoint Online aislado.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: determinar los grupos de SharePoint y los niveles de permisos

Todos los sitios de grupo de SharePoint Online se crean de forma predeterminada con los siguientes grupos de SharePoint:
  
- \<Miembros de name> de sitio
    
- \<Visitantes del sitio name>
    
- \<Propietarios de name> de sitios
    
Estos grupos son independientes de los grupos de Office 365 y Azure Active Directory (AD) y constituyen la base para asignar permisos a los recursos del sitio.
  
El conjunto de permisos específicos que determina lo que un miembro de un grupo de SharePoint puede hacer en un sitio es un nivel de permisos. De forma predeterminada, hay tres niveles de permisos para un sitio de grupo de SharePoint Online: editar, leer y control total. La siguiente tabla muestra la correlación predeterminada de los grupos de SharePoint y los niveles de permisos asignados:
  
|**Grupo de SharePoint**|**Nivel de permisos**|
|:-----|:-----|
|\<Miembros de name> de sitio  <br/> |Editar  <br/> |
|\<Visitantes del sitio name>  <br/> |Lectura  <br/> |
|\<Propietarios de name> de sitios  <br/> |Control total  <br/> |
   
 **Procedimiento recomendado:** Puede crear grupos de SharePoint y niveles de permisos adicionales. Sin embargo, se recomienda usar los grupos de SharePoint y los niveles de permisos predeterminados para el sitio de SharePoint Online aislado.
  
Estos son los grupos de SharePoint y los niveles de permisos predeterminados.
  
![Los grupos de SharePoint y los niveles de permisos predeterminados para un sitio de SharePoint Online.](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: asignar permisos a los usuarios con grupos de acceso

Para asignar permisos a usuarios, puede agregar su cuenta de usuario, o un grupo de Office 365 o Azure AD del que la cuenta de usuario es miembro, a los grupos de SharePoint. Una vez agregadas, a las cuentas de usuario de Office 365, ya sea directa o indirectamente la pertenencia a un grupo de Office 365 o de Azure AD, se les asigna el nivel de permisos asociado con el grupo de SharePoint.
  
Con los grupos de SharePoint predeterminados como ejemplo:
  
- Los miembros del grupo de SharePoint ** \<miembros del sitio name>** , que pueden incluir cuentas de usuario y grupos, tienen asignado el nivel de permisos de **edición** .
    
- Los miembros del grupo de ** \<SharePoint name> visitantes** , que pueden incluir cuentas de usuario y grupos, tienen asignado el nivel de permisos de **lectura** .
    
- A los miembros del grupo de SharePoint ** \<propietarios de name> de sitios** , que pueden incluir cuentas de usuario y grupos, se les asigna el nivel de permisos **control total**
    
 **Procedimiento recomendado:** Aunque puede administrar permisos mediante cuentas de usuario individuales, en su lugar se recomienda usar un único grupo de Azure AD, conocido como grupo de acceso. Esto simplifica la administración de permisos a través de la pertenencia al grupo de acceso, en lugar de administrar la lista de cuentas de usuario para cada grupo de SharePoint.
  
Los grupos de Azure AD para Office 365 son distintos de los grupos de Office 365. Los grupos de Azure AD aparecen en el centro de administración de Office con su **tipo** establecido en **seguridad** y no tienen una dirección de correo electrónico. Los grupos de Azure AD se pueden administrar dentro de:
  
- Windows Server Active Directory (AD)
    
    Estos son grupos que se han creado en su infraestructura local de Windows Server AD y sincronizados con su suscripción a Office 365. En el centro de administración de Office, estos grupos tienen un **Estado** **sincronizado con Active**Directory.
    
- Office 365
    
    Se trata de grupos que se han creado con el centro de administración de Office, el portal de Azure o PowerShell de Microsoft. En el centro de administración de Office, estos grupos tienen un **Estado** de **nube**.
    
 **Procedimiento recomendado:** Si está usando Windows Server AD local y sincronizándose con su suscripción de Office 365, realice la administración de usuarios y grupos con Windows Server AD.
  
Para los sitios de grupo de SharePoint Online aislados, la estructura de grupo recomendada tiene el siguiente aspecto:
  
|**Grupo de SharePoint**|**Grupo de acceso basado en Azure AD**|**Nivel de permisos**|
|:-----|:-----|:-----|
|\<Miembros de name> de sitio  <br/> |\<Miembros de name> de sitio  <br/> |Editar  <br/> |
|\<Visitantes del sitio name>  <br/> |\<Visores de name> de sitio  <br/> |Lectura  <br/> |
|\<Propietarios de name> de sitios  <br/> |\<Administradores de name> de sitios  <br/> |Control total  <br/> |
   
 **Procedimiento recomendado:** Aunque puede usar los grupos Office 365 o Azure AD como miembros de los grupos de SharePoint, le recomendamos que use grupos de Azure AD. Los grupos de Azure AD, administrados mediante Windows Server AD o Office 365, proporcionan más flexibilidad para usar grupos anidados para asignar permisos.
  
Estos son los grupos predeterminados de SharePoint configurados para usar grupos de acceso basados en Azure AD.
  
![Uso de grupos de acceso como miembros de grupos de sitio de SharePoint Online predeterminados.](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
Al diseñar los tres grupos de acceso, tenga en cuenta lo siguiente:
  
- Solo debe haber unos pocos miembros en el ** \<** grupo de acceso de administradores de name> de sitios que correspondan a un pequeño número de administradores de SharePoint Online que administran el sitio de grupo.
    
- La mayoría de los miembros del sitio se encuentran en los grupos de acceso ** \<name> miembros** del sitio o ** \<sitios name> visores** . Como los miembros del sitio ** \<** en el grupo de acceso de miembros de name> del sitio tienen la capacidad de eliminar o modificar los recursos del sitio, considere detenidamente su pertenencia. Si tiene dudas, agregue el miembro de sitio al grupo de acceso de ** \<visores del sitio name>** .
    
Este es un ejemplo de los grupos de SharePoint y los grupos de acceso para un sitio aislado denominado ProyectoX.
  
![Un ejemplo del uso de grupos de acceso para un sitio de SharePoint Online denominado ProyectoX.](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: usar grupos anidados de Azure AD

Para un proyecto limitado a un número reducido de personas, un solo nivel de grupos de acceso basado en Azure AD que se agrega a los grupos de SharePoint del sitio se ajustará a la mayoría de los escenarios. Sin embargo, si tiene un gran número de personas y esas personas ya son miembros de grupos de Azure AD establecidos, puede asignar permisos de SharePoint más fácilmente mediante grupos anidados o grupos que contengan otros grupos como miembros.
  
Por ejemplo, desea crear un sitio de grupo aislado de SharePoint Online para colaborar entre los ejecutivos de los departamentos de ventas, marketing, ingeniería, legal y soporte técnico, y los departamentos que ya poseen sus propios grupos con cuenta de usuario Ejecutiva miembros. En lugar de crear un grupo nuevo para los nuevos miembros del sitio y colocar en él todas las cuentas de usuario Ejecutiva, coloque los grupos ejecutivos existentes para cada departamento en el nuevo grupo.
  
 Si está compartiendo una suscripción de Office 365 entre varias organizaciones, un único nivel de pertenencia al grupo de un sitio aislado para una organización podría ser difícil de administrar debido al número total de cuentas de usuario. En este caso, puede usar grupos anidados de Azure AD para cada organización que contenga los grupos dentro de sus organizaciones para administrar los permisos.
  
Para usar grupos anidados de Azure AD:
  
1. Identifique o cree los grupos de Azure AD que contendrán cuentas de usuario y agregue las cuentas de usuario adecuadas como miembros.
    
2. Cree el grupo de acceso de Azure AD basado en el contenedor que contendrá los otros grupos de Azure AD y agregue esos grupos como miembros.
    
3.  Para el nivel adecuado de acceso para el grupo de acceso del contenedor, identifique el grupo de SharePoint y el nivel de permisos correspondiente.
    
> [!NOTE]
> No puede usar grupos de Office 365 anidados. 
  
Este es un ejemplo de grupos de Azure AD anidados para el grupo de acceso a los miembros del ProyectoX.
  
![Un ejemplo del uso de grupos de acceso anidados para el grupo de acceso de los miembros del sitio del ProyectoX.](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Debido a que todas las cuentas de usuario de los equipos de clientes potenciales de investigación, ingeniería y proyecto tienen como objetivo ser miembros del sitio, es más fácil agregar sus grupos de Azure AD al grupo de acceso de los miembros del ProyectoX.
  
## <a name="next-step"></a>Siguiente paso

Cuando esté listo para crear y configurar un sitio aislado en producción, vea [implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vea también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)
  
[Administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)



