---
title: Qué incluyen las plantillas de directiva DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.DLPNewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c2e588d3-8f4f-4937-a286-8c399f28953a
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye plantillas de directiva de listas para usar que los requisitos de cumplimiento de normas comunes, como lo que ayuda a proteger la información confidencial sujetos al acto de mantenimiento seguro de Estados Unidos (de direcciones HIPAA), Estados Unidos Gramm-Leach-Bliley Act (GLBA) o Patriot Act de Estados Unidos. En este tema se enumera todos los de la directiva de plantillas, ¿qué tipos de información confidencial que buscan y ¿cuáles son las condiciones predeterminadas y las acciones.
ms.openlocfilehash: 345738244b9573b1af4d55ede86a568bf136f048
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536359"
---
# <a name="what-the-dlp-policy-templates-include"></a>Qué incluyen las plantillas de directiva DLP

Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye plantillas de directiva de listas para usar que los requisitos de cumplimiento de normas comunes, como lo que ayuda a proteger la información confidencial sujetos al acto de mantenimiento seguro de Estados Unidos (de direcciones HIPAA), Estados Unidos Gramm-Leach-Bliley Act (GLBA) o Patriot Act de Estados Unidos. En este tema se enumera todos los de la directiva de plantillas, ¿qué tipos de información confidencial que buscan y ¿cuáles son las condiciones predeterminadas y las acciones. En este tema no incluye todos los detalles de cómo se configura cada plantilla de directiva; en su lugar, el tema presenta con usted suficiente información para ayudarle a decidir qué plantilla es el mejor punto de partida para su escenario. Recuerde que puede personalizar estas plantillas de directivas para satisfacer los requisitos específicos.
  
## <a name="australia-financial-data"></a>Datos financieros de Australia

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-health-records-act-hrip-act"></a>Ley de registros de salud de Australia (Ley HRIP)

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|HRIP de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta médica de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|HRIP de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta médica de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-personally-identifiable-information-pii-data"></a>Datos de identificación personal (PII) de Australia

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de permiso de conducción de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de permiso de conducción de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-privacy-act"></a>Ley de privacidad de Australia

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Privacidad de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Privacidad de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-financial-data"></a>Datos financieros de Canadá

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-health-information-act-hia"></a>Ley de información sobre salud (HIA) de Canadá

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|HIA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|HIA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-health-act-phipa---ontario"></a>Ley sobre salud personal de Canadá (PHIPA) - Ontario

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PHIPA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PHIPA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-health-information-act-phia---manitoba"></a>Ley de información sobre salud personal de Canadá (PHIA) - Manitoba

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PHIA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PHIA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-information-protection-act-pipa"></a>Ley de protección de información personal de Canadá (PIPA)

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PIPA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIPA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-information-protection-act-pipeda"></a>Ley de protección de información personal de Canadá (PIPEDA)

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PIPEDA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIPEDA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personally-identifiable-information-pii-data"></a>Datos de identificación personal de Canadá (PII)

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-data-protection-act"></a>Ley de protección de datos de Francia

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|DPA de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|DPA de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-financial-data"></a>Datos financieros de Francia

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Francia

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 1, recuento máximo 9  <br/>  Número de permiso de conducción de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de permiso de conducción de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="general-data-protection-regulation-gdpr"></a>Reglamento de protección de datos general (GDPR)

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Bajo volumen que se encuentra el contenido de la UE confidenciales  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia del controlador de la UE: count Min 1, el número máximo de 9  <br/>  Número de identificación nacional de la UE: Recuento Min 1, recuento máximo de 9  <br/>  Número de cuenta de Passport de la UE: Recuento Min 1, recuento máximo de 9  <br/>  Número de seguridad Social de la UE (SSN) o identificador equivalente: count Min 1, el número máximo de 9  <br/>  Recuento de número de identificación fiscal de la UE (TIN) — Min 1, recuento máximo de 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar informes de incidentes al administrador  <br/> |
|Gran volumen de contenido de la UE confidenciales encontrado  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia del controlador de la UE: count Min 1, el número máximo de 9  <br/>  Número de identificación nacional de la UE: Recuento Min 1, recuento máximo de 9  <br/>  Número de cuenta de Passport de la UE: Recuento Min 1, recuento máximo de 9  <br/>  Número de seguridad Social de la UE (SSN) o identificador equivalente: count Min 1, el número máximo de 9  <br/>  Recuento de número de identificación fiscal de la UE (TIN) — Min 1, recuento máximo de 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Restringir el acceso al contenido para los usuarios externos  <br/>  Notificar a los usuarios con correo electrónico y sugerencias de directivas  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informes de incidentes al administrador  <br/> |
   
