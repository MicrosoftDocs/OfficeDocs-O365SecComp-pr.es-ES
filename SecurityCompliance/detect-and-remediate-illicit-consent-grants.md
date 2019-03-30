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
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Aprenda a reconocer y corregir el consentimiento ilícito concede un ataque en Office 365.
ms.openlocfilehash: 32fa8fedd0cac0ba1a6193b7b107492efb136838
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999943"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>Detectar y solucionar la concesión de consentimiento ilegal en Office 365

**Resumen**  Aprenda a reconocer y corregir el consentimiento ilícito concede un ataque en Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>¿Cuál es el ataque de concesión de consentimiento ilícito en Office 365?
En un ataque de consentimiento ilícito, el atacante crea una aplicación registrada de Azure que solicita acceso a datos como la información de contacto, el correo electrónico o los documentos. A continuación, el atacante engaña a un usuario final para que conceda a esa aplicación el consentimiento para obtener acceso a sus datos mediante un ataque de suplantación de identidad o insertando código ilícito en un sitio web de confianza. Una vez que se ha concedido el consentimiento de la aplicación ilícita, tiene acceso de nivel de cuenta a los datos sin necesidad de una cuenta de la organización. Los pasos de corrección normales, como restablecer las contraseñas de las cuentas infringidas o requerir la autenticación multiFactor (MFA) en las cuentas, no son eficaces contra este tipo de ataque, ya que son aplicaciones de terceros y son externas a la organización. Estos ataques aprovechan un modelo de interacción que presupone que la entidad que llama a la información es la automatización y no es una persona.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>¿Qué aspecto tiene un ataque ilegal de concesión de consentimiento en Office 365?
Debe buscar en el **registro de auditoría** de Office 365 para encontrar signos, también denominados "indicadores de peligro" (IOC) de este ataque. Para las organizaciones con muchas aplicaciones registradas en Azure y una base de usuarios grande, el procedimiento recomendado es revisar las concesiones de consentimiento de las organizaciones cada semana.
### <a name="steps-for-finding-signs-of-this-attack"></a>Pasos para buscar signos de este ataque
1. Abra el **centro de seguridad y cumplimiento** en el inquilino de Office 365.
2. Vaya al nodo de **investigación de & de búsqueda** y seleccione búsqueda de registros de **Auditoría** .
3. Cree una búsqueda (todas las actividades y todos los usuarios), filtre los resultados para el consentimiento de la aplicación y agregue OAuth2PermissionGrant.
4. Examine las propiedades extendidas y compruebe si IsAdminContent está establecido en true.


