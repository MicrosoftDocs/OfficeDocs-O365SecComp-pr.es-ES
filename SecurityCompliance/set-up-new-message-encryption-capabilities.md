---
title: Configurar las nuevas capacidades de cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: Nuevo Office 365 Message Encryption capacidades fundamentan en protección de la información de Azure, su organización pueden usar protegida comunicación por correo electrónico con personas dentro y fuera de su organización. Las nuevas capacidades OME trabajar con otras organizaciones de Office 365, Outlook.com, Gmail y otros servicios de correo electrónico.
ms.openlocfilehash: a30054bf7b03a3e4fadf9a0e34537c682c10e217
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696254"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurar las nuevas capacidades de cifrado de mensajes de Office 365

Con las nuevas capacidades de Office 365 Message Encryption (OME), que aprovechen las características de protección de protección de la información de Azure, su organización puede compartir fácilmente correo electrónico protegido con cualquier usuario en cualquier dispositivo. Los usuarios pueden enviar y recibir mensajes protegidos con otras organizaciones de Office 365, así como los clientes que no sean Office 365 mediante Outlook.com, Gmail y otros servicios de correo electrónico.

||
|:-----|
|En este artículo es parte de una serie de artículos sobre Office 365 Message Encryption más grande. En este artículo está destinada a los administradores y profesionales de TI. Si sólo está buscando información en enviar o recibir un mensaje cifrado, vea la lista de los artículos de [Office 365 Message Encryption (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>Introducción a OME mediante la activación de Azure Rights Management, parte de la protección de la información de Azure

Ahora es fácil empezar a trabajar con las nuevas capacidades OME. A partir de febrero de 2018, Office 365 automáticamente permite que las nuevas capacidades OME para las organizaciones optan dentro de nuestros centros de datos. La organización es optan si es un nuevo inquilino de Office 365 y su organización tiene las suscripciones adecuadas. **Si ha habilitado Azure Rights Management (RMS Azure), parte de la protección de la información de Azure, a continuación, se permiten automáticamente el cifrado de mensajes de Office 365 para usted.** No tiene que hacer nada más para habilitar OME. Para activar Azure Rights Management, vea [Activar Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). Para obtener información acerca de las suscripciones, vea "¿qué suscripciones necesito para usar el nuevo capabilities? OME" en las [Preguntas más frecuentes sobre el cifrado de mensajes de Office 365](ome-faq.md). Para obtener información sobre la compra de una suscripción a la protección de la información de Azure, consulte [Protección de la información de Azure](https://azure.microsoft.com/services/information-protection/).
  
Si se usa Exchange Online con el servicio de administración de derechos de Active Directory (AD RMS), no se puede habilitar estas nuevas capacidades de inmediato. En su lugar, debe migrar desde AD RMS para protección de la información de Azure en primer lugar. Cuando haya terminado de la migración, puede completar los pasos.
  
Si opta por seguir utilizando local AD RMS con Exchange Online en lugar de migrar a la protección de la información de Azure, no podrá usar estas nuevas capacidades.
  
## <a name="how-the-new-capabilities-for-ome-work"></a>Cómo funcionan las nuevas capacidades para OME

Las nuevas capacidades de Office 365 Message Encryption usan las capacidades de protección, también denominadas Azure Rights Management (RMS Azure), de protección de la información de Azure. Esto incluye las directivas de cifrado, identidad y autorización para ayudar a proteger su correo electrónico. Puede cifrar los mensajes mediante el uso de las plantillas de administración de derechos, la [opción no reenviar](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)y la [opción de cifrar sólo](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). A continuación, los usuarios pueden cifrar mensajes de correo electrónico y una gran variedad de datos adjuntos de Office 365 mediante el uso de estas opciones. Para obtener una lista completa de tipos de datos adjuntos compatibles, vea ["tipos de archivo están cubiertas por las políticas de IRM cuando se adjuntan a los mensajes" en la introducción a IRM para mensajes de correo electrónico](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). Como administrador, también puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede definir una regla donde todos los mensajes no protegidos que se dirigen a un destinatario concreto o que contienen palabras específicas en la línea de asunto están protegidos contra el acceso no autorizado y los destinatarios no pueden copiar o imprimir el contenido del mensaje.
  
A diferencia de la versión anterior de OME, estas nuevas capacidades proporcionan una experiencia unificada remitente si va a enviar correo dentro de su organización o a destinatarios fuera de Office 365. Además, los destinatarios que reciben un mensaje de correo electrónico protegido enviado a una cuenta de Office 365 en 2016 de Outlook o Outlook en el sitio web, no tiene que realizar ninguna acción adicional para ver el mensaje. Funciona de manera transparente. Los destinatarios con otros clientes de correo electrónico y proveedores de servicios de correo electrónico también tienen una experiencia mejorada. Para obtener información, vea [sobre los mensajes protegidos en Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) y [cómo abrir un mensaje protegido](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Para obtener una lista detallada de las diferencias entre la versión anterior de OME y las nuevas capacidades OME, vea [Comparar versiones de OME](ome-version-comparison.md).
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>Pasos para configurar manualmente las nuevas capacidades para OME

Las nuevas capacidades OME se habilitan automáticamente para la mayoría de las organizaciones de Office 365. Si su organización no tiene OME habilitado automáticamente o si activa las nuevas capacidades OME desactivado, siga estos pasos para configurar manualmente las nuevas capacidades para OME.
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>Para configurar manualmente las nuevas capacidades para OME

1. Asegúrese de que tiene la suscripción adecuada para su organización. Para obtener información acerca de las suscripciones, consulte "¿qué suscripciones necesito para usar el nuevo capabilities? OME" en la [preguntas más frecuentes de Office 365 mensaje cifrado.](ome-faq.md). Para obtener información sobre la compra de una suscripción a la protección de la información de Azure, consulte [Protección de la información de Azure](https://azure.microsoft.com/services/information-protection/).

2. Decida si desea que Microsoft para administrar la clave de raíz para la protección de la información de Azure (valor predeterminado), o generar y administrar esta clave usted mismo (conocido como Traer su propia clave o BYOK). Si desea generar y administrar esta clave usted mismo, debe completar algunos pasos antes de configurar las nuevas capacidades para OME. Para obtener más información, vea [planeación y la implementación de la clave de inquilino de protección de la información de Azure](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key). Microsoft recomienda completar estos pasos antes de configurar OME.

3. Habilitar las nuevas capacidades para OME mediante la activación de Azure Rights Management. Para obtener instrucciones, vea [Activar Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). En este caso, Office 365 permite automáticamente las nuevas capacidades OME para usted.

    > [!TIP]
    > Outlook en la Web se almacena en caché su interfaz de usuario, por lo que es una buena idea que hay que esperar un día antes de intentar aplicar las nuevas capacidades para OME a los mensajes de correo electrónico con este cliente. Antes de la interfaz de usuario se actualiza para reflejar la nueva configuración, las nuevas capacidades para OME no estarán disponibles. Una vez que se actualiza la interfaz de usuario, los usuarios pueden proteger mensajes de correo electrónico mediante el uso de las nuevas capacidades para OME.
  
4. (Opcional) Configurar las reglas de flujo de correo nuevo o actualice reglas de flujo de correo existentes que definen cómo y cuándo desea que Office 365 para cifrar los mensajes enviados desde su organización.

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>Compruebe que las nuevas capacidades para OME están configuradas correctamente mediante el uso de Windows PowerShell

Siga estos pasos para comprobar que el inquilino está configurado correctamente para usar las nuevas capacidades para OME a través de Exchange Online PowerShell.
  
1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet Test-IRMConfiguration mediante la siguiente sintaxis:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   Por ejemplo:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

    Donde la dirección de correo electrónico es la dirección de correo electrónico de un usuario en la organización de Office 365. Mientras opcional, que se proporcione una dirección de correo electrónico del remitente fuerza al sistema a llevar a cabo comprobaciones adicionales. Los resultados de deben tener un aspecto como las siguientes:

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not 
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

    Donde *Contoso* se reemplaza con el nombre de la organización de Office 365.

    Los nombres de las plantillas predeterminadas que se devuelven en los resultados pueden ser diferentes de los que se muestran en los resultados anteriores.

    Para obtener una introducción a las plantillas e información acerca de las plantillas predeterminadas, vea [configuración y administración de plantillas para la protección de la información de Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información acerca de la no reenviar opción, la opción sólo para cifrar y cómo crear plantillas adicionales o averiguar qué derechos se incluyen en una plantilla existente, vea [configuración de derechos de uso de Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).

3. Ejecute el cmdlet Remove-PSSession para desconectarse del servicio de administración de derechos.
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>Pasos siguientes: definir nuevas reglas de flujo de correo que utilice las nuevas capacidades OME

Este paso es opcional para las nuevas implementaciones OME, sin embargo, este paso es necesario para las implementaciones de OME existentes que ya tienen las reglas de flujo de correo configuradas para cifrar el correo saliente. Si desea aprovechar las ventajas de las nuevas capacidades OME, debe actualizar las reglas de flujo de correo existente. De lo contrario, los usuarios seguirán recibir correo cifrado que usa el formato de los datos adjuntos HTML anterior en lugar de la experiencia OME nuevo, sin problemas.
  
Reglas de flujo de correo determinan en qué correo electrónico de condiciones deben cifrarse los mensajes, así como las condiciones para que el cifrado de quitar. Cuando se establece una acción para una regla, todos los mensajes que coincidan con las condiciones de regla se cifran cuando se envían.
  
Para obtener más información acerca de las reglas de flujo de correo, consulte [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Temas relacionados

[Enviar, ver y responder a los mensajes cifrados en Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[Habilitar Aadrm](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[Conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md)
