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
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Obtenga información sobre cómo reconocer y responder a una cuenta de correo electrónico en peligro en Office 365
ms.openlocfilehash: 9a3dcc2d10c7487e525ae127674a830f9a921a60
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782187"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Responder a una cuenta de correo electrónico en peligro en Office 365

**Resumen** Obtenga información sobre cómo reconocer y responder a una cuenta de correo electrónico en peligro en Office 365.

## <a name="what-is-a-compromised-email-account-in-office-365"></a>¿Qué es una cuenta de correo electrónico en riesgo en Office 365?
El acceso a los buzones de correo, los datos y otros servicios de Office 365, se controla mediante el uso de credenciales, por ejemplo un nombre de usuario y contraseña o PIN. Cuando alguien que no sea el usuario previsto roba esas credenciales, las credenciales robadas se consideran se ve comprometida. Con ellos, el atacante puede iniciar sesión como el usuario original y realizar acciones ilegal. Con las credenciales robadas, el atacante puede tener acceso a buzones de correo de Office 365, las carpetas de SharePoint o archivos de OneDrive del usuario del usuario. Una acción suele verse es el atacante enviar mensajes de correo electrónico como el usuario original a los destinatarios tanto dentro como fuera de la organización. Cuando el atacante correos electrónicos de datos a destinatarios externos, esto se denomina exfiltration de datos.

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Síntomas de una cuenta de correo electrónico en peligro Office 365
Es posible que tenga en cuenta los usuarios y se informe de actividad inusual en sus buzones de correo de Office 365. Estos son algunos síntomas comunes:
- Actividad sospechosa, como mensajes de correo electrónico falta o se elimina.
- Otros usuarios pueden recibir mensajes de correo electrónico de la cuenta en peligro sin el correspondiente existentes en la carpeta **Elementos enviados** del remitente de correo electrónico.
- La presencia de las reglas de bandeja de entrada que no se han creado por el usuario previsto o el administrador. Estas reglas automáticamente pueden reenviar mensajes de correo electrónico a direcciones desconocidas o moverlos a las carpetas de **Correo electrónico no deseado**, **notas**o **Suscripciones RSS** .
- Es posible que se puede cambiar el nombre del usuario para mostrar en la lista Global de direcciones.
- Se bloquea el buzón del usuario de envío de correo electrónico.
- Las carpetas enviados o elementos eliminados en Microsoft Outlook o en Microsoft Outlook Web App contienen mensajes de cuenta entrado en mi sistema comunes, como "Estoy quedó en Londres, enviar dinero."
- Se han actualizado los cambios del perfil poco habitual, como el nombre, el número de teléfono o el código postal.
- Se requieren cambios de credencial poco habitual, como varios cambios de contraseña.
- Reenvío de correo se ha agregado recientemente.
- Recientemente se agregó una firma poco habitual, como una firma banca falsos o una firma de drogas con receta.

Si un usuario informa de cualquiera de los síntomas anteriores, debe realizar más investigación. La seguridad de Office 365 & Centro de cumplimiento y el Portal de Azure ofrecen herramientas para ayudarle a investigar la actividad de una cuenta de usuario que sospecha que puede poner en peligro.
- Office 365 unificada registros de auditoría de seguridad & Centro de cumplimiento - revisar todas las actividades de la cuenta de sospecha mediante el filtrado de los resultados de la fecha intervalo que abarca desde inmediatamente antes de que se ha producido la actividad sospechosa para la fecha actual. No filtra en las actividades durante la búsqueda.
- Use los registros de inicio de sesión de Azure AD y otros informes de riesgo que están disponibles en el portal de Azure AD. Examine los valores de estas columnas:
    - Revise la dirección IP
    - ubicaciones de inicio de sesión
    - tiempos de inicio de sesión
    - inicio de sesión de éxito o error



## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Procedimiento para proteger y restaurar la función de correo electrónico a un sospechoso en riesgo cuenta de Office 365 y buzón de correo

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Incluso después de que ha recuperado el acceso a su cuenta, el atacante puede haber agregado entradas de puerta trasera que permiten que el atacante reanudar el control de la cuenta.

Debe realizar los pasos siguientes para volver a obtener acceso a su cuenta cuanto mejor para asegurarse de que no se reanuda el pirata de controlar su cuenta. Estos pasos le ayudarán a quitar todas las entradas de puerta trasera que el pirata es posible que haya agregado a su cuenta. Después de realizar estos pasos, le recomendamos que ejecute una detección de virus para asegurarse de que el equipo no está en peligro.

### <a name="step-1-reset-the-users-password"></a>Paso 1 restablece la contraseña del usuario
> [!WARNING]
> No enviar la nueva contraseña para el usuario previsto a través de correo electrónico como el atacante aún tiene acceso a los buzones de correo en este momento.

