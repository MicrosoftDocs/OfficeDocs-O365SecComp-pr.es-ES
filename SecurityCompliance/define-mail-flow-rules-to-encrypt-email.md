---
title: Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: Como administrador global de Office 365, puede crear reglas para habilitar el cifrado de mensajes de Office 365 (OME) de flujo de correo. Puede cifrar los mensajes de correo electrónico saliente y quitar el cifrado de mensajes internos o de las respuestas a los mensajes cifrados enviados desde su organización.
ms.openlocfilehash: 06668f29e69c885adb8c67d723efe42b4a4aa166
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535859"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365

Como administrador global de Office 365, puede crear reglas de flujo de correo, también conocida como reglas de transporte, para ayudar a proteger los mensajes de correo electrónico se envían y reciben. Puede configurar reglas para cifrar los mensajes de correo electrónico saliente y quitar el cifrado de mensajes cifrados procedentes de su organización o de las respuestas a los mensajes cifrados enviados desde su organización. Puede usar el centro de administración de Exchange (EAC) o los cmdlets de Windows PowerShell para Exchange Online para crear estas reglas. Además de las reglas de cifrado global, también puede elegir habilitar o deshabilitar las opciones de cifrado de mensajes individuales para los usuarios finales.
  
Si recientemente migrado desde AD RMS para protección de la información de Azure, debe revisar las reglas de flujo de correo existentes para asegurarse de que siguen funcionando en el nuevo entorno. Además, si desea aprovechar las ventajas de las nuevas capacidades de Office 365 Message Encryption (OME) disponibles para usted a través de la protección de la información de Azure, debe actualizar las reglas de flujo de correo existente. De lo contrario, los usuarios seguirán recibir correo cifrado que usa el formato de los datos adjuntos HTML anterior en lugar de la experiencia OME nuevo, sin problemas. Si no ha configurado OME aún, consulte [Set up nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure](set-up-new-message-encryption-capabilities.md) para obtener información. 
  
Para obtener información acerca de los componentes que componen las reglas de flujo de correo y cómo de las reglas de flujo de correo, consulte [(reglas de transporte) de reglas de flujo de correo en Exchange Online](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx). Para obtener información adicional acerca de cómo funcionan las reglas de flujo de correo con Azure protección de la información, vea [configuración de Exchange Online reglas de flujo de correo para las etiquetas de protección de la información de Azure](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).
  
## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Crear una regla de flujo de correo para cifrar mensajes de correo electrónico con las nuevas capacidades OME

Puede definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas capacidades OME mediante el EAC.
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a>Para crear una regla para cifrar los mensajes de correo electrónico con las nuevas capacidades OME desde el EAC

1. En un explorador web, usando una cuenta de trabajo o escuela que se ha concedido permisos de administrador global, [iniciar sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).
    
2. Elija el icono de **administración** . 
    
3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.
    
4. En el EAC, vaya a **flujo de correo** \> **reglas** \> ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ( **nuevo**) \> **crear una nueva regla**. Para obtener más información sobre cómo usar el CEF, vea el [Centro de administración de Exchange en Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).
    
5. En **nombre**, escriba un nombre para la regla, como Encrypt mail for DrToniRamos@hotmail.com.
    
6. En **Aplicar esta regla si** seleccione una condición y especifique un valor si es necesario. Por ejemplo, para cifrar los mensajes que se dirigen a DrToniRamos@hotmail.com: 
    
    1. En **Aplicar esta regla si**, seleccione **el destinatario es**.
    
    2. Seleccione un nombre existente en la lista de contactos o escriba una nueva dirección de correo electrónico en el cuadro **Comprobar nombres**. 
    
        Para seleccionar un nombre existente, selecciónelo en la lista y, a continuación, haga clic en **Aceptar**.
    
        Para escribir un nuevo nombre, escriba una dirección de correo electrónico en el cuadro **Comprobar nombres** y, a continuación, seleccione **Comprobar nombres** \> **Aceptar**.
    
