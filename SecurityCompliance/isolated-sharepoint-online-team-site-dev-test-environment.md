---
title: Sitio de grupo de SharePoint Online aislado en su entorno para desarrollo y pruebas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Resumen: Configure un sitio de grupo de SharePoint Online que esté aislado del resto de la organización en su entorno para desarrollo y pruebas de Office 365.'
ms.openlocfilehash: 0aa5e6e47344134b1e103fb287f627afd2808af6
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345822"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Sitio de grupo de SharePoint Online aislado en su entorno para desarrollo y pruebas

 **Resumen**: Configure un sitio de grupo de SharePoint Online que esté aislado del resto de la organización en su entorno para desarrollo y pruebas de Office 365.
  
Sitios de equipo de SharePoint Online en Office 365 son ubicaciones para la colaboración mediante una biblioteca de documentos comunes, un bloc de notas de OneNote y otros servicios. En muchos casos, desea que todo el acceso y la colaboración entre departamentos y organizaciones. Sin embargo, en algunos casos, que desea controlar estrechamente el acceso y los permisos para la colaboración entre un pequeño grupo de personas.
  
Acceso a sitios de equipo de SharePoint Online y qué pueden hacer los usuarios se controla mediante grupos de SharePoint y los niveles de permisos. De forma predeterminada, los sitios de SharePoint Online tienen tres niveles de acceso:
  
- **Miembros**, que pueden ver, crear y modificar los recursos del sitio.
    
- **Propietarios**, que tienen un control total sobre el sitio y pueden cambiar los permisos.
    
- **Visitantes**, que únicamente pueden ver los recursos del sitio.
    
En este artículo pasos a través de la configuración de un sitio de grupo de SharePoint Online aislado para un proyecto de investigación secreto asignó un nombre ProyectoX. Los requisitos de acceso son:
  
- Solo los miembros del proyecto pueden acceder al sitio y a su contenido (documentos, Bloc de notas de OneNote y páginas), con niveles de permiso de SharePoint de edición y visualización controlados a través de la pertenencia al grupo.
    
- Únicamente el creador del sitio y los miembros de un grupo de administradores del sitio pueden llevar a cabo tareas relacionadas con la administración, lo que incluye la modificación de los permisos del sitio.
    
La configuración de un sitio de grupo de SharePoint Online aislado en su entorno para desarrollo y pruebas de Office 365 se divide en tres fases:
  
1. Crear el entorno de desarrollo y pruebas de Office 365.
    
2. Crear los usuarios y los grupos de ProyectoX.
    
3. Crear un sitio de grupo de SharePoint Online para ProyectoX y aislarlo.
    
