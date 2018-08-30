---
title: Resolución automática de problemas y supervisión de Office 365
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
description: Información sobre la supervisión de Office 365 y funcionalidades de Autorrecuperación.
ms.openlocfilehash: ff9471eaa6117ca3d7761549bca9ab629020fe79
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535796"
---
# <a name="office-365-monitoring-and-self-healing"></a>Resolución automática de problemas y supervisión de Office 365
Dado que la escala de Office 365, sería imposible mantener los datos de cliente resistente y seguros de malware sin supervisión integradas que exhaustiva, alertas que es inteligente y resolución automática de problemas son rápida y confiable. Supervisión de un conjunto de servicios en la escala de Office 365 es muy difícil. Las máximas nueva y metodologías necesitan para presentarse, y todo nuevos conjuntos de tecnología necesarios para crearse para operar y administrar el servicio en un entorno global conectado. Nos hemos alejará el enfoque de recolección de datos de supervisión y el filtrado tradicional para crear alertas para un enfoque que se basa en el análisis de datos; poner las señales y creación de confianza en que los datos y, a continuación, utilizar la automatización para recuperar o resolver el problema. Este enfoque ayuda a tomar a personas fuera de la ecuación de recuperación, a su vez lo que hace que las operaciones de error menos costoso, más rápido y menos propensas a. 

Fundamental a Office 365 supervisión es una colección de tecnologías que conforman nuestro motor de entendimiento de datos, que se basa en Azure, SQL Azure y [Abrir origen transmisión por secuencias de tecnología de base de datos](http://cassandra.apache.org/). Está diseñado para recopilar y agregar datos y llegar a conclusiones. Actualmente, procesa los eventos de más de 500 millones por hora de servidores más de 100.000 (~ 15 TB por día) diseminados por docenas de centros de datos en muchas regiones, y estos números están creciendo. 

Office 365 usa *fuera de supervisión*, que implica la creación de las transacciones sintéticas para probar todo lo que es importante. Por ejemplo, en Exchange Online cada escenario está probando cada base de datos en todo el mundo cada cinco minutos de forma dispersas, proporcionar cerca de la cobertura continua de todos los elementos que se encuentra en el sistema. Desde varias ubicaciones, se realizan las transacciones de la prueba de 250 millones por día para crear una línea de base sólida o heartbeat para el servicio. 

Office 365 también usa el concepto de *Alerta roja*, que reduce el tamaño hacia abajo todas las señales de supervisión de todos los equipos en nuestros centros de datos en algo fácil de administrar un ser humano. El concepto es bastante sencillo: si algo que sucede a través de varias señales, debe haber algo. No es sobre la creación de confianza en una señal, se trata de tener fidelidad razonable para cada señal de manera que se obtenga una mayor precisión. Este sistema de supervisión, es tan eficaz que no disponemos de personal de 24 horas, 7 inspeccionando a nuestros monitores; lo único que tenemos es la máquina que se activa si se detecta un problema, en cuyo caso que escribe el personal en llamada adecuado o más a menudo como es el caso, se acaba vamos y solucionar el problema. Una vez se iniciar la recopilación de las señales y generar alertas rojas fuera de ellos, podemos empezar hacer triangular en todas las particiones de nuestro servicio. 

En función de la combinación de la alerta de error y las alertas de rojo, esta alerta indica exactamente qué componentes podría tener un problema, y que el sistema se va a probar corregir el problema por sí mismo mediante el reinicio de un servidor de buzones. 

Además de capacidades tales como la restauración de página único de Autorrecuperación, Exchange Online incluye varias características que adoptan un enfoque para supervisar y resolución automática de problemas que se centra en la conservación de la experiencia del usuario final. Estas características incluyen *Disponibilidad administrada*, que proporciona las acciones de recuperación y supervisión integradas y AutoReseed, que restaura automáticamente la redundancia de base de datos después de un error de disco. 

## <a name="managed-availability"></a>Disponibilidad administrada 
Disponibilidad administrada proporciona una solución de recuperación y comprobación de mantenimiento nativo que supervisa y protege la experiencia del usuario final a través de acciones de recuperación. Disponibilidad administrada es la integración de las acciones de recuperación y supervisión integradas con la plataforma de alta disponibilidad de Exchange. Se ha diseñado para detectar y recuperarse de problemas tan pronto como se producen y se descubren por el sistema. A diferencia de las soluciones de supervisión externas anteriores y técnicas para Exchange, no intente disponibilidad administrada identificar o comunicarse la causa raíz de un problema. En su lugar, se se centra en los aspectos de recuperación que abarcan tres áreas clave de la experiencia del usuario final: 
- **Disponibilidad** : los usuarios pueden tener acceso al servicio? 
- **Latencia** : ¿cómo es la experiencia de los usuarios? 
- **Errores** - los usuarios son capaces de llevar a cabo lo que desean? 

Disponibilidad administrada es una característica interna que se ejecuta en cada servidor de Office 365 ejecuta Exchange Online. Sondea y analiza cientos de métricas de mantenimiento cada segundo. Si se encuentra algo que sea incorrecto, la mayor parte de la hora es fija automáticamente. Pero siempre habrá problemas que disponibilidad administrada no podrá corregir su propio. En esos casos, disponibilidad administrada escalará el problema a un equipo de soporte técnico de Office 365 por medio de registro de eventos. 

## <a name="autoreseed"></a>AutoReseed 
Los servidores de Exchange Online se implementan en una configuración que almacena varias bases de datos y sus secuencias de registro en el mismo disco que no son RAID. Esta configuración a menudo se conoce como *sólo un montón de discos* (JBOD) debido a que no hay mecanismos de redundancia de almacenamiento, como RAID, se usan para duplicar los datos en el disco. Cuando se produce un error en un disco en un entorno de JBOD, se pierden los datos en ese disco. 

Al indicar el tamaño de Exchange Online y el hecho de que se implementa en él son millones de unidades de disco, errores de la unidad de disco son una ocurrencia regular en Exchange Online. De hecho, más de 100 producirá un error en todos los días. Cuando se produce un error en un disco en una implementación de la empresa local, un administrador debe reemplazar el disco con errores y restaurar los datos afectados manualmente. En una implementación de nube el tamaño de Office 365, tener operadores (administradores de la nube) reemplazar manualmente los discos no es práctico ni económica viable. 

Reinicialización automática o *AutoReseed*, es una característica que es el reemplazo de ¿qué es normalmente controlado por el operador de acción en respuesta a un error en el disco, daño de base de datos o a otro problema que requiera un reinicializar de una copia de la base de datos. AutoReseed está diseñado para restaurar automáticamente la redundancia de base de datos después de un error de disco mediante el uso de discos de repuesto que ya han aprovisionados en el sistema. Si se produce un error en un disco, las copias de base de datos almacenadas en dicho disco se reinicializar automáticamente a un disco de repuesto preconfigurado en el servidor, restaurando así redundancia. 