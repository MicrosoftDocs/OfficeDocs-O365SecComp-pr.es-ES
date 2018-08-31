---
title: Detectar y solucionar la concesión de consentimiento ilegal en Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
ms.custom: ''
ms.assetid: ''
search.appverid:
- MET150
description: Obtenga información sobre cómo reconocer y corregir el ataque de concede a consentimiento ilegal en Office 365.
ms.openlocfilehash: 412b601af30ce87332225d271ec1a9e622012405
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536852"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>Detectar y solucionar la concesión de consentimiento ilegal en Office 365

**Resumen**  Obtenga información sobre cómo reconocer y corregir el ataque de concede a consentimiento ilegal en Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>¿Qué es el ataque de concesión de consentimiento ilegal en Office 365?
En un consentimiento ilegal conceder ataque, que el atacante crea una aplicación registrado de Azure que solicita acceso a datos como información de contacto, correo electrónico, o documentos. El atacante trucos, a continuación, un usuario final en la concesión de dicho consentimiento de aplicación para tener acceso a sus datos a través de un ataque de suplantación de identidad, o insertando código ilegal en un sitio Web de confianza. Después de que se ha concedido a la aplicación ilegal consentimiento, tiene el nivel de cuenta de acceso a datos sin la necesidad de una cuenta profesional. Pasos de corrección normal, como restablecer las contraseñas de cuentas ha puesto en peligro o que requieren la autenticación multifactor (MFA) en las cuentas, no son eficaces contra este tipo de ataque, ya que estos son aplicaciones de terceros y que son externos a la organización. Estos ataques sacar provecho de un modelo de interacción que se da por supuesto la entidad que llama a la información es automatización y no un humanos.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>¿Qué un consentimiento ilegal grant ataque aspecto en Office 365?
Debe buscar el Office 365 de **registro de auditoría** para buscar signos, que también se denomina indicadores de compromiso (IOC) de este ataque. Para las organizaciones con muchas aplicaciones registradas en Azure y una base de usuarios de gran tamaño, el procedimiento recomendado es revisar su consentimiento de las organizaciones concede a semanalmente.
### <a name="steps-for-finding-signs-of-this-attack"></a>Pasos de la búsqueda de signos de este ataque
1. Abra el **Centro de cumplimiento y seguridad** en el inquilino de Office 365.
2. Desplácese hasta el nodo **búsqueda & investigación** y seleccione la búsqueda de **registro de auditoría** .
3. Crear una búsqueda (todas las actividades y todos los usuarios) y filtrar los resultados para su consentimiento a la aplicación y agregar OAuth2PermissionGrant.
4. Examine la comprobación y propiedades extendidas para ver si IsAdminContent se establece en True.


