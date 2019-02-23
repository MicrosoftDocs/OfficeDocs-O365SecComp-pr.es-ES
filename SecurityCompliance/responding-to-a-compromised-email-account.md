---
title: Responder a una cuenta de correo electrónico en peligro en Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Obtenga información sobre cómo reconocer y responder a una cuenta de correo electrónico comprometida en Office 365
ms.openlocfilehash: 8d2e7f501b6e3ee73a14d4d7b3edb4c49f99d051
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213220"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Responder a una cuenta de correo electrónico en peligro en Office 365

**Resumen** Obtenga información sobre cómo reconocer y responder a una cuenta de correo electrónico comprometida en Office 365.

## <a name="what-is-a-compromised-email-account-in-office-365"></a>¿Qué es una cuenta de correo electrónico comprometida en Office 365?
El acceso a los buzones de correo de Office 365, datos y otros servicios, se controla mediante el uso de credenciales, por ejemplo, un nombre de usuario y una contraseña o PIN. Cuando alguien que no sea el usuario deseado roba esas credenciales, las credenciales robadas se consideran comprometidas. Con ellos, el atacante puede iniciar sesión como usuario original y realizar acciones ilícitas. Con las credenciales robadas, el atacante puede tener acceso al buzón del usuario 365 de Office, las carpetas de SharePoint o los archivos del OneDrive del usuario. Una acción que se suele ver es que el atacante envía mensajes de correo electrónico como usuario original a los destinatarios tanto dentro como fuera de la organización. Cuando el atacante envía datos por correo electrónico a destinatarios externos, se denomina "exfiltración de datos".

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Síntomas de una cuenta de correo electrónico de Office 365 en peligro
Los usuarios podrían notar e informar de actividad inusual en sus buzones de Office 365. Estos son algunos síntomas comunes:
- Actividad sospechosa, como mensajes de correo electrónico que faltan o están eliminados.
- Otros usuarios pueden recibir mensajes de correo electrónico de la cuenta en peligro sin el correo electrónico correspondiente existente en la carpeta **elementos enviados** del remitente.
- La presencia de reglas de la bandeja de entrada que no fueron creadas por el usuario o el administrador correspondiente. Estas reglas pueden reenviar automáticamente los correos electrónicos a direcciones desconocidas o moverlos a las carpetas **notas**, **correo electrónico no deseado**o suscripciones **RSS** .
- El nombre para mostrar del usuario puede cambiarse en la lista global de direcciones.
- Se impide que el buzón del usuario envíe correo electrónico.
- Las carpetas elementos enviados o eliminados de Microsoft Outlook o Outlook en la web (anteriormente conocido como Outlook Web App) contienen mensajes de cuentas malintencionadas comunes, como "Estoy atascado en Londres, enviar dinero".
- Se han actualizado los cambios de perfil inusuales, como el nombre, el número de teléfono o el código postal.
- Se requieren cambios inusuales en las credenciales, como varios cambios de contraseña.
- El reenvío de correo se ha agregado recientemente.
- Se ha agregado recientemente una firma inusual, como una firma bancaria falsa o una firma de medicamento recetado.

Si un usuario informa de los síntomas anteriores, debe realizar una investigación más detallada. El centro de seguridad & cumplimiento de Office 365 y Azure portal ofrecen herramientas para ayudarle a investigar la actividad de una cuenta de usuario que sospecha que puede estar en peligro.
- Los registros de auditoría unificada de Office 365 en el centro de seguridad & cumplimiento: Revise todas las actividades de la cuenta sospechosa filtrando los resultados para el intervalo de fechas comprendido entre inmediatamente antes de que la actividad sospechosa se produjera hasta la fecha actual. No filtra por las actividades durante la búsqueda.
- Use los registros de inicio de sesión de Azure AD y otros informes de riesgos que están disponibles en el portal de Azure AD. Examine los valores de estas columnas:
    - Revisar dirección IP
    - ubicaciones de inicio de sesión
    - tiempos de inicio de sesión
    - Inicio de sesión correcto o erróneo

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Cómo proteger y restaurar la función de correo electrónico en una cuenta y un buzón de Office 365 sospechosos de estar en peligro

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Incluso después de haber recuperado el acceso a su cuenta, el atacante puede haber agregado entradas de puerta trasera que permitan al atacante reanudar el control de la cuenta.

Debe realizar los pasos siguientes para volver a obtener acceso a su cuenta lo antes que sea mejor para asegurarse de que el secuestrador no reanude el control de la cuenta. Estos pasos le ayudarán a quitar las entradas de la puerta trasera que el secuestrador haya agregado a su cuenta. Después de realizar estos pasos, le recomendamos que ejecute una detección de virus para asegurarse de que el equipo no está en peligro.

### <a name="step-1-reset-the-users-password"></a>Paso 1 restablecer la contraseña del usuario
> [!WARNING]
> No envíe la nueva contraseña al usuario previsto a través del correo electrónico, ya que el atacante sigue teniendo acceso al buzón en este momento.

