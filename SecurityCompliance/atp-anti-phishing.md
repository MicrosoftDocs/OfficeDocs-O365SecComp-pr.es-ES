---
title: Funciones de ATP contra suplantación de identidad en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: ATP contra suplantación de identidad se ofrece como parte de la protección de amenaza avanzada de Office 365. ATP contra suplantación de identidad, aplica un conjunto de modelos de aprendizaje de máquina junto con los algoritmos de detección de suplantación a los mensajes entrantes para proporcionar protección para mercancías y lanza ataques de suplantación de identidad. Todos los mensajes están sujetas a un amplio conjunto de modelos de aprendizaje de máquina capacitados para detectar los mensajes de suplantación de identidad, junto con un conjunto de algoritmos avanzados que se usa para proteger contra diversos ataques de suplantación de usuario y dominio. ATP contra suplantación de identidad protege su organización de acuerdo a las directivas que se establecen por su Office 365 globales o los administradores de seguridad.
ms.openlocfilehash: cff25316f9a03bdfafd195eb408584ab8bca6343
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536036"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Funciones de ATP contra suplantación de identidad en Office 365

ATP contra suplantación de identidad se ofrece como parte de [La protección de amenaza avanzada de Office 365](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx). ATP contra suplantación de identidad, aplica un conjunto de modelos de aprendizaje de máquina junto con los algoritmos de detección de suplantación a los mensajes entrantes para proporcionar protección para mercancías y lanza ataques de suplantación de identidad. Todos los mensajes están sujetas a un amplio conjunto de modelos de aprendizaje de máquina capacitados para detectar los mensajes de suplantación de identidad, junto con un conjunto de algoritmos avanzados que se usa para proteger contra diversos ataques de suplantación de usuario y dominio. ATP contra suplantación de identidad protege su organización de acuerdo a las directivas que se establecen por su Office 365 globales o los administradores de seguridad.
  
Para obtener más información, vea [configurar las directivas de ATP contra suplantación de identidad en Office 365](set-up-atp-anti-phishing-policies.md).
  