Si este valor es true, indica que alguien con acceso de administrador Global es posible que haya concedido acceso amplio a los datos. Si esto es inesperado, lleve a cabo pasos para [confirmar un ataque](detect-and-remediate-illicit-consent-grants.md#confirmattack).

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>Cómo confirmar un ataque
Si dispone de uno o más instancias de la IOCs enumeran anteriormente, debe hacer nuevas investigaciones para positiva confirmar que se ha producido el ataque. Puede usar cualquiera de estos tres métodos para confirmar el ataque.
- Realizar un inventario de las aplicaciones y sus permisos de uso del portal de Azure Active Directory. Este método es exhaustiva, pero sólo se puede comprobar un usuario a la vez que puede llevar mucho tiempo si tiene muchos usuarios para comprobar.
- Realizar un inventario de las aplicaciones y sus permisos de uso de PowerShell. Este es el método más rápido y más completo, con la menor cantidad de sobrecarga.
- Hacer que los usuarios individualmente Compruebe sus aplicaciones y los permisos y notificar los resultados de vuelta a los administradores para la corrección.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventario de aplicaciones con acceso de la organización
Puede hacer esto para los usuarios con el Portal de Azure Active Directory o PowerShell o hacer que los usuarios enumerar su acceso a la aplicación de forma individual.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Pasos para usar el Portal de Azure Active Directory
Puede buscar las aplicaciones para que cualquier usuario individual le haya asignado permisos mediante el [Portal de Azure Active Directory](https://portal.azure.com/). 
1. Inicie sesión el Portal de Azure con derechos administrativos.
2. Seleccione el servidor blade de Azure Active Directory.
3. Seleccione **los usuarios**.
4. Seleccione el usuario que desee revisar.
5. Seleccione **las aplicaciones**.

Esto le mostrará las aplicaciones que están asignadas al usuario y qué permisos tienen las aplicaciones.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Pasos para hacer que los usuarios enumerar su acceso a la aplicación
Hacer que los usuarios vaya a https://myapps.microsoft.com y revise su propios acceso de la aplicación no existe. Debe ser capaz de ver todas las aplicaciones con acceso, ver detalles acerca de ellos (incluido el ámbito de acceso) y poder revocar privilegios para aplicaciones sospechosos o ilegal.

### <a name="steps-for-doing-this-with-powershell"></a>Pasos para realizar esta acción con PowerShell
Es la forma más sencilla para comprobar el ataque ilegal Grant da su consentimiento ejecutar [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que se va a volcar todos los permisos de aplicación para todos los usuarios y concede a consentimiento de OAuth en su arrendamiento en un archivo .csv. 

#### <a name="pre-requisites"></a>Requisitos previos
- La biblioteca de Windows Azure AD PowerShell instalada.
- Derechos de administrador global en el inquilino que se ejecutará la secuencia de comandos.
- Administrador local en el equipo desde el que se ejecutarán las secuencias de comandos.

> [!IMPORTANT]
> Se recomienda encarecidamente que requieren autenticación multifactor en su cuenta administrativa.  Esta secuencia de comandos admite la autenticación de MFA.

1. Inicie sesión en el equipo que se ejecutará la secuencia de comandos con derechos de administrador local.
2. Descargue o copie el script [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de depósito en una carpeta desde la que se ejecutará el scruipt.  Se trata de la misma carpeta a la que se escribirá el archivo de salida "permissions.csv".
3. Abra una sesión de PowerShell como administrador y abra la carpeta que se ha guardado la secuencia de comandos.
4. Conectar con el directorio mediante el cmdlet [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) .
5. Ejecute esta línea de comandos de PowerShell como sigue:`.Get-AzureASPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

La secuencia de comandos genera un archivo denominado Permissions.csv. Siga estos pasos para buscar concesiones de permisos de aplicación ilegal: 
1. En la columna ConsentType (columna G) de búsqueda para el valor "AllPrinciples". El permiso AllPrincipals permite que la aplicación cliente tener acceso al contenido de todos los usuarios en el arrendamiento. Las aplicaciones de Office 365 nativas necesitan este permiso para que funcione correctamente. Todas las aplicaciones que no son de Microsoft con este permiso deben ser revisada cuidadosamente.
2.  En la revisión de columna (columna F) permisos los permisos que cada uno de ellos delegados aplicación tiene al contenido. Busque el permiso de "Lectura" y "Escribir" o "*. Todos los"permisos y revisar que estos cuidadosamente porque no pueden ser adecuadas.
3.  Revise los usuarios específicos que tienen autorizaciones concedidas. Si el alto perfil o usuarios de alto impacto tienen inapropiados autorizaciones concedidas, debe investigar más.
4.  En la columna ClientDisplayName (columna C) busque aplicaciones que parecen sospechosas. Aplicaciones con nombres mal escritos, super anodino nombres o nombres de sonido intruso deben ser revisadas cuidadosamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinar el ámbito del ataque
Cuando haya terminado de realizar un inventario de acceso de la aplicación, revise la Office 365 de **registro de auditoría** para determinar el alcance de la infracción.  Búsqueda en los usuarios afectados, los marcos de tiempo que la aplicación ilegal tenía acceso a la organización y los permisos que tenía la aplicación. Puede buscar en el **registro de auditoría** en el [Centro de cumplimiento y seguridad de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c). 

> [!IMPORTANT]
> [Auditoría de buzón de correo](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918) y la [actividad de auditoría para administradores y usuarios](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) deben estar habilitado antes del ataque para obtener esta información.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>Procedimiento para detener y corregir un ataque de concesión de consentimiento ilegal
Una vez que haya identificado una aplicación con permisos ilegal, tiene varios métodos para quitar dicho acceso.
- Puede revocar el permiso de usuario de la aplicación en el Portal de Azure Active Directory por:
    - Navegue hasta el usuario afectado en el servidor blade de **Usuario de Active Directory de Azure** .
    - Seleccione **las aplicaciones**.
    - Seleccione la aplicación ilegal.
    - Haga clic en **Quitar** en el detalle hacia abajo.
- Puede revocar la concesión de consentimiento de OAuth con PowerShell siguiendo los pasos descritos en [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0).
- Puede revocar la asignación de rol de la aplicación de servicio con PowerShell siguiendo los pasos descritos en [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0).
- También puede deshabilitar inicio de sesión en por completo la cuenta afectada, que a su vez se va a deshabilitar el acceso de aplicación a los datos de esa cuenta. Por supuesto, esto no es ideal para la productividad del usuario final, pero si está trabajando para limitar el impacto rápidamente, puede ser una corrección a corto plazo viable.
- Puede desactivar aplicaciones integradas para el inquilino. Este es un paso radical que deshabilita la capacidad de los usuarios finales de otorgar la autorización en todo el inquilino. Esto impide que los usuarios sin darse cuenta conceder acceso a una aplicación malintencionada. Esto no se recomienda encarecidamente tal y como ve muy dificulta la capacidad del usuario para ser productivos con aplicaciones de otros fabricantes.  Para ello, siga los pasos de [Aplicaciones integrado de activar o desactivar](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Seguro de Office 365 como una ciberseguridad pro
Su suscripción de Office 365 incluye un conjunto eficaz de características de seguridad que puede utilizar para proteger los datos y los usuarios.  Usar el [Guía de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y más allá de](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) para implementar Microsoft procedimientos recomendado para proteger el inquilino de Office 365.
- Tareas de llevar a cabo en los primeros 30 días.  Estos tienen un efecto inmediato y están bajo impacto para los usuarios.
- Tareas de llevar a cabo en 90 días. Estos tardan un poco más tiempo para planear e implementar pero mejorar considerablemente el nivel de seguridad.
- Más allá de 90 días. Estas mejoras se basan en su primer trabajo de 90 días.

## <a name="see-also"></a>Vea también:
- [Inesperado de la aplicación en mi lista de aplicaciones de](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) guía a los administradores a través de varias acciones que se desean hacer después de darse cuenta hay inesperadas aplicaciones con acceso a datos.
- [Integración de aplicaciones con Azure Active Directory]  (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) es una introducción de alto nivel de consentimiento y permisos.  Preste especial atención a la sección de [información general sobre el marco de consentimiento](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework) .
- [Problemas de desarrollo de mi aplicación](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) proporciona vínculos a los diversos consentimiento de artículos relacionados.
- [Las aplicaciones y objetos de entidad de seguridad de servicio en Azure Active Directory (AD Azure)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) ofrece una visión general de los objetos de entidad de seguridad de aplicación y servicio que son básicas en el modelo de aplicación.
- [Administrar el acceso a las aplicaciones](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) es una visión general de las capacidades que tienen los administradores para administrar el acceso de usuario a las aplicaciones.