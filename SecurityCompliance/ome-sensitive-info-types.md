---
title: Nueva directiva de cifrado de mensajes de Office 365 para información confidencial
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/16/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Aplica automáticamente la directiva de cifrado de mensajes de Office 365 para implantar para todos los inquilinos de tipos de información confidencial.'
ms.openlocfilehash: f83bf0fe572586b3becf2dd53395e611bdaaea24
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614384"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>Directiva de cifrado de mensajes de Office 365 para información confidencial

Para un grupo de inquilinos, según su tamaño de la organización y la complejidad de flujo de correo, seleccione que hacemos una implantación lenta de una nueva directiva automática en los inquilinos de Office 365 que se aplicará el cifrado de mensajes de Office 365 a los correos electrónicos que contienen ciertos tipos de confidenciales información. Que se prueban con un pequeño grupo de inquilinos. No se implementarán esta directiva a todas las organizaciones y consideraciones como el tamaño de la organización y complejidad de flujo de correo se utilizará para determinar la idoneidad para esta implantación. Si se selecciona la organización para esta implantación, recibirá una notificación en el centro de mensajes de Office 365 notificarlo a la fecha en la que se creará esta directiva automática y se le dará al menos un aviso de 30 días y la opción de voluntaria. Si no desea esperar a que Microsoft crear esta directiva y le gustaría hacerlo usted, puede crear esta directiva automática mediante reglas de flujo de correo de Exchange.

## <a name="when-to-expect-the-update-for-your-tenant"></a>Cuándo se espera que la actualización para el inquilino

La organización recibirá una notificación en el centro de mensajes de Office 365 notificarlo a la fecha en la que se creará esta directiva automática en su inquilino. Se le dará al menos un aviso de 30 días y también tendrá la opción de voluntaria. Un escenario en el que es posible que desee excluir potencialmente es si tiene una solución de prevención de pérdida de datos 3rd terceros que ya se examina para tipos de confidenciales. Para obtener más detalles acerca de cómo voluntaria están disponibles más adelante en este artículo.

## <a name="sensitive-information-type-policy-details"></a>Detalles de directivas de tipo de información confidencial

Se creará una regla de flujo de correo de Exchange en la organización que se va a cifrar automáticamente mensajes de correo electrónico desde fuera de la organización con el *Solo cifrar* directiva si los mensajes de correo electrónico o sus datos adjuntos contienen los siguientes tipos de información confidencial:

- Número de enrutamiento ABA
- Número de tarjeta de crédito
- Número de drogas Agencia de cumplimiento (DEA)
- Estados Unidos / número de pasaporte del Reino Unido
- Número de cuenta bancaria de Estados Unidos
- Número de identificación de contribuyente individual (ITIN) de EE. UU.
- Número de seguridad social (SSN) de EE. UU.

> [!Note]
> Los tipos de confidenciales exactos pueden diferir mediante la configuración regional de su organización y se comunican en la notificación de centro de mensajes.

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué es necesario hacer para preparar para este cambio?

No es necesario que actualizar o modificar los valores de configuración de Office 365 existentes antes de realizar este cambio nuevo. Sin embargo, es posible que desee actualizar cualquier documentación procede del usuario final y el material de aprendizaje para preparar las personas de su organización para que este cambio. Compartir estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:

- [Enviar, ver y responder a los mensajes cifrados en Outlook para PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Office 365 Essentials vídeo: Cifrado de mensajes de Office](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>¿Cómo se representará este cambio en el registro de auditoría?

Esta actividad se audita y está disponible para los clientes.  La operación es 'New-TransportRule' y es un fragmento de código de una entrada de auditoría de la búsqueda de registro de auditoría de seguridad & centro de cumplimiento de ejemplo a continuación:

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey": "Operador de Microsoft"," UserType": 3,"versión": 1,"carga de trabajo":"Exchange","IPCliente":"123.456.147.68:17584","ObjectId":"UserId "," ":"() Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX de Microsoft 15.20.1382.008)","Parameters": {"Nombre":"Organización","Valor":" d. 123456-221-12346"{"Nombre":"ApplyRightsProtectionTemplate","Valor":"Cifrar"}, {"Nombre":"Nombre","Valor":"Cifrar correos con información confidencial salientes (fuera de la regla del cuadro)"}, {"Nombre":" MessageContainsDataClassifications"... etcetera.*
 |

## <a name="how-do-i-opt-out"></a>¿Voluntaria?

Si le gustaría voluntaria de este cambio, siga estos pasos:

1. Uso de una cuenta de trabajo o escuela que tiene permisos de administrador global de la organización de Office 365, iniciar una sesión de Windows PowerShell y conectarse a Exchange Online. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).
2. Ejecute el cmdlet Set-IRMConfiguration como sigue:

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-or-customize-the-automatic-policy"></a>¿Cómo deshabilitar o personalizar la directiva automática?

Si no voluntaria de este cambio y ya se ha creado la regla de flujo de correo de Exchange, puede [Deshabilitar o editar la regla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) yendo al **flujo de correo** > **reglas** en el Exchange admin center (EAC) y deshabilite la regla "*cifrar correos salientes con información confidencial (fuera de la regla del cuadro)*".
