---
title: Detectar y corregir las reglas de Outlook y los ataques de inserción de formularios personalizados en Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Obtenga información sobre cómo reconocer y corregir los ataques de las reglas de Outlook y de las inyecciones de formularios personalizados en Office 365
ms.openlocfilehash: 59d45e50e15e3709c8a041ead59b8cc6e2a38306
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30656066"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Office 365

**Resumen** Obtenga información sobre cómo reconocer y corregir los ataques de las reglas de Outlook y de las inyecciones de formularios personalizados en Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>¿Qué es el ataque de inserción de formularios personalizados y reglas de Outlook?
Una vez que un atacante ha incumplido una cuenta en su arrendamiento y se incluye en, hay que probar y establecer una forma de seguir adelante o una forma de volver a ella una vez que se han descubierto y eliminado. Esto se denomina establecer un mecanismo de persistencia. Dos formas de hacerlo es aprovechando las reglas de Outlook o inyectando formularios personalizados en Outlook.
En ambos casos, la regla o el formulario se sincronizan desde el servicio de nube hacia el cliente de escritorio, por lo que un formato completo y la reinstalación del software cliente no eliminan el mecanismo de inserción. Esto se debe a que, al volver a conectar el software de cliente de Outlook al buzón de la nube, se volverán a descargar las reglas y los formularios de la nube. Una vez que las reglas y los formularios están en su ubicación, el atacante los usa para ejecutar código remoto o personalizado, normalmente para instalar malware en el equipo local. A continuación, el malware vuelve a robar credenciales o realiza otras actividades ilícitas. La buena noticia es que si mantiene los clientes revisados a la versión más reciente, no es vulnerable a la amenaza como los valores predeterminados del cliente de Outlook actual bloquean ambos mecanismos. 

Normalmente, los ataques siguen estos patrones:

