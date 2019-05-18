---
title: Configurar las nuevas capacidades de cifrado de mensajes de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Nuevas capacidades de cifrado de mensajes de Office 365 basadas en Azure Information Protection, su organización puede usar la comunicación de correo electrónico protegida con personas de dentro y fuera de la organización. Las nuevas capacidades de OME funcionan con otras organizaciones de Office 365, Outlook.com, gmail y otros servicios de correo electrónico.
ms.openlocfilehash: 415e598a28033271b115aff639fb1ddd7a6345af
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156512"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurar las nuevas capacidades de cifrado de mensajes de Office 365

Las nuevas capacidades de cifrado de mensajes (OME) de Office 365 permiten que las organizaciones compartan correo electrónico protegido con cualquier usuario en cualquier dispositivo. Los usuarios pueden intercambiar mensajes protegidos con otras organizaciones de Office 365, así como con clientes que no son de Office 365 con Outlook.com, gmail y otros servicios de correo electrónico.

||
|:-----|
|Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está dirigido a administradores y profesionales de ti. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

Siga los pasos a continuación para asegurarse de que las nuevas capacidades de OME estén disponibles en su organización de Office 365.

## <a name="verify-that-azure-rights-management-is-active"></a>Comprobar que Azure Rights Management está activo

Las nuevas funciones de OME aprovechan las características de protección de [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), la tecnología que usa [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) para proteger los correos electrónicos y documentos a través de los controles de acceso y cifrado.

El único requisito previo para usar las nuevas capacidades de OME es que [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) debe estar activado en el espacio empresarial de la organización. Si es así, Office 365 activa automáticamente las nuevas funciones de OME y no es necesario realizar ninguna acción.

Azure RMS también se activa automáticamente en la mayoría de los planes elegibles, por lo que es probable que no tenga que hacer nada en este sentido. Vea [Activar Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) para obtener más información.

>[!IMPORTANT]
>Si usa Active Directory Rights Management Service (AD RMS) con Exchange Online, debe [migrar a Azure Information Protection para](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) poder usar las nuevas funcionalidades de OME. OME no es compatible con AD RMS.  

Para obtener más información, vea:

- [¿Qué suscripciones necesito para usar las nuevas capacidades de OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) para comprobar si el plan de suscripción incluye Azure Information Protection (que incluye la funcionalidad de Azure RMS).
- [Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) para obtener información sobre cómo comprar una suscripción elegible.  

### <a name="manually-activating-azure-rights-management"></a>Activación manual de Azure Rights Management

Si ha deshabilitado Azure RMS o si no se activó automáticamente por algún motivo, puede hacerlo manualmente en el:

- **Centro de administración de office 365**: vea [Cómo activar Azure Rights Management desde el centro de administración de Office 365](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) para obtener instrucciones.
- **Portal de Azure**: vea [Cómo activar Azure Rights Management desde Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) para obtener instrucciones.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Configurar la administración de la clave de inquilino de Azure Information Protection

Este es un paso opcional. Permitir que Microsoft administre la clave raíz para Azure Information Protection es la configuración predeterminada y la mejor práctica recomendada para la mayoría de los inquilinos de Office 365. Si este es el caso, no es necesario realizar ninguna acción.

Hay muchas razones, por ejemplo, para los requisitos de cumplimiento, que pueden requerir que genere y administre su propia clave raíz (también denominada traer su propia clave (BYOK)). Si este es el caso, le recomendamos que complete los pasos necesarios antes de configurar las nuevas funciones de OME. Consulte [planeación e implementación de la clave de inquilino de Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) para obtener más información.

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Comprobar la nueva configuración de OME en Exchange Online PowerShell

Puede comprobar que el inquilino de Office 365 está configurado correctamente para usar las nuevas funciones de OME en [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
  
1. [Conéctese a Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su inquilino de Office 365.

2. Ejecute el cmdlet Get-IRMConfiguration.

     Debe ver un valor de $True para el parámetro AzureRMSLicensingEnabled, que indica que OME está configurado en el espacio empresarial. Si no es así, use set-IRMConfiguration para establecer el valor de AzureRMSLicensingEnabled en $True para habilitar OME.

3. Ejecute el cmdlet test-IRMConfiguration con la siguiente sintaxis:

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

4. Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Pasos siguientes: definir reglas de flujo de correo para usar las nuevas funciones de OME

Si ya hay reglas de flujo de correo configuradas para cifrar el correo electrónico en su organización de Office 365, debe actualizar las reglas existentes para usar las nuevas funciones de OME. Para implementaciones nuevas, necesita crear nuevas reglas de flujo de correo.

>[!IMPORTANT]
>Si no actualiza las reglas de flujo de correo existentes, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior, en lugar de la nueva experiencia de OME sin problemas.

Las reglas de flujo de correo determinan en qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar ese cifrado. Cuando se establece una acción para una regla, los mensajes que cumplan las condiciones de la regla se cifran cuando se envían.
  
Para conocer los pasos para crear reglas de flujo de correo para OME, vea [definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

Para actualizar las reglas existentes para usar las nuevas capacidades de OME:

1. En el centro de administración de Office 365, vaya a **centros de administración _GT_ Exchange**.
2. En el centro de administración de Exchange, vaya a **reglas de flujo de correo >**.
3. Para cada regla, en **hacer lo siguiente**:
    - Seleccione **modificar la seguridad de los mensajes**.
    - Seleccione **aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.
    - Seleccione una plantilla RMS de la lista.
    - Haga clic en **Guardar**.
    - Seleccione **Aceptar**.
