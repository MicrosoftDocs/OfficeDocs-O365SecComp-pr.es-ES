---
title: Directiva de cifrado de mensajes de Office 365 para información confidencial
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: la Directiva de cifrado de mensajes de Office 365 para tipos de información confidencial ahora está disponible.'
ms.openlocfilehash: e2a72ee85ca65a2fe8ae1543979b51915ff0a88f
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696204"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>Directiva de cifrado de mensajes de Office 365 para información confidencial

Actualización (1/30/19): en el 2018 de octubre, hemos trabajado con una pequeña muestra de clientes para comprender si podemos simplificar la protección al cifrar automáticamente los correos electrónicos confidenciales en función de determinados tipos de información confidencial. En función de los comentarios positivos de este ejemplo, decidimos expandir a un perfil más diverso de los inquilinos en diciembre de 2018. Después de comunicar la próxima implementación para seleccionar los inquilinos, escuchamos sus comentarios y determinamos que los clientes con entornos más complejos querían implementar las reglas con más cuidado y que, por lo tanto, estamos ajustando los planes.

Si la organización se seleccionó para la implementación a partir del 15 de enero de 2019, no se implementará la Directiva automática. En su lugar, proporcionaremos instrucciones en este artículo sobre cómo puede completar la implementación de. Siga leyendo para saber cómo hacerlo.

||
|:-----|
|Este artículo forma parte de una amplia serie de artículos sobre el cifrado de mensajes de Office 365. Este artículo está destinado a los administradores y ITPros. Si solo está buscando información sobre cómo enviar o recibir un mensaje cifrado, vea la lista de artículos en el cifrado de [mensajes de Office 365 (OME)](ome.md) y busque el artículo que mejor se adapte a sus necesidades. |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a>Cómo crear la Directiva de tipo de información confidencial para su espacio empresarial

Puede usar las reglas de flujo de correo de Exchange o la prevención de pérdida de datos (DLP) de Office 365 para crear la Directiva de tipo de información confidencial. Para crear una regla de flujo de correo de Exchange, puede usar el centro de administración de Exchange (EAC) o PowerShell.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Para crear la Directiva mediante reglas de flujo de correo en el EAC

Inicie sesión en el centro de administración de Exchange (EAC) y vaya a**reglas**de **flujo** > de correo. Allí, cree una regla que aplique el cifrado de mensajes de Office 365 basándose en condiciones como la presencia de determinadas palabras clave o tipos de información confidencial en el mensaje o los datos adjuntos.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Para crear la Directiva mediante reglas de flujo de correo en PowerShell

Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie una sesión de Windows PowerShell y conéctese a Exchange Online. Para obtener instrucciones, vea [conectarse a Exchange Online PowerShell](https://aka.ms/exopowershell). Use los cmdlets Set-IRMConfiguration y New-TransporRule para crear la Directiva.

### <a name="example-mail-flow-rule-created-with-powershell"></a>Ejemplo de regla de flujo de correo creada con PowerShell

Ejecutar los siguientes comandos en PowerShell cree una regla de flujo de correo de Exchange que cifre automáticamente los correos electrónicos que se encuentran fuera de la organización con la Directiva de *solo cifrado* si los mensajes de correo electrónico o los datos adjuntos contienen los siguientes elementos confidenciales tipos de información:

- Número de enrutamiento ABA
- Número de tarjeta de crédito
- Número de la Agencia para la imPosición de drogas (DEA)
- Número de pasaporte de Estados Unidos/Reino Unido
- Número de cuenta bancaria de Estados Unidos
- Número de identificación de contribuyente individual (ITIN) de EE. UU.
- Número de seguridad social (SSN) de EE. UU.

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a>Acceso a datos adjuntos de destinatarios

Una vez que un mensaje está cifrado, los destinatarios tendrán acceso sin restricciones a los datos adjuntos una vez que accedan y abran el correo electrónico cifrado.

## <a name="to-prepare-for-this-change"></a>Para prepararse para este cambio

Es posible que desee actualizar toda la documentación para el usuario final y los materiales de formación correspondientes para preparar a los usuarios de su organización para este cambio. Comparta estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:

- [Enviar, ver y responder mensajes cifrados en Outlook para PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Vídeo de Office 365 Essentials: cifrado de mensajes de Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Ver estos cambios en el registro de auditoría

Esta actividad se audita y está disponible para los administradores de Office 365. La operación es ' New-TransportRule ' y un fragmento de código de una entrada de auditoría de la búsqueda de registros de auditoría en el centro de seguridad & Compliance Center se muestra a continuación:

|     |
| --- |
| *{"CreationTime": "2018-11-28T23:35:01", "ID": "a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c", "Operation": "New-TransportRule", "OrganizationId": "123456-221d-12345", "RecordType": 1, "ResultStatus": "true", "UserKey": "Microsoft Operator", " UserType ": 3," versión ": 1" carga de trabajo ":" Exchange "," ClientIP ":" 123.456.147.68:17584 "," ObjectId ":" "," UserId ":" Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso. My Microsoft. com "," OriginatingServer ":" CY4PR13MBXXXX ( 15.20.1382.008) "," paraMeters ": {" Name ":" Organization "," Value ":" 123456-221d-12346 "{" Name ":" ApplyRightsProtectionTemplate "," Value ":" enCrypt "}, {" Name ":" Name "," Value ":" enCrypt saliente Sensitive email (regla no actualizada) "}, {" Name ":" MessageContainsDataClassifications "... demás.* |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Para deshabilitar o personalizar la Directiva de tipos de información confidencial

Una vez que haya creado la regla de flujo de correo de Exchange, puede deshabilitarla [o editarla](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) en**reglas** de **flujo** > de correo en el centro de administración de Exchange (EAC) y deshabilitar la regla "*cifrar mensajes de correo electrónico confidenciales salientes" (regla* "no es de la casilla") ".
