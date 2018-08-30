---
title: Detectar y personalizados y las reglas de Outlook de corrección de los ataques de inserciones de formularios en Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Obtenga información sobre cómo reconocer y corregir las reglas de Outlook y los ataques de inserciones de formularios personalizados en Office 365
ms.openlocfilehash: 893ade67976d7e6d1442a23f1f61948cea591dad
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535872"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Office 365

**Resumen** Obtenga información sobre cómo reconocer y corregir las reglas de Outlook y los ataques de inserciones formularios personalizados en Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>¿Qué es el ataque de inserción de las reglas de Outlook y formularios personalizados?
Después de que un atacante ha infringido una cuenta en su arrendamiento y obtiene, va a probar y establecer permanecer en una forma o una forma de recuperar después de que se descubren y se quitan. Esto se denomina el establecimiento de un mecanismo de persistencia. Dos formas que puede hacer esto son aprovechando las reglas de Outlook o insertando formularios personalizados en Outlook. En ambos casos, el formulario o la regla se sincroniza desde el servicio de nube hacia abajo hasta el cliente de escritorio, por lo que un formato completo y volver a instalarlo del software de cliente no eliminar el mecanismo de inserción. Esto es debido a que cuando se vuelve a conectar el software de cliente de Outlook con el buzón de correo en la nube se descargará volver a las reglas y los formularios de la nube. Una vez que las reglas y los formularios están en su lugar, el atacante los utiliza para ejecutar código remoto o personalizado, normalmente para instalar malware en el equipo local. El malware, a continuación, volver a roba credenciales o realiza otra actividad ilegal. La buena noticia es que si mantener a los clientes revisados hasta la versión más reciente, no es vulnerables a las amenazas como valores predeterminados de cliente de Outlook actuales bloquean ambos mecanismos. 

Los ataques suelen seguir estos patrones de:

La vulnerabilidad de reglas
1. El atacante roba el nombre de usuario y la contraseña de uno de los usuarios.
2. El atacante, a continuación, inicia sesión en ese buzón de Exchange de los usuarios. El buzón de correo puede ser en Exchange online o de Exchange local.
3. El atacante, a continuación, crea una regla de reenvío en el buzón de correo que se desencadena cuando el buzón de correo recibe un correo electrónico que coincida con los criterios de la regla. Los criterios de la regla y el contenido del correo electrónico desencadenador es a medida para cada uno de los otros.
4. El atacante envía el correo electrónico de desencadenador para el usuario que está utilizando su buzón normalmente.
5. Cuando se recibe el correo electrónico, se activa la regla. La acción de la regla es normalmente iniciar una aplicación en un servidor (Web WebDAV) remoto.
6. La aplicación normalmente instala malware, como [Imperio de Powershell](https://www.powershellempire.com/), localmente en el equipo del usuario.
7. El malware permite que el atacante volver a robar el nombre de usuario y contraseña u otras credenciales desde el equipo local y realizar otras actividades malintencionadas.

La vulnerabilidad de formularios
1. El atacante roba el nombre de usuario y la contraseña de uno de los usuarios.
2. El atacante, a continuación, inicie sesión en ese buzón de Exchange de los usuarios. El buzón de correo puede ser en Exchange online o de Exchange local.
3. A continuación, el atacante crea una plantilla de formulario de correo personalizado y lo inserta en el buzón del usuario.  El formulario personalizado se desencadena cuando el buzón de correo recibe un correo electrónico que requiere el buzón de correo para cargar el formulario personalizado. El formulario personalizado y el formato de correo electrónico son a medida para cada uno de los otros.
4. El atacante envía el correo electrónico de desencadenador para el usuario, que está utilizando su buzón normalmente.
5. Cuando se recibe el correo electrónico, se carga el formulario. El formulario inicia una aplicación en un servidor (Web WebDAV) remoto.
6. La aplicación normalmente instala malware, como [Imperio de Powershell](https://www.powershellempire.com/), localmente en el equipo del usuario.
7. El malware permite que el atacante volver a robar el nombre de usuario y contraseña u otras credenciales desde el equipo local y realizar otras actividades malintencionadas.


## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>¿Las reglas de un y ataque de inserción de formularios personalizados de sería parecida a Office 365?

Estos mecanismos de persistencia están poco probable que se den cuenta de los usuarios y es posible que en algunos casos incluso ser invisibles a ellos.  En este artículo se explica cómo buscar cualquiera de los siete signos (indicadores de peligro) enumerados a continuación. Si encuentra alguna de estas, necesita lleve a cabo los pasos de corrección.

- Poner en peligro los indicadores de las reglas
    - La acción de regla es iniciar una aplicación.
    - Regla hace referencia a un archivo EXE, ZIP o dirección URL.
    - En el equipo local, busque el nuevo proceso comienza que se originan desde el PID de Outlook.
- Poner en peligro los indicadores de los formularios personalizados 
    - Formulario personalizado presente guarda como su propia clase de mensaje.
    - Clase de mensaje contiene código ejecutable.
    - Normalmente se almacenan en las carpetas Bandeja de entrada o de biblioteca de formularios personales.
    - Formulario se denomina IPM. Tenga en cuenta. [nombre personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Pasos para buscar signos de este ataque y confirmarla
Puede usar cualquiera de estos dos métodos para confirmar el ataque.
- Examinar manualmente las reglas y formularios para cada buzón de correo mediante el cliente de Outlook.  Este método es exhaustiva, pero sólo se puede comprobar el usuario de buzón de correo a la vez que puede llevar mucho tiempo si tiene muchos usuarios para comprobar.  También se puede producir una infracción del equipo en el que se ejecuta la comprobación de.
- Utilice la secuencia de comandos de PowerShell [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) para volcar automáticamente todo el correo reenviar las reglas y formularios personalizados para todos los usuarios en su arrendamiento. Este es el método más rápido y más seguro con la menor cantidad de sobrecarga.


### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmar la reglas de ataque mediante el cliente de Outlook
1. Abra al cliente de Outlook de los usuarios como el usuario.  El usuario puede necesitar su ayuda en el examen de las reglas en su buzón.
2. Consulte el artículo de [Administrar mensajes mediante el uso de reglas de correo electrónico](https://support.office.com/article/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59#ID0EAABAAA=2010) para los procedimientos sobre cómo abrir la interfaz de las reglas en las versiones 2007, 2010 o 2013 de Outlook.
3. Busque las reglas que el usuario no ha creado, o cualquier inesperadas reglas o reglas con nombres sospechosos.
4. Buscar en la descripción de la regla para las acciones de regla que inicio y la aplicación o hacer referencia a un. EXE. Archivo ZIP o para iniciar una dirección URL.
5. Busque los nuevos procesos que se inician utilizando el identificador de proceso de Outlook.  Consulte para [encontrar el identificador de proceso](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Pasos para confirmar el ataque de formularios mediante el cliente de Outlook
1. Abra al cliente de Outlook del usuario como el usuario.
2. Siga los pasos descritos en, [Mostrar la pestaña Programador](https://support.office.com/article/show-the-developer-tab-e1192344-5e56-4d45-931b-e5fd9bea2d45) para la versión de los usuarios de Outlook.
3. Abra la ficha Programador ahora visible en Outlook y haga clic en **diseñar un formulario**.
4. En la lista **Buscar en** , seleccione la **Bandeja de entrada** . Buscar todos los formularios personalizados.  Formularios personalizados son lo suficientemente raros, por lo que si tiene todos los formularios personalizados en absoluto, merece la pena una mirada más profunda.
5. Investigar todos los formularios personalizados, sobre todo aquellas marcadas como ocultas.
6. Abra todos los formularios personalizados y en el grupo **formulario** , haga clic en **Ver código** para ver lo que se ejecuta cuando se carga el formulario.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Pasos para confirmar el ataque de formularios y las reglas de uso de PowerShell
La forma más sencilla para comprobar una de las reglas o ataque de formularios personalizados que se va a ejecutar el script de PowerShell [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) .  Esta secuencia de comandos se conecta a todos los buzones en el inquilino y vuelca todas las reglas y de formularios en dos archivos .csv files.

#### <a name="pre-requisites"></a>Requisitos previos
Debe tener un derechos de administrador global para ejecutar el script debido a que la secuencia de comandos se conecta a todos los buzones en el arrendamiento para leer las reglas y los formularios.

1. Inicie sesión en el equipo en el que se ejecutará la secuencia de comandos con derechos de administrador local.
2. Descargue o copie el script Get-AllTenantRulesAndForms.ps1 de depósito en una carpeta desde la que se ejecutará.  La secuencia de comandos creará dos archivos de fecha que se mostrará en esta carpeta, MailboxFormsExport-aaaa-mm-dd.csv y MailboxRulesExport-aaaa-mm-dd.csv.
3. Abra una sesión de PowerShell como administrador y abra la carpeta que se ha guardado la secuencia de comandos.
4. Ejecute esta línea de comandos de PowerShell de manera `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretación de los resultados

MailboxRulesExport -*aaaa-mm-dd*.csv – se examinan las reglas (uno por fila) para las condiciones de la acción que incluyen aplicaciones o ejecutables.
- ActionType (columna A) – si ve el valor "ID_ACTION_CUSTOM", la regla es probable malintencionado.
- IsPotentiallyMalicious (columna D) – si este valor es "TRUE", es probable que la regla malintencionado.
- ActionCommand (columna G): si se muestra una lista de una aplicación o los archivos que tengan un .exe, la extensión .zip o una entrada que hace referencia a una dirección URL, que no deberían para estar ahí, es probable que la regla malintencionado.

MailboxFormsExport -*aaaa-mm-dd*.csv – en general, el uso de formularios personalizados es muy raro.  Si encuentra alguna en este libro, abra el buzón de ese usuario y examine el propio formulario.  Si su organización no había puesto allí intencionadamente, es probable que malintencionado.



## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Procedimiento para detener y corregir el ataque de formularios y las reglas de Outlook
Si encuentra cualquier evidencia de cualquiera de estos ataques, corrección es simple, sólo se elimina la regla o formulario desde el buzón de correo. Puede hacer esto con el cliente de Outlook o mediante PowerShell remoto para quitar las reglas.

### <a name="using-outlook"></a>Uso de Outlook
1. Identificar todos los dispositivos que el usuario ha usado con Outlook.  Que se necesitan limpiarse de malware posible.  No permitir al usuario el inicio de sesión y usar el correo electrónico hasta que se limpien todos los dispositivos.
2. Siga los pasos de la [eliminación de una regla](https://support.office.com/article/Delete-a-rule-2F0E7139-F696-4422-8498-44846DB9067F) para cada dispositivo.
3. Si no está seguro sobre la presencia de otro software malintencionado, puede dar formato y volver a instalar todo el software en el dispositivo.  Puede seguir los pasos de los fabricantes para restablecer el dispositivo a la imagen de fábrica para dispositivos móviles.
4. Instale las versiones más recientes de Outlook.  Recuerde que la versión actual de Outlook bloquea ambos tipos de este ataque de forma predeterminada.
5. Una vez que se han quitado todas las copias sin conexión del buzón, restablecer la contraseña del usuario (utilice una alta calidad uno) y siga los pasos de la [autenticación con varios factores del programa de instalación para los usuarios de Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) si ya no se ha habilitado MFA. Esto garantiza que las credenciales del usuario no se exponen a través de otros medios (por ejemplo, para volver a usar suplantación de identidad o contraseña).

### <a name="using-powershell"></a>Uso de PowerShell
Hay dos cmdlets de PowerShell remoto que puede usar para quitar o deshabilitar reglas peligrosas. Sólo tiene que seguir los pasos.
 
Pasos para los buzones de correo que se encuentran en un servidor de Exchange

1. Conectar con el servidor de Exchange mediante PowerShell remoto. Siga los pasos de [Conectar con los servidores de Exchange mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps).
2. Si desea quitar completamente una sola regla, varias reglas o todas las reglas de un uso de buzón de correo el [cmdlet Remove-Bandeja de entrada regla ](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)- use esta opción para quitar completamente varios de uno, o todas las reglas del buzón de correo.
3. Si desea conservar la regla y su contenido para una mayor investigación use el [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

Pasos para los buzones de correo en Exchange Online
1. Siga los pasos en [conectarse a Exchange Online mediante PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
2.  Si desea quitar completamente una sola regla, varias reglas, o todas las reglas de un buzón de correo utilice el [cmdlet Remove-Bandeja de entrada de regla](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps).
3.  Si desea conservar la regla y su contenido para una mayor investigación use el [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

## <a name="how-to-minimize-future-attacks"></a>Procedimiento para minimizar los ataques futuros

### <a name="first-protect-your-accounts"></a>Primera: proteger las cuentas

Las vulnerabilidades de seguridad de las reglas y formularios sólo se utilizan por un atacante después de que han robado o una de las cuentas de usuario de su tipo de brecha. Por lo tanto, el primer paso para evitar el uso de estas vulnerabilidades de seguridad contra su organización es proteger las cuentas de usuario de forma más agresiva.  Algunas de las formas más comunes que son tipo de brecha cuentas son a través de suplantación de identidad o [contraseña pulverización](http://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) ataques.



Es la mejor forma de proteger las cuentas de usuario y especialmente las cuentas de administrador, para [Configurar la autenticación multifactor para usuarios de Office 365](https://support.office.com/article/set-up-multi-factor-authentication-for-office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).  También debe:
<ol>
    <li>Supervisar cómo las cuentas de usuario son <a href="https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports">acceso y utilizar</a>. No puede impedir que el incumplimiento inicial, pero se reducirá la duración y el impacto de la infracción mediante la detección de antes. Puede utilizar estos métodos: <a href="https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475">las directivas de seguridad de la aplicación de Office 365 en la nube</a> para supervisar las cuentas y alertas en una actividad inusual.<ol type="a">
            <li><b>Varios intentos de inicio de sesión con errores</b> Esta directiva de perfiles de su entorno y desencadenadores alertas cuando los usuarios realizan varias actividades de inicio de sesión con errores en una única sesión con respecto a la línea de base aprendida, que podría indicar un intento de infracción contra.</li>
            <li><b>Imposible de viajes</b> - Esta directiva de perfiles de su entorno y activa las alertas cuando se detectan actividades desde el mismo usuario en distintas ubicaciones dentro de un período de tiempo más corto que el tiempo de viaje esperado entre las dos ubicaciones. Esto podría indicar que un usuario diferente está usando las mismas credenciales. Detectar este comportamiento anómalo exige un período de aprendizaje inicial de siete días durante el cual aprende patrón de actividad de un usuario nuevo.</li>
            <li><b>No habitual suplanta la actividad (por usuario)</b> - Esta directiva de perfiles de su entorno y activa las alertas cuando los usuarios realizan varias actividades suplantadas en una sola sesión con respecto a la línea de base aprendida, que podría indicar un intento de infracción contra.</li>
        </ol>
    </li>
    <li>Sacar provecho de una herramienta como la <a href="https://securescore.office.com/">Puntuación de Office 365 seguro</a> para administrar los comportamientos y las configuraciones de seguridad de cuentas. 
    </li>
</ol> 

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: Mantener a los clientes de Outlook actual
Se actualizó totalmente y revisen versiones de Outlook 2013 y 2016 deshabilitación la acción de regla o formulario "Iniciar aplicación" de forma predeterminada.  Esto le permitirá garantizar que, incluso si un atacante ruptura de la cuenta, se bloquearán las acciones de regla y formulario.  Puede instalar las últimas actualizaciones y revisiones de seguridad, siga los pasos descritos en [las actualizaciones de instalación de Office](https://support.office.com/article/Install-Office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5).

Estas son las versiones de revisión para su Outlook 2013 y clientes de 2016:
- Outlook 2013: 15.0.4937.1000 o posterior
- Outlook 2016: 16.0.4534.1001 o posterior

Para obtener más información sobre las revisiones de seguridad individuales, consulte:

- [Revisión de seguridad de Outlook 2013](https://support.microsoft.com/en-us/help/3191938) 
- [Revisión de seguridad de Outlook 2016](https://support.microsoft.com/en-us/help/3191883)

### <a name="third-monitor-your-outlook-clients"></a>Tercer: Supervisar a los clientes de Outlook
Tenga en cuenta que, incluso con las revisiones y actualizaciones instaladas, es posible que un atacante cambiar la configuración del equipo local para volver a habilitar el comportamiento de "Iniciar aplicación". Puede usar [La administración avanzada de directivas de grupo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) para supervisar y aplicar las directivas de equipo local en los clientes.  
Puede para ver si "Iniciar aplicación" se ha volver a habilitado a través de una invalidación en el registro mediante el uso de la información en el [procedimiento para ver el registro del sistema mediante el uso de las versiones de 64 bits de Windows](https://support.microsoft.com/en-us/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows).  Compruebe estas subclaves: 

- Outlook 2016: HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\
- Outlook 2013: HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\

Busque la clave EnableUnsafeClientMailRules. Si existe y está establecida en 1, se ha reemplazado la revisión de seguridad de Outlook y el equipo es vulnerable al ataque de reglas del formulario. Si el valor es 0, se deshabilita la acción "Iniciar aplicación".  Si está instalada la versión actualizada y con la revisión de Outlook y esta clave del registro no está presente, un sistema no es vulnerable a estos ataques.

Los clientes con las instalaciones de Exchange local deben tener en cuenta el bloqueo de las versiones anteriores de Outlook que no tengan las revisiones disponibles. Obtener información detallada acerca de este proceso puede encontrarse en el [cliente de Outlook de la configuración de bloqueo](https://technet.microsoft.com/en-us/library/dd335207(v=exchg.150).aspx)de artículo.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Seguro de Office 365 como una ciberseguridad pro
Su suscripción de Office 365 incluye un conjunto eficaz de características de seguridad que puede utilizar para proteger los datos y los usuarios.  Usar el [Guía de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y más allá de](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) para implementar Microsoft procedimientos recomendado para proteger el inquilino de Office 365.
- Tareas de llevar a cabo en los primeros 30 días.  Estos tienen un efecto inmediato y están bajo impacto para los usuarios.
- Tareas de llevar a cabo en 90 días. Estos tardan un poco más tiempo para planear e implementar pero mejorar considerablemente el nivel de seguridad.
- Más allá de 90 días. Estas mejoras se basan en su primer trabajo de 90 días.

## <a name="see-also"></a>Vea también:
- [Las reglas de Outlook malintencionado](https://silentbreaksecurity.com/malicious-outlook-rules/) por SilentBreak Post de seguridad acerca de las reglas de Vector proporciona una revisión detallada de cómo las reglas de Outlook. 
- [MAPI sobre HTTP y Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) en el blog de Sensepost sobre Mailrule Pwnage trata de una herramienta denominada regla que le permite aprovechar los buzones de correo a través de las reglas de Outlook.
- [Shells y formularios de outlook](https://sensepost.com/blog/2017/outlook-forms-and-shells/) en el blog de Sensepost sobre Vector de amenaza de formularios. 
- [Codebase de regla](https://github.com/sensepost/ruler)
- [Indicadores de regla de compromiso](https://github.com/sensepost/notruler/blob/master/iocs.md)