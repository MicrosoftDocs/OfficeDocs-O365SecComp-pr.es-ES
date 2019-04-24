---
title: Resistencia de datos en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Comprenda la resistencia de los datos en Microsoft Office 365.
ms.openlocfilehash: ef8f3f9599f187e26885cb8ff81559546cc49c50
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262862"
---
# <a name="data-resiliency-in-office-365"></a>Resistencia de datos en Office 365

## <a name="introduction"></a>Introducción
Teniendo en cuenta la naturaleza compleja de la informática en la nube, Microsoft es conscientes de que no se trata de un caso en el que las cosas vayan mal, sino cuando. Diseñamos nuestros servicios en la nube para maximizar la confiabilidad y minimizar los efectos negativos en los clientes cuando las cosas salen mal. Hemos superado la estrategia tradicional de confiar en una infraestructura física compleja y hemos construido la redundancia directamente en nuestros servicios en la nube. Usamos una combinación de una infraestructura física menos compleja y un software más inteligente que construye la resistencia de los datos en nuestros servicios y ofrece alta disponibilidad a nuestros clientes. 

## <a name="resiliency-and-recoverability-are-built-in"></a>La resistencia y la capacidad de recuperación están integradas 
La creación de la resistencia y la recuperación comienza con la suposición de que se producirá un error en la infraestructura y los procesos subyacentes en algún punto: el hardware (infraestructura) no funcionará, los seres humanos harán errores y el software tendrá errores. Aunque sería incorrecto que los desarrolladores de software no estuvieran pensando en estos aspectos antes de la nube, el modo en que se controlaban estos problemas en una implementación de ti típica era muy diferente antes de la nube: 
- En primer lugar, las protecciones de hardware y de la infraestructura eran significativas. Esto significaba que los centros de recursos con una confiabilidad de 99,99% requerían una potencia y redundancia de red importantes, y los servidores se implementaban con clústeres basados en hardware, dos fuentes de alimentación, dos interfaces de red y similares. 
- Segundo, el proceso es primordial. Los equipos de operaciones mantuvieron rigurosos procedimientos, cambios en Windows y, a menudo, un overhead importante en la administración de proyectos. 
- En tercer lugar, la implementación se realizó a un ritmo glacial. La implementación de código sin la propiedad del origen significaba que se esperaba la publicación de versiones de revisión, y las versiones de versiones principales implicaban sustitución de hardware y una importante inversión en capital. Además, la única forma de corregir un problema era revertir. Por lo tanto, la mayoría de las organizaciones de ti distribuirían solo las versiones principales para evitar el trabajo de mantener actualizada. 
- Por último, la escala de los sistemas implementados, así como el nivel de su interconexión es históricamente mucho más pequeña de lo que ahora es. 

Hoy en día, los clientes esperan una innovación continua de Microsoft sin poner en riesgo la calidad, y esto es uno de los motivos por los que los servicios y el software de Microsoft se construyen teniendo en cuenta la resistencia y la capacidad de recuperación. 

## <a name="office-365-data-resiliency-principles"></a>Principios de resistencia de datos de Office 365 
La resistencia se refiere a la capacidad de un servicio basado en la nube para resistir determinados tipos de errores y seguir funcionando completamente desde el punto de vista de los clientes. La resistencia de los datos significa que, independientemente de los errores que se produzcan en Office 365, los datos críticos del cliente permanecen intactos y no se ven afectados. Para ello, los servicios de Office 365 se han diseñado en torno a cinco principios de resistencia específicos: 
- Hay datos críticos y no críticos. Los datos no críticos (por ejemplo, si se ha leído un mensaje) se pueden interrumpir en escenarios de errores poco comunes. Los datos críticos (por ejemplo, datos de clientes como los mensajes de correo electrónico) deben protegerse con un costo muy bajo. Como objetivo de diseño, los mensajes de correo entregados son siempre críticos y los elementos como si se ha leído un mensaje no son críticos. 
- Las copias de los datos de los clientes se deben separar en distintas zonas de errores o en tantos dominios de error como sea posible (por ejemplo, centros de datos, accesibles mediante credenciales únicas (proceso, servidor u operador) para proporcionar aislamiento de errores. 
- Los datos críticos de los clientes deben supervisarse para conmutar por error cualquier parte de la atomicidad, la coherencia, el aislamiento y la durabilidad (ACID). 
- Los datos de los clientes deben protegerse de daños. Debe analizarse o supervisarse de forma activa, repararse y recuperarse. 
- La mayoría de los resultados de pérdida de datos de acciones del cliente permiten que los clientes se recuperen por su cuenta mediante una interfaz gráfica de usuario que les permite restaurar los elementos eliminados accidentalmente. 
 
Mediante la creación de nuestros servicios en la nube para estos principios, junto con una sólida prueba y validación, Office 365 es capaz de cumplir y superar los requisitos de los clientes, al tiempo que garantiza una plataforma para una innovación y mejora continuas. 

## <a name="related-links"></a>Vínculos relacionados

- [Trabajar con datos dañados](office-365-dealing-with-data-corruption.md)
- [Protección de malware y Ransomware](office-365-malware-and-ransomware-protection.md)
- [Supervisión y recuperación automática](office-365-monitoring-and-self-healing.md)
- [Resistencia de datos de Exchange](office-365-exchange-data-resiliency.md)
- [Resistencia de datos de SharePoint](office-365-sharepoint-data-resiliency.md)