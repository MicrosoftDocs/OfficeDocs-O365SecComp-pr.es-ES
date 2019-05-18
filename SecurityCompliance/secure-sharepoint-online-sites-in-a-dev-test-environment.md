---
title: Protección de sitios de SharePoint Online en un entorno de desarrollo y pruebas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/09/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Resumen: cree sitios de grupo de SharePoint Online en un entorno de desarrollo y pruebas, que pueden ser públicos, privados, confidenciales o extremadamente confidenciales.'
ms.openlocfilehash: 743a008a1d445d63054888499a0a805e546a1a4c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158822"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>Protección de sitios de SharePoint Online en un entorno de desarrollo y pruebas

 **Resumen:** cree sitios de grupo de SharePoint Online en un entorno de desarrollo y pruebas, que pueden ser públicos, privados, confidenciales o extremadamente confidenciales.
  
En este artículo, se ofrecen instrucciones paso a paso para crear un entorno de desarrollo y pruebas donde se incluyan los cuatro tipos de sitios de grupo de SharePoint Online para la solución [Protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md).
  
![Los cuatro sitios de grupo del entorno de desarrollo y pruebas de SharePoint Online seguro.](media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
Con este entorno de prueba y desarrollo podrá experimentar con los comportamientos de protección de la información y ajustar la configuración a sus necesidades concretas antes de implementar sitios de grupo de SharePoint Online en producción.
  
## <a name="phase-1-create-your-devtest-environment"></a>Fase 1: Crear el entorno de prueba y desarrollo

En esta fase se obtienen suscripciones de prueba para Office 365 y Enterprise Mobility + Security (EMS) para una organización ficticia.
  
Siga primero las instrucciones de la **fase 2** del [entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).
  
Después, regístrese en la suscripción de prueba de EMS y agréguela a la misma organización de la suscripción de prueba de Office 365.
  
1. Si es necesario, inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de la cuenta de administrador global de la suscripción de prueba.
    
2. En el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.
    
3. En la página **Servicios de compra**, busque el elemento **Enterprise Mobility + Security E5**. Mantenga el puntero del mouse sobre ese elemento y haga clic en **Iniciar prueba gratuita**.
    
4. En la página **Confirmar pedido**, haga clic en **Probar ahora**.
    
5. En la página **Recibo del pedido**, haga clic en **Continuar**.
    
Después, habilite la licencia de Enterprise Mobility + Security E5 para la cuenta de administrador global.
  
1. En la pestaña **Centro de administración de Microsoft 365** del explorador, en el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
    
2. Haga clic en la cuenta de administrador global y, después, en **Editar** para **Licencias de productos**.
    
3. En el panel **Licencias de productos**, cambie la licencia del producto de **Enterprise Mobility + Security E5** a **Activada**, seleccione **Guardar** y, después, haga clic en **Cerrar** dos veces.
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fase 2: Crear y configurar los usuarios y grupos de Azure Active Directory (AD)

En esta fase se crean y configuran los grupos y usuarios de Azure AD para la organización ficticia.
  
Primero, cree un conjunto de grupos para una organización típica en Azure Portal.
  
1. En otra pestaña del explorador, vaya a Azure Portal en [https://portal.azure.com](https://portal.azure.com). Si es necesario, inicie sesión con las credenciales de la cuenta de administrador global de la suscripción de prueba de Office 365 E5.
    
2. En Azure Portal, haga clic en **Azure Active Directory > Grupos**.
    
3. En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.
    
4. En la hoja **Grupo**:
    
  - Seleccione **Office 365** en **Tipo de grupo**.
    
  - Escriba **Directivos** en **Nombre**.
    
  - Seleccione **Asignada** en **Tipo de pertenencia**.
      
5. Haga clic en **Crear** y, después, cierre la hoja **Grupo**.
    
6. Repita los pasos del 3 al 5 para los siguientes nombres de grupo:
    
  - IT staff (Personal de TI)
    
  - Research staff (Personal de investigación)
    
  - Regular staff (Personal normal)
    
  - Marketing staff (Personal de marketing)
    
  - Sales staff (Personal de ventas)
    
7. Mantenga la pestaña de Azure Portal abierta en el explorador.
    
Después, configure la asignación automática de licencias para que se asignen licencias de forma automática a los miembros de los grupos para las suscripciones de Office 365 y EMS.
  
1. En Azure Portal, haga clic en **Azure Active Directory > Licencias > Todos los productos**.
    
2. En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y, después, haga clic en **+ Asignar**.
    
3. En la hoja **Asignar licencia**, haga clic en **Usuarios y grupos**.
    
4. En la lista de grupos, seleccione lo siguiente:
    
  - C-Suite (Directivos)
    
  - IT staff (Personal de TI)
    
  - Research staff (Personal de investigación)
    
  - Regular staff (Personal normal)
    
  - Marketing staff (Personal de marketing)
    
  - Personal de ventas
    
5. Haga clic en **Seleccionar** y, después, en **Asignar**.
    
6. Cierre la pestaña Azure Portal del explorador.
    
Después conéctese al módulo de PowerShell de Azure Active Directory para Graph como se indica en el artículo [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Rellene el nombre de la organización, la ubicación y una contraseña común; después, ejecute los siguientes comandos desde el símbolo del sistema de PowerShell o el entorno de scripts integrado (ISE) para crear cuentas de usuario y agregarlas a sus respectivos grupos:
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> Se usa una contraseña común para automatizar y facilitar la configuración de un entorno de prueba y desarrollo. Evidentemente, esto no se recomienda en el caso de suscripciones de producción. 
  
Después, siga estos pasos para comprobar que la asignación de licencias basada en grupos funcione correctamente.
  
1. En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Administrador**.
    
2. En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Usuarios**.
    
3. En la lista de usuarios, haga clic en **CEO** (Consejero delegado).
    
4. En el panel que muestra las propiedades de la cuenta de usuario **CEO**, compruebe que se le han asignado las licencias **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** (en **Licencias de productos**).
    
## <a name="phase-3-create-office-365-retention-labels"></a>Fase 3: crear etiquetas de retención de Office 365

En esta fase, se crean las etiquetas de retención para los diferentes niveles de seguridad de las carpetas de documentos de sitios de grupo de SharePoint Online.


1. Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con su cuenta de administrador global.
    
2. En la pestaña **Inicio: cumplimiento de Microsoft 365** del navegador, haga clic en **Clasificaciones > Etiquetas**.
    
3. Haga clic en **Etiquetas de retención > Crear una etiqueta**.
    
4. En el panel **Nombre de la etiqueta**, escriba **Público interno** en **el espacio provisto**, y después haga clic en **Siguiente**.

5. En el panel **descriptores de plan de archivos**, haga clic en **Siguiente**.
    
6. En el panel **Configuración de etiqueta**, si es necesario, marque **Retención** como **Activada** y haga clic en **Siguiente**.
    
7. En el panel **Revise su configuración**, haga clic en **Crear la etiqueta**.
    
8. Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:
    
  - Private
    
  - Confidencial
    
  - Extremadamente confidencial
  
9. En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).
    
10. En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.
    
11. En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.
    
12. Haga clic en **Listo**.
    
13. En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.
    
14. En el panel **Seleccionar ubicaciones**, haga clic en **Siguiente**.
    
15. En el panel **Escriba un nombre para la directiva**, escriba **Organización de ejemplo** en **Nombre** y haga clic en **Siguiente**.
    
16. En el panel **Revise la configuración**, haga clic en **Publicar etiquetas** y, después, en **Cerrar**.
    
## <a name="phase-4-create-your-sharepoint-online-team-sites"></a>Fase 4: Crear los sitios de grupo de SharePoint Online

En esta fase se crean y configuran los cuatro tipos de sitios de grupo de SharePoint Online de la organización de ejemplo.
  
### <a name="organization-wide-team-site"></a>Sitio de grupo De organización

Para crear un sitio de grupo público de línea base de SharePoint Online, haga lo siguiente:
  
1. Si es necesario, inicie sesión en el [portal de Office 365](https://portal.office.com) con las credenciales de la cuenta de administrador global de la suscripción de prueba.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Nombre del sitio**, escriba **En toda la organización**. 
    
6. En **Descripción del sitio de grupo**, escriba **Sitio de SharePoint para toda la organización**.
    
7. En **Configuración de privacidad**, seleccione **Público: cualquier usuario de la organización puede obtener acceso a este sitio** y, después, haga clic en **Siguiente**.
    
8. En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.
    
Después configure la carpeta de documentos del sitio de grupo en toda la organización para la etiqueta Interno público.
  
1. En la pestaña **En toda la organización: Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y, después, en **Configuración de la biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Aplicar la etiqueta a los elementos de esta biblioteca**.
    
4. En **Configuración: Aplicar etiqueta**, seleccione **Interno público** y haga clic en **Guardar**.
    
### <a name="project-1-team-site"></a>Sitio de grupo Proyecto 1

Para crear un sitio de grupo de SharePoint Online privado como línea base para un proyecto dentro de la organización, siga este procedimiento:
  
1. Si es necesario, inicie sesión en el [portal de Office 365](https://portal.office.com) con las credenciales de la cuenta de administrador global de la suscripción de prueba.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Nombre del sitio**, escriba **Proyecto 1**. 
    
6. En **Descripción del sitio de grupo**, escriba **Sitio de SharePoint para Proyecto 1**.
    
7. En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.
    
8. En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.
    
Después, configure la carpeta de documentos del sitio de grupo Proyecto 1 para la etiqueta Privado.
  
1. En la pestaña **Proyecto 1: Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y, después, en **Configuración de la biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración: Aplicar etiqueta**, seleccione **Privado** y haga clic en **Guardar**.
    
### <a name="marketing-campaigns-team-site"></a>Sitio de grupo Campañas de marketing

Para crear un sitio de grupo de SharePoint Online aislado que tenga el nivel confidencial para recursos de campañas de marketing, siga este procedimiento:

 
1. Si es necesario, inicie sesión en el [portal de Office 365](https://portal.office.com) con las credenciales de la cuenta de administrador global de la suscripción de prueba.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Team site name** (Nombre del sitio de grupo), escriba **Campañas de marketing**.
    
6. En **Descripción del sitio de grupo**, escriba **Sitio de SharePoint para recursos de campañas de marketing (confidencial)**.
    
7.  En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.
    
8. En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.
    
9. En la barra de herramientas de la nueva pestaña **Campañas de marketing** del explorador, haga clic en el icono de configuración y, después, en **Permisos del sitio**.
    
10. En el panel **Permisos del sitio**, haga clic en **Configuración de permisos avanzada**.
    
11. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
    
12. En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive las casillas **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio**, escriba **ITAdmin1@**\<nombre de la organización>**.onmicrosoft.com** en **Enviar todas las solicitudes de acceso** y, después, haga clic en **Aceptar**.
    
13. Haga clic en **Campañas de Marketing: Miembros** en la lista.
    
14. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
15. En el cuadro de diálogo **Compartir**, escriba **Personal de marketing**, selecciónelo y haga clic en **Compartir**.
    
16. Repita los pasos 14 y 15 para la cuenta de usuario **Investigador1**.
    
17. Haga clic en el botón Volver del explorador.
    
18. Haga clic en **Campañas de marketing: Propietarios** en la lista.
    
19. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
20. En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.
    
21. Haga clic en el botón Volver del explorador.
    
22. Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Campañas de marketing: Inicio** del explorador y, después, cierre el panel **Permisos del sitio**.
    
Estos son los resultados de la configuración de los permisos:
  
- El grupo de SharePoint **Campañas de marketing-Miembros** solamente contiene el grupo **Campañas de marketing** (que contiene la cuenta de usuario de administrador global), el grupo **Marketing staff** [Personal de marketing] \(que contiene las cuentas de usuario Marketing1 y Marketing2) y la cuenta de usuario **Researcher1**.
    
- El grupo de SharePoint **Campañas de marketing-Propietarios** solo contiene el grupo **IT staff** [Personal de TI] \(que contiene únicamente las cuentas de usuario ITAdmin1 e ITAdmin2).
    
- El grupo de SharePoint **Campañas de marketing-Visitantes** no contiene grupos ni cuentas de usuario.
    
- Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Campañas de marketing: Propietarios**).
    
- Otras cuentas de usuario no pueden acceder al sitio ni a sus recursos, pero pueden pedir acceso al sitio, que enviará un correo electrónico al buzón de la cuenta de usuario ITAdmin1.
    
Después, configure la carpeta de documentos del sitio de grupo Campañas de marketing para la etiqueta Confidencial.
  
1. En la pestaña **Campañas de marketing: Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y, después, en **Configuración de la biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración: Aplicar etiqueta**, seleccione **Confidencial** y, después, haga clic en **Guardar**.
    
Luego configure una directiva de prevención de pérdida de datos (DLP) que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Confidencial, que incluye el sitio Campañas de marketing, fuera de la organización.

1. Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) con su cuenta de administrador global.
    
2. En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.
    
3. En el panel **Inicio > Prevención de pérdida de datos**, haga clic en **Crear una directiva**.
    
4. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
    
5. En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Confidencial** en **Nombre** y haga clic en **Siguiente**.
    
6. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.
    
7. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.
    
8. En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Editar**.
    
9. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.
    
10. En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.
    
11. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
    
12. En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Siguiente**.

13. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
    
14. En el panel **Personalizar sugerencias de directiva y notificaciones de correo electrónico**, haga clic en **Personalizar el texto de la sugerencia de directiva**.
    
15. En el cuadro de texto, escriba o pegue una de las siguientes sugerencias, dependiendo de si ha implementado Azure Information Protection para proteger los archivos más confidenciales:
    
  - Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
    
16. Haga clic en **Aceptar**.
    
17. En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.
    
18. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.
    
19. En el panel **Revise su configuración**, haga clic en **Crear** y, después, en **Cerrar**.
  
### <a name="company-strategy-team-site"></a>Sitio de grupo Estrategia de la compañía

Para crear un sitio de grupo aislado de SharePoint Online que tenga el nivel extremadamente confidencial para recursos estratégicos de empresa dirigido a los directores ejecutivos de la organización, haga lo siguiente:
  
1. Si es necesario, inicie sesión en el [portal de Office 365](https://portal.office.com) con las credenciales de la cuenta de administrador global de la suscripción de prueba.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Team site name** (Nombre de sitio de grupo), escriba **Estrategia de empresa**.
    
6. En **Descripción del sitio de grupo**, escriba **Sitio de SharePoint para la estrategia de la compañía (extremadamente confidencial)**.
    
7.  En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.
    
8. En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.
    
9. En la barra de herramientas de la nueva pestaña **Estrategia de la compañía** del explorador, haga clic en el icono de configuración y, después, en **Permisos del sitio**.
    
10. En el panel **Permisos del sitio**, haga clic en **Configuración de permisos avanzada**.
    
11. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
    
12. En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio** (de forma que las tres casillas estén desactivadas) y haga clic en **Aceptar**.
    
13. En la lista, haga clic en **Miembros de estrategia de la compañía**.
    
14. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
15. En el cuadro de diálogo **Compartir**, escriba **Directivos**, selecciónelo y, después, haga clic en **Compartir**.
    
16. En la lista, haga clic en **Propietarios de estrategia de la compañía**.
    
17. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
18. En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.
    
19. Haga clic en el botón Volver del explorador.
    
20. Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Estrategia de la compañía: Inicio** del explorador y, después, cierre el panel **Permisos del sitio**.
    
Estos son los resultados de la configuración de los permisos:
  
- El grupo de SharePoint **Estrategia de la compañía: Miembros** solo contiene el grupo **Directivos** (que contiene únicamente las cuentas de usuario del consejero delegado, el director de seguridad y el director de información) y el grupo **Estrategia de la compañía** (que contiene únicamente la cuenta de usuario del administrador global).
    
- El grupo de SharePoint **Estrategia de la compañía: Propietarios** solo contiene el grupo **Personal de TI** (que contiene únicamente las cuentas de usuario AdminTI1 y AdminTI2).
    
- El grupo de SharePoint **Estrategia de la compañía: Visitantes** no contiene grupos ni cuentas de usuario.
    
- Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Estrategia de empresa-Propietarios**).
    
- Otras cuentas de usuario no pueden acceder al sitio o a sus recursos ni pedir acceso al sitio. Los permisos adicionales para el sitio deben ser asignados por el administrador global o por un miembro del grupo **Estrategia de empresa-Propietarios**.
    
Después, configure la carpeta de documentos del sitio de grupo Estrategia de empresa para la etiqueta Extremadamente confidencial.
  
1. En la pestaña **Estrategia de la compañía: Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y, después, en **Configuración de la biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración: Aplicar etiqueta**, seleccione **Extremadamente confidencial** y, después, haga clic en **Guardar**.
    
Después, configure una directiva de DLP que impida a los usuarios compartir un documento en un sitio de grupo de SharePoint Online con la etiqueta Extremadamente confidencial, que incluye el sitio Estrategia de empresa, fuera de la organización.
  
1. Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) con su administrador global.
    
2. En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.
    
3. En el panel **Inicio > Prevención de pérdida de datos**, haga clic en **Crear una directiva**.
    
4. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
    
5. En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Extremadamente confidencial** en **Nombre** y haga clic en **Siguiente**.
    
6. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.
    
7. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.
    
8. En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Editar**.
    
9. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.
    
10. En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.
    
11. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
    
12. En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Siguiente**.

13. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
    
14. En el panel **Personalizar sugerencias de directiva y notificaciones de correo electrónico**, haga clic en **Personalizar el texto de la sugerencia de directiva**.
    
15. En el cuadro de texto, escriba o pegue una de las siguientes sugerencias, dependiendo de si ha implementado Azure Information Protection para proteger los archivos más confidenciales:
    
  - Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
    
16. Haga clic en **Aceptar**.
    
17. En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.
    
18. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.
    
19. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.
   
    
Después, siga las instrucciones de [Activar Azure RMS con el Centro de administración de Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).
  
Después, siga estos pasos para configurar Azure Information Protection con una nueva directiva con ámbito y la subetiqueta de protección y permisos para el grupo de directivos:
  
1. De ser preciso, inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con su cuenta de administrador global.
    
2. En una pestaña independiente del explorador, vaya a Azure Portal ([https://portal.azure.com](https://portal.azure.com)).
    
3. Si es la primera vez que configura Azure Information Protection, vea [estas instrucciones](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).
    
4. En el panel de lista, haga clic en **Más servicios**, escriba **information** y haga clic en **Azure Information Protection**.

5. Haga clic en **Etiquetas**.
    
6. Haga clic con el botón derecho en la etiqueta **Extremadamente confidencial** y, después, seleccione **Agregar una subetiqueta**.
    
7. Escriba **Miembros del equipo directivo** en **Nombre** y en **Descripción**.
    
8. En **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.
    
9. En la sección **Protección**, haga clic en **Azure (clave de nube)**.
    
10. En la hoja **Protección**, en **Configuración de protección**, haga clic en **+ Agregar permisos**.
    
11. En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **+ Examinar directorio**.
    
12. En el panel **Usuarios y grupos de AAD**, seleccione **Directivos** y, después, haga clic en **Seleccionar**.
    
13. En **Seleccionar permisos del conjunto predefinido o personalizado**, haga clic en **Personalizar** y, después, active las casillas **Ver derechos**, **Editar contenido**, **Guardar**, **Responder** y **Responder a todos**.
    
14. Haga clic en **Aceptar** dos veces.
    
15. En la hoja **Subetiqueta**, haga clic en **Guardar** y, después, seleccione **Aceptar**.

16. En la hoja **Azure Information Protection**, haga clic en **Directivas > + Agregar una directiva**.
    
17. Escriba **EstrategiaEmpresa** en **Nombre de la directiva**, y **Documentos del sitio de grupo Estrategia de la compañía** en **Descripción**.
    
18. Haga clic en **Seleccionar a qué usuarios o grupos se aplica esta directiva > Usuarios o grupos** y seleccione **C-Suite**.
    
19. Haga clic en **Seleccionar > Aceptar**.

20. Haga clic en **Agregar o quitar etiquetas**. En el panel **Directiva: Agregar o quitar etiquetas**, seleccione **Directivos** y, después, haga clic en **Aceptar**.   

21. Haga clic en **Guardar**y después en **Aceptar**.
    
Para proteger un documento con Azure Information Protection y la nueva etiqueta, [necesita instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en un equipo de prueba, instalar Office desde el centro de administración y, después, iniciar sesión desde Microsoft Word con una cuenta del grupo **Directivos** de la suscripción de prueba.
  
Ahora está listo para crear documentos en estos cuatro sitios y probar el acceso a ellos con diferentes cuentas de usuario de la suscripción de evaluación.
  
Esta es la configuración general de los cuatro sitios de grupo de SharePoint Online.
  
![Los cuatro sitios de grupo del entorno de desarrollo y pruebas de SharePoint Online seguro.](media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
## <a name="next-step"></a>Paso siguiente

Cuando esté listo para la implementación en producción de sitios seguros de SharePoint Online, vea [Protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md) para obtener información detallada y vínculos a artículos de implementación paso a paso.
  
## <a name="see-also"></a>Vea también

[Protección de archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




