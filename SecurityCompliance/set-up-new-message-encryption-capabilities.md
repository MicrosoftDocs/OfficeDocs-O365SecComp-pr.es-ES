---
title: Configurar las nuevas capacidades de cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Con las nuevas capacidades de cifrado de mensajes de Office 365 creadas con base en Azure Information Protection, su organización puede usar la comunicación por correo electrónico protegida con personas de dentro y fuera de la organización. Las nuevas funcionalidades de OME funcionan con otras organizaciones de Office 365, Outlook.com, Gmail y otros servicios de correo electrónico.
ms.openlocfilehash: 835b1d6f40868684536dbea8f75dab0665950210
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854804"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurar las nuevas capacidades de cifrado de mensajes de Office 365

Las nuevas funcionalidades de cifrado de mensajes de Office 365 (OME) permiten que las organizaciones compartan mensajes de correo electrónico protegidos con cualquier persona en cualquier dispositivo. Los usuarios pueden intercambiar mensajes protegidos con otras organizaciones de Office 365, así como con clientes que no son parte de Office 365 pero que usan Outlook.com, Gmail y otros servicios de correo electrónico.

||
|:-----|
|Este artículo forma parte de una gran serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a administradores y profesionales de TI. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en [Cifrado de mensajes de Office 365 (OME)](ome.md) y localice el artículo que mejor se adapta a sus necesidades. |
||

Siga los pasos que se indican a continuación para asegurarse de que las nuevas funcionalidades de OME estén disponibles en su organización 365 de Office.

## <a name="verify-that-azure-rights-management-is-active"></a>Verificar que Azure Rights Management está habilitada

Las nuevas funcionalidades de OME aprovechan las características de protección de [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-information-protection), la tecnología usada por [Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-azure-rms) para proteger los correos electrónicos y los documentos mediante controles de acceso y encriptación.

El único requisito previo para usar las nuevas funcionalidades de OME es que la funcionalidad [Azure Rights Management](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-azure-rms) debe estar activada en el espacio empresarial de su organización. Si lo está, Office 365 activa automáticamente las nuevas funcionalidades de OME y no es necesario realizar ninguna acción.

Azure RMS también se activa automáticamente en la mayoría de los planes compatibles, por lo que probablemente tampoco tendrá que hacer nada al respecto. Vea [Activar Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) para obtener más información.

>[!IMPORTANT]
>Si usa los servicios de Active Directory Rights Management (AD RMS) con Exchange Online, tendrá que [migrar a Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/migrate-from-ad-rms-to-azure-rms) antes de poder usar las nuevas funcionalidades de OME. OME no es compatible con AD RMS.  

Para obtener más información, vea:

- [¿Qué suscripciones necesito para usar las nuevas funcionalidades de OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) para comprobar si el plan de suscripción incluye Azure Information Protection (que incluye la funcionalidad de Azure RMS).
- [Azure Information Protection](https://azure.microsoft.com/es-ES/services/information-protection/) para obtener información sobre cómo comprar una suscripción apta.  

### <a name="manually-activating-azure-rights-management"></a>Activar Azure Rights Management manualmente

Si deshabilitó Azure RMS, o si no se activó automáticamente por algún motivo, puede activarlo manualmente en:

- **El Centro de administración de Microsoft 365**: vea [Cómo activar Azure Rights Management desde el centro de administración](https://docs.microsoft.com/es-ES/azure/information-protection/activate-office365) para obtener instrucciones.
- **Azure Portal**: vea [Cómo activar Azure Rights Management desde Azure Portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) para obtener instrucciones.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Configurar la administración del espacio empresarial de Azure Information Protection

Este paso es opcional. Permitir que Microsoft administre la clave raíz de Azure Information Protection es la configuración predeterminada y el procedimiento recomendado para la mayoría de los espacios empresariales de Office 365. Si este es el caso, no es necesario que realice ninguna acción.

Hay muchos motivos, por ejemplo, los requisitos de cumplimiento, que pueden requerir la creación y administración de su propia clave raíz (también conocido como Bring your own key (BYOK)). Si este es el caso, le recomendamos que complete los pasos requeridos antes de configurar las nuevas funcionalidades de OME. Vea [Planificar e implementar la clave de espacio empresarial de Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) para obtener más información.

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Comprobar la nueva configuración de OME en PowerShell de Exchange Online

Puede comprobar que su espacio empresarial de Office 365 está configurado correctamente para usar las nuevas funcionalidades de OME en [Exchange Online PowerShell](https://docs.microsoft.com/es-ES/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
  
1. [Conectarse a Exchange Online PowerShell](https://docs.microsoft.com/es-ES/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su espacio empresarial de Office 365.

2. Ejecute el cmdlet Get-IRMConfiguration.

     Debería ver un valor $True para el parámetro AzureRMSLicensingEnabled, el cuál indica que OME está configurado en su espacio empresarial. Si no lo está, utilice set-IRMConfiguration para establecer el valor de AzureRMSLicensingEnabled en $True para habilitar OME.

3. Ejecute el cmdlet test-IRMConfiguration usando la siguiente sintaxis:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Ejemplo**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - Proporcionar un correo electrónico del remitente es opcional, pero obliga al sistema a ejecutar comprobaciones adicionales. Use la dirección de correo electrónico de cualquier usuario de su espacio empresarial de Office 365.

     Sus resultados deben ser similares a estos:

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

   - El nombre de su organización de Office 365 reemplazará a *Contoso*.

   - Los nombres de las plantillas predeterminadas pueden diferir de los que se muestran arriba. Vea [Configurar y administrar plantillas para Azure Information Protection](https://docs.microsoft.com/es-ES/azure/information-protection/configure-policy-templates) para obtener más información.

4. Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Pasos siguientes: defina reglas de flujo de correo para usar las nuevas funcionalidades de OME

Si existen reglas de flujo de correo configuradas previamente para cifrar el correo electrónico de su organización de Office 365, debe actualizar las reglas existentes para usar las nuevas funcionalidades de OME. Para las nuevas implementaciones, debe crear nuevas reglas de flujo de correo.

>[!IMPORTANT]
>Si no actualiza las reglas de flujo de correo existentes, los usuarios seguirán recibiendo correo cifrado con el formato de archivo adjunto HTML anterior, en lugar de la nueva experiencia de OME de conexión directa.

Las reglas de flujo de correo determinan bajo qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar ese cifrado. Al establecer una acción para una regla, todos los mensajes que coinciden con las condiciones de la regla se cifran al enviarse.
  
Para conocer los pasos para crear reglas de flujo de correo para OME, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

Para actualizar las reglas existentes para poder usar las nuevas funcionalidades de OME:

1. En el centro de administración de Microsoft 365, vaya a **Centros de administración > Exchange**.
2. En el centro de administración de Exchange, vaya a **Flujo de correo > Reglas**.
3. Para cada regla, en **Hacer lo siguiente**:
    - Seleccione **Modificar la seguridad de los mensajes**.
    - Seleccione **Aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.
    - Seleccione una plantilla RMS de la lista.
    - Seleccione **Guardar**.
    - Seleccione **Aceptar**.
