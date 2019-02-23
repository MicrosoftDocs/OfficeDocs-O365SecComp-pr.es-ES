---
title: Configurar las nuevas capacidades de cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: Nuevas capacidades de cifrado de mensajes de Office 365 basadas en Azure Information Protection, su organización puede usar la comunicación de correo electrónico protegida con personas de dentro y fuera de la organización. Las nuevas capacidades de OME funcionan con otras organizaciones de Office 365, Outlook.com, gmail y otros servicios de correo electrónico.
ms.openlocfilehash: eddafca15fa4efdd3f929145e7933a3b7dfb5f27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220650"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurar las nuevas capacidades de cifrado de mensajes de Office 365

Con las nuevas capacidades de cifrado de mensajes de Office 365 (OME), que aprovechan las características de protección de Azure Information Protection, su organización puede compartir fácilmente el correo electrónico protegido con cualquier persona en cualquier dispositivo. Los usuarios pueden enviar y recibir mensajes protegidos con otras organizaciones de Office 365, así como con clientes que no son de Office 365 con Outlook.com, gmail y otros servicios de correo electrónico.

||
|:-----|
|Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>Introducción a OME mediante la activación de Azure Rights Management, parte de Azure Information Protection

Ahora es fácil empezar a trabajar con las nuevas capacidades de OME. A partir del 2018 de febrero de 365, Office habilita automáticamente las nuevas capacidades de OME para las organizaciones elegibles dentro de nuestros centros de recursos. Su organización es elegible si es un nuevo inquilino de Office 365 y su organización tiene las suscripciones adecuadas. **Si ha habilitaDo Azure Rights Management (Azure RMS), parte de Azure Information Protection, se habilitará automáticamente el cifrado de mensajes de Office 365.** No tiene que hacer nada más para habilitar OME. Para activar Azure Rights Management, vea [Activar Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). Para obtener más información acerca de las suscripciones, vea "What suscripciones necesito use The New OME capabilities?" en el archivo de [preguntas más frecuentes sobre el cifrado de mensajes de Office 365](ome-faq.md). Para obtener información sobre cómo comprar una suscripción a Azure Information Protection, consulte [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).
  
Si usa Exchange Online con el servicio de administración de derechos de Active Directory (AD RMS), no puede habilitar estas nuevas funcionalidades inmediatamente. En su lugar, debe realizar la migración de AD RMS a Azure Information Protection en primer lugar. Una vez finalizada la migración, puede completar correctamente estos pasos.
  
Si opta por seguir usando AD RMS local con Exchange online en lugar de migrar a Azure Information Protection, no podrá usar estas nuevas funciones de.
  
## <a name="how-the-new-capabilities-for-ome-work"></a>Funcionamiento de las nuevas capacidades de OME

Las nuevas capacidades de cifrado de mensajes de Office 365 usan las capacidades de protección, también denominada Azure Rights Management (Azure RMS), de Azure Information Protection. Esto incluye directivas de cifrado, identidades y autorización para ayudar a proteger el correo electrónico. Puede cifrar mensajes mediante el uso de plantillas de Rights Management, la [opción](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)no reenviar y la [opción de solo cifrado](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). A continuación, los usuarios pueden cifrar los mensajes de correo electrónico y una gran variedad de datos adjuntos de Office 365 mediante estas opciones. Para obtener una lista completa de los tipos de datos adjuntos admitidos, consulte ["tipos de archivos cubiertos por las directivas de IRM cuando se adjuntan a mensajes" en Introducción a IRM para los mensajes de correo electrónico](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). Como administrador, también puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede definir una regla en la que todos los mensajes desprotegidos que se dirijan a un destinatario específico o que contengan palabras específicas en la línea de asunto estén protegidos contra el acceso no autorizado, y los destinatarios no podrán copiar ni imprimir el contenido del mensaje.
  