1. Siga los procedimientos restablecer una contraseña de Office 365 empresa para otros usuarios en [administradores: restablecer contraseñas de empresa de office 365](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**Notas**:
- Asegúrese de que la contraseña es segura y de que contiene mayúsculas y minúsculas, por lo menos un número y un carácter especial. 
- No vuelva a usar ninguna de las últimas cinco contraseñas. Aunque el requisito de historial de contraseñas le permite volver a usar una contraseña más reciente, debe seleccionar algo que el atacante no pueda adivinar.
- Si su identidad local se ha federado con Office 365, debe cambiar la contraseña local y, a continuación, debe notificar al administrador el peligro.

> [!TIP]
> Se recomienda encarecidamente que habilite la autenticación multiFactor (MFA) para evitar el riesgo, especialmente en el caso de las cuentas con privilegios administrativos.  Puede obtener más información [aquí](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Paso 2 quitar direcciones de reenvío de correo sospechoso
1. Abra el **centro de administración de Office 365 _GT_ usuarios activos**.
2. Busque la cuenta de usuario en cuestión y expanda **configuración de correo**.
3. Para el reenvío de **correo electrónico**, haga clic en **Editar**.
4. Quite cualquier dirección de reenvío sospechosa.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Paso 3 desHabilitar las reglas de la bandeja de entrada sospechosa
1. Inicie sesión en el buzón del usuario con Outlook en la Web.
2. Haga clic en el icono de engranaje y haga clic en **correo**.
3. Haga clic en la **bandeja de entrada y las reglas de barrido** y revise las reglas.
4. DesHabilite o elimine las reglas sospechosas.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Paso 4 desbloquear al usuario para que no envíe correo
Si el buzón sospechoso comprometido se usó de forma ilegal para enviar correo no deseado, es probable que se haya bloqueado el envío de correo al buzón.
1. Para desbloquear un buzón para que no envíe correo, siga los procedimientos que se describen en [quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Paso 5 opcional: impedir que se inicie sesión en la cuenta de usuario
> [!IMPORTANT]
> Puede impedir que se inicie sesión en la cuenta sospechosamente expuesta hasta que considere que es seguro volver a habilitar el acceso.

1. Vaya al Centro de administración de Office 365.
2. En el Centro de administración de Office 365, seleccione **Usuarios**.
3. Seleccione el empleado que desee bloquear y, a continuación, elija **Editar** junto a **Estado de inicio de sesión** en el panel de usuario.
4. En el panel **Estado de inicio de sesión**, elija **Inicio de sesión bloqueado** y luego **Guardar**. 
5. En el centro de administración de Office 365, en el panel de navegación inferior izquierdo, expanda **centros de administración** y seleccione **Exchange**.
6. En el centro de administración de Exchange, vaya a **destinatarios _GT_ buzoNes de correo**.
7. Seleccione el usuario y, en la página de propiedades de usuario, en **dispositivos móviles**, haga clic en deshabilitar **Exchange ActivcSync** y deshabilitar **OWA para dispositivos** y responda **sí** a ambos.
8. En **conectividad de correo**, deshabilite y responda **sí**. **** 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Paso 6 opcional: quitar la cuenta sospechoso de estar en peligro de todos los grupos de roles administrativos
> [!NOTE]
> La pertenencia al grupo de roles administrativo puede restaurarse una vez que la cuenta se haya asegurado.

1. Inicie sesión en el centro de administración de Office 365 con una cuenta de administrador global y Abra **usuarios activos**.
2. Busque la cuenta sospechosamente en peligro y compruebe manualmente si hay roles administrativos asignados a la cuenta.
3. Abra el **centro de seguridad _AMP_ cumplimiento**.
4. Haga clic en **permisos**.
5. Revise manualmente los grupos de roles para ver si la cuenta sospechosamente expuesta es miembro de cualquiera de ellos.  Si es: a. Haga clic en el grupo de roles y haga clic en **Editar Grupo de roles**.  b. Haga clic en **seleccionar miembros** y **Editar** para quitar el usuario del grupo de roles.
6. Abrir el **centro de administración de Exchange**
7. Haga clic en **permisos**.
8. Revise manualmente los grupos de roles para ver si la cuenta sospechosamente expuesta es miembro de cualquiera de ellos. Si es: a. Haga clic en el grupo de roles y haga clic en **Editar**.  b. Use la sección **miembros** para quitar el usuario del grupo de roles.

### <a name="step-7-optional-additional-precautionary-steps"></a>Paso 7 opcional: pasos adicionales de precaución
1. Asegúrese de comprobar los elementos enviados. Es posible que deba informar a los usuarios de la lista de contactos que su cuenta se ha puesto en peligro. Es posible que el atacante le haya pedido dinero, suplantación de identidad, por ejemplo, que se haya quedado en un país diferente y que necesite dinero, o que el atacante pueda enviarle un virus para secuestrar también sus equipos.
2. Puede que se haya puesto en peligro cualquier otro servicio que haya usado esta cuenta de Exchange como cuenta de correo electrónico alternativa. En primer lugar, siga estos pasos para su suscripción de Office 365 y, a continuación, siga estos pasos para sus otras cuentas.
3. Asegúrese de que la información de contacto, como números de teléfono y direcciones, es correcta.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteger Office 365 como un Cybersecurity Pro
Su suscripción a Office 365 incluye un eficaz conjunto de capacidades de seguridad que puede usar para proteger sus datos y sus usuarios.  Use el [plan de desarrollo de seguridad de Office 365: principales prioridades de los primeros 30 días, 90 días y más allá](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) de implementar los procedimientos recomendados de Microsoft para proteger su inquilino de Office 365.
- Tareas que se deben realizar en los primeros 30 días.  Estos tienen un efecto inmediato y tienen un impacto bajo para los usuarios.
- Tareas que se deben realizar en 90 días. Estos requieren un poco más de tiempo para planear e implementar, pero mejoran considerablemente su postura de seguridad.
- Más allá de 90 días. Estas mejoras se basan en el trabajo de los primeros 90 días.

## <a name="see-also"></a>Vea también:
- [Procedimientos recomendados de seguridad para Office 365](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Office 365](detect-and-remediate-outlook-rules-forms-attack.md)
- [Centro de quejas sobre delitos de Internet](http://www.ic3.gov/preventiontips.aspx)
- [Fraude de valores y de la Comisión de Exchange: fraude de "phishing"](http://www.sec.gov/investor/pubs/phishing.htm)
