---
title: Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: Los administradores pueden aprender a crear reglas de flujo de correo (también conocidas como reglas de transporte) para cifrar y descifrar mensajes mediante el cifrado de mensajes de Office 365 (OME).
ms.openlocfilehash: 38838bea22eda1b3bc92fa33902ed38f4cd052e5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218560"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365

Como administrador global de Office 365, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para ayudar a proteger los mensajes de correo electrónico que envíe y reciba. Puede configurar reglas para cifrar los mensajes de correo electrónico salientes y quitar el cifrado de los mensajes cifrados que provengan de la organización o de las respuestas a los mensajes cifrados que se envían desde la organización. Puede usar el centro de administración de Exchange (EAC) o Exchange Online PowerShell para crear estas reglas. Además de las reglas de cifrado general, también puede optar por habilitar o deshabilitar las opciones de cifrado de mensajes individuales para los usuarios finales.

||
|:-----|
|Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

Si migró recientemente de AD RMS a Azure Information Protection, deberá revisar sus reglas de flujo de correo existentes para asegurarse de que siguen funcionando en su nuevo entorno. Además, si desea aprovechar las nuevas capacidades de cifrado de mensajes de Office 365 (OME) disponibles a través de Azure Information Protection, debe actualizar las reglas de flujo de correo existentes. De lo contrario, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior en lugar de la nueva experiencia de OME sin problemas. Si todavía no ha configurado OME, vea [configurar las nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md) para obtener información.