A diferencia de la versión anterior de OME, estas nuevas capacidades proporcionan una experiencia de remitente unificado, ya sea para enviar correo dentro de su organización o para destinatarios fuera de Office 365. Además, los destinatarios que reciben un mensaje de correo electrónico protegido que se envía a una cuenta de Office 365 en Outlook 2016 o en Outlook en la web no tienen que realizar ninguna acción adicional para ver el mensaje. Funciona sin problemas. Los destinatarios que usan otros clientes de correo electrónico y proveedores de servicios de correo electrónico también tienen una mejor experiencia. Para obtener más información, vea información [sobre los mensajes protegidos en Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) y [Cómo abrir un mensaje protegido](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Para obtener una lista detallada de las diferencias entre la versión anterior de OME y las nuevas capacidades de OME, vea [Compare Versions of OME](ome-version-comparison.md).
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>Pasos para configurar manualmente las nuevas funciones de OME

Las nuevas capacidades de OME se habilitan automáticamente para la mayoría de las organizaciones de Office 365. Si la organización no tiene instalado automáticamente OME o si ha desactivado las nuevas funciones de OME, siga estos pasos para configurar manualmente las nuevas funciones de OME.
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>Para configurar manualmente las nuevas funciones para OME

1. Asegúrese de que tiene la suscripción adecuada para su organización. Para obtener información acerca de las suscripciones, consulte "What suscripciones necesito use The New OME capabilities?" en el archivo de [preguntas más frecuentes sobre el cifrado de mensajes de Office 365.](ome-faq.md) Para obtener información sobre cómo comprar una suscripción a Azure Information Protection, consulte [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).

2. Decida si desea que Microsoft administre la clave raíz de Azure Information Protection (el valor predeterminado) o genere y administre esta clave usted mismo (conocido como BYOK). Si desea generar y administrar esta clave usted mismo, debe realizar algunos pasos antes de configurar las nuevas capacidades de OME. Para obtener más información, vea [planeación e implementación de la clave de inquilino de Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key). Microsoft recomienda que complete estos pasos antes de configurar OME.

3. Habilite las nuevas funciones para OME activando Azure Rights Management. Para obtener instrucciones, consulte [Activar Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). Al hacerlo, Office 365 automáticamente habilita las nuevas funciones de OME para usted.

    > [!TIP]
    > Outlook en la Web almacena en caché su interfaz de usuario, por lo que es una buena idea esperar un día antes de intentar aplicar las nuevas funciones de OME a los mensajes de correo electrónico mediante este cliente. Antes de que la interfaz de usuario se actualice para reflejar la nueva configuración, las nuevas funciones de OME no estarán disponibles. Una vez que se actualiza la interfaz de usuario, los usuarios pueden proteger los mensajes de correo electrónico con las nuevas funciones de OME.
  
4. Opcional Configure nuevas reglas de flujo de correo o actualice las reglas de flujo de correo existentes que definen cómo y cuándo desea que Office 365 Cifre los mensajes enviados desde su organización.

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>Comprobar que las nuevas capacidades para OME están configuradas correctamente mediante Windows PowerShell

Siga estos pasos para comprobar que el inquilino está configurado correctamente para usar las nuevas funciones de OME a través de PowerShell de Exchange Online.
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Ejecute el cmdlet test-IRMConfiguration con la siguiente sintaxis:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   Por ejemplo:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

    Donde email address es la dirección de correo electrónico de un usuario de su organización de Office 365. Si bien es opcional, al suministrar una dirección de correo electrónico del remitente, el sistema debe realizar comprobaciones adicionales. Los resultados deben tener el siguiente aspecto:

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

    Donde *contoso* es reemplazado por el nombre de su organización de Office 365.

    Los nombres de las plantillas predeterminadas que se devuelven en los resultados pueden ser diferentes de los mostrados en los resultados anteriores.

    Para obtener una introducción a las plantillas y la información sobre las plantillas predeterminadas, vea [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre la opción no reEnviar, la opción de solo cifrado y cómo crear plantillas adicionales, o averiguar qué derechos se incluyen en una plantilla existente, vea [Configuring Usage Rights for Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).

3. Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>Pasos siguientes: definir nuevas reglas de flujo de correo que usen las nuevas funciones de OME

Este paso es opcional para las implementaciones de OME nuevas; sin embargo, este paso es necesario para las implementaciones de OME existentes que ya tienen reglas de flujo de correo configuradas para cifrar el correo saliente. Si desea aprovechar las nuevas capacidades de OME, debe actualizar las reglas de flujo de correo existentes. De lo contrario, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior en lugar de la nueva experiencia de OME sin problemas.
  
Las reglas de flujo de correo determinan en qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar ese cifrado. Cuando se establece una acción para una regla, los mensajes que cumplan las condiciones de la regla se cifran cuando se envían.
  
Para obtener más información acerca de las reglas de flujo de correo, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Temas relacionados

[Enviar, ver y responder mensajes cifrados en Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[EnAble-Aadrm](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[Conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md)
