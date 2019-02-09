---
title: Funciones de ATP contra suplantación de identidad en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP contra suplantación de identidad es parte de la protección de amenaza avanzada de Office 365. ATP contra suplantación de identidad, aplica un conjunto de modelos de aprendizaje de máquina junto con los algoritmos de detección de suplantación a los mensajes entrantes para proporcionar protección para mercancías y lanza ataques de suplantación de identidad. Todos los mensajes están sujetas a un amplio conjunto de modelos de aprendizaje de máquina capacitados para detectar los mensajes de suplantación de identidad, junto con un conjunto de algoritmos avanzados que se usa para proteger contra diversos ataques de suplantación de usuario y dominio.
ms.openlocfilehash: c3e44a313bf9c823fbfda138fc5a10294993d509
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792275"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Funciones de ATP contra suplantación de identidad en Office 365

ATP contra suplantación de identidad es parte de [La protección de amenaza avanzada de Office 365](office-365-atp.md). ATP contra suplantación de identidad, aplica un conjunto de modelos de aprendizaje de máquina junto con los algoritmos de detección de suplantación a los mensajes entrantes para proporcionar protección para mercancías y lanza ataques de suplantación de identidad. Todos los mensajes están sujetas a un amplio conjunto de modelos de aprendizaje de máquina capacitados para detectar los mensajes de suplantación de identidad, junto con un conjunto de algoritmos avanzados que se usa para proteger contra diversos ataques de suplantación de usuario y dominio. ATP contra suplantación de identidad protege su organización de acuerdo a las directivas que se establecen por su Office 365 globales o los administradores de seguridad.
  
Para obtener más información, vea [configurar las directivas contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> Sólo está disponible en avanzada protección contra amenazas, que se incluye en las suscripciones, como [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 educación A5, etcetera ATP contra suplantación de identidad. Si su organización tiene una suscripción a Office 365 que no incluye Office 365 ATP, puede comprar potencialmente ATP como un complemento. Para obtener más información, vea [precios y planes de protección de amenaza avanzada de Office 365](https://products.office.com/exchange/advance-threat-protection) y [Office 365 avanzada Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Cómo funciona la ATP contra suplantación de identidad

ATP anti-phishing comprueba los mensajes entrantes para los indicadores de que el mensaje puede ser la suplantación de identidad. Cada vez que un usuario está cubierto por una directiva de ATP (los datos adjuntos seguros, vínculos seguros o contra suplantación de identidad) se evalúa el mensaje entrante por máquina varios modelos que analizar el mensaje para determinar si la directiva se aplica al mensaje y la acción apropiada de aprendizaje tomar, en función de la directiva configurada.
  
ATP contra suplantación de identidad permite a los administradores globales de Office 365 o administradores de seguridad definir las directivas que proporcionan protección contra ataques de suplantación de identidad que incluyen la suplantación de usuarios o dominios. (o ambos). Los administradores globales de Office 365 o administradores de seguridad definición dentro de la directiva de usuario y los dominios se debe proteger contra los ataques de suplantación mediante una lista fija de usuarios o dominios o mediante el uso de inteligencia de buzón de correo. Inteligencia de buzón de correo es una descripción avanzada de hábitos de correo electrónico de un usuario y contactos personales. ATP aprende cómo cada usuario individual se comunica con otros usuarios dentro y fuera de la organización y genera un mapa de estas relaciones. Este mapa permite ATP conocer más detalles acerca de cómo asegurarse de que los mensajes de derecho son identificados como suplantación.
  
Las directivas de ATP contra suplantación de identidad se puede aplicar a un conjunto específico de personas o grupos de la organización, o a un dominio completo o todos los dominios personalizados. Para obtener más información, vea [configurar las directivas contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Cómo obtener ATP contra suplantación de identidad

Características de ATP Anti-Phishing forman parte de la [Protección avanzada de amenaza](office-365-atp.md); Sin embargo, la protección contra suplantación de identidad de ATP se aplica cuando se definen las directivas contra suplantación de identidad. (Un ejemplo es una directiva de suplantación). Consulte [configurar las directivas contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Cómo saber si ATP contra suplantación de identidad está en su lugar

Directivas de anti-phishing ATP deben definirse en orden para protección surta efecto. Compruebe esto en primer lugar para comprobar la protección está en su lugar.

Además, los informes están disponibles para mostrar cómo funciona el servicio para la organización. Para obtener más información, vea [Ver informes de protección de amenaza avanzada de Office 365](view-reports-for-atp.md).

Máquina de anti-phishing ATP modelos para que esté activo para un usuario determinado de aprendizaje, que el usuario debe ser parte de una directiva de [Datos adjuntos seguros de ATP](atp-safe-attachments.md), [Vínculos seguros ATP](atp-safe-links.md)o ATP Anti-Phishing definida. 

En la siguiente tabla se describe algunos escenarios de ejemplo. En cada uno de estos ejemplos, la organización está usando Office 365 Enterprise E5, que incluye la protección contra amenazas de avanzada.
  
|**Escenario de ejemplo**|**¿Se aplica en este caso ATP contra suplantación de identidad?**|
|:-----|:-----|
|Organización de Pat tiene E5 Enterprise de Office 365, pero nadie ha definido las directivas de ATP seguros los datos adjuntos, vínculos seguros ATP o ATP avanzado de suplantación de identidad todavía.|No. Aunque la característica está disponible, debe definirse al menos una directiva de ATP en orden de la máquina de ATP modelos de aprendizaje para que funcione. Para la suplantación una directiva contra suplantación de identidad de ATP también debe ser en su lugar.|
|Lee es un empleado del departamento de ventas de Contoso. Organización de Díaz tiene una directiva contra suplantación de identidad de ATP en contexto que se aplica a los empleados de finanzas sólo.|No. En este caso, ATP contra suplantación de identidad (modelos de equipo y protección de suplantación) se aplicará a los empleados de finanzas, pero otros empleados, incluido el departamento de ventas, no lo haría.|
|Ayer, un administrador de Office 365 en la organización de Jean establecer una directiva de ATP contra suplantación de identidad que se aplica a todos los empleados. Anteriormente en la actualidad, Jean recibió un mensaje de correo electrónico que incluya una suplantación cubierta por la directiva.|Sí. En este ejemplo, Jean tiene una licencia para protección avanzada de amenaza y se ha definido una directiva contra suplantación de identidad de ATP que incluye Jean. Normalmente tiene unos 30 minutos para una nueva directiva tener efecto en centros de datos; Dado que un día ha pasado en este caso, la directiva debe ser en vigor.|

## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Protección contra suplantación de identidad (phishing) en Office 365](anti-phishing-protection.md)
  
[Configurar las directivas contra suplantación de identidad en Office 365](set-up-anti-phishing-policies.md)
  
[Vínculos seguros de ATP en Office 365](atp-safe-links.md)
  
[Configurar directivas de ATP vínculos seguros en Office 365](set-up-atp-safe-links-policies.md)
  
[Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md)
  
[Configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)
  
[Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md)
