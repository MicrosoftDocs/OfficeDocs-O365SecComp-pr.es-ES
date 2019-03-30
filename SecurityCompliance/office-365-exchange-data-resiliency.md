---
title: Resistencia de datos de Exchange de Office 365
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
description: Una explicación de los diversos aspectos de la resistencia de datos en Exchange Online y Office 365.
ms.openlocfilehash: 9e61efaf95d466fcb268e12317c7feab0701c062
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004237"
---
# <a name="exchange-online-data-resiliency-in-office-365"></a>Resistencia de datos de Exchange online en Office 365

## <a name="introduction"></a>Introducción
Hay dos tipos de daños que pueden afectar a una base de datos de Exchange: los daños físicos, que suelen deberse a problemas de hardware (en particular, del hardware de almacenamiento) y a los daños lógicos, que se producen debido a otros factores. Por lo general, hay dos tipos de daños lógicos que pueden producirse dentro de una base de datos de Exchange: 
- **Daño lógico de base** de datos: la suma de comprobación de la página de la base de datos coincide, pero los datos de la página son incorrectos lógicamente. Esto puede ocurrir cuando el motor de base de datos (el motor de almacenamiento extensible (ESE)) intenta escribir una página de base de datos y, aunque el sistema operativo devuelve un mensaje de operación correcta, los datos nunca se escriben en el disco o se escriben en el lugar equivocado. Esto se conoce como un *vaciado perdido*. ESE incluye numerosas características y protecciones diseñadas para evitar daños físicos en una base de datos y otros escenarios de pérdida de datos. Para evitar que los vaciados perdidos pierdan datos, ESE incluye un mecanismo de detección de vaciado perdido en la base de datos junto con una característica (restauración de una sola página) para corregirlo. 
- **Almacenar los daños lógicos** : los datos se agregan, eliminan o manipulan de una manera que el usuario no espera. Normalmente, estos casos son causados por aplicaciones de otros fabricantes. Solo se considera un daño, por lo general, porque el usuario lo ve como un daño. El almacén de Exchange considera que la transacción que produce los daños de lógica es una serie de operaciones MAPI válidas. Las características de [conservación local](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) de Exchange Online proporcionan protección para almacenar los daños lógicos (porque impide que un usuario o una aplicación eliminen el contenido de forma permanente). 

Exchange Online realiza varias comprobaciones de coherencia en los archivos de registro replicados durante la inspección de registros y la reproducción de registros. Estas comprobaciones de coherencia impiden que el sistema replique los daños físicos. Por ejemplo, durante la inspección de registros, hay una comprobación de integridad física que comprueba el archivo de registro y valida que la suma de comprobación registrada en el archivo de registro coincida con la suma de comprobación generada en la memoria. Además, se examina el encabezado del archivo de registro para asegurarse de que la firma del archivo de registro registrada en el encabezado del registro coincide con la del archivo de registro. Durante la reproducción del registro, el archivo de registro sufre más análisis. Por ejemplo, el encabezado de la base de datos también contiene la firma del registro que se compara con la firma del archivo de registro para asegurarse de que coinciden. 

La protección contra daños en los datos de buzones de correo en Exchange Online se consigue mediante el uso de la protección de datos nativa de Exchange, una estrategia de resistencia que aprovecha la replicación en el nivel de la aplicación en varios servidores y varios centros de datos junto con otros características que ayudan a evitar la pérdida de datos debido a daños o a otros motivos. Estas características incluyen características nativas administradas por Microsoft o la propia aplicación de Exchange Online, como:

- [Grupos de disponibilidad de datos](https://docs.microsoft.com/exchange/back-up-email)
- Corrección de bits único 
- Análisis de bases de datos en línea 
- Detección de vaciado perdida 
- Restauración de una sola página 
- Servicio de replicación de buzones 
- Comprobaciones del archivo de registro 
- Implementación en un sistema de archivos resistente 

Para obtener más información sobre las características nativas enumeradas anteriormente, haga clic en los hipervínculos anteriores y vea a continuación para obtener información adicional y detalles sobre los elementos sin hipervínculos. Además de estas características nativas, Exchange Online también incluye características de resistencia de datos que los clientes pueden administrar, como: 
- [Recuperación de elemento único (habilitada de forma predeterminada)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [Conservación local y retención por juicio](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [Retención de elementos eliminados y buzones de correo eliminados temporalmente (ambos habilitados de forma predeterminada)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>Grupos de disponibilidad de base de datos 
Todas las bases de datos de buzones de correo de Office 365 se hospedan en un [grupo de disponibilidad de base de datos (Dag)](https://docs.microsoft.com/exchange/back-up-email) y se replican en centros de datos independientes geográficamente dentro de la misma región. La configuración más común es cuatro copias de bases de datos en cuatro centros de datos; sin embargo, algunas regiones tienen menos centros de datos (las bases de datos se replican en tres centros de datos en la India y dos centros de datos en Australia y Japón). Sin embargo, en todos los casos, todas las bases de datos de buzones tienen cuatro copias que se distribuyen en varios centros de datos, lo que garantiza que los datos del buzón de correo estén protegidos del software, el hardware o incluso los errores del centro de datos. 

A partir de estas cuatro copias, tres de ellas están configuradas como de alta disponibilidad. La cuarta copia se configura como una [copia retrasada](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies)de la base de datos. La copia de base de datos atrasada no está destinada a la recuperación de buzones individuales o la recuperación de elementos de buzón. Su objetivo es proporcionar un mecanismo de recuperación para el caso excepcional de que se produzcan daños lógicos catastróficos en todo el sistema. 

Las copias de base de datos atrasadas en Exchange online están configuradas con un tiempo de retardo de reproducción de archivo de registro de siete días. Además, el administrador de reTardo de reproducción de Exchange está habilitado para proporcionar la reproducción dinámica de archivos de registro para las copias retrasadas a fin de permitir copias de bases de datos atrasadas para la reparación automática y la administración del crecimiento del archivo de registro. Aunque las copias de base de datos retrasadas se usan en Exchange Online, es importante comprender que no son una copia de seguridad de un momento dado garantizado. Las copias de base de datos atrasadas en Exchange Online tienen un umbral de disponibilidad, normalmente alrededor del 90%, debido a los períodos en los que el disco que contiene una copia retrasada se pierde debido a un error en el disco, la copia retrasada se convierte en una copia de alta disponibilidad (debido a la reproducción automática), también como los períodos en los que la copia de base de datos retrasada vuelve a generar la cola de reproducción de registros. 

## <a name="transport-resilience"></a>Resistencia de transporte 
Exchange Online incluye dos características principales de resistencia de transporte: la redundancia de instantáneas y la red de seguridad. La redundancia de instantáneas mantiene una copia redundante de un mensaje mientras está en tránsito. La red de seguridad mantiene una copia redundante de un mensaje después de que el mensaje se entregue correctamente. 

Con la redundancia de instantáneas, cada servidor de transporte de Exchange Online hace una copia de todos los mensajes que recibe antes de confirmar que recibe correctamente el mensaje al servidor de envío. Esto hace que todos los mensajes de la canalización de transporte sean redundantes mientras están en tránsito. Si Exchange Online determina que el mensaje original se perdió en el tránsito, se entrega una copia redundante del mensaje. 

Red de seguridad es una cola de transporte que está asociada con el servicio de transporte en un servidor de buzones de correo. Esta cola almacena copias de mensajes correctamente procesados por el servidor. Cuando una base de datos de buzones o un error del servidor requieren activar una copia obsoleta de la base de datos de buzones, los mensajes de la cola de seguridad de la red se reenvían automáticamente a la nueva copia activa de la base de datos de buzones. La red de seguridad también es redundante, lo que elimina el transporte como un punto único de error. Usa el concepto de una red de seguridad principal y una red de seguridad de instantáneas donde la red de seguridad principal no está disponible durante más de 12 horas, las solicitudes de reenvío se convierten en solicitudes de reenvío de instantánea y los mensajes se vuelven a entregar desde la red de seguridad de instantáneas.

Los reenvíos de mensajes desde la red de seguridad se inician automáticamente mediante el componente Active Manager del servicio de replicación de Microsoft Exchange que administra los Dag y las copias de bases de datos de buzones. No se requiere ninguna acción manual para reenviar mensajes desde la red de seguridad. 

## <a name="single-bit-correction"></a>Corrección de bits único 
ESE incluye un mecanismo para detectar y resolver errores CRC de un solo bit (también conocidos como volteo de un bit) que son el resultado de errores de hardware (y, como tal, representan daños físicos). Cuando se producen estos errores, ESE los corrige automáticamente y registra un evento en el registro de eventos. 

## <a name="online-database-scanning"></a>Análisis de bases de datos en línea 
El análisis de base de datos en línea (también conocido como suma de comprobación de *base de datos*) es el proceso en el que ese usa un comprobador de coherencia de la base de datos para leer cada página y comprobar si hay errores El objetivo principal es detectar daños físicos y vaciados perdidos que podrían no ser detectados por operaciones transaccionales. El análisis de bases de datos también realiza operaciones de bloqueo posterior a la tienda. El espacio se puede perder debido a bloqueos y el análisis de base de datos en línea busca y recupera el espacio perdido. El sistema está diseñado pensando en que todas las bases de datos se digitalizan completamente una vez cada siete días. 

## <a name="lost-flush-detection"></a>Detección de vaciado perdida 
Un vaciado perdido se produce cuando una operación de escritura de base de datos que el subsistema de disco o el sistema operativo devolvió como completada no se escribió en el disco o se escribió en una ubicación incorrecta. Las incidencias de vaciado perdidas pueden resultar en daños lógicos de base de datos, por lo que, para evitar que los vaciados perdidos provoquen pérdida de datos, ESE incluye un mecanismo de detección de vaciado perdido. A medida que las páginas de base de datos se escriben en copias pasivas, se realiza una comprobación de los vaciados perdidos en la copia activa. Si se detecta un vaciado perdido, ESE puede reparar el proceso mediante un proceso de revisión de página. 

## <a name="single-page-restore"></a>Restauración de una sola página 
La restauración de página única, aka *Page Patching*, es un proceso automático en el que las páginas de base de datos dañadas se reemplazan por copias en buen estado de una réplica en buen estado. El proceso de reparación de una página dañada depende de si la copia de la base de datos está activa o pasiva. Cuando una copia de base de datos activa encuentra una página dañada, puede copiar una página de una de sus réplicas, siempre que la página que copie esté completamente actualizada. Esto se consigue al colocar una solicitud para la página en la secuencia de registro, que es la base de la replicación de la base de datos de buzones. En cuanto una réplica detecta la solicitud de la página, le responde enviando una copia de la página a la copia de la base de datos solicitante. La restauración de página única también proporciona un mecanismo de comunicación asincrónica del activo para solicitar una página de las réplicas, incluso si las réplicas están actualmente sin conexión. 

En caso de que se dañe una copia de base de datos pasiva, incluida una copia de base de datos atrasada, ya que estas copias siempre están detrás de su copia activa, siempre es seguro copiar cualquier página de la copia activa a una copia pasiva. Una copia de base de datos pasiva es, por naturaleza, altamente disponible, por lo que, durante el proceso de revisión de página, se suspende la reproducción de registros, pero la copia de registros sigue. La copia pasiva de la base de datos recupera una copia de la página dañada de la copia activa, espera hasta que se copie e inspeccione el archivo de registro que cumpla el requisito de generación de registro máximo necesario y, a continuación, se revisa la página dañada. Una vez que se ha aplicado la revisión a la página, se reanuda la reproducción del registro. El proceso es el mismo para la copia retrasada de la base de datos, excepto en que la base de datos atrasada reproduce primero todos los archivos de registro que son necesarios para lograr un estado revisable. 

## <a name="mailbox-replication-service"></a>Servicio de replicación de buzones 
Mover buzones es una parte fundamental de la administración de un servicio de correo electrónico a gran escala. Siempre se actualizan las tecnologías y las actualizaciones de hardware y versiones, por lo que tiene un sistema sólido y acelerado que permite a nuestros ingenieros realizar este trabajo mientras se mantiene el buzón de correo transparente para los usuarios (asegurándose de que permanecen en línea). durante todo el proceso) es clave y se asegura de que el proceso se escale correctamente a medida que los buzones de correo se agrandan y más grandes. 

El servicio de replicación de buzones de correo de Exchange (MRS) es responsable de mover buzones entre bases de datos. Durante el movimiento, MRS realiza una comprobación de coherencia en todos los elementos del buzón. Si se encuentra un problema de coherencia, MRS corregirá el problema o pasará por alto los elementos dañados, con lo que se quitará el daño del buzón. 

Como MRS es un componente de Exchange Online, podemos realizar cambios en su código para solucionar nuevas formas de daños que se detectan en el futuro. Por ejemplo, si se detecta un problema de coherencia que MRS no puede corregir, podemos analizar el daño, cambiar el código MRS y corregir la incoherencia (si sabemos cómo). 

## <a name="log-file-checks"></a>Comprobaciones del archivo de registro 
Todos los archivos de registro de transacciones generados por una base de datos de Exchange experimentan varias formas de comprobaciones de coherencia. Cuando se crea un archivo de registro, lo primero que debe hacer es escribir un patrón de bits y, a continuación, se realiza una serie de escrituras en el registro. Esto permite a Exchange Online ejecutar una serie de comprobaciones (vaciado perdido, CRC y otras comprobaciones) para validar cada archivo de registro a medida que se escribe y de nuevo cuando se replica. 

## <a name="deployment-on-resilient-file-system"></a>Implementación en un sistema de archivos resistente 
Para ayudar a evitar que se produzcan daños en el nivel del sistema de archivos, Exchange Online se está implementando en particiones del sistema de archivos resistente (ReFS) para proporcionar funciones de recuperación mejoradas. ReFS es un sistema de archivos en Windows Server 2012 y versiones posteriores diseñado para ser más resistente contra daños en los datos, lo que maximiza la disponibilidad e integridad de los datos. Concretamente, ReFS incorpora mejoras en la forma en que se actualizan los metadatos, lo que ofrece una mejor protección para los datos y reduce los casos de corrupción de datos. También usa las sumas de comprobación para comprobar la integridad de los datos de archivo y los metadatos, lo que garantiza que se encuentren y reparen fácilmente los datos dañados. 

Exchange Online aprovecha varias ventajas de ReFS: 
- Una mayor resistencia en la integridad de los datos significa menos incidentes de daños en los datos. La reducción del número de incidentes de daños implica menos reinicializaciones de base de datos innecesarias. 
- La suma de comprobación que se ejecuta en los metadatos permite detectar casos de daños de forma rápida y más determinista, lo que nos permite corregir los daños en los datos del cliente antes de que ocurran errores en gris en los volúmenes de datos.
- Diseñado para funcionar correctamente con conjuntos de datos extremadamente grandes (petabytes y más grandes) sin impacto en el rendimiento
- Compatibilidad con otras características usadas por Exchange Online, como el cifrado de BitLocker. 

Exchange Online también se beneficia de otras características de ReFS: 
- **Integridad (secuencias de integridad)** : ReFS almacena los datos de una manera que los protege de muchos de los errores comunes que normalmente pueden provocar la pérdida de datos. Office 365 Search usa secuencias de integridad para ayudar con la detección de daños en el disco inicial y las sumas de comprobación del contenido de los archivos. La característica también reduce los incidentes de daños causados por "escrituras incompletas" (cuando una operación de escritura no se completa debido a interrupciones de energía, etc.). 
- **Availability (Valor_residual)** : ReFS da prioridad a la disponibilidad de los datos. Históricamente, los sistemas de archivos solían ser susceptibles de daños en los datos, lo que requeriría que el sistema se desconectase para su reparación. Aunque rara vez se produce algún daño, ReFS implementa Salvage, una característica que elimina los datos dañados del espacio de nombres en un volumen activo y garantiza que los datos correctos no se ven perjudicados por los datos no reparables. La aplicación de la característica de recuperación y el aislamiento de los datos dañados para los volúmenes de bases de datos de Exchange Online significa que podemos mantener las bases de datos no afectadas en un volumen dañado en buen estado entre el momento de la corrupción y la acción de reparación. Esto aumenta la disponibilidad de las bases de datos que normalmente se verían afectadas por problemas de daños en el disco. 