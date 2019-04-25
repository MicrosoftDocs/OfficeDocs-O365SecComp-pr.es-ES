---
title: Responder a una cuenta de correo electrónico en peligro en Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a reconocer y responder a una cuenta de correo electrónico en peligro en Office 365
ms.openlocfilehash: abb9cbae0d1df41f5513e7958aaf1dc04ce66154
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264842"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Responder a una cuenta de correo electrónico en peligro en Office 365

**Resumen** Aprenda a reconocer y responder a una cuenta de correo electrónico en peligro en Office 365

## <a name="what-is-a-compromised-email-account-in-office-365"></a>¿Qué es una cuenta de correo electrónico en peligro en Office 365?
El acceso a los buzones, los datos y otros servicios de Office 365 se controla mediante el uso de credenciales, como un nombre de usuario y contraseña o PIN. Cuando alguien que no sea el usuario roba estas credenciales, se considera que las credenciales robadas suponen un riesgo. Con ellas, el atacante puede iniciar sesión como el usuario original y realizar acciones ilícitas.
Con las credenciales robadas, el atacante puede obtener acceso a archivos en OneDrive del usuario, las carpetas de SharePoint o el buzón de Office 365 del usuario. Una acción habitual es que el atacante envíe correos electrónicos como el usuario original a destinatarios tanto dentro como fuera de la organización. Cuando el atacante envía datos a destinatarios externos, se denomina "exfiltración" de datos.

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Síntomas de una cuenta de correo electrónico en peligro de Office 365
Los usuarios pueden observar e informar sobre actividad inusual en sus buzones de Office 365. Estos son algunos síntomas comunes:
- Actividad sospechosa, como correos electrónicos eliminados o que faltan.
- Otros usuarios pueden recibir correos electrónicos de la cuenta en peligro sin que el correo electrónico correspondiente aparezca en la carpeta **Elementos enviados** del remitente.
- La presencia de reglas de bandeja de entrada que no se han creado por el usuario o el administrador. Estas reglas pueden reenviar automáticamente correos electrónicos a direcciones desconocidas o moverlos a las carpetas de **Notas**, **Correo no deseado** o **Suscripciones RSS**.
- El nombre para mostrar del usuario puede cambiarse en la lista Global de direcciones.
- El buzón del usuario está bloqueado para enviar correo electrónico.
- Las carpetas de Elementos enviados o Elementos eliminados en Microsoft Outlook o Outlook en la Web (anteriormente conocido como Outlook Web App) contienen mensajes comunes de cuentas robadas, como "Estoy atascado en Londres, envíame dinero".
- Se han realizado cambios inusuales en el perfil, como el nombre, el número de teléfono o el código postal.
- Cambios inusuales de credenciales, como múltiples cambios de contraseña requeridos.
- Se ha agregado recientemente el reenvío de correo.
- Se ha agregado recientemente una firma inusual, como una firma de entidad bancaria falsa o una firma de recetas de medicamentos.

Si un usuario informa de los síntomas anteriores, debería realizar una mayor investigación. El Centro de seguridad y cumplimiento de Microsoft 365 y el Portal de Azure ofrecen herramientas para ayudarle a investigar la actividad de una cuenta de usuario que crea que puede estar en riesgo.
- Registros de auditoría unificados de Office 365 en el Centro de seguridad y cumplimiento: revise todas las actividades de la cuenta sospechosa, filtre los resultados con un rango de fechas que abarque desde antes de que se produjese la actividad sospechosa hasta la fecha actual. No filtre las actividades durante la búsqueda.
- Use los registros de inicio de sesión de Azure AD y otros informes de riesgos que están disponibles en el portal de Azure AD. Examine los valores de estas columnas:
    - Revise la dirección IP
    - ubicaciones de inicio de sesión
    - horas de inicio de sesión
    - inicios de sesión correctos y fallidos

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Cómo proteger y restaurar la función de correo electrónico a un buzón o una cuenta de Office 365 en peligro

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Incluso después de haber recuperado el acceso a su cuenta, el atacante puede haber agregado entradas traseras que permiten le permiten reanudar el control de la cuenta.

Debe realizar todos los pasos siguientes para volver a tener acceso a su cuenta lo antes posible para asegurarse de que el atacante no reanude el control de su cuenta. Estos pasos le ayudan a quitar las entradas traseras que puede haber agregado el atacante a su cuenta. Después de completar estos pasos, se recomienda que ejecute una detección de virus para asegurarse de que su equipo no está en peligro.

### <a name="step-1-reset-the-users-password"></a>Paso 1 Restablecer la contraseña del usuario
> [!WARNING]
> No envíe la nueva contraseña al usuario en cuestión por correo electrónico, ya que el atacante todavía tiene acceso al buzón en este momento.

