---
title: Nueva directiva de cifrado de mensajes de Office 365 para información confidencial
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Aplica automáticamente la directiva de cifrado de mensajes de Office 365 para implantar para todos los inquilinos de tipos de información confidencial.'
ms.openlocfilehash: f5996707d1cafe8dc1bf90856878de0a4fb7b77b
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2019
ms.locfileid: "27752096"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>Directiva de cifrado de mensajes de Office 365 para información confidencial

Se van a crear una nueva directiva automática en los inquilinos de Office 365 que se aplicarán el cifrado de mensajes de Office 365 a todos los correos electrónicos que contienen información confidencial y que se están enviando fuera de su organización. Esta nueva regla de flujo de correo de Exchange se crearán automáticamente en el inquilino de Office 365 para que su organización se protegerán de forma predeterminada.

## <a name="when-to-expect-the-update-for-your-tenant"></a>Cuándo se espera que la actualización para el inquilino

La organización recibirá una notificación en el centro de mensajes de Office 365 notificarlo a la fecha en la que se creará esta directiva automática en su inquilino. Se le dará al menos un aviso de 30 días y también tendrá la opción de voluntaria. Un escenario en el que es posible que desee excluir potencialmente es si tiene una solución de prevención de pérdida de datos 3rd terceros que ya se examina para tipos de confidenciales. Para obtener más detalles acerca de cómo voluntaria están disponibles más adelante en este artículo.

## <a name="sensitive-information-type-policy-details"></a>Detalles de directivas de tipo de información confidencial

Se creará una regla de flujo de correo de Exchange en la organización que se va a cifrar automáticamente mensajes de correo electrónico desde fuera de la organización con el *Solo cifrar* directiva si contienen los siguientes tipos de información confidencial:

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

Esta actividad se audita y está disponible para los clientes.  La operación es 'New-TransportRule' y es un fragmento de código de una entrada de auditoría de ejemplo de la búsqueda de registro de auditoría en el centro de cumplimiento y seguridad a continuación:

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

## <a name="how-do-i-disable-the-automatic-policy"></a>¿Cómo se puede deshabilitar la directiva automática?

Si no voluntaria de este cambio y ya se ha creado la regla de correo de Exchange, puede [Deshabilitar la regla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) yendo al **flujo de correo** > de**reglas** en la administración de Exchange (EAC) del centro y deshabilite la regla "*cifrar saliente mensajes de correo electrónico confidenciales (fuera de la regla del cuadro)*".