Para obtener información sobre los componentes que conforman las reglas de flujo de correo y cómo funcionan las reglas de flujo de correo, consulte [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Para obtener más información acerca de cómo funcionan las reglas de flujo de correo con Azure Information Protection, consulte [configuración de reglas de flujo de correo de Exchange Online para las etiquetas de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Para entornos híbridos de Exchange, los usuarios locales pueden enviar correo cifrado usando OME solo si el correo electrónico se enruta a través de Exchange Online. Para configurar OME en un entorno híbrido de Exchange, primero debe [configurar un híbrido mediante el Asistente para la configuración híbrida](https://docs.microsoft.com/Exchange/exchange-hybrid) y, a continuación, [configurar el correo para que fluya desde su servidor de correo electrónico hacia Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Una vez que haya configurado el correo para que fluya a través de Office 365, puede configurar las reglas de flujo de correo para OME mediante esta guía.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Crear reglas de flujo de correo para cifrar los mensajes de correo electrónico con las nuevas funciones de OME

Puede definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas capacidades de OME mediante el EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Usar el EAC para crear una regla para cifrar mensajes de correo electrónico con las nuevas funciones de OME

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **** \> **reglas** de flujo de correo **** ![y seleccione nuevo](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> icono nuevo para **crear una nueva regla**. Para obtener más información acerca del uso de EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como cifrar correo para DrToniRamos@hotmail.com.

6. En **Aplicar esta regla si** seleccione una condición y especifique un valor si es necesario. Por ejemplo, para cifrar los mensajes que se dirigen a DrToniRamos@hotmail.com:

   1. En **Aplicar esta regla si**, seleccione **el destinatario es**.

   2. Seleccione un nombre existente en la lista de contactos o escriba una nueva dirección de correo electrónico en el cuadro **Comprobar nombres**.

      - Para seleccionar un nombre existente, selecciónelo en la lista y, a continuación, haga clic en **Aceptar**.

      - Para escribir un nuevo nombre, escriba una dirección de correo electrónico en el cuadro **Comprobar nombres** y, a continuación, seleccione **Comprobar nombres** \> **correctos**.

7. Para agregar más condiciones, elija **más opciones** y, a continuación, elija **Agregar condición** y seleccione en la lista.

   Por ejemplo, para aplicar la regla solo si el destinatario está fuera de **** la organización, seleccione **Agregar condición** y, a continuación, seleccione **el destinatario es externo o interno** \> **fuera de la organización** \> .

8. Para habilitar el cifrado con las nuevas capacidades de OME, desde **haga lo siguiente**, seleccione **modificar la seguridad de los mensajes** y, a continuación, elija aplicar el cifraDo de **mensajes de Office 365 y la protección de derechos**. Seleccione una plantilla RMS de la lista, elija **Guardar**y, después, haga clic en **Aceptar**.
  
  La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por parte de Office 365. Si la lista está vacía, asegúrese de haber configurado el cifrado de mensajes de Office 365 con las nuevas funciones, tal como se describe en [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, vea [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre **** la opción no reenviar, vea la opción no reenviar [para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **solo cifrar** , vea la [opción cifrar solo para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Puede elegir **Agregar acción** si desea especificar otra acción.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Usar el EAC para actualizar una regla de flujo de correo existente para usar las nuevas funciones de OME

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

5. En la lista de reglas de flujo de correo, seleccione la regla que desea modificar para usar las nuevas funciones de OME y **** ![, a continuación](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif), elija Editar icono Editar.

6. Para habilitar el cifrado con las nuevas capacidades de OME, desde **haga lo siguiente**, elija **modificar la seguridad de los mensajes** y, a continuación, elija aplicar el cifraDo de **mensajes de Office 365 y la protección de derechos**. Seleccione una plantilla RMS de la lista, elija **Guardar** y, a continuación, elija **Aceptar**.

   La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por parte de Office 365. Si la lista está vacía, asegúrese de haber configurado el cifrado de mensajes de Office 365 con las nuevas funciones, tal y como se describe en [configurar nuevas capacidades de cifrado de mensajes de office 365 que se basan en Azure Information Protection](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, vea [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre **** la opción no reenviar, vea la opción no reenviar [para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **solo cifrar** , vea la [opción cifrar solo para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Puede elegir **Agregar acción** si desea especificar otra acción.

7. En la **siguiente** lista, quite las acciones asignadas para **modificar la seguridad** \> de los mensajes, **aplique la versión anterior de OME**.

8. Elija **Guardar**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Crear reglas de flujo de correo para el cifrado de mensajes de Office 365 sin las nuevas funciones

Si todavía no ha movido su organización de Office 365 a las nuevas capacidades de OME, use estas tareas para definir reglas de flujo de correo para cifrar mensajes para la organización. Microsoft recomienda que cree un plan para cambiar a las nuevas funciones de OME en cuanto sea razonable para su organización. Para obtener instrucciones, vea [configurar las nuevas funciones de cifrado de mensajes de Office 365 basadas en Azure Information Protection](set-up-new-message-encryption-capabilities.md).

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Usar el EAC para crear una regla de flujo de correo para cifrar mensajes de correo electrónico sin las nuevas funciones OME

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **** \> **reglas** de flujo de correo **** ![y seleccione nuevo](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> icono nuevo para **crear una nueva regla**. Para obtener más información acerca del uso de EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como cifrar correo para DrToniRamos@hotmail.com.

6. En **Aplicar esta regla si** seleccione una condición y especifique un valor si es necesario. Por ejemplo, para cifrar los mensajes que se dirigen a DrToniRamos@hotmail.com:

   1. En **Aplicar esta regla si**, seleccione **el destinatario es**.

   2. Seleccione un nombre existente en la lista de contactos o escriba una nueva dirección de correo electrónico en el cuadro **Comprobar nombres**.

      - Para seleccionar un nombre existente, selecciónelo en la lista y, a continuación, haga clic en **Aceptar**.

      - Para escribir un nuevo nombre, escriba una dirección de correo electrónico en el cuadro **Comprobar nombres** y, a continuación, seleccione **Comprobar nombres** \> **correctos**.

7. Para agregar más condiciones, elija **más opciones** y, a continuación, seleccione **Agregar condición** y seleccione en la lista.

   Por ejemplo, para aplicar la regla solo si el destinatario está fuera de **** la organización, seleccione **Agregar condición** y, a continuación, seleccione **el destinatario es externo o interno** \> **fuera de la organización** \> .

8. Para habilitar el cifrado sin usar las nuevas funciones de OME, en **hacer lo siguiente**, seleccione **modificar la seguridad** \> **de mensajes aplique la versión anterior de OME**y, a continuación, elija **Guardar**.

  Si recibe un error que hace que las licencias de IRM no estén habilitadas, todavía no ha configurado OME para su organización. Si desea configurar OME ahora, debe configurarlo para usar las nuevas funciones de OME. Para obtener más información, consulte [configurar las nuevas capacidades de cifrado de mensajes de Office 365 basadas en Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft ya no admite la configuración de nuevas implementaciones de OME sin las nuevas funciones.

  Puede elegir **Agregar acción** si desea especificar otra acción.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Usar Exchange Online PowerShell para crear una regla de flujo de correo para cifrar mensajes de correo electrónico sin las nuevas funciones OME

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Cree una regla con el cmdlet **New-TransportRule** y establezca el parámetro _ApplyOME_ en `$true`.

   En este ejemplo, es necesario que todos los mensajes de correo electrónico enviados a DrToniRamos@hotmail.com se cifren.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **Notas**:

   - El nombre único de la nueva regla es "cifrar regla para recuperación ante desastres Toni Ramos".

   - El __ parámetro sentto especifica los destinatarios del mensaje (identificados por nombre, dirección de correo electrónico, nombre distintivo, etc.). En este ejemplo, el destinatario se identifica mediante la dirección de correo electrónico "DrToniRamos@hotmail.com".

   - El parámetro _SentToScope_ especifica la ubicación de los destinatarios del mensaje. En este ejemplo, el buzón de correo del destinatario está en hotmail y no forma parte de la organización de Office 365, `NotInOrganization` por lo que se usa el valor.

   Para obtener la sintaxis detallada e información sobre los parámetros, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas funciones OME

Cuando los usuarios de correo electrónico envían mensajes cifrados, los destinatarios de esos mensajes pueden responder con respuestas cifradas. Puede crear reglas de flujo de correo para quitar automáticamente el cifrado de las respuestas para que los usuarios de correo electrónico de la organización no tengan que iniciar sesión en el portal de cifrado para verlos. Puede usar el EAC o los cmdlets de Windows PowerShell para definir estas reglas. Si aún no usa las nuevas funciones OME, solo puede descifrar mensajes que se envían desde dentro de la organización o mensajes que son respuestas a los mensajes enviados desde dentro de la organización. No se pueden descifrar los mensajes cifrados que se originan fuera de la organización.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Usar el EAC para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas funciones de OME

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.

4. En el EAC, vaya a **** \> **reglas** de flujo de correo **** ![y seleccione nuevo](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> icono nuevo para **crear una nueva regla**. Para obtener más información acerca del uso de EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como quitar el cifrado del correo entrante.

6. En **aplicar esta regla si** selecciona las condiciones en las que se debe quitar el cifrado de los mensajes, como **el destinatario se encuentra** \> **dentro de la organización**.

7. En **hacer lo siguiente**, seleccione **modificar la seguridad** \> **de los mensajes Quite la versión anterior de OME**.

8. Seleccione **Guardar**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Usar Exchange Online PowerShell para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas funciones de OME

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Cree una regla con el cmdlet **New-TransportRule** y establezca el parámetro _RemoveOME_ en `$true`.

   En este ejemplo se quita el cifrado de todo el correo enviado a los destinatarios de la organización de Office 365.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **Notas**:

   - El nombre único de la nueva regla es "quitar el cifrado del correo entrante".

   - El parámetro _SentToScope_ especifica la ubicación de los destinatarios del mensaje. En este ejemplo, se usa `InOrganization` el valor Value, que indica lo siguiente:

     - El destinatario es un buzón, un usuario de correo, un grupo o una carpeta pública habilitada para correo en la organización.

       o

     - La dirección de correo electrónico del destinatario está en un dominio aceptado que está configurado como un dominio autoritativo o un dominio de retransmisión interno en su organización, _y_ el mensaje se ha enviado o recibido a través de una conexión autenticada.

Para obtener la sintaxis detallada e información sobre los parámetros, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

## <a name="related-topics"></a>Temas relacionados

[Cifrado en Office 365](encryption.md)

[Configurar las nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md)

[Agregar personalización de marca a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md)

[Reglas de flujo de correo (reglas de transporte) en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
