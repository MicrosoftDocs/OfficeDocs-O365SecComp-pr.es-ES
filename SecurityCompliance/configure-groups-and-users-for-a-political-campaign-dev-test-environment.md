---
title: Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Resumen: Cree suscripciones de evaluación de Office 365 y Enterprise Mobility + Security (EMS) que incluyan usuarios y grupos en un entorno de desarrollo y prueba para una campaña política.'
ms.openlocfilehash: bd491bf34f8625b9ed03ce32c8edcc2f446e2464
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259618"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política

 **Resumen:** Cree suscripciones de evaluación de Office 365 y Enterprise Mobility + Security (EMS) que incluyan usuarios y grupos en un entorno de desarrollo y prueba para una campaña política.
  
Siga las instrucciones de este artículo para crear un entorno de desarrollo y prueba que incluya cuentas de usuario simplificadas y grupos para la solución de [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).
  
## <a name="phase-1-create-your-office-365-devtest-environment"></a>Fase 1: Crear el entorno de desarrollo y prueba de Office 365

En esta fase se obtienen suscripciones de evaluación para Office 365 E5 y Enterprise Mobility + Security (EMS) E5 para una organización ficticia que representa una campaña política.
  
Siga primero las instrucciones de la **fase 2** del [entorno de desarrollo y prueba de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).
  
Después, inscríbase en la suscripción de evaluación de EMS E5 y la agregará a la misma organización de la suscripción de evaluación de Office 365.
  
1. Si es necesario, inicie sesión en el centro de administración con las credenciales de la cuenta de administrador global de la suscripción de evaluación. Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Haga clic en el icono **Administración**.
    
3. En la pestaña **Centro de administración de Office** del explorador, en el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.
    
4. En la página **Servicios de compra**, busque el elemento **Enterprise Mobility + Security E5**. Mantenga el puntero del mouse sobre ese elemento y haga clic en **Iniciar prueba gratuita**.
    
5. En la página **Confirmar pedido**, haga clic en **Probar ahora**.
    
6. En la página **Recibo del pedido**, haga clic en **Continuar**.
    
Después, habilite la licencia de EMS E5 para la cuenta de administrador global.
  
1. En la pestaña **Centro de administración de Microsoft 365** del explorador, en el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
    
2. Haga clic en la cuenta de administrador global y, después, en **Editar** para **Licencias de productos**.
    
3. En el panel **Licencias de productos**, cambie la licencia del producto de **Enterprise Mobility + Security E5** a **Activada**, seleccione **Guardar** y, después, haga clic en **Cerrar** dos veces.
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Fase 2: Crear y configurar los grupos de Azure Active Directory (AD)

En esta fase se crean y configuran los grupos de Azure AD para la campaña.
  
En primer lugar, cree un conjunto de grupos para una campaña política típica en Azure Portal.
  
1. En una pestaña independiente en el explorador, vaya a Azure Portal en [https://portal.azure.com](https://portal.azure.com). Si es necesario, inicie sesión con las credenciales de la cuenta de administrador global de la suscripción de evaluación de Office 365 E5.
    
2. En Azure Portal, haga clic en **Azure Active Directory > Usuarios y grupos > Todos los grupos**.
    
3. Siga estos pasos para cada nombre de grupo de la lista:
    
  - Personal directivo y estratégico
    
  - Personal de TI
    
  - Personal de Análisis
    
  - Personal básico de plantilla
    
  - Personal de Operaciones
    
  - Personal de campo
    
1. En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.
    
2. Escriba el nombre del grupo de la lista en **Nombre**.
    
3. Seleccione **Usuario dinámico** en **Pertenencia**.
    
4. Haga clic en **Sí** en **¿Quiere habilitar las características de Office?**
    
5. Haga clic en **Agregar una consulta dinámica**.
    
6. En **Add users where** (Agregar usuarios donde), seleccione **departamento**.
    
7. En el siguiente campo, seleccione **Es igual a**.
    
8. En el siguiente campo, escriba el nombre del grupo de la lista.
    
9. Haga clic en **Agregar consulta** luego en **Crear**.
    
10. Haga clic en **Users and groups - All groups** (Usuarios y grupos - Todos los grupos).
    
Después, configure los grupos para que a los miembros se les asignen automáticamente licencias de Office 365 E5 y EMS E5.
  
1. En Azure Portal, haga clic en **Azure Active Directory > Licencias > Todos los productos**.
    
2. En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y haga clic en **+ Asignar**.
    
3. En la hoja **Asignar licencia**, haga clic en **Usuarios y grupos**.
    
4. En la lista de grupos, seleccione los siguientes:
    
  - Personal de Análisis
    
  - Personal de campo
    
  - Personal de TI
    
  - Personal de Operaciones
    
  - Personal básico de plantilla
    
  - Personal directivo y estratégico
    
5. Haga clic en **Seleccionar** y luego en **Siguiente**.
    
6. Cierre la pestaña Azure Portal del explorador.
    
## <a name="phase-3-add-your-user-accounts"></a>Fase 3: Agregar las cuentas de usuario

En esta fase se agregan las cuentas de usuario de ejemplo para la campaña política.
  
Primero, [Conéctese al módulo de PowerShell de Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Después, rellene el nombre de la organización, su ubicación y una contraseña común y, luego, ejecute estos comandos en el entorno de script integrado (ISE) o el símbolo del sistema de PowerShell:
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1") 
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }

```

> [!IMPORTANT]
> Se usa una contraseña común para automatizar y facilitar la configuración de un entorno de desarrollo y prueba. Nos se recomienda hacerlo con suscripciones de producción. Cuando inicie sesión con cada una de estas nuevas cuentas de usuario, se le pedirá que cambie la contraseña. 
  
Siga estos pasos para comprobar que las licencias basadas en grupos y la pertenencia dinámica a grupos funcionan correctamente.
  
1. En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Administrador**.
    
2. En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Usuarios**.
    
3. En la lista de usuarios, haga clic en **Candidato**.
    
4. En el panel que muestra las propiedades de la cuenta de usuario **Candidato**, compruebe que:
    
  - Es un miembro del grupo **Personal directivo y estratégico** (en **Pertenencia a grupos**).
    
  - Se le han asignado las licencias de **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** (en **Licencias de productos**).
    
5. Cierre el panel de la cuenta de usuario **Candidato**.
    
## <a name="record-values-for-future-reference"></a>Registrar valores para referencia futura

Registre estos valores para trabajar con las suscripciones de prueba de Office 365 y EMS en este entorno de desarrollo y pruebas:
  
- Nombre de la organización de la suscripción de prueba: ![](./media/Common-Images/TableLine.png) 
    
    Por ejemplo, en el nombre de dominio de la suscripción de prueba de contoso.onmicrosoft.com, el nombre de la organización es “contoso”.
    
- Nombre del administrador global de Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com
    
    Registre la contraseña de esta cuenta y la contraseña inicial común de las demás cuentas de usuario en una ubicación segura.
    
## <a name="next-step"></a>Paso siguiente

Cree los cuatro tipos distintos de sitios de grupo de SharePoint Online en este entorno de desarrollo y pruebas con [Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política](create-team-sites-in-a-political-campaign-dev-test-environment.md).
  
## <a name="see-also"></a>Vea también

[Guía de seguridad de Microsoft para campañas políticas, ONG y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política](create-team-sites-in-a-political-campaign-dev-test-environment.md)
  
[Guías del entorno de pruebas de adopción de la nube (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




