---
title: Nueva directiva de cifrado de mensajes de Office 365 para información confidencial
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/13/2018
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Nueva Office 365 Message Encryption directiva para la información confidencial.'
ms.openlocfilehash: 180050d1bf9303f6d29bc126e66ac53211c2fb34
ms.sourcegitcommit: 3aae959ea1ac5ef61a9942c681d334831e6b6038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271096"
---
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a>Nueva directiva de cifrado de mensajes de Office 365 para información confidencial

Se van a crear una nueva directiva automática en los inquilinos de Office 365 que se aplicarán el cifrado de mensajes de Office 365 a todos los correos electrónicos que contienen información confidencial y que se están enviando fuera de su organización. Esta nueva regla de flujo de correo de Exchange se crearán automáticamente en el inquilino de Office 365 para que su organización se protegerán de forma predeterminada.

## <a name="how-will-this-work"></a>¿Cómo funcionará?

La organización recibirá una notificación en el centro de mensajes de Office 365 notificarlo a la fecha en la que se creará esta directiva automática en su inquilino. Se le dará al menos un aviso de 30 días y también tendrá la opción de voluntaria. Un escenario en el que es posible que desee excluir potencialmente es si tiene una solución de prevención de pérdida de datos 3rd terceros que ya se examina para tipos de confidenciales.

## <a name="new-policy-details"></a>Detalles de la directiva nueva

Se creará una nueva regla de flujo de correo de Exchange en la organización que se va a cifrar automáticamente mensajes de correo electrónico desde fuera de la organización con el *Solo cifrar* directiva si contienen los siguientes tipos de información confidencial:

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

No es necesario que actualizar o modificar los valores de configuración de Office 365 existentes antes de realizar este cambio nuevo. Sin embargo, es posible que desee actualizar cualquier documentación procede del usuario final y el material de aprendizaje para preparar las personas de su organización para que este cambio.

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>¿Cómo se representará este cambio en el registro de auditoría?

Esta actividad se audita y está disponible para los clientes.  La operación es 'New-TransportRule' y es un fragmento de código de una entrada de auditoría de ejemplo de la búsqueda de registro de auditoría en el centro de cumplimiento y seguridad a continuación:

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey": "Operador de Microsoft"," UserType": 3,"versión": 1,"carga de trabajo":"Exchange","IPCliente":"123.456.147.68:17584","ObjectId":"UserId "," ":"() Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX de Microsoft 15.20.1382.008)","Parameters": {"Nombre":"Organización","Valor":" d. 123456-221-12346"{"Nombre":"ApplyRightsProtectionTemplate","Valor":"Cifrar"}, {"Nombre":"Nombre","Valor":"Cifrar correos con información confidencial salientes (fuera de la regla del cuadro)"}, {"Nombre":" MessageContainsDataClassifications"... etcetera.*
 |

## <a name="how-do-i-opt-out"></a>¿Voluntaria?

Si le gustaría voluntaria de este cambio, siga estos pasos:

1. Conectarse a [Exchange Online PowerShell](https://aka.ms/exopowershell) como un usuario con la función de administrador global.
2.  Ejecute el siguiente código después de la autenticación:

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a>¿Cómo se puede deshabilitar la directiva automática?

Si no voluntaria de este cambio y ya se ha creado la regla de correo de Exchange, puede [Deshabilitar la regla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) yendo al **flujo de correo** > de**reglas** en la administración de Exchange (EAC) del centro y deshabilite la regla "*cifrar saliente mensajes de correo electrónico confidenciales (fuera de la regla del cuadro)*".
