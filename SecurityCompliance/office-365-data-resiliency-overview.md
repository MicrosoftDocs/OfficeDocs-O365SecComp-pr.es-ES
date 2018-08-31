---
title: Resistencia de datos en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Comprender la resistencia de datos en Microsoft Office 365.
ms.openlocfilehash: 7d43c766615ff1520c6529427116c42795da8565
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536472"
---
# <a name="data-resiliency-in-office-365"></a>Resistencia de datos en Office 365

## <a name="introduction"></a>Introducción
Dada la naturaleza compleja de la informática en nube, Microsoft es cuidado de que no es un caso de si se producen errores, pero en su lugar cuando. En el diseño de nuestros servicios de nube para maximizar la confiabilidad y minimizar los efectos negativos en los clientes cuando surgen problemas. Hemos eliminado más allá de la estrategia de tradicional de depender de la infraestructura física complejo y hemos creado redundancia directamente en nuestros servicios de nube. Se usa una combinación de infraestructura física menos complejo y el software más inteligente que genera la resistencia de datos en nuestros servicios y ofrece una alta disponibilidad a nuestros clientes. 

## <a name="resiliency-and-recoverability-are-built-in"></a>La resistencia y la capacidad de recuperación están integradas 
Creación de resistencia y recuperación se inicia con el supuesto de que la infraestructura y los procesos subyacentes se producirá un error en algún momento: se producirá un error de hardware (infraestructura), los humanos cometen errores y software tendrá errores. Aunque sería incorrecto decir que los programadores de software no eran pensar en estas cosas antes de la nube, ¿cómo se administran estos problemas en una implementación típica de TI era muy diferente antes de la nube: 
- En primer lugar, protecciones de hardware e infraestructura fueron importantes. Esto significaba tener centros de datos con redundancia de red y capacidad importantes de confiabilidad del 99,99% necesarios, y se han implementado los servidores con clustering basado en hardware, fuentes de alimentación duales, interfaces de red duales y similares. 
- En segundo lugar, el proceso era un requisito imprescindible. Los equipos de operaciones mantienen procedimientos rigurosos, cambiar windows estaban empleados, y a menudo hubo sobrecarga de administración de proyecto importante. 
- En tercer lugar, implementación tuvo lugar a un ritmo glacial. Implementación de código sin necesidad de poseer el origen cuyo objetivo es esperar a versiones de revisiones y versión principal libera sustitución de hardware necesarios para y gastos de capital significativo. Además, la única manera de corregir un problema era reversión. Por lo tanto, la mayoría de las organizaciones de TI podrían implementar versiones principales sólo para evitar el trabajo para mantener actualizado. 
- Por último, la escala de los sistemas instalados, así como el nivel de su interconexión era tradicionalmente mucho menor que lo es ahora. 

En la actualidad, los clientes esperan continua innovación de Microsoft sin poner en peligro la calidad, y se trata de uno de los motivos por qué se crean los servicios y el software de Microsoft con la resistencia y la capacidad de recuperación en cuenta. 

## <a name="office-365-data-resiliency-principles"></a>Principios de resistencia de datos de Office 365 
Resistencia hace referencia a la capacidad de un servicio basado en la nube para soportar determinados tipos de errores y aún permanecen completamente funcional desde la perspectiva del cliente. Resistencia de datos significa que independientemente de qué errores se producen dentro de Office 365, datos importantes de clientes permanecen intacta y no afectado. Con ese fin, Office 365 servicios han sido diseñados alrededor de cinco principios de resistencia específico: 
- No hay datos críticos y no críticos. Datos no críticos (por ejemplo, si un mensaje se leyó) se pueden quitar en escenarios de error muy poco frecuente. Costo extrema, se deben proteger datos críticos (por ejemplo, los datos del cliente, como mensajes de correo electrónico). Como un objetivo de diseño, los mensajes de correo entregado siempre son esenciales y cosas como si se leyó un mensaje es que no sean críticos. 
- Copias de datos de clientes deben dividirse en zonas de tolerancia diferente o tantos defecto dominios como sea posible (por ejemplo, centros de datos, puede tener acceso a las credenciales único (proceso, servidor u operador)) para proporcionar aislamiento de errores. 
- Datos importantes de clientes se deben supervisar para errores de cualquier parte de atomicidad, coherencia, aislamiento, durabilidad (ACID). 
- Los datos de cliente deben ser protegidos de daños. Debe ser activamente digitalizado o supervisados, reparable y recuperables. 
- La mayoría los resultados de pérdida de datos de acciones de cliente, por lo que permiten a los clientes recuperar por sí mismos mediante una interfaz gráfica de usuario que les permite restaurar elementos eliminados accidentalmente. 
 
A través de la creación de nuestros servicios de nube a estos principios, junto con las pruebas y la validación, sólida Office 365 es capaz de satisfacer y superar los requisitos de los clientes mientras se asegura una plataforma para continua innovación y mejora. 

## <a name="related-links"></a>Vínculos relacionados

- [Trabajar con datos dañados](office-365-dealing-with-data-corruption.md)
- [Protección de malware y Ransomware](office-365-malware-and-ransomware-protection.md)
- [Supervisión y recuperación automática](office-365-monitoring-and-self-healing.md)
- [Resistencia de datos de Exchange](office-365-exchange-data-resiliency.md)
- [Resistencia de datos de SharePoint](office-365-sharepoint-data-resiliency.md)