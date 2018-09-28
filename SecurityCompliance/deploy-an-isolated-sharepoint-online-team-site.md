---
title: Implementar un sitio de grupo de SharePoint Online aislado
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 'Resumen: Implementación de un nuevo sitio de grupo SharePoint Online aislado con estas instrucciones paso a paso.'
ms.openlocfilehash: d233ec46b1e7257a92451c781afd6c61312f44b8
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345982"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Implementar un sitio de grupo de SharePoint Online aislado

 **Resumen:** Implementar un nuevo sitio de grupo SharePoint Online aislado con estas instrucciones paso a paso.
  
En este artículo es una guía paso a paso de implementación para crear y configurar un sitio de grupo de SharePoint Online aislado en Microsoft Office 365. Estos pasos supone el uso de los tres grupos de SharePoint predeterminados y niveles de permiso correspondiente, con un grupo de acceso basado en Azure Active Directory AD único para cada nivel de acceso.
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fase 1: Crear y rellenar los grupos de acceso de sitio de equipo

En esta fase, crear los tres grupos de Azure access basada en AD para grupos de SharePoint tres predeterminados y rellenará con las cuentas de usuario adecuados.
  
> [!NOTE]
> Los siguientes pasos se suponen que todas las cuentas de usuario necesarios ya existen y se asignan las licencias adecuadas. En caso contrario, por favor, agregarlos y asignar licencias antes de continuar con el paso 1. 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Paso 1: Los administradores de SharePoint Online para el sitio de lista

Determinar que el conjunto de usuario cuentas correspondiente a los administradores de SharePoint Online para el sitio de grupo aislado.
  
Si están administrando cuentas de usuario y grupos a través de Office 365 y desea usar Windows PowerShell, realice una lista de su usuario (UPN) de los nombres de entidad de seguridad (ejemplo UPN: belindan@contoso.com).
  
### <a name="step-2-list-the-members-for-the-site"></a>Paso 2: Se enumeran a los miembros del sitio

Determinar el conjunto de cuentas de usuario correspondiente a los miembros del sitio de grupo aislado, quienes se colaboran en recursos almacenados dentro del sitio.
  
Si están administrando cuentas de usuario y grupos a través de Office 365 y desea usar PowerShell, realice una lista de los UPN. Si hay una gran cantidad de miembros del sitio, puede almacenar la lista de nombres principales de usuario en un archivo de texto y agregarlos todos con un solo comando de PowerShell.
  
### <a name="step-3-list-the-viewers-for-the-site"></a>Paso 3: Enumere los visores del sitio

Determinar el conjunto de cuentas de usuario correspondiente a los visores del sitio del grupo aislado, quienes pueden ver los recursos almacenados en el sitio, pero no modificarlas o colaborar directamente en su contenido.
  
Si están administrando cuentas de usuario y grupos a través de Office 365 y desea usar PowerShell, realice una lista de los UPN. Si hay una gran cantidad de miembros del sitio, puede almacenar la lista de nombres principales de usuario en un archivo de texto y agregarlos todos con un solo comando de PowerShell.
  
Visores para el sitio pueden incluir ejecutiva, los asesores legales o partes interesadas entre departamentos.
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Paso 4: Crear los grupos de tres acceso para el sitio en Azure AD

Debe crear los siguientes grupos de acceso en Azure AD:
  
- Administradores de sitio (que contengan la lista desde el paso 1)
    
- Miembros del sitio (que contengan la lista desde el paso 2)
    
- Visores del sitio (que contengan la lista desde el paso 3)
    