Si este valor es true, indica que un usuario con acceso de administrador global puede haber concedido acceso general a los datos. Si esto es inesperado, siga los pasos para [confirmar un ataque](detect-and-remediate-illicit-consent-grants.md#confirmattack).

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>Cómo confirmar un ataque
Si tiene una o más instancias de la IOCs enumeradas anteriormente, debe seguir investigando para confirmar que se ha producido el ataque. Puede usar cualquiera de estos tres métodos para confirmar el ataque.
- Las aplicaciones de inventario y sus permisos mediante el portal de Azure Active Directory. Este método es exhaustivo, pero solo puede realizar comprobaciones en un usuario cada vez que puede llevar mucho tiempo si tiene que comprobar muchos usuarios.
- Aplicaciones de inventario y sus permisos mediante PowerShell. Este es el método más rápido y completo, con la menor cantidad de sobrecarga.
- Pida a los usuarios que comprueben individualmente sus aplicaciones y permisos, y devuelvan los resultados a los administradores para corregirlos.

## <a name="inventory-apps-with-access-in-your-organization"></a>Aplicaciones de inventario con acceso en la organización
Puede hacerlo para los usuarios con el portal de Azure Active Directory o con PowerShell, o bien hacer que los usuarios enumeren individualmente el acceso a la aplicación.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Pasos para usar el portal de Azure Active Directory
Puede buscar las aplicaciones a las que cualquier usuario individual ha concedido permisos mediante el uso del [portal de Azure Active Directory](https://portal.azure.com/). 
1. Inicie sesión en Azure portal con derechos administrativos.
2. Seleccione la hoja Azure Active Directory.
3. Seleccione **usuarios**.
4. Seleccione el usuario que desea revisar.
5. Seleccione **aplicaciones**.

Esto le mostrará las aplicaciones que se asignan al usuario y qué permisos tienen en el Applcations.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Pasos para hacer que los usuarios enumeren el acceso a la aplicación
Pida a los usuarios que https://myapps.microsoft.com vayan a y revisen su propio acceso a la aplicación. Deben poder ver todas las aplicaciones con acceso, ver detalles sobre ellas (incluido el ámbito de acceso) y poder revocar los privilegios de aplicaciones sospechosas o ilícitas.

### <a name="steps-for-doing-this-with-powershell"></a>Pasos para hacerlo con PowerShell
La forma más sencilla de comprobar el ataque de consentimiento ilícito es ejecutar [Get-AzureADPSPermissions. PS1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que volcarán todas las concesiones de consentimiento de OAuth y las aplicaciones de OAuth para todos los usuarios de su arrendamiento en un archivo. csv. 

#### <a name="pre-requisites"></a>Requisitos previos
- La biblioteca de Azure AD PowerShell instalada.
- Derechos de administrador global en el espacio empresarial en el que se ejecutará el script.
- Administrador local en el equipo desde el que se ejecutarán los scripts.

> [!IMPORTANT]
> Se recomienda encarecidamente que requiera la autenticación multifactor en su cuenta administrativa.  Este script admite la autenticación MFA.

1. Inicie sesión en el equipo en el que va a ejecutar el script con derechos de administrador local.
2. Descargue o copie el script [Get-AzureADPSPermissions. PS1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de github a una carpeta desde la que se ejecutará el scruipt.  Se trata de la misma carpeta en la que se escribirá el archivo "Permissions. csv" de salida.
3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.
4. Conéctese a su directorio mediante el cmdlet [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) .
5. Ejecute esta línea de comandos de PowerShell de la siguiente manera:`Get-AzureADPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

La secuencia de comandos genera un archivo denominado perMissions. csv. Siga estos pasos para buscar concesiones de permisos de aplicaciones ilícitas: 
1. En la columna ConsentType (Column G), busque el valor "AllPrinciples". El permiso AllPrincipals permite a la aplicación cliente obtener acceso al contenido de todo el inquilino. Las aplicaciones nativas de Office 365 necesitan este permiso para funcionar correctamente. Todas las aplicaciones que no sean de Microsoft con este permiso deben revisarse con cuidado.
2.  En la columna permiso (columna F), revise los permisos que tiene cada aplicación delegada en el contenido. Busque el permiso "leer" y "escribir" o "*. All "permiso y revise estos detenidamente porque es posible que no sean apropiados.
3.  Revise los usuarios específicos que tienen permisos concedidos. Si los usuarios de alto impacto o alto impacto tienen concedidos inadecuados, debe investigar más.
4.  En la columna ClientDisplayName (columna C), busque las aplicaciones que parecen sospechosas. Las aplicaciones con nombres mal escritos, nombres de súper Bland o nombres de sonido de hacker deben revisarse detenidamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinar el ámbito del ataque
Una vez que haya terminado de inventariar el acceso a la aplicación, revise el **registro de auditoría** de Office 365 para determinar el ámbito completo de la infracción.  Busque los usuarios afectados, los intervalos de tiempo en los que la aplicación ilícita tuvo acceso a su organización y los permisos que tenía la aplicación. Puede buscar en el **registro de auditoría** del [centro de seguridad y cumplimiento de Microsoft 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c). 

> [!IMPORTANT]
> [](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918) La auditoría de buzones y la [Auditoría de actividades para administradores y usuarios](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) deben estar habilitados antes del ataque para que pueda obtener esta información.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>Cómo detener y corregir un ataque de concesión de consentimiento ilícito
Una vez que haya identificado una aplicación con permisos de ilícitas, tiene varias formas de quitar ese acceso.
- Puede revocar el permiso de la aplicación en el portal de Azure Active Directory de la siguiente manera:
    - Navegue al usuario afectado en la hoja de **usuario de Azure Active** Directory.
    - Seleccione **aplicaciones**.
    - Seleccione la aplicación ilícita.
    - Haga clic en **quitar** en el detalle.
- Puede revocar la concesión de consentimiento de OAuth con PowerShell siguiendo los pasos descritos en [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0).
- Puede revocar la asignación de roles de aplicación de servicio con PowerShell siguiendo los pasos descritos en [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0).
- También puede deshabilitar el inicio de sesión para la cuenta afectada por completo, que a su vez deshabilitará el acceso a la aplicación a los datos de esa cuenta. Esto no es ideal para la productividad del usuario final, por supuesto, pero si está trabajando para limitar rápidamente el impacto, puede ser una corrección viable a corto plazo.
- Puede desactivar las aplicaciones integradas para su arrendamiento. Se trata de un paso drástico que deshabilita la capacidad de los usuarios finales para conceder consentimiento en un espacio empresarial. Esto evita que los usuarios concedan de forma inadvertida acceso a una aplicación malintencionada. Esto no es muy recomendable ya que perjudica seriamente la capacidad de los usuarios de ser productivo con aplicaciones de terceros.  Para ello, siga los pasos que se indican en [activar o desactivar las aplicaciones integradas](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteger Office 365 como un Cybersecurity Pro
Su suscripción a Office 365 incluye un eficaz conjunto de capacidades de seguridad que puede usar para proteger sus datos y sus usuarios.  Use el [plan de desarrollo de seguridad de Office 365: principales prioridades de los primeros 30 días, 90 días y más allá](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) de implementar los procedimientos recomendados de Microsoft para proteger su inquilino de Office 365.
- Tareas que se deben realizar en los primeros 30 días.  Estos tienen un efecto inmediato y tienen un impacto bajo para los usuarios.
- Tareas que se deben realizar en 90 días. Estos requieren un poco más de tiempo para planear e implementar, pero mejoran considerablemente su postura de seguridad.
- Más allá de 90 días. Estas mejoras se basan en el trabajo de los primeros 90 días.

## <a name="see-also"></a>Vea también:
- Una [aplicación inesperada en la lista de mis aplicaciones](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) dirige a los administradores a través de diversas acciones que quizás deseen realizar después de la realización de que hay aplicaciones inesperadas con acceso a los datos.
- [Integración de aplicaciones con Azure Active Directory]  (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) es una introducción de alto nivel de consentimiento y permisos.  Preste especial atención a la [información general de la sección del marco de consentimiento](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework) .
- [Problemas en el desarrollo de la aplicación](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) proporciona vínculos a varios artículos relacionados con el consentimiento.
- La [aplicación y los objetos de entidad de servicio de Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) proporcionan una introducción a los objetos de la entidad de servicio y la aplicación que son fundamentales para el modelo de la aplicación.
- [Manage Access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) es una introducción a las funcionalidades que los administradores tienen para administrar el acceso de los usuarios a las aplicaciones.