> [!TIP]
> Haga clic [aquí](http://aka.ms/catlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de One Microsoft Cloud.
  
## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a>Fase 1: Crear un entorno de desarrollo y pruebas ligero o de una empresa simulada de Office 365

Si desea crear un sitio de grupo de SharePoint Online aislado en una forma sencilla con los requisitos mínimos, siga las instrucciones que aparecen en las fases 2 y 3 del [entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).
  
Si desea crear un sitio de grupo de SharePoint Online aislado en una configuración de empresa simulado, siga las instrucciones que aparecen en la [sincronización de directorios para el entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).
  
> [!NOTE]
> Crear un sitio de SharePoint Online aislado no requiere un entorno para desarrollo y pruebas empresarial simulado que incluya una intranet simulada conectada a Internet y una sincronización de directorios para un bosque de Windows Server AD. Se proporciona aquí como opción para que pueda probar un sitio de SharePoint Online aislado y experimentar con él en un entorno que representa una organización típica. 
  
## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: Crear cuentas de usuario y obtener acceso a grupos

Use las instrucciones en [conectarse a Office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx) para conectarse a su suscripción de trazas de Office 365 con su cuenta de administrador global de:
  
- Su equipo (para el entorno de desarrollo y pruebas ligero de Office 365).
    
- La máquina virtual CLIENTE1 (para el entorno de desarrollo y pruebas de una empresa ficticia de Office 365).
    
Para crear los nuevos grupos de acceso para el sitio de grupo ProyectoX SharePoint Online, ejecute estos comandos desde el símbolo del sistema de Windows Azure Active Directory módulo para Windows PowerShell:
  
```
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

> [!TIP]
> Haga clic [aquí](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1) para un archivo de texto que contiene todos los comandos de PowerShell en este artículo.
  
Rellene el nombre de la organización (ejemplo: contosotoycompany), el código de país de dos caracteres para su ubicación y, después, ejecute los comandos siguientes desde el símbolo del sistema de Módulo Microsoft Azure Active Directory para Windows PowerShell:
  
```
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del responsable de diseño y guárdela en un lugar seguro.
  
Ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell:
  
```
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del responsable de investigación y guárdela en un lugar seguro.
  
Ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell:
  
```
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del vicepresidente de investigación y guárdela en un lugar seguro.
  
A continuación, para agregar las cuentas de nuevo a los nuevos grupos de acceso, ejecute estos comandos de PowerShell desde el símbolo del sistema de Windows Azure Active Directory módulo para Windows PowerShell:
  
```
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Resultados:
  
- El grupo de acceso de los miembros ProyectoX contiene las cuentas de usuario potenciales Designer y potenciales entrevistador
    
- El grupo de acceso de administradores de ProyectoX contiene la cuenta de administrador global para la suscripción de prueba
    
- El grupo de acceso ProyectoX visores contiene la cuenta de usuario de VP de desarrollo
    
La figura 1 muestra los grupos de acceso y su pertenencia.
  
**Figura 1**

![Los grupos de Office 365 y su pertenencia a un sitio de grupo de SharePoint Online aislado](media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)
  
## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: Crear un sitio de grupo de SharePoint Online para ProyectoX y aislarlo

Para crear un sitio de grupo de SharePoint Online para ProyectoX, siga estos pasos:
  
1. Mediante un explorador en cualquiera de su equipo local (configuración ligero) o en CLIENT1 (configuración de empresa simulado), inicie sesión el portal de Office 365 ([https://portal.office.com](https://portal.office.com)) con su cuenta de administrador global.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña SharePoint del explorador, haga clic en **+ Crear sitio**.
    
4. En **nombre del sitio del equipo**, escriba **ProyectoX**. En **la configuración de privacidad**, seleccione **privada - sólo los miembros pueden tener acceso a este sitio**.
    
5. En **Descripción del sitio de grupo**, escriba **Sitio de SharePoint para ProyectoX** y, a continuación, haga clic en **Siguiente**.
    
6. ¿En la **que desea agregar**? panel, haga clic en **Finalizar**.
    
7. En la nueva pestaña **ProyectoX-Inicio** del explorador, en la barra de herramientas, haga clic en el icono de configuración y, a continuación, en **Permisos del sitio**.
    
8. En el panel **Permisos del sitio**, haga clic en **Configuración de permisos avanzada**.
    
9. En la nueva pestaña **Permisos: ProyectoX** del explorador, haga clic en **Configuración de solicitud de acceso**.
    
10. En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir solicitudes de acceso** (de modo que las tres casillas estén desactivadas) y, a continuación, haga clic en **Aceptar**.
    
11. Haga clic en la opción **Miembros del ProyectoX** de la lista.
    
12. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
13. En el cuadro de diálogo **Compartir**, escriba **Miembros del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.
    
14. Haga clic en el botón Volver del explorador.
    
15. Haga clic en la opción **Propietarios del ProyectoX** de la lista.
    
16. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
17. En el cuadro de diálogo **Compartir**, escriba **Administradores del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.
    
18. Haga clic en el botón Volver del explorador.
    
19. Haga clic en la opción **Visitantes del ProyectoX** de la lista.
    
20. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
21. En el cuadro de diálogo **Compartir**, escriba **Lectores del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.
    
22. Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Inicio del ProyectoX** del explorador y, a continuación, cierre el panel **Permisos del sitio**.

    
Estos son los resultados de la configuración de los permisos:
  
- El grupo de SharePoint miembros de ProyectoX contiene sólo el grupo de acceso de miembros de ProyectoX (que contiene sólo las cuentas de usuario potenciales Designer y potenciales entrevistador) y el grupo ProyectoX (que contiene sólo la cuenta de usuario de administrador global).
    
- El grupo de SharePoint de propietarios de ProyectoX contiene sólo el grupo de acceso de administradores de ProyectoX (que contiene sólo la cuenta de usuario de administrador global).
    
- El grupo de SharePoint visitantes de ProyectoX contiene sólo el grupo de acceso de visores de ProyectoX (que contiene sólo la cuenta de usuario de desarrollo VP).
    
- Los miembros no pueden modificar los permisos del nivel del sitio (solo los miembros del grupo “Administradores del ProyectoX” pueden realizar esta acción).
    
- El resto de cuentas de usuario no pueden tener acceso al sitio ni a sus recursos, y tampoco pueden solicitar acceso al sitio.
    
En la figura 2 se muestran los grupos de SharePoint y su pertenencia.
  
**Figura 2**

![Los grupos de SharePoint Online y su pertenencia a un sitio de grupo de SharePoint Online aislado](media/595abff4-64f9-49de-a37a-c70c6856936b.png)
  
Ahora vamos a demostrar acceso con la cuenta de usuario del diseñador potenciales:
  
1. Cierre la pestaña **Inicio del ProyectoX** del explorador y, a continuación, haga clic en la pestaña **Página principal de Microsoft Office**.
    
2. Haga clic en el nombre de su administrador global y, a continuación, en **Cerrar sesión**.
    
3. Inicie sesión el portal de Office 365 ([https://portal.office.com](https://portal.office.com)) con el nombre de cuenta de diseñador potenciales y su contraseña.
    
4. En la lista de iconos, haga clic en **SharePoint**.
    
5. En la ficha nuevo de **SharePoint** en el explorador, escriba **ProyectoX** en el cuadro de búsqueda, activar la búsqueda y, a continuación, haga clic en el sitio de grupo **ProyectoX** . Debería ver una nueva ficha en el explorador para el sitio de grupo ProyectoX.
    
6. Haga clic en el icono de configuración. Fíjese en que no hay ninguna opción para **Permisos del sitio**. Esto es correcto, ya que solo los miembros del grupo Administradores del ProyectoX pueden modificar los permisos del sitio.
    
7. Abra el Bloc de notas o el editor de texto que prefiera.
    
8. Copie la dirección URL del sitio de grupo de ProyectoX y péguela en una nueva línea del Bloc de notas o su editor de texto.
    
9. En la pestaña **Inicio de ProyectoX** del explorador, haga clic en **Documentos**.
    
10. Copie la dirección URL de la carpeta de documentos del ProyectoX y péguela en una nueva línea del Bloc de notas o del editor de texto.
    
11. En la pestaña **Documentos del ProyectoX** del explorador, haga clic en **Nuevo > Documento de Word**.
    
12. Escriba texto en la página **Word Online**, espere a que el estado indique **Guardado**, haga clic en el botón Atrás del explorador y, a continuación, actualice la página. Debería ver un nuevo **Documento.docx** en la carpeta **Documentos**.
    
13. Haga clic en el botón de puntos suspensivos del archivo **Documento.docx** y, a continuación, en **Obtener un vínculo**.
    
14. Copie la dirección URL en el cuadro de diálogo **Compartir 'Document.docx'** y pegarlo en una nueva línea en el Bloc de notas o el editor de texto y, a continuación, cierre el cuadro de diálogo **Compartir 'Document.docx'** .
    
15. Cierre las pestañas **Documentos del ProyectoX** y **SharePoint** del explorador y, a continuación, haga clic en la pestaña **Página principal de Microsoft Office**.
    
16. Haga clic en el nombre del **responsable de diseño** y, a continuación, en **Cerrar sesión**.

    
Ahora vamos a demostrar acceso con la cuenta de usuario de VP de desarrollo:
  
1. Inicie sesión el portal de Office 365 ([https://portal.office.com](https://portal.office.com)) con el nombre de cuenta de VP de desarrollo y su contraseña.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la ficha nuevo de **SharePoint** en el explorador, escriba **ProyectoX** en el cuadro de búsqueda, activar la búsqueda y, a continuación, haga clic en el sitio de grupo **ProyectoX** . Debería ver una nueva ficha en el explorador para el sitio de grupo ProyectoX.
    
4. Haga clic en **Documentos** y, a continuación, en el archivo **Documento.docx**.
    
5. En la pestaña **Documento.docx** del explorador, intente modificar el texto. Debería ver un mensaje con el texto **El documento es de solo lectura**. Esto ocurre porque la cuenta de usuario de vicepresidente de desarrollo solo tiene permisos de visualización en el sitio.
    
6. Cierre las pestañas **Documento.docx**, **Documentos del ProyectoX** y **SharePoint** del explorador.
    
7. En la pestaña **Página principal de Microsoft Office**, haga clic en el nombre del **vicepresidente de desarrollo** y, a continuación, en **Cerrar sesión**.

    
Ahora vamos a demostrar acceso con una cuenta de usuario que no tiene permisos:
  
1. Inicie sesión el portal de Office 365 ([https://portal.office.com](https://portal.office.com)) con el nombre de la cuenta de usuario 3 y su contraseña.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. 	En la nueva pestaña **SharePoint** del explorador, escriba **ProyectoX** en el cuadro de búsqueda y, a continuación, active la búsqueda. Debería ver el mensaje **No se encontró nada que coincida con la búsqueda**.
    
4. Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL del sitio del ProyectoX en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.
    
5. Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL de la carpeta de documentos del ProyectoX en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.
    
6. Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL del archivo Documentos.docx en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.
    
7. Desde la pestaña **SharePoint** de su explorador, haga clic en la pestaña **Página principal de Microsoft Office**, haga clic en el nombre **Usuario 3** y, a continuación, en **Cerrar sesión**.

    
Su sitio de SharePoint Online aislado ahora está listo para su experimentación adicional.
  
## <a name="next-step"></a>Paso siguiente

Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vea también

[Sitios de grupo de SharePoint Online aislados](isolated-sharepoint-online-team-sites.md)
  
[Guías de entorno de pruebas de adopción de la nube (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[Entorno de desarrollo y pruebas de la configuración básica](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)
  
[Entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