## <a name="germany-financial-data"></a>Datos financieros de Alemania

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros de Alemania: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Alemania: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="germany-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Alemania

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Alemania: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Alemania: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Alemania: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Alemania: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Alemania: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Alemania: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-financial-data"></a>Datos financieros de Israel

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Israel

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-protection-of-privacy"></a>Protección de privacidad en Israel

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Privacidad de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Privacidad de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-financial-data"></a>Datos financieros de Japón

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Japón: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-personally-identifiable-information-pii-data"></a>Datos de identificación personal (PII) de Japón

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-protection-of-personal-information"></a>Protección de información personal de Japón

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PPI de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PPI de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="pci-data-security-standard-pci-dss"></a>Estándar de seguridad de datos PCI (PCI DSS)

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PCI DSS: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PCI DSS: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia---anti-cyber-crime-law"></a>Ley contra el crimen cibernético de Arabia Saudí

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|ACC de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|ACC de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia-financial-data"></a>Datos financieros de Arabia Saudí

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Arabia Saudí

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Arabia Saudí: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Arabia Saudí: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-access-to-medical-reports-act"></a>Ley de acceso a informes médicos del Reino Unidos

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|AMRA de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|AMRA de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-data-protection-act"></a>Ley de protección de datos del Reino Unido

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|DPA de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|DPA de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-financial-data"></a>Datos financieros del Reino Unido

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-personal-information-online-code-of-practice-piocp"></a>Código de prácticas en línea de información personal (PIOCP) del Reino Unido

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PIOCP de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIOCP de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) del Reino Unido

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-privacy-and-electronic-communications-regulations"></a>Normas de comunicaciones electrónicas y privacidad del Reino Unido

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PECR de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PECR de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-federal-trade-commission-ftc-consumer-rules"></a>Normas del consumidor de la Comisión Federal de Comercio de los EE.UU.

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Reglas de la FTC de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de enrutamiento ABA: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Reglas de la FTC de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de enrutamiento ABA: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-financial-data"></a>Datos financieros de EE.UU.

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros - Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de enrutamiento ABA: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros - Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de enrutamiento ABA: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-gramm-leach-bliley-act-glba"></a>Ley Gramm-Leach-Bliley (GLBA) de EE.UU.

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|GLBA de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|GLBA de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-health-insurance-act-hipaa"></a>Ley de seguros de salud (HIPAA) de los EE. UU.

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Coincide con el contenido HIPAA de EE.  <br/> | Contiene cualquiera de la siguiente información confidencial:  <br/>  Número de seguridad Social de Estados Unidos (SSN): count Min 1, Max contar cualquiera  <br/>  Agencia de cumplimiento de drogas (DEA) número: Número 1 de Min, Max contar cualquiera  <br/> **AND** <br/>  Contenido contiene cualquiera de estos términos:  <br/>  Clasificación internacional de enfermedades (ICD-9-CM) — Min count 1, Max contar cualquiera  <br/>  Clasificación internacional de enfermedades (ICD-10-CM) — Min count 1, Max contar cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
   
## <a name="us-patriot-act"></a>Ley Patriota de los EE.UU.

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Ley Patriota de los EE.UU.: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Ley Patriota de los EE.UU.: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Estados Unidos

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-state-breach-notification-laws"></a>Leyes de notificación de incumplimiento estatal de EE.UU.

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Incumplimientos estatales de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de permiso de conducción de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Incumplimientos estatales de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de permiso de conducción de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-state-social-security-number-confidentiality-laws"></a>Leyes de confidencialidad sobre el número de Seguridad Social de EE.UU.

|**Nombre de la regla**|**Condiciones de <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Leyes sobre el SSN de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Leyes sobre el SSN de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   