1. Siga la contraseña de negocio restablecer un Office 365 para alguien else procedimientos de [administradores: restablecer Office 365 contraseñas de negocio](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**Notas:**
- Asegúrese de que la contraseña es segura y que contiene al menos un carácter especial, al menos un número y letras mayúsculas y minúsculas. 
- No volver a usar cualquiera de las últimas cinco contraseñas. Aunque el requisito de historial de contraseña permite reutilizar una contraseña más reciente, debe seleccionar algo que no se puede estimar el atacante.
- Si su identidad local está asociado a Office 365, debe cambiar su contraseña local y, a continuación, debe notificar a su administrador del peligro.

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Paso 2 direcciones de reenvío de correo electrónico sospechosos Remove
1. Abrir la **Centro de administración de Office 365 > usuarios activos**.
2. Busque la cuenta de usuario en cuestión y expanda **Configuración de correo**.
3. **Reenvío de correo electrónico**, haga clic en **Editar**.
4. Quitar las direcciones de transferencia sospechosos.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Paso 3 deshabilitar todas las reglas de bandeja de entrada sospechosos
1. Inicie sesión en el buzón del usuario mediante Outlook Web App (OWA).
2. Haga clic en el icono del engranaje y haga clic en **correo**.
3. Haga clic en **reglas de bandeja de entrada y barrido** y revisar las reglas.
4. Deshabilitar o eliminar reglas sospechosas.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Paso 4 desbloquear el usuario envíe mensajes de correo
Si el buzón de correo en peligro sospechoso se usó de forma ilegal para enviar correo electrónico de spam, es probable que se ha bloqueado el buzón de correo de envío de correo.
1. Para desbloquear un buzón de correo de envío de correo, siga los procedimientos de [eliminación de un usuario, el dominio o la dirección IP de una lista de bloqueados después de enviar correo electrónico de spam](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Paso 5 opcional: Bloquear la cuenta de usuario de inicio de sesión en
> [!IMPORTANT]
> Puede bloquear la cuenta en peligro sospechosa de iniciar sesión hasta que usted cree que es segura para volver a habilitar el acceso.

1. Vaya al Centro de administración de Office 365.
2. En el centro de administración de Office 365, seleccione **los usuarios**.
3. Seleccione al empleado que desea bloquear y, a continuación, elija **Editar** junto al **estado de sesión** en el panel de usuario
4. En el panel de **estado de sesión** , elija **Inicio de sesión bloqueado** y, a continuación, en **Guardar**. 
5. En el centro de administración de Office 365, en el panel de navegación inferior izquierda, expanda **Centros de administración** y seleccione **Exchange**.
6. En el centro de administración de Exchange, vaya a **destinatarios > buzones de correo**.
7. Seleccione el usuario y en la página de propiedades de usuario, en **Dispositivos móviles**, haga clic en **Deshabilitar ActivcSync de Exchange** y **Deshabilitar OWA para dispositivos** y responda **Sí** a ambos.
8. En la **Conectividad de correo electrónico**, **Deshabilitar** y respuesta **Sí**. 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Opcional de paso 6: Quitar la cuenta en peligro sospechosa de todos los grupos de funciones administrativas
> [!NOTE]
> Pertenencia al grupo de rol administrativo se puede restaurar después de que la cuenta se ha protegido.

1. Inicie sesión en el centro de administración de Office 365 con una cuenta de administrador global y abra **Usuarios activos**.
2. Busque la sospecha cuenta en riesgo y comprobar de forma manual para ver si hay cualquier funciones administrativas asignadas a la cuenta.
3. Abra el **Centro de cumplimiento y seguridad**.
4. Haga clic en **permisos**.
5. Revisar manualmente los grupos de funciones para ver si el sospechoso en riesgo cuenta es un miembro de cualquiera de ellos.  Si es: a. Haga clic en el grupo de roles y haga clic en **Editar grupo de funciones**.  b. Haga clic en **Eligió miembros** y **Editar** para quitar el usuario del grupo de funciones.
6. Abra el **Centro de administración de Exchange**
7. Haga clic en **permisos**.
8. Revisar manualmente los grupos de funciones para ver si el sospechoso en riesgo cuenta es un miembro de cualquiera de ellos. Si es: a. Haga clic en el grupo de roles y haga clic en **Editar**.  b. utilizar la sección **miembros** para quitar el usuario del grupo de funciones.

### <a name="step-7-optional-additional-precautionary-steps"></a>Opcional paso 7: Los pasos preventivos adicionales
1. Asegúrese de que compruebe los elementos enviados. Es posible que deba informar a las personas en la lista de contactos que se ha puesto en peligro su cuenta. El atacante puede solicitarles para dinero, suplantación de identidad, por ejemplo, que se han en desuso en un país distinto y sea necesario dinero, o el atacante puede enviarle un virus secuestrar también sus equipos.
2. Cualquier otro servicio que usa esta cuenta de Exchange, tal y como se han comprometido su cuenta de correo electrónico alternativo. En primer lugar, siga estos pasos para la suscripción de Office 365 y, a continuación, siga estos pasos para otras cuentas.
3. Asegúrese de que su información de contacto, como números de teléfono y direcciones, es correcto.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Seguro de Office 365 como una ciberseguridad pro
Su suscripción de Office 365 incluye un conjunto eficaz de características de seguridad que puede utilizar para proteger los datos y los usuarios.  Usar el [Guía de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y más allá de](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) para implementar Microsoft procedimientos recomendado para proteger el inquilino de Office 365.
- Tareas de llevar a cabo en los primeros 30 días.  Estos tienen un efecto inmediato y están bajo impacto para los usuarios.
- Tareas de llevar a cabo en 90 días. Estos tardan un poco más tiempo para planear e implementar pero mejorar considerablemente el nivel de seguridad.
- Más allá de 90 días. Estas mejoras se basan en su primer trabajo de 90 días.

## <a name="see-also"></a>Vea también:
- [Procedimientos recomendados de seguridad para Office 365](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Office 365](detect-and-remediate-outlook-rules-forms-attack.md)
- [Centro de quejas delito de Internet](http://www.ic3.gov/preventiontips.aspx)
- [Securities and Exchange Commission - loterías "Phishing"](http://www.sec.gov/investor/pubs/phishing.htm)
