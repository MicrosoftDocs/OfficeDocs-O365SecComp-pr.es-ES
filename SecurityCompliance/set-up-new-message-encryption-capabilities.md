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
ms.openlocfilehash: fd237e537aa1ff961d2d975b3b30f4a51744ba7c
ms.sourcegitcommit: e24f70699021c4f4ba56508ad0afb6f65010c357
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2019
ms.locfileid: "31479656"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurar las nuevas capacidades de cifrado de mensajes de Office 365

Las nuevas capacidades de cifrado de mensajes (OME) de Office 365 permiten que las organizaciones compartan correo electrónico protegido con cualquier usuario en cualquier dispositivo. Los usuarios pueden intercambiar mensajes protegidos con otras organizaciones de Office 365, así como con clientes que no son de Office 365 con Outlook.com, gmail y otros servicios de correo electrónico.


>[!NOTE]
>Este artículo está dirigido a administradores y profesionales de ti. Si es un usuario final, consulte la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) para obtener soluciones adecuadas.

Siga los pasos a continuación para asegurarse de que las nuevas capacidades de OME estén disponibles en su inquilino de Office 365.

## <a name="verify-azure-rights-management-arm-is-active"></a>Compruebe que Azure Rights Management (ARM) esté activo

>[!NOTE]
>Las nuevas capacidades de OME aprovechan las características de protección de [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), la tecnología usada por [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).

El único requisito previo para usar las nuevas capacidades de OME es que [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) debe activarse en el inquilino de Office 365. Si es así, Office 365 activa automáticamente las nuevas funciones de OME y no es necesario realizar ninguna acción.

La ARM también se activa automáticamente en la mayoría de los planes elegibles, por lo que es probable que no tenga que hacer nada en este sentido. Vea [Activar Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) para obtener más.

>[!IMPORTANT]
>Si usa Active Directory Rights Management Service (AD RMS) con Exchange Online, debe [migrar a Azure Information Protection para](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) poder usar las nuevas funcionalidades de OME. AD RMS no es compatible con ARM.  

Para obtener más información, consulte:

- [¿Qué suscripciones necesito para usar las nuevas capacidades de OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) para comprobar si el plan de suscripción incluye Azure Information Protection (que incluye ARM).
- [Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) para obtener información sobre cómo comprar una suscripción elegible.  

### <a name="manually-activating-arm"></a>Activar manualmente la ARM

Si ha deshabilitado la ARM o si no se activó automáticamente por algún motivo, puede activarla manualmente en:

- **Centro de administración de office 365**: vea [Cómo activar Azure Rights Management desde el centro de administración de Office 365](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) para obtener instrucciones.
- **Portal de Azure**: vea [Cómo activar Azure Rights Management desde Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) para obtener instrucciones.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Configurar la administración de la clave de inquilino de Azure Information Protection

Este es un paso opcional. Permitir que Microsoft administre la clave raíz para Azure Information Protection es la configuración predeterminada y la mejor práctica recomendada para la mayoría de los inquilinos de Office 365. Si este es el caso, no es necesario realizar ninguna acción.

Hay muchas razones, por ejemplo, para los requisitos de cumplimiento, que pueden requerir que genere y administre su propia clave raíz (también denominada traer su propia clave (BYOK)). Si este es el caso, le recomendamos que complete los pasos necesarios antes de configurar las nuevas funciones de OME. Consulte [planeación e implementación de la clave de inquilino de Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) para obtener más información.

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Comprobar la nueva configuración de OME en Exchange Online PowerShell

Puede comprobar que el inquilino de Office 365 está configurado correctamente para usar las nuevas funciones de OME en [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
  
1. [Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su inquilino de Office 365.

2. Ejecute el cmdlet test-IRMConfiguration con la siguiente sintaxis:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Ejemplo**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - La inclusión de un correo electrónico de remitente es opcional, pero obliga al sistema a realizar comprobaciones adicionales. Use la dirección de correo electrónico de cualquier usuario en el inquilino de Office 365. 

     Los resultados deben ser similares a:

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

   - El nombre de su organización de Office 365 reemplazará a *contoso*.

   - Los nombres de plantilla predeterminados pueden ser diferentes de los mostrados anteriormente. Consulte [configurar y administrar plantillas para Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) para obtener más información.

3. Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a>Actualizar las reglas de flujo de correo para usar las nuevas funciones de OME

Si ya hay reglas de flujo de correo configuradas [para cifrar el correo electrónico](define-mail-flow-rules-to-encrypt-email.md) en el inquilino de Office 365, debe actualizar estas reglas existentes para usar las nuevas funciones de OME. En el caso de implementaciones nuevas, este paso no es necesario en esta fase.   

>[!Note]
>Las reglas de flujo de correo definen las condiciones en las que se cifran los mensajes de correo electrónico y cuándo debe quitarse el cifrado. Consulte [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md) para obtener más información.

Para actualizar las reglas existentes para usar las nuevas capacidades de OME:

1. En el centro de administración de Office 365, vaya a **centros de administración _GT_ Exchange**.

2. En el centro de administración de Exchange, vaya a **reglas de flujo de correo >**. 
3. Para cada regla, en **hacer lo siguiente**:
    - Seleccione **modificar la seguridad de los mensajes**.
    - Seleccione **aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.
    - Seleccione una plantilla RMS de la lista.
    - Seleccione **Guardar**.
    - Seleccione **Aceptar**.
  
>[!IMPORTANT]
>Si no actualiza las reglas de flujo de correo existentes, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior, en lugar de las nuevas funcionalidades de OME.