El ataque de reglas
1. El atacante roba el nombre de usuario y la contraseña de uno de los usuarios.
2. A continuación, el atacante inicia sesión en el buzón de correo de Exchange de los usuarios. El buzón puede estar en Exchange online o en Exchange local.
3. A continuación, el atacante crea una regla de reenvío en el buzón que se desencadena cuando el buzón recibe un correo electrónico que coincide con los criterios de la regla. Los criterios de regla y el contenido del correo electrónico del desencadenador se realizan de una a otra.
4. El atacante envía el mensaje de correo electrónico del desencadenador al usuario que está usando su buzón normalmente.
5. Cuando se recibe el correo electrónico, se activa la regla. La acción de la regla suele ser iniciar una aplicación en un servidor remoto (WebDAV).
6. Normalmente, la aplicación instala malware, como [PowerShell Empire](https://www.powershellempire.com/), de forma local en el equipo del usuario.
7. El malware permite al atacante volver a robar el nombre de usuario y la contraseña del usuario u otras credenciales del equipo local y realizar otras actividades malintencionadas.

La vulnerabilidad de los formularios
1. El atacante roba el nombre de usuario y la contraseña de uno de los usuarios.
2. A continuación, el atacante inicia sesión en el buzón de correo de Exchange de los usuarios. El buzón puede estar en Exchange online o en Exchange local.
3. A continuación, el atacante crea una plantilla de formulario de correo personalizada y la inserta en el buzón del usuario.  El formulario personalizado se desencadena cuando el buzón recibe un correo electrónico que requiere que el buzón de correo cargue el formulario personalizado. El formulario personalizado y el formato de correo electrónico se realizan de forma personalizada entre sí.
4. El atacante envía el mensaje de correo electrónico del desencadenador al usuario, que usa el buzón normalmente.
5. Cuando se recibe el mensaje de correo electrónico, se carga el formulario. El formulario inicia una aplicación en un servidor remoto (WebDAV).
6. Normalmente, la aplicación instala malware, como [PowerShell Empire](https://www.powershellempire.com/), de forma local en el equipo del usuario.
7. El malware permite al atacante volver a robar el nombre de usuario y la contraseña del usuario u otras credenciales del equipo local y realizar otras actividades malintencionadas.


## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>¿Qué puede parecer un ataque de inserción de reglas y formularios personalizados como Office 365?

Es improbable que los usuarios detecten estos mecanismos de persistencia y, en algunos casos, incluso pueden ser invisibles para ellos.  En este artículo se explica cómo buscar cualquiera de los siete signos (indicadores de peligro) que se enumeran a continuación. Si encuentra alguno de estos, debe seguir los pasos de corrección.

- Indicadores del compromiso de reglas
    - La acción de regla es iniciar una aplicación.
    - La regla hace referencia a un EXE, ZIP o dirección URL.
    - En el equipo local, busque inicios de proceso nuevos que se originen desde el PID de Outlook.
- Indicadores de la puesta en peligro de los formularios personalizados 
    - El formulario personalizado está guardado como su propia clase de mensaje.
    - La clase de mensaje contiene código ejecutable.
    - Suele almacenarse en la biblioteca de formularios personales o en las carpetas de la bandeja de entrada.
    - El formulario se denomina IPM. Note. [nombre personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Pasos para buscar signos de este ataque y confirmarlo
Puede usar cualquiera de estos dos métodos para confirmar el ataque.
- Examine manualmente las reglas y los formularios de cada buzón de correo mediante el cliente de Outlook.  Este método es exhaustivo, pero solo puede consultar a un usuario de buzón de correo a la vez que puede llevar mucho tiempo si tiene que comprobar muchos usuarios.  También puede provocar una infracción del equipo desde el que está ejecutando la comprobación.
- Use el script de PowerShell [Get-AllTenantRulesAndForms. PS1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) para volcar automáticamente todas las reglas de reenvío de correo y los formularios personalizados para todos los usuarios del arrendamiento. Este es el método más rápido y seguro con la menor cantidad de sobrecarga.


### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmar el ataque de reglas mediante el cliente de Outlook
1. Abra el cliente de Outlook de los usuarios como usuario.  Es posible que el usuario necesite su ayuda para examinar las reglas de su buzón.
2. Consulte [administrar mensajes de correo electrónico](https://support.office.com/article/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59#ID0EAABAAA=2010) mediante el artículo de reglas para obtener los procedimientos sobre cómo abrir la interfaz de reglas en las versiones 2007, 2010 o 2013 de Outlook.
3. Busque las reglas que el usuario no ha creado o las reglas o reglas inesperadas con nombres sospechosos.
4. Busque en la descripción de la regla las acciones de regla que se inician y se aplicación o que hacen referencia a. EXE,. Archivo ZIP o para iniciar una dirección URL.
5. Busque los nuevos procesos que empiecen a usar el ID de proceso de Outlook.  Consulte [Buscar el identificador de proceso](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Pasos para confirmar el ataque de formularios con el cliente de Outlook
1. Abra el cliente de Outlook de usuario como usuario.
2. Siga los pasos descritos en, [Mostrar la ficha programador](https://support.office.com/article/show-the-developer-tab-e1192344-5e56-4d45-931b-e5fd9bea2d45) para la versión de usuario de Outlook.
3. Abra la pestaña programador ahora visible en Outlook y haga clic en **diseñar un formulario**.
4. Seleccione la **bandeja de entrada** en la lista **Buscar en** . Busque otros formularios personalizados.  Los formularios personalizados son muy raros que si tiene algún formulario personalizado, merece la pena tener un aspecto más profundo.
5. Investigue los formularios personalizados, en especial los que están marcados como ocultos.
6. Abra cualquier formulario personalizado y, en el grupo de **formularios** , haga clic en **Ver código** para ver lo que se ejecuta cuando se carga el formulario.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Pasos para confirmar el ataque de reglas y formularios con PowerShell
La forma más sencilla de comprobar un ataque de reglas o formularios personalizados es ejecutar el script de PowerShell [Get-AllTenantRulesAndForms. PS1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) .  Este script se conecta a todos los buzones del espacio empresarial y vuelca todas las reglas y formularios en dos archivos. csv.

#### <a name="pre-requisites"></a>Requisitos previos
Deberá contar con un derecho de administrador global para ejecutar el script, ya que el script se conecta a todos los buzones del espacio empresarial para leer las reglas y los formularios.

1. Inicie sesión en el equipo en el que va a ejecutar el script con derechos de administrador local.
2. Descargue o copie el script Get-AllTenantRulesAndForms. PS1 de GitHub a una carpeta desde la que lo ejecutará.  El script creará dos archivos de marcas de fecha en esta carpeta, MailboxFormsExport-yyyy-mm-dd. csv y MailboxRulesExport-yyyy-mm-dd. csv.
3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.
4. Ejecute esta línea de comandos de PowerShell `.\Get-AllTenantRulesAndForms.ps1`de la siguiente manera: .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretación del resultado

MailboxRulesExport-*yyyy-MM-DD*. csv: Examine las reglas (una por fila) para las condiciones de acción que incluyen aplicaciones o ejecutables.
- ActionType (columna A): Si ve el valor "ID_ACTION_CUSTOM", es probable que la regla sea malintencionada.
- IsPotentiallyMalicious (columna D): Si este valor es "TRUE", es probable que la regla sea malintencionada.
- ActionCommand (columna G): si se muestra una aplicación o cualquier archivo con una extensión. exe,. zip o una entrada que hace referencia a una dirección URL, que no se supone que esté ahí, es probable que la regla sea malintencionada.

MailboxFormsExport-*yyyy-MM-DD*. csv: en general, el uso de formularios personalizados es muy raro.  Si encuentra algún en este libro, abre el buzón de correo del usuario y examina el propio formulario.  Si su organización no la puso intencionadamente, es probable que sea malintencionado.



## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Cómo detener y corregir el ataque a las reglas y formularios de Outlook
Si encuentra algún indicio de alguno de estos ataques, la corrección es sencilla, simplemente elimine la regla o el formulario del buzón. Puede hacerlo con el cliente de Outlook o con PowerShell remoto para quitar reglas.

### <a name="using-outlook"></a>Uso de Outlook
1. Identifique todos los dispositivos que el usuario ha usado con Outlook.  Todos necesitan limpiarse del posible malware.  No permita que el usuario inicie sesión y use el correo electrónico hasta que se limpien todos los dispositivos.
2. Siga los pasos descritos en [eliminar una regla](https://support.office.com/article/Delete-a-rule-2F0E7139-F696-4422-8498-44846DB9067F) para cada dispositivo.
3. Si no está seguro de la presencia de otro malware, puede formatear y volver a instalar todo el software en el dispositivo.  Para dispositivos móviles, puede seguir los pasos de los fabricantes para restablecer el dispositivo en la imagen de fábrica.
4. Instale las versiones más actualizadas de Outlook.  Recuerde que la versión actual de Outlook bloquea ambos tipos de este ataque de forma predeterminada.
5. Una vez que se hayan quitado todas las copias sin conexión del buzón de correo, restablezca la contraseña del usuario (use una alta calidad) y siga los pasos de [configurar la autenticación multifactor para los usuarios de Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) si la MFA no se ha habilitado todavía. Esto garantiza que las credenciales del usuario no se exponen a través de otros medios (como el phishing o la reutilización de contraseña).

### <a name="using-powershell"></a>Mediante PowerShell
Hay dos cmdlets de PowerShell remoto que puede usar para quitar o deshabilitar reglas peligrosas. Solo tiene que seguir los pasos.
 
Pasos para buzones de correo que están en un servidor de Exchange

1. Conéctese al servidor de Exchange mediante PowerShell remoto. Siga los pasos descritos en [Connect to Exchange Servers Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps).
2. Si desea quitar por completo una sola regla, varias reglas o todas las reglas de un buzón de correo, use el [cmdlet Remove-Inbox Rule ](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)-use this para quitar por completo una, varias o todas las reglas del buzón.
3. Si desea conservar la regla y su contenido para seguir investigando, use el [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

Pasos para buzones de correo en Exchange Online
1. Siga los pasos descritos en [Connect to Exchange Online Using PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
2.  Si desea quitar por completo una sola regla, varias reglas o todas las reglas de un buzón de correo, use el [cmdlet Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps).
3.  Si desea conservar la regla y su contenido para seguir investigando, use el [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

## <a name="how-to-minimize-future-attacks"></a>Cómo minimizar los ataques futuros

### <a name="first-protect-your-accounts"></a>Primero: Proteja sus cuentas

Los atacantes solo usan las reglas y los formularios para aprovechar una vez que han robado o infringido una de sus cuentas de usuario. Por lo tanto, el primer paso para evitar el uso de estos ataques contra su organización es proteger sus cuentas de usuario de forma agresiva.  Algunas de las formas más comunes en las que las cuentas se infringen son los ataques de suplantación de identidad (phishing) o de [niebla de contraseña](http://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) .



La mejor forma de proteger las cuentas de usuario y, especialmente sus cuentas de administrador, es [configurar la autenticación multifactor para los usuarios de Office 365](https://support.office.com/article/set-up-multi-factor-authentication-for-office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).  También debe hacer lo siguiente:
<ol>
    <li>Supervisar cómo se <a href="https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports">obtiene acceso</a>a las cuentas de usuario y cómo se usan. No puede evitar la infracción inicial, pero reducirá la duración y el impacto de la infracción al detectarla antes. Puede usar <a href="https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475">las siguientes directivas de seguridad de aplicaciones de nube de Office 365</a> para supervisar sus cuentas y enviar alertas sobre actividad inusual. 
        <ol type="a">
            <li><b>Varios intentos erróneos de inicio de sesión</b> Esta directiva perfila el entorno y desencadena alertas cuando los usuarios realizan varias actividades de inicio de sesión fallidas en una sola sesión con respecto a la línea base aprendida, lo que podría indicar un intento de infracción.</li>
            <li><b>Recorrido imposible</b> - Esta directiva perfila el entorno y activa alertas cuando se detectan actividades del mismo usuario en diferentes ubicaciones dentro de un período de tiempo menor que el tiempo de viaje esperado entre las dos ubicaciones. Esto puede indicar que un usuario diferente usa las mismas credenciales. La detección de este comportamiento anómalo requiere un período inicial de aprendizaje de siete días durante el cual aprende el patrón de actividad de un nuevo usuario.</li>
            <li><b>Actividad suplantaDa inusual (por usuario)</b> - Esta directiva perfila el entorno y desencadena alertas cuando los usuarios realizan varias actividades suplantadas en una única sesión con respecto a la línea base aprendida, lo que podría indicar una infracción de intento.</li>
        </ol>
    </li>
    <li>Aproveche una herramienta como la <a href="https://securescore.office.com/">puntuación segura de Office 365</a> para administrar los comportamientos y las configuraciones de seguridad de la cuenta. 
    </li>
</ol> 

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: mantener actualizados los clientes de Outlook
Las versiones completamente actualizadas y revisadas de Outlook 2013 y 2016 deshabilitan la acción de formulario o regla "Iniciar aplicación" de forma predeterminada.  Esto garantizará que, incluso si un atacante infringe la cuenta, se bloquearán las acciones de formulario y regla.  Para instalar las revisiones de seguridad y las actualizaciones más recientes, siga los pasos descritos en [instalar actualizaciones de Office](https://support.office.com/article/Install-Office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5).

Estas son las versiones de revisión para los clientes de Outlook 2013 y 2016:
- Outlook 2013:15.0.4937.1000 o superior
- Outlook 2016:16.0.4534.1001 o superior

Para obtener más información sobre las revisiones de seguridad individuales, vea:

- [Revisión de seguridad de Outlook 2013](https://support.microsoft.com/en-us/help/3191938) 
- [Revisión de seguridad de Outlook 2016](https://support.microsoft.com/en-us/help/3191883)

### <a name="third-monitor-your-outlook-clients"></a>Tercero: Supervise los clientes de Outlook
Tenga en cuenta que, incluso con las revisiones y actualizaciones instaladas, un atacante puede cambiar la configuración del equipo local para volver a habilitar el comportamiento "Iniciar aplicación". Puede usar la [Administración avanzada de directivas de grupo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) para supervisar y aplicar directivas de equipo local en los clientes.  
Puede ver si "Iniciar aplicación" se ha rehabilitado a través de una invalidación en el registro mediante el uso de la información de [Cómo ver el registro del sistema con las versiones de 64 bits de Windows](https://support.microsoft.com/en-us/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows).  Compruebe estas subclaves: 

- Outlook 2016: HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\
- Outlook 2013: HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\

Busque la clave EnableUnsafeClientMailRules. Si está y se establece en 1, la revisión de seguridad de Outlook se ha reemplazado y el equipo es vulnerable al ataque de reglas o formularios. Si el valor es 0, la acción "Iniciar aplicación" está deshabilitada.  Si está instalada la versión actualizada y revisada de Outlook y esta clave del registro no está presente, un sistema no es vulnerable a estos ataques.

Los clientes con instalaciones de Exchange locales deben considerar el bloqueo de versiones anteriores de Outlook que no tienen revisiones disponibles. Encontrará más información sobre este proceso en el artículo [configure Outlook Client blocking](https://technet.microsoft.com/en-us/library/dd335207(v=exchg.150).aspx).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteger Office 365 como un Cybersecurity Pro
Su suscripción a Office 365 incluye un eficaz conjunto de capacidades de seguridad que puede usar para proteger sus datos y sus usuarios.  Use el [plan de desarrollo de seguridad de Office 365: principales prioridades de los primeros 30 días, 90 días y más allá](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) de implementar los procedimientos recomendados de Microsoft para proteger su inquilino de Office 365.
- Tareas que se deben realizar en los primeros 30 días.  Estos tienen un efecto inmediato y tienen un impacto bajo para los usuarios.
- Tareas que se deben realizar en 90 días. Estos requieren un poco más de tiempo para planear e implementar, pero mejoran considerablemente su postura de seguridad.
- Más allá de 90 días. Estas mejoras se basan en el trabajo de los primeros 90 días.

## <a name="see-also"></a>Vea también:
- [Reglas](https://silentbreaksecurity.com/malicious-outlook-rules/) malintencionadas de Outlook por SilentBreak Security post about rules vector proporciona una revisión detallada de las reglas de Outlook. 
- [MAPI sobre http y Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) en el blog de Sensepost acerca de Mailrule Pwnage describe una herramienta denominada regla que le permite aprovechar buzones de correo mediante reglas de Outlook.
- [Formularios y shells de Outlook](https://sensepost.com/blog/2017/outlook-forms-and-shells/) en el blog de Sensepost sobre el vector de amenazas de formularios. 
- [Código base de regla](https://github.com/sensepost/ruler)
- [Indicadores de compromiso de la regla](https://github.com/sensepost/notruler/blob/master/iocs.md)