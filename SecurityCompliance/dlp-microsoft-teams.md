---
title: Prevención de pérdida de datos y Microsoft Teams
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Ahora puede aplicar directivas de DLP a chats y canales de Microsoft Teams. Lea este artículo para obtener más información sobre cómo funciona.
ms.openlocfilehash: 4edc05a2e0759884570239a038d0869e15240d17
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478229"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevención de pérdida de datos y Microsoft Teams
<!-- the note duplicates the first sentence of the overview, delete one or the other- -->

> [!NOTE]
> Las capacidades de prevención de pérdida de datos se han agregado recientemente a los mensajes de chat y de canal de Microsoft Teams para los usuarios con licencia de Office 365 Advanced Compliance, que está disponible como opción independiente y se incluye en Office 365 E5 y el cumplimiento de Microsoft 365 E5. Para obtener más información sobre los requisitos de licencia, consulte la [Guía de licencias de servicios en el nivel de inquilino de 365 de Microsoft](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Información general de DLP para Microsoft Teams

Recientemente, se ampliaron las capacidades de [prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP) para incluir los mensajes de chat y canales de Microsoft Teams. Si su organización tiene DLP, ahora puede definir directivas que impiden que los usuarios compartan información confidencial en una sesión de chat o de canal de Microsoft Teams. A continuación, se muestran algunos ejemplos de cómo funciona esta protección:

- **Ejemplo 1: proteger la información confidencial en los mensajes**. Suponga que alguien intenta compartir información confidencial en un canal o chat de Microsoft Teams con invitados (usuarios externos). Si tiene definida una directiva DLP para evitar esto, se eliminan los mensajes con información confidencial que se envían a los usuarios externos. Esto sucede automáticamente y en segundos, según la configuración de la Directiva DLP.

    > [!NOTE]
    > DLP para Microsoft Teams bloquea el contenido confidencial cuando se comparte con los usuarios de Microsoft teams que tienen:<br/>- [acceso de invitado](https://docs.microsoft.com/MicrosoftTeams/guest-access) en equipos y canales; o<br/>- [acceso externo](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) en reuniones y sesiones de chat. <p>La DLP para sesiones de chat externas solo funcionará si el remitente y el receptor están en modo de solo Teams y usan la [Federación nativa de Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access). DLP for Teams no bloquea mensajes en [](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) interoperabilidad con Skype empresarial o con sesiones de chat no nativas federadas.

- **Ejemplo 2: protección de información confidencial en documentos**. Suponga que alguien intenta compartir un documento con invitados en un canal o chat de Microsoft Teams, y que el documento contiene información confidencial. Si tiene definida una directiva DLP para evitar esto, el documento no se abrirá para esos usuarios. Tenga en cuenta que, en este caso, la Directiva DLP debe incluir SharePoint y OneDrive para que la protección esté en su ubicación. (Este es un ejemplo de DLP para SharePoint que se muestra en Microsoft Teams y, por lo tanto, requiere que los usuarios tengan licencia para Office 365 DLP (incluido en Office 365 E3), pero no requiere que los usuarios tengan licencia para Office 365 el cumplimiento avanzado.)

## <a name="policy-tips-help-educate-users"></a>Las sugerencias de directivas ayudan a los usuarios

De forma similar a cómo funciona DLP en [Exchange, Outlook, Outlook en la web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, sitios de OneDrive para la empresa](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)y [clientes de escritorio de Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), las sugerencias de directiva aparecen cuando una acción entra en conflicto con una directiva DLP. A continuación, se muestra un ejemplo de una sugerencia de directiva:

![Notificación de mensajes bloqueados en Microsoft Teams](media/dlp-teams-blockedmessage-notification.png)

En este caso, el remitente ha intentado compartir un número de la seguridad social en un canal de Microsoft Teams. El vínculo **¿Qué puedo hacer?** abre un cuadro de diálogo que proporciona opciones para que el remitente resuelva el problema. Observe que, en este caso, el remitente puede optar por invalidar la Directiva o notificar a un administrador que la revise y la resuelva.

![Opciones para resolver el mensaje bloqueado](media/dlp-teams-blockedmessage-possibleactions.png)

En su organización, puede optar por permitir que los usuarios invaliden una directiva DLP. Y, cuando configure las directivas de DLP, puede usar las sugerencias de directiva predeterminadas o [personalizar las sugerencias de directiva](#to-customize-policy-tips) para su organización. 

Volviendo a nuestro ejemplo, en el que un remitente compartió un número de la seguridad social en un canal de Teams, esto es lo que vio el destinatario:

![Mensaje bloqueado](media/dlp-teams-blockedmessage-notification-to-user.png)

El vínculo **¿Qué es esto?** abre un [artículo](data-loss-prevention-policies.md) sobre las directivas de DLP, que ayuda a explicar por qué se bloqueó el mensaje.

### <a name="to-customize-policy-tips"></a>Para personalizar las sugerencias de Directiva

Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas de DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al centro de cumplimiento de & de seguridad de[https://protection.office.com](https://protection.office.com)Office 365 () e inicie sesión.

2. Elija **** > **Directiva**de prevención de pérdida de datos. 

3. Seleccione una directiva y, junto a **configuración de directiva**, elija **Editar**.

4. Puede crear una nueva regla o editar una regla existente para la Directiva.<br/>![Edición de una regla para una directiva](media/dlp-teams-editrule.png)<br/>

5. En la pestaña notificaciones del **usuario** , seleccione **personalizar el texto del correo electrónico** o **personalizar las opciones de texto de la sugerencia de directiva** .<br/>![Personalizar las notificaciones de usuario y las sugerencias de Directiva](media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique el texto que desea usar para las notificaciones de correo electrónico o las sugerencias de directiva y, a continuación, elija **Guardar**. 

7. En la pestaña **configuración de directiva** , elija **Guardar**.

Espere aproximadamente una hora para que los cambios funcionen en el centro de datos y sincronicen las cuentas de usuario.
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Agregar Microsoft Teams como ubicación a las directivas de DLP existentes

Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas de DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al centro de cumplimiento de & de seguridad de[https://protection.office.com](https://protection.office.com)Office 365 () e inicie sesión.

2. Elija **** > **Directiva**de prevención de pérdida de datos. 

3. Seleccione una directiva y mire los valores en **ubicaciones**. Si ve **los mensajes de chat y de canal**de Microsoft Teams, ya está todo configurado. Si no lo hace, haga clic en **Editar**.<br/>![Ubicaciones para la directiva existente](media/dlp-teams-editexistingpolicy.png)<br/>

4. En la columna **Estado** , active la Directiva para **los mensajes de chat y de canal**de Microsoft Teams.<br/>![DLP para los chats y canales de Microsoft Teams](media/dlp-teams-addteamschatschannels.png)<br/>

5. Conserve la configuración predeterminada de todas las cuentas o especifique las cuentas que se van a incluir o excluir.

6. Haga clic en **Guardar **.

Espere aproximadamente una hora para que los cambios funcionen en el centro de datos y sincronicen las cuentas de usuario.
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definir una nueva Directiva de DLP para Microsoft Teams

Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas de DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al centro de cumplimiento de & de seguridad de[https://protection.office.com](https://protection.office.com)Office 365 () e inicie sesión.

2. Elegir **** > **** directiva > **de prevención de pérdida de datos + crear una directiva**. 

3. Elija una [plantilla](data-loss-prevention-policies.md#dlp-policy-templates)y, a continuación, elija **siguiente**.<br/>En nuestro ejemplo, elegimos la plantilla de datos de información de identificación personal de Estados Unidos.<br/>![Plantilla de privacidad para la Directiva DLP](media/dlp-teams-createnewpolicy-template.png)<br/>

4. En la pestaña Nombre de la **Directiva** , especifique un nombre y una descripción para la Directiva y, a continuación, elija **siguiente**. 

5. En la pestaña **elegir ubicaciones** , mantenga la configuración predeterminada de todas las ubicaciones o seleccione **permitirme elegir ubicaciones específicas**y, después, haga clic en **siguiente**.<br/>Si ha elegido ubicaciones específicas, selecciónelas para su Directiva DLP y, a continuación, elija **siguiente**.<br/>![Ubicaciones de directivas de DLP](media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > Si desea asegurarse de que los documentos que contienen información confidencial no se compartan de manera inadecuada, asegúrese de que los **sitios de SharePoint** y **las cuentas de OneDrive** estén activados, junto con **los mensajes de chat y de canal**de Teams.
<br/>

6. En la **pestaña Configuración de directiva** , en **personalizar el tipo de contenido que quiere proteger**, mantenga la configuración sencilla predeterminada o elija **Usar configuración avanzada**y, a continuación, elija **siguiente**. Si elige la configuración avanzada, puede crear o editar reglas para la Directiva. (Para obtener ayuda, consulte [Configuración sencilla frente a configuración avanzada](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)).

7.  En la pestaña **configuración de directiva** , en **¿qué desea hacer si se detecta información confidencial?**, revise la configuración. (Aquí puede elegir mantener las [sugerencias de directiva y notificaciones de correo electrónico](use-notifications-and-policy-tips.md)predeterminadas o personalizarlas).<br/>![Configuración de directivas de DLP con sugerencias y notificaciones](media/dlp-teams-policysettings-tipsemails.png)<br/>Cuando haya terminado de revisar o editar la configuración, elija **siguiente**.

8. En la **pestaña Configuración de directiva** , en **¿desea activar la Directiva o probar la primera?**, elija si desea activar la Directiva, [probarla primero](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)o dejarla desactivada por ahora y, a continuación, elija **siguiente**.<br/>![Especificar si se va a activar la Directiva](media/dlp-teams-policysettings-turnonnow.png)<br/>

9. En la pestaña **revisar la configuración** , revise la configuración de la nueva Directiva. Elija **Editar** para realizar cambios. Cuando haya terminado, elija **crear**. 

Espere aproximadamente una hora para que la nueva Directiva funcione a través del centro de datos y sincronice las cuentas de usuario.

## <a name="related-articles"></a>Artículos relacionados

[Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)

[Enviar notificaciones de email y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