1. Siga los procedimientos para Restablecer una contraseña de otro usuario de Office 365 para la Empresa en [Administradores: restablecer contraseñas de Office 365 de la empresa](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**Notas:**
- Asegúrese de que la contraseña es segura y que contiene al menos un carácter especial, al menos un número y letras mayúsculas y minúsculas. 
- No vuelva a usar ninguna de las últimas cinco contraseñas. Aunque el requisito de historial de contraseña le permite volver a usar una contraseña más reciente, debería seleccionar algo que el atacante no pueda adivinar.
- Si la identidad local se federa con Office 365, debe cambiar la contraseña en el entorno local y, a continuación, debe notificar a su administrador del ataque.

> [!TIP]
> Se recomienda que habilite la autenticación multifactor (MFA) para evitar los robos de cuenta, especialmente para las cuentas con privilegios de administrador.  Puede obtener más información [aquí](https://support.office.com/es-ES/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Paso 2 Eliminar direcciones de reenvío de correo electrónico sospechosas
1. Abra el **Centro de administración de Microsoft 365 > Usuarios activos**.
2. Busque la cuenta del usuario en cuestión y expanda **Configuración de correo**.
3. Para **Reenvío de correo electrónico**, haga clic en **Editar**.
4. Quite las direcciones de reenvío sospechosas.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Paso 3 Deshabilitar las reglas de bandeja de entrada sospechosas
1. Inicie sesión en el buzón del usuario con Outlook en la Web.
2. Haga clic en el icono del engranaje y en **Correo**.
3. Haga clic en **Reglas de bandeja de entrada y barrido** y revise las reglas.
4. Deshabilite o elimine las reglas sospechosas.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Paso 4 Desbloquear el usuario para que pueda enviar correo
Si el buzón en peligro se usó de forma ilícita para enviar correo no deseado, es probable que el buzón se haya bloqueado para impedir el envío de correo.
1. Para desbloquear el envío de correo de un buzón, siga los procedimientos descritos en [Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Paso 5 opcional: Bloquear la cuenta de usuario para impedir el inicio de sesión
> [!IMPORTANT]
> Puede bloquear la cuenta en peligro e impedir que inicie hasta que crea que es seguro volver a habilitar el acceso.

1. Vaya al Centro de administración de Microsoft 365.
2. En el Centro de administración de Microsoft 365, seleccione **Usuarios**.
3. Seleccione el empleado que desee bloquear y luego elija **Editar** junto a **Estado de inicio de sesión** en el panel de usuario.
4. En el panel **Estado de inicio de sesión**, elija **Inicio de sesión bloqueado** y luego **Guardar**. 
5. En el Centro de administración, en el panel de navegación de la parte inferior izquierda, expanda **Centros de administración** y seleccione **Exchange**.
6. En el Centro de administración de Exchange, navegue a **Destinatarios > Recursos**.
7. Seleccione el usuario y, en la página de propiedades de usuario, en **Dispositivos móviles**, haga clic en **Deshabilitar Exchange ActiveSync** y **Deshabilitar OWA para dispositivos** y responda **Sí** a ambos.
8. En **Conectividad de correo**, haga clic en **Deshabilitar** y responda **Sí**. 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Paso 6 opcional: Quitar la cuenta en peligro de todos los grupos de roles administrativos
> [!NOTE]
> La pertenencia a grupos de roles administrativos puede restaurarse después de haber asegurado la cuenta.

1. Inicie sesión en el Centro de administración de Microsoft 365 con una cuenta de administrador global y abra **Usuarios activos**.
2. Busque la cuenta en peligro y compruebe manualmente si hay roles administrativos asignados a la cuenta.
3. Abra el **Centro de seguridad y cumplimiento**.
4. Haga clic en **Permisos**.
5. Revise manualmente los grupos de roles para ver si la cuenta en peligro es miembro de cualquiera de ellos.  Si lo es: a. Haga clic en el grupo de roles y **Editar grupo de roles**.
    b. Haga clic en **Elegir miembros** y **Editar** para quitar el usuario del grupo de roles.
6. Abra el **Centro de administración de Exchange**.
7. Haga clic en **Permisos**.
8. Revise manualmente los grupos de roles para ver si la cuenta en peligro es miembro de cualquiera de ellos. Si lo es: a. Haga clic en el grupo de roles y en **Editar**.
    b. Use la sección **miembros** para quitar el usuario del grupo de roles.

### <a name="step-7-optional-additional-precautionary-steps"></a>Paso 7 opcional: Pasos de precauciones adicionales
1. Asegúrese de comprobar los elementos enviados. Puede que tenga que informar a los usuarios de la lista de contactos de que su cuenta está comprometida. El atacante puede haberles pedido dinero fingiendo, por ejemplo, que estaba perdido en un país distinto y necesitaba dinero, o el atacante puede enviarles un virus para obtener acceso también a sus equipos.
2. Cualquier otro servicio que use esta cuenta de Exchange como cuenta de correo electrónico alternativa puede haberse comprometido también. En primer lugar, siga estos pasos para la suscripción de Office 365 y, a continuación, siga estos pasos para otras cuentas.
3. Asegúrese de que la información de contacto, como los números de teléfono y direcciones, es correcta.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteger Office 365 como un profesional de ciberseguridad
Su suscripción a Office 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios.  Use el [Plan de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y en adelante](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Office 365.
- Tareas a realizar en los primeros 30 días.  Estas tienen un efecto inmediato y de bajo impacto para los usuarios.
- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.
- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también:
- [Procedimientos recomendados de seguridad para Office 365](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Office 365](detect-and-remediate-outlook-rules-forms-attack.md)
- [Centro de Quejas de Crímenes por Internet](http://www.ic3.gov/preventiontips.aspx)
- [Bolsas de valores de EE. UU.: Fraude de suplantación de identidad](http://www.sec.gov/investor/pubs/phishing.htm)
- Para informar directamente a Microsoft y su administrador sobre el correo no deseado [Use el complemento Informar sobre el mensaje](https://support.office.com/es-ES/article/Use-the-Report-Message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