1. En el explorador, vaya al portal de Azure en [https://portal.azure.com](https://portal.azure.com) y el inicio de sesión con las credenciales de una cuenta que se ha asignado con función de administrador de control de usuario o administrador de la compañía.
    
2. En Azure Portal, haga clic en **Azure Active Directory > Grupos**.
    
3. En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.
    
4. En la hoja **Grupo**:
    
  - Seleccione **Office 365** en **Tipo de grupo**.
    
  - En **nombre**, escriba el nombre del grupo.
    
  - Escriba una descripción del grupo en la **Descripción del grupo**.
    
  - Seleccione **Asignada** en **Tipo de pertenencia**.
    
5. Haga clic en **Crear** y, después, cierre la hoja **Grupo**.
    
6. Repita los pasos 3 a 5 para los grupos adicionales.
    
> [!NOTE]
> Debe utilizar el portal de Azure para crear los grupos para que tengan las características de Office habilitadas. Si un sitio de SharePoint Online aislado más adelante está configurado como un sitio altamente confidencial con una etiqueta de protección de información de Azure (AIP) para cifrar los archivos y asignar permisos a grupos específicos, los grupos permitidos deben haber creado con las características de Office habilitado. No se puede cambiar la configuración de las características de Office de un grupo de Azure AD después de que se han creado. 
  
Aquí es la configuración resultante con los grupos de acceso de tres sitios.
  
![Los tres grupos de acceso de su implementación de un sitio de SharePoint Online aislado.](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Paso 5. Agregue las cuentas de usuario a los grupos de acceso

En este paso, realice lo siguiente:
  
1. Agregar la lista de usuarios desde el paso 1 al grupo de acceso de los administradores de sitio
    
2. Agregar la lista de usuarios desde el paso 2 al grupo de acceso de miembros del sitio
    
3. Agregar la lista de usuarios desde el paso 3 al grupo de acceso de los visores de sitio
    
Si va a administrar cuentas de usuario y grupos a través de Windows Server AD, agregue los usuarios a los grupos de acceso apropiado con su usuario normal de Windows Server AD y procedimientos de administración de grupo y espere para la sincronización con su suscripción de Office 365.
  
Si va a administrar cuentas de usuario y grupos a través de Office 365, puede usar el centro de administración de Office o PowerShell. Si tiene nombres de grupo duplicado para cualquiera de los grupos de acceso, debe usar el centro de administración de Office.
  
Para el centro de administración de Office, inicie sesión con una cuenta de usuario que se ha asignado el rol de administrador de la cuenta de usuario o administrador de la compañía y usar grupos para agregar las cuentas de usuario adecuados y grupos a los grupos de acceso apropiado.
  
Para [Conectar con el módulo Azure Active Directory PowerShell V2](https://go.microsoft.com/fwlink/?linkid=842218)de primera de PowerShell.
  
A continuación, use el siguiente bloque de comando para agregar una cuenta de usuario individual a un grupo de acceso:
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> Para un archivo de texto que contiene todos los comandos de PowerShell y un Excel hoja de trabajo de configuración que genera comandos de PowerShell en función de su grupo y usuario los nombres de cuenta, descargue el [Aislado SharePoint Online equipo sitio Kit de implementación](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907). 
  
Si almacena el UPN de cuentas de usuario para cualquiera de los grupos de acceso en un archivo de texto, puede usar el siguiente bloque de comandos de PowerShell para agregarlos a la vez:
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Para PowerShell, use el siguiente bloque de comando para agregar un grupo individual a un grupo de acceso:
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

Los resultados deben ser las siguientes:
  
- Grupo de Azure AD de administradores de sitio contiene las cuentas de usuario de administración de sitios o grupos
    
- Grupo de Azure AD de miembros del sitio contiene las cuentas de usuario de sitio miembro o grupos
    
- El grupo de visores Azure AD de sitio contiene las cuentas de usuario o grupos que solo se pueden ver el contenido del sitio
    
Validar la lista de miembros del grupo para cada grupo de acceso con el centro de administración de Office o con el siguiente bloque de comandos de PowerShell:
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Aquí es la configuración resultante con los grupos de acceso de tres sitios rellenado con las cuentas de usuario o grupos.
  
![Los tres grupos de acceso completados con cuentas de usuario.](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fase 2: Crear y configurar el sitio de grupo aislado

En esta fase, crear el sitio de SharePoint Online aislado y configurar los permisos para los niveles de permisos de SharePoint Online de forma predeterminada usar los nuevos grupos de Azure access basada en AD.
  
En primer lugar, cree el sitio de grupo SharePoint Online con estos pasos.
  
1. Inicie sesión en el portal de Office 365 con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online). Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **nombre del sitio**, escriba un nombre para el sitio de grupo. 
    
6. En la **Descripción del sitio del equipo,** escriba una descripción opcional del propósito del sitio.
    
7. En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.
    
8. En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.
    
A continuación, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos.
  
1. En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.
    
2. En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).
    
3. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
    
4. En el cuadro de diálogo **Configuración de las solicitudes de acceso** , desactive **Permitir miembro para compartir el sitio y archivos y carpetas individuales** y **Permitir las solicitudes de acceso** (de manera que se desactivan todas las casillas de verificación tres) y, a continuación, haga clic en **Aceptar**.
    
5. En la ficha **permisos** del explorador, haga clic en ** \<nombre del sitio > miembros** en la lista.
    
6. En **Personas y grupos**, haga clic en **Nuevo**.
    
7. En el cuadro de diálogo **Compartir** , escriba el nombre del grupo de acceso de los miembros del sitio, selecciónelo y, a continuación, haga clic en **Compartir**.
    
8. Haga clic en el botón Volver del explorador.
    
9. Haga clic en ** \<nombre del sitio > propietarios** en la lista.
    
10. En **Personas y grupos**, haga clic en **Nuevo**.
    
11. En el cuadro de diálogo **Compartir** , escriba el nombre del grupo de acceso de los administradores del sitio, selecciónelo y, a continuación, haga clic en **Compartir**.
    
12. Haga clic en el botón Volver del explorador.
    
13. Haga clic en ** \<nombre del sitio > visitantes** en la lista.
    
14. En **Personas y grupos**, haga clic en **Nuevo**.
    
15. En el cuadro de diálogo **Compartir** , escriba el nombre del grupo de acceso de los visores del sitio, selecciónelo y, a continuación, haga clic en **Compartir**.
    
16. Cierre la pestaña **Permisos** del explorador.
    
Los resultados de esta configuración de permisos son los siguientes:
  
- La ** \<nombre del sitio > propietarios** grupo de SharePoint contiene el grupo de acceso de los administradores de sitio, en que todos los miembros tienen el nivel de permiso **control total** .
    
- La ** \<nombre del sitio > miembros** grupo de SharePoint contiene el grupo de acceso de los miembros de sitio, en la que todos los miembros tienen el nivel de permisos **Editar** .
    
- La ** \<nombre del sitio > visitantes** grupo de SharePoint contiene el grupo de acceso de los visores de sitio, en que todos los miembros tienen el nivel de permiso de **lectura** .
    
- Se deshabilita la capacidad para miembros invitar a otros miembros o para miembros solicitar acceso.
    
Aquí es la configuración resultante con los tres grupos de SharePoint para el sitio configurado para usar los tres grupos de acceso, que se rellenan con las cuentas de usuario o grupos de Azure AD.
  
![La configuración final del sitio de SharePoint Online aislado con grupos de acceso y cuentas de usuario.](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
Usted y los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar con los recursos del sitio.
  
## <a name="next-step"></a>Paso siguiente

Cuando se necesita cambiar la pertenencia al grupo de acceso de sitio o crear una carpeta de documentos con permisos personalizados, vea [administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Consulte también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)
  
[Diseñar un sitio de grupo de SharePoint Online aislado](design-an-isolated-sharepoint-online-team-site.md)
  
[Administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md)
  



