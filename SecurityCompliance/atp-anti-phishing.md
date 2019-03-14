---
title: Funciones de ATP contra suplantación de identidad en Office 365
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
description: La protección contra phishing de ATP forma parte de la protección contra amenazas avanzada de Office 365. ATP anti-phishing aplica un conjunto de modelos de aprendizaje automático junto con algoritmos de detección de suplantación a los mensajes entrantes para proporcionar protección para los ataques de suplantación de identidad (phishing) y de consumo. Todos los mensajes están sujetos a un amplio conjunto de modelos de aprendizaje de máquinas capacitados para detectar mensajes de suplantación de identidad (phishing), junto con un conjunto de algoritmos avanzados que se usan para proteger contra varios ataques de suplantación de usuario y de dominio.
ms.openlocfilehash: 25e7845ab7d16b0766636006f2c55debfee2f9f9
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276380"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Funciones de ATP contra suplantación de identidad en Office 365

La protección contra phishing de ATP forma parte de la [protección contra amenazas avanzada de Office 365](office-365-atp.md). ATP anti-phishing aplica un conjunto de modelos de aprendizaje automático junto con algoritmos de detección de suplantación a los mensajes entrantes para proporcionar protección para los ataques de suplantación de identidad (phishing) y de consumo. Todos los mensajes están sujetos a un amplio conjunto de modelos de aprendizaje de máquinas capacitados para detectar mensajes de suplantación de identidad (phishing), junto con un conjunto de algoritmos avanzados que se usan para proteger contra varios ataques de suplantación de usuario y de dominio. La protección contra el phishing de ATP protege a su organización de acuerdo con las directivas establecidas por los administradores globales o de seguridad de Office 365.
  
Para obtener más información, consulte [set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> La protección contra phishing de ATP solo está disponible en la protección contra amenazas avanzada, que se incluye en las suscripciones, como [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education A5, etc. Si su organización tiene una suscripción de Office 365 que no incluye ATP de Office 365, puede comprar ATP como complemento. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Cómo funciona la protección contra el phishing ATP

Anti-phishing de ATP comprueba los mensajes entrantes en busca de indicadores de que el mensaje puede ser una suplantación de identidad. Siempre que un usuario está cubierto por una directiva ATP (datos adjuntos seguros, vínculos seguros o antiphishing) el mensaje entrante se evalúa en varios modelos de aprendizaje automático que analizan el mensaje para determinar si la Directiva se aplica al mensaje y la acción correspondiente es se realiza en función de la Directiva configurada.
  
ATP anti-phishing permite a los administradores globales de Office 365 o a los administradores de seguridad definir directivas que proporcionan protección contra ataques de suplantación de identidad (phishing) que incluyen la suplantación de usuarios o dominios. (o ambos). Los administradores globales de Office 365 o los administradores de seguridad definen en la Directiva qué usuarios y dominios deben protegerse de los ataques de suplantación mediante una lista fija de usuarios o dominios o mediante el uso de la inteligencia de buzones de correo. La inteligencia de buzones es un conocimiento avanzado de las hábitos de correo electrónico y los contactos personales de un usuario. ATP aprende cómo cada usuario individual se comunica con otros usuarios de dentro y fuera de la organización y crea un mapa de estas relaciones. Esta asignación permite que ATP comprenda más detalles sobre cómo asegurarse de que los mensajes correctos se identifican como suplantación.
  
Las directivas antiphishing de ATP se pueden aplicar a un conjunto específico de personas o grupos de la organización, o a un dominio completo o a todos los dominios personalizados. Para obtener más información, consulte [set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Cómo obtener anti-phishing de ATP

Las características contra la suPlantación de identidad ATP forman parte de la [protección contra amenazas avanzada](office-365-atp.md); sin embargo, la protección contra la suplantación de identidad ATP se aplica cuando se definen las directivas antiphishing. (Un ejemplo es una directiva basada en suplantación). Consulte [set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Cómo saber si se ha implementado anti-phishing de ATP

Las directivas antiphishing de ATP deben definirse en orden para que la protección esté en vigor. Compruebe esto primero para comprobar que la protección está en su lugar.

Además, los informes están disponibles para mostrar cómo funciona el servicio para su organización. Para obtener más información, consulte [View Reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).

Para que los modelos de aprendizaje de equipos anti-phishing de ATP estén activos para un usuario concreto, dicho usuario debe formar parte de una directiva de [datos adjuntos seguros](atp-safe-attachments.md)de ATP definida, [vínculos seguros de ATP](atp-safe-links.md)o una directiva antiphishing de ATP. 

En la tabla siguiente se describen algunos escenarios de ejemplo. En cada uno de estos ejemplos, la organización usa Office 365 Enterprise E5, que incluye protección contra amenazas avanzada.
  
|**Escenario de ejemplo**|**¿Se aplica la protección contra la suplantación ATP en este caso?**|
|:-----|:-----|
|La organización de Pat tiene Office 365 Enterprise E5, pero nadie ha definido ninguna directiva para los datos adjuntos seguros de ATP, los vínculos seguros de ATP o el phishing avanzado de ATP todavía.|No. Aunque la característica está disponible, se debe definir al menos una directiva ATP para que funcionen los modelos de aprendizaje automático de ATP. Para la suplantación, también debe estar implementada una directiva antiphishing de ATP.|
|Lee es un empleado del Departamento de ventas de contoso. La organización de Lee tiene una directiva contra la suplantación de identidad ATP que solo se aplica a los empleados de finanzas.|No. En este caso, la antiphishing de ATP (modelos de equipo e protección de suplantación) se aplicaría a los empleados de finanzas, pero otros empleados, incluido el Departamento de ventas, no lo harían.|
|Ayer, un administrador de Office 365 en la organización de Jean configuró una directiva antiphishing de ATP que se aplica a todos los empleados. Anteriormente, Jean recibió un mensaje de correo electrónico que incluye una suplantación cubierta por la Directiva.|Sí. En este ejemplo, Jean tiene una licencia para la protección contra amenazas avanzada y se ha definido una directiva contra la suplantación de identidad (ATP) que incluye Jean. Por lo general, la nueva Directiva tarda unos 30 minutos en surtir efecto en los centros de recursos; como se ha pasado un día en este caso, la Directiva debe estar en vigor.|

## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Protección contra suplantación de identidad (phishing) en Office 365](anti-phishing-protection.md)
  
[Configurar directivas antiphishing en Office 365](set-up-anti-phishing-policies.md)
  
[Vínculos seguros de ATP en Office 365](atp-safe-links.md)
  
[Configurar las directivas de vínculos seguros ATP en Office 365](set-up-atp-safe-links-policies.md)
  
[Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md)
  
[Configurar las directivas de datos adjuntos seguros ATP en Office 365](set-up-atp-safe-attachments-policies.md)
  
[Ver los informes para la protección contra amenazas avanzada](view-reports-for-atp.md)