> [!NOTE]
> Sólo está disponible en avanzada protección contra amenazas, disponibles con Office 365 Enterprise E5 ATP contra suplantación de identidad. Si su organización usa otra suscripción de Office 365 Enterprise, protección avanzada de amenaza puede adquirirse como un complemento. (Como un administrador global, en el centro de administración de Office 365, elija **facturación** \> **Agregar suscripciones**.) Para obtener más información acerca de las opciones del plan, consulte [comparar todos los Office 365 para planes de negocios](https://go.microsoft.com/fwlink/?linkid=844053). 
    
## <a name="how-atp-anti-phishing-works"></a>Cómo funciona la ATP contra suplantación de identidad
<a name="Howantiphishworks"> </a>

ATP anti-phishing comprueba los mensajes entrantes para los indicadores de que el mensaje puede ser la suplantación de identidad. Cada vez que un usuario está cubierto por una directiva de ATP (los datos adjuntos seguros, vínculos seguros o contra suplantación de identidad) se evalúa el mensaje entrante por máquina varios modelos que analizar el mensaje para determinar si la directiva se aplica al mensaje y la acción apropiada de aprendizaje tomar, en función de la directiva configurada.
  
ATP contra suplantación de identidad permite a los administradores globales de Office 365 o administradores de seguridad definir las directivas que proporcionan protección contra ataques de suplantación de identidad que incluyen la suplantación de usuarios o dominios. (o ambos). Los administradores globales de Office 365 o administradores de seguridad definición dentro de la directiva de usuario y los dominios se debe proteger contra los ataques de suplantación mediante una lista fija de usuarios o dominios o mediante el uso de inteligencia de buzón de correo. Inteligencia de buzón de correo es una descripción avanzada de hábitos de correo electrónico de un usuario y contactos personales. ATP aprende cómo cada usuario individual se comunica con otros usuarios dentro y fuera de la organización y genera un mapa de estas relaciones. Este mapa permite ATP conocer más detalles acerca de cómo asegurarse de que los mensajes de derecho son identificados como suplantación.
  
Las directivas de ATP contra suplantación de identidad se puede aplicar a un conjunto específico de personas o grupos de la organización, o a un dominio completo o todos los dominios personalizados. Para obtener más información, vea [configurar las directivas de ATP contra suplantación de identidad en Office 365](set-up-atp-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Cómo obtener ATP contra suplantación de identidad
<a name="Howtogetantiphish"> </a>

ATP contra suplantación de identidad es parte de avanzada protección contra amenazas, que se incluye en Office 365 Enterprise E5. También se puede adquirir protección avanzada de amenaza como un complemento de Office 365 Enterprise E1 o E3 Enterprise de Office 365. Para obtener más información acerca de las opciones del plan, consulte [comparar todos los Office 365 para planes de negocios](https://go.microsoft.com/fwlink/?linkid=844053).
  
ATP contra suplantación de identidad se aplica cuando una directiva contra suplantación de identidad, como una directiva de suplantación se configuran. (Vea [configurar las directivas de ATP contra suplantación de identidad en Office 365](set-up-atp-anti-phishing-policies.md)).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Cómo saber si ATP contra suplantación de identidad está en su lugar
<a name="IsantiphishOn"> </a>

Directivas de anti-phishing ATP deben definirse en orden para la protección a estar activo. Para que los modelos de aprendizaje de máquina de anti-phishing ATP estar activa para un usuario, ese usuario debe ser parte de datos adjuntos seguros definido, vínculos seguros o directiva contra suplantación de identidad. En la siguiente tabla se describe algunos escenarios de ejemplo. En cada uno de estos ejemplos, la organización está usando Office 365 Enterprise E5, que incluye la protección contra amenazas de avanzada.
  
|**Escenario de ejemplo**|**¿Se aplica en este caso ATP contra suplantación de identidad?**|
|:-----|:-----|
|Organización de Pat tiene E5 Enterprise de Office 365, pero nadie ha definido las directivas de ATP seguros los datos adjuntos, vínculos seguros ATP o ATP avanzado de suplantación de identidad todavía.|No. Aunque la característica está disponible, debe definirse al menos una directiva de ATP en orden de la máquina de ATP modelos de aprendizaje para que funcione. Para la suplantación una directiva contra suplantación de identidad de ATP también debe ser en su lugar.|
|Lee es un empleado del departamento de ventas de Contoso. Organización de Díaz tiene una directiva contra suplantación de identidad de ATP en contexto que se aplica a los empleados de finanzas sólo.|No. En este caso, ATP contra suplantación de identidad (modelos de equipo y protección de suplantación) se aplicará a los empleados de finanzas, pero otros empleados, incluido el departamento de ventas, no lo haría.|
|Ayer, un administrador de Office 365 en la organización de Jean establecer una directiva de ATP contra suplantación de identidad que se aplica a todos los empleados. Anteriormente en la actualidad, Jean recibió un mensaje de correo electrónico que incluya una suplantación cubierta por la directiva.|Sí. En este ejemplo, Jean tiene una licencia para protección avanzada de amenaza y se ha definido una directiva contra suplantación de identidad de ATP que incluye Jean. Normalmente tiene unos 30 minutos para una nueva directiva tener efecto en centros de datos; Dado que un día ha pasado en este caso, la directiva debe ser en vigor.|
   
## <a name="related-topics"></a>Temas relacionados
<a name="IsantiphishOn"> </a>

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Protección contra suplantación de identidad (phishing) en Office 365](anti-phishing-protection.md)
  
[Configurar directivas de ATP contra suplantación de identidad en Office 365](set-up-atp-anti-phishing-policies.md)
  
[Vínculos seguros de ATP en Office 365](atp-safe-links.md)
  
[Configurar directivas de ATP vínculos seguros en Office 365](set-up-atp-safe-links-policies.md)
  
[Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md)
  
[Configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)
  
[Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md)
  