7. Para agregar más condiciones, elija **más opciones** y, a continuación, elija **Agregar condición** y seleccione de la lista. 
    
    Por ejemplo, para aplicar la regla sólo si el destinatario está fuera de su organización, seleccione **Agregar condición** y, a continuación, seleccione **el destinatario es interna y externa** \> **fuera de la organización** \> **Aceptar**.
    
8. Para habilitar el cifrado mediante las nuevas capacidades OME, de **hacer lo siguiente**, seleccione **modificar la seguridad de los mensajes** y, a continuación, elija **aplicar el cifrado de mensajes de Office 365 y protección de derechos**. Seleccione una plantilla de RMS en la lista, elija **Guardar**y, a continuación, elija **Aceptar**.
    
    La lista de plantillas incluye todas las plantillas predeterminadas y opciones, así como las plantillas personalizadas que ha creado para utilizan por Office 365. Si la lista está vacía, asegúrese de que ha configurado el cifrado de mensajes de Office 365 con las nuevas capacidades como se describe en [Configurar nuevas capacidades de Office 365 Message Encryption integradas en la parte superior de la protección de la información de Azure](set-up-new-message-encryption-capabilities.md). Para obtener información acerca de las plantillas predeterminadas, vea [configuración y administración de plantillas para la protección de la información de Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información acerca de la opción **No reenviar** , vea [no reenviar una opción para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información acerca de la opción de **cifrar sólo** , vea [cifrar sólo una opción para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).
    
    Puede elegir **Agregar acción** si desea especificar otra acción. 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a>Para actualizar una regla de flujo de correo existente para usar las nuevas capacidades OME desde el EAC

1. En un explorador web, usando una cuenta de trabajo o escuela que se ha concedido permisos de administrador global, [iniciar sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).
    
2. Elija el icono de **administración** . 
    
3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.
    
4. En el EAC, vaya a **flujo de correo** \> **reglas**.
    
5. En la lista de reglas de flujo de correo, seleccione la regla que desea modificar para usar las nuevas capacidades OME y, a continuación, elija ![icono Editar](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ( **Editar**).
    
6. Para habilitar el cifrado mediante las nuevas capacidades OME, de **hacer lo siguiente**, seleccione **modificar la seguridad de los mensajes** y, a continuación, elija **aplicar el cifrado de mensajes de Office 365 y protección de derechos**. Seleccione una plantilla de RMS en la lista, elija **Guardar** y, a continuación, elija **Aceptar**.
    
    La lista de plantillas incluye todas las plantillas predeterminadas y opciones, así como las plantillas personalizadas que ha creado para utilizan por Office 365. Si la lista está vacía, asegúrese de que ha configurado el cifrado de mensajes de Office 365 con las nuevas capacidades como se describe en [Configurar nuevas capacidades de Office 365 Message Encryption integradas en la parte superior de la protección de la información de Azure](set-up-new-message-encryption-capabilities.md). Para obtener información acerca de las plantillas predeterminadas, vea [configuración y administración de plantillas para la protección de la información de Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información acerca de la opción **No reenviar** , vea [no reenviar una opción para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información acerca de la opción de **cifrar sólo** , vea [cifrar sólo una opción para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).
    
    Puede elegir **Agregar acción** si desea especificar otra acción. 
    
7. En la lista **haga lo siguiente** , quitar todas las acciones que se asignan a **modificar la seguridad de los mensajes** \> **aplicar la versión anterior de OME**.
    
8. Elija **Guardar**.
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Creación de reglas de cifrado de mensajes de Office 365 sin las nuevas capacidades

Si aún no se ha desplazado la organización de Office 365 para las nuevas capacidades OME, utilice estos procedimientos para definir las reglas de flujo de correo para cifrar los mensajes para su organización. Microsoft recomienda que realice un plan para mover a las nuevas capacidades OME tan pronto como es razonable para la organización. Para obtener instrucciones, vea [Configurar nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure](set-up-new-message-encryption-capabilities.md).
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a>Para crear una regla para cifrar los mensajes de correo electrónico sin las nuevas capacidades OME desde el EAC

1. En un explorador web, usando una cuenta de trabajo o escuela que se ha concedido permisos de administrador global, [iniciar sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).
    
2. Elija el icono de **administración** . 
    
3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.
    
4. En el EAC, vaya a **flujo de correo** \> **reglas** \> **+** ( **nuevo**) \> **crear una nueva regla**. Para obtener más información sobre cómo usar el CEF, vea el [Centro de administración de Exchange en Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).
    
5. En **nombre**, escriba un nombre para la regla, como Encrypt mail for DrToniRamos@hotmail.com.
    
6. En **Aplicar esta regla si** seleccione una condición y especifique un valor si es necesario. Por ejemplo, para cifrar los mensajes que se dirigen a DrToniRamos@hotmail.com: 
    
1. En **Aplicar esta regla si**, seleccione **el destinatario es**.
    
2. Seleccione un nombre existente en la lista de contactos o escriba una nueva dirección de correo electrónico en el cuadro **Comprobar nombres**. 
    
    Para seleccionar un nombre existente, selecciónelo en la lista y, a continuación, haga clic en **Aceptar**.
    
    Para escribir un nuevo nombre, escriba una dirección de correo electrónico en el cuadro **Comprobar nombres** y, a continuación, seleccione **Comprobar nombres** \> **Aceptar**.
    
7. Para agregar más condiciones, elija **más opciones** y, a continuación, seleccione **Agregar condición** y seleccione de la lista. 
    
    Por ejemplo, para aplicar la regla sólo si el destinatario está fuera de su organización, seleccione **Agregar condición** y, a continuación, seleccione **el destinatario es interna y externa** \> **fuera de la organización** \> **Aceptar**.
    
8. Para habilitar el cifrado sin usar las nuevas capacidades OME, en **hacer lo siguiente**, seleccione **modificar la seguridad de los mensajes** \> **aplicar la versión anterior de OME**y, a continuación, elija **Guardar**.
    
    Si recibe un error que IRM licencias no está habilitada, a continuación, no ha configurado OME para su organización todavía. Si desea configurar ahora OME, debe configurar para usar las nuevas capacidades OME. Para obtener información, vea [Configurar nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure](set-up-new-message-encryption-capabilities.md). Microsoft ya no admite la configuración de las nuevas implementaciones de OME sin las nuevas capacidades.
    
    Puede elegir **Agregar acción** si desea especificar otra acción. 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>Para crear una regla para cifrar los mensajes de correo electrónico sin las nuevas capacidades OME mediante el uso de Windows PowerShell para Exchange Online

1. Usar Windows PowerShell en el equipo local para crear una sesión remota de PowerShell para Exchange Online. Para obtener más información, vea [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).
    
2. Definir una regla mediante el cmdlet **New-TransportRule** y establezca el atributo **ApplyOME** en **true**.
    
    Por ejemplo, para requerir que se deben cifrar todos los mensajes de correo electrónico que se dirigen a DrToniRamos@hotmail.com, escriba:
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    En este ejemplo:
    
  - El nombre de la nueva regla es "Cifrar regla para recuperación ante desastres Toni Ramos".
    
  - El parámetro **- SentTo** , especifica una condición que tiene el aspecto de los destinatarios de mensajes de correo electrónico. Puede usar cualquier valor que identifica de forma exclusiva el destinatario, como una dirección de correo electrónico, el nombre, el nombre distintivo (DN), etcetera. En este ejemplo, el destinatario es identificado por la dirección de correo electrónico "DrToniRamos@hotmail.com". 
    
  - El parámetro **- SentToScope** especifica una condición que busca la ubicación de los destinatarios. En este ejemplo, el buzón del destinatario está en hotmail y no forma parte de la organización de Office 365, por lo que se usa el valor de "NotInOrganization". 
    
    Para obtener más información acerca de las condiciones en que puede establecer en las reglas de flujo de correo con este cmdlet, vea [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas capacidades OME

Cuando los usuarios de correo electrónico envían mensajes cifrados, los destinatarios de los mensajes pueden responder con respuestas cifradas. Puede crear reglas de flujo para quitar automáticamente el cifrado de las respuestas para que usuarios de correo electrónico de la organización no tengan que iniciar sesión en el portal de cifrado para verlas correo. Puede usar los cmdlets de Windows PowerShell o de CEF para definir estas reglas. Si todavía no utiliza las nuevas capacidades OME, sólo puede descifrar los mensajes que se envía desde dentro de su organización o los mensajes que son respuestas a los mensajes enviados desde dentro de la organización. No se puede descifrar los mensajes cifrados que se originan desde fuera de la organización.
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a>Para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas capacidades OME desde el EAC
<a name="DecryptruleEACNoNewOME"> </a>

1. En un explorador web, con una cuenta de trabajo o escuela que se ha concedido permisos de administrador, [iniciar sesión en Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).
    
2. Elija el icono de **administración** . 
    
3. En el Centro de administración de Office 365, elija **Centros de administración** \> **Exchange**.
    
4. En el EAC, vaya a **flujo de correo** \> **reglas** \> **+** ( **nuevo**) \> **crear una nueva regla**. Para obtener más información sobre cómo usar el CEF, vea el [Centro de administración de Exchange en Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx).
    
5. En **nombre**, escriba un nombre para la regla, como quitar el cifrado de correo entrante.
    
6. En **aplicar esta regla si** , seleccione las condiciones donde se debe quitar el cifrado de mensajes, como **el destinatario está ubicado** \> **dentro de la organización**.
    
7. En **hacer lo siguiente**, seleccione **modificar la seguridad de los mensajes** \> **quitar la versión anterior de OME**.
    
8. Seleccione **Guardar**.
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>Para crear una regla para quitar el cifrado de las respuestas de correo electrónico cifradas sin las nuevas capacidades OME mediante el uso de Windows PowerShell para Exchange Online
<a name="DecryptrulePShellNoNewOME"> </a>

1. Usar Windows PowerShell en el equipo local para crear una sesión remota de PowerShell para Exchange Online. Para obtener más información, vea [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).
    
2. Definir una regla mediante el cmdlet **New-TransportRule** y establezca el atributo **RemoveOME** en **true**.
    
    Por ejemplo, para quitar el cifrado de todo el correo enviado a los destinatarios de la organización de Office 365, escriba:
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    En este ejemplo:
    
  - El nombre de la nueva regla es "Quitar el cifrado de correo entrante".
    
  - El parámetro **- SentToScope** especifica una condición que busca la ubicación de los destinatarios. En este ejemplo, se usa el valor de "InOrganization" que indica que: 
    
  - El destinatario es un buzón de correo, usuario de correo, grupo o carpeta pública habilitada para correo en la organización, o
    
  - La dirección de correo electrónico del destinatario pertenece a un dominio aceptado que se configura como dominio autoritario o como dominio de retransmisión interna y el mensaje se envió o recibió por una conexión autenticada.
    
    Para obtener más información acerca de las condiciones en que puede establecer en las reglas de flujo de correo con este cmdlet, vea [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).
    
## <a name="related-topics"></a>Temas relacionados

[Cifrado en Office 365](encryption.md)
  
[Configurar nuevas capacidades de Office 365 Message Encryption fundamentan en protección de la información de Azure](set-up-new-message-encryption-capabilities.md)
  
[Agregar personalización de marca a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md)
  
[Reglas de flujo de correo (reglas de transporte) en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[Reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  

