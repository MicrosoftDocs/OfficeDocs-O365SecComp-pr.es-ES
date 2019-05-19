---
title: Usar Exchange Online y el Centro de seguridad y cumplimiento para cumplir con la norma SEC 17a-4
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Cohasset Associates ha validado que, cuando Exchange Online y el Centro de seguridad y cumplimiento se configuran según las recomendaciones, cumplen con los requisitos de almacenamiento relevantes de las normas CFTC 1.31(c)-(d), FINRA 4511 y SEC 17a-4. Puede descargar la evaluación.
ms.openlocfilehash: 60b8d27ed75afbfd6ffc5d8e254738ea62e0d21b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156202"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>Usar Exchange Online y el Centro de seguridad y cumplimiento para cumplir con la norma SEC 17a-4

Si su organización necesita cumplir con normas reglamentarias para la conservación de datos, el Centro de seguridad y cumplimiento de Office 365 proporciona características para administrar el ciclo de vida de sus datos en Exchange Online. Entre estas características, se incluye la capacidad de conservar, auditar, buscar y exportar sus datos. Estas funciones son suficientes para satisfacer las necesidades de la mayoría de las organizaciones.

Pero algunas organizaciones de sectores con reglamentos estrictos están sujetas a requisitos reglamentarios con mayores limitaciones. Por ejemplo, las entidades financieras (como bancos y corredores de bolsa) están sujetas a la norma 17a-4 emitida por la Comisión de bolsas de valores (SEC). La norma 17a-4 tiene requisitos especiales para el almacenamiento de datos electrónicos, incluidos varios aspectos de la administración de registros, como la duración, el formato, la calidad, la disponibilidad y la responsabilidad de la retención de registros.

Para que estas organizaciones puedan comprender mejor cómo aprovechar el Centro de seguridad y cumplimiento para adaptarse a sus obligaciones reglamentarias para Exchange Online, específicamente en relación con los requisitos de la norma 17a-4, publicamos una evaluación de forma conjunta con Cohasset Associates.

Cohasset ha validado que, cuando Exchange Online y el Centro de seguridad y cumplimiento se configuran según las recomendaciones, cumplen con los requisitos de almacenamiento relevantes de las normas CFTC 1.31(c)-(d), FINRA 4511 y SEC 17a-4. Usamos este conjunto de reglas porque representa la guía más prescriptiva globalmente en relación con la retención de registros para entidades financieras.

## <a name="download-the-cohasset-assessment"></a>Descargar la evaluación de Cohasset

Puede [descargar la evaluación de Cohasset aquí](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

![Página de título de la evaluación descargable por Cohasset Associates](media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>Esta evaluación es específica para Exchange Online.

Tenga en cuenta que esta evaluación es específica para Exchange Online. En la evaluación, no se incluyen otros servicios de Office 365, como SharePoint Online o OneDrive para la Empresa, aunque estamos planeando admitir esos servicios en relación con la norma SEC 17a-4 en el futuro.

Es importante comprender que Skype Empresarial y Teams también almacenan datos en Exchange Online. Por lo tanto, se evalúan mensajes de Skype Empresarial y mensajes de chat y de canal de Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>Usar Bloqueo de conservación es clave para la configuración recomendada

Con frecuencia, en los sectores con reglamentos estrictos, es necesario almacenar las comunicaciones electrónicas para cumplir con el requisito WORM (escribir una vez, leer varias veces). El requisito WORM dicta una solución de almacenamiento en la que un registro tiene que:

- Conservarse durante un período de retención que no puede acortarse, solo incrementarse.
- Ser inmutable, lo que significa que el registro no se puede sobrescribir, borrar ni modificar durante el período de retención necesario.

En Exchange Online, cuando se aplica una [directiva de retención](retention-policies.md) en el buzón de un usuario, todo el contenido del usuario se conserva basándose en los criterios de la directiva. De hecho, si un usuario intenta eliminar o modificar un correo electrónico, se conservará una copia del correo electrónico antes del cambio en una ubicación oculta y segura del buzón del usuario. Las directivas de retención permiten garantizar que una organización conserve comunicaciones electrónicas, pero esas directivas se pueden modificar.

Al colocar un Bloqueo de conservación en una directiva de retención, una organización se asegura de que la directiva no se pueda modificar. De hecho, después de aplicar un Bloqueo de conservación en una directiva de retención, las acciones siguientes están restringidas:

- El período de retención de la directiva solo se puede incrementar, no se puede acortar.
- Se pueden agregar usuarios a la directiva, pero no se puede quitar ningún usuario.
- Un administrador no puede eliminar una directiva de retención.

Bloqueo de conservación puede ayudarle a cumplir con los requisitos reglamentarios de SEC 17a-4.

## <a name="how-to-set-up-preservation-lock"></a>Configurar Bloqueo de conservación

Se puede bloquear una directiva de retención mediante el uso de PowerShell. Para obtener más información, vea [Bloquear una directiva de retención](retention-policies.md#locking-a-retention-policy).

## <a name="known-limitations"></a>Limitaciones conocidas

Somos conscientes de algunas limitaciones en Exchange Online. Estamos trabajando de forma activa en estas limitaciones y esperamos admitir estos escenarios en julio de 2019:

- La auditoría de nivel de elemento no está disponible en los buzones de grupo de Office 365.
- Las comunicaciones en conversaciones no están disponibles para los mensajes de canal y de chat de Teams.
- Los “me gusta” no se conservan para los mensajes de canal y de chat de Teams.
