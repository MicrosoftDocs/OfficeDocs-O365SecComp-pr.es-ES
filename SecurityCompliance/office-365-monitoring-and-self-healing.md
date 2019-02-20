---
title: Supervisión y recuperación automática de Office 365
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Información sobre la supervisión y las funcionalidades de Autorrecuperación de Office 365.
ms.openlocfilehash: 799c4dc97e9cc88dcc77f17b0f11ab76525012d9
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090522"
---
# <a name="office-365-monitoring-and-self-healing"></a>Supervisión y recuperación automática de Office 365
A partir de la escala de Office 365, sería imposible mantener los datos de los clientes resistentes y protegidos del malware sin una supervisión integrada que sea exhaustiva, lo que alerta de que es inteligente y tiene una solución automática y que es más rápida y fiable. La supervisión de un conjunto de servicios en la escala de Office 365 es muy desafiante. Es necesario crear nuevas metodologías y máximas y nuevos conjuntos de tecnología para que funcionen y administren el servicio en un entorno global conectado. Hemos alejado el enfoque de supervisión tradicional de recopilación de datos y filtrado para crear alertas de un enfoque basado en análisis de datos; tomar señales y confiar en esos datos y luego usar la automatización para recuperar o resolver el problema. Este enfoque ayuda a sacar a los seres humanos de la ecuación de recuperación, que a su vez hace que las operaciones sean menos costosas, rápidas y menos propensos a errores. 

La supervisión de Office 365 es una colección de tecnologías que comprenden nuestro motor de información de datos, que se basa en Azure, SQL Azure y la [tecnología de bases de datos de secuencias de código abierto](http://cassandra.apache.org/). Está diseñado para recopilar y agregar datos y obtener conclusiones. Actualmente, procesa más de 500 millones eventos por hora de más de 100.000 servidores (aprox. 15 TB por día) dispersos en docenas de centros de información en varias regiones y estas cifras están creciendo. 

Office 365 usa *la supervisión externa*, que implica la creación de transacciones sintéticas para probar todo lo que es importante. Por ejemplo, en Exchange Online cada escenario está probando cada base de datos en todo el mundo cada cinco minutos de forma dispersa, lo que proporciona una cobertura casi continua de todo lo que vive en el sistema. Desde varias ubicaciones, 250 millones transacciones de prueba por día se realizan para crear una línea base sólida o un latido para el servicio. 

Office 365 también usa el concepto de *alerta roja*, que reduce todas las señales de supervisión de todos los equipos de nuestros centros de proceso de trabajo a algo manejable por un humano. El concepto es bastante sencillo: Si ocurre algo en varias señales, debe haber algo en marcha. No se trata de crear confianza en una señal, ya que se trata de tener una fidelidad razonable para cada señal, de modo que pueda obtener una mayor precisión. Este sistema de supervisión es tan potente que no disponemos del personal 24x7 para supervisar nuestros monitores; todo lo que tenemos es la maquinaria que se activa si detecta un problema, en cuyo caso irá a la página del personal de llamada adecuado o, en la mayoría de los casos, el problema será seguir adelante y resolver el problema. Una vez que empezamos a recopilar señales y a crear alertas rojas en ellas, podemos empezar a triangular en todas nuestras particiones de servicio. 

Basándose en la combinación de la alerta de error y las alertas en rojo, esta alerta indica exactamente qué componentes podrían tener un problema y que el sistema intentará corregir el problema por sí mismo reiniciando un servidor de buzones de correo. 

Además de las funcionalidades de recuperación automática, como la restauración de una sola página, Exchange Online incluye varias características que adoptan un enfoque para la supervisión y la reparación automática que se centra en preservar la experiencia del usuario final. Estas características incluyen la *disponibilidad administrada*, que proporciona acciones de recuperación y supervisión integradas, y AutoReseed, que restaura automáticamente la redundancia de la base de datos después de un error en el disco. 

## <a name="managed-availability"></a>Disponibilidad administrada 
La disponibilidad administrada proporciona una solución de comprobación de estado y recuperación nativa que supervisa y protege la experiencia del usuario final a través de acciones orientadas a la recuperación. La disponibilidad administrada es la integración de acciones de recuperación y supervisión integradas con la plataforma de alta disponibilidad de Exchange. Está diseñado para detectar y recuperarse de los problemas tan pronto como se producen y detectados por el sistema. A diferencia de las soluciones y técnicas de supervisión externas anteriores de Exchange, la disponibilidad administrada no intenta identificar o comunicar la causa raíz de un problema. En su lugar, se centra en los aspectos de recuperación que abordan tres áreas clave de la experiencia del usuario final: 
- **Disponibilidad** : ¿pueden los usuarios tener acceso al servicio? 
- **Latencia** : ¿Cómo es la experiencia de los usuarios? 
- **Errores** : ¿los usuarios pueden realizar lo que quieren? 

La disponibilidad administrada es una característica interna que se ejecuta en cada servidor de Office 365 que ejecuta Exchange Online. Sondea y analiza cientos de métricas de salud cada segundo. Si se detecta que hay algún error, la mayoría de las veces se corrige automáticamente. Pero siempre habrá problemas que la disponibilidad administrada no podrá arreglar por sí mismo. En estos casos, la disponibilidad administrada remitirá el problema a un equipo de soporte técnico de Office 365 por medio del registro de eventos. 

## <a name="autoreseed"></a>AutoReseed 
Los servidores de Exchange Online se implementan en una configuración que almacena varias bases de datos y sus secuencias de registro en el mismo disco que no es RAID. Esta configuración a menudo se conoce como *un conjunto de discos* (JBOD) porque no se usan mecanismos de redundancia de almacenamiento, como RAID, para duplicar los datos en el disco. Cuando se produce un error en un disco en un entorno JBOD, los datos en ese disco se pierden. 

Dado el tamaño de Exchange Online y el hecho que se implementó en él, hay millones de unidades de disco, los errores de la unidad de disco son una ocurrencia regular en Exchange Online. De hecho, más de 100 errores cada día. Cuando se produce un error en un disco en una implementación empresarial local, un administrador debe reemplazar manualmente el disco con errores y restaurar los datos afectados. En una implementación en la nube, el tamaño de Office 365, la necesidad de que los operadores (administradores de nube) reemplacen los discos manualmente no sea práctico ni económicamente viable. 

La reinicialización automática, o *AutoReseed*, es una característica que reemplaza a la acción controlada normalmente por operador en respuesta a un error de disco, a un evento de daños en la base de datos o a otro problema que requiere la reinicialización de una copia de base de datos. AutoReseed está diseñada para restaurar automáticamente la redundancia de base de datos después de un error de disco mediante el uso de discos de reserva que se han aprovisionado en el sistema. Si se produce un error en un disco, las copias de base de datos almacenadas en ese disco se reinicializan automáticamente en un disco de reserva preconfigurado en el servidor, con lo que se restaura la redundancia. 