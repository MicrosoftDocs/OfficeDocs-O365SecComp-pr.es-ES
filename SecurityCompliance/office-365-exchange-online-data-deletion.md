---
title: Eliminación de datos de Exchange online de Office 365
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
description: Cómo se administran las eliminaciones de datos flexibles y nítidas en Exchange Online.
ms.openlocfilehash: 977beb41469e0015e22aea6750cfd657d9ee3b39
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262692"
---
# <a name="exchange-online-data-deletion-in-office-365"></a>Eliminación de datos de Exchange online en Office 365
En Exchange Online, hay dos tipos de eliminaciones: eliminaciones de software y eliminaciones de hardware. Esto se aplica tanto a los buzones de correo como a los elementos de un buzón.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>Buzones eliminados temporalmente y eliminados permanentemente
Un buzón de usuario eliminado temporalmente es un buzón que se ha eliminado mediante el centro de administración de Microsoft 365 o el cmdlet Remove-Mailbox y que todavía se ha estado en la papelera de reciclaje de Azure Active Directory durante menos de 30 días. Un buzón se puede eliminar de forma temporal de cualquiera de las siguientes maneras:
- El buzón de usuario asociado a la cuenta de usuario de Azure Active Directory se ha eliminado temporalmente (el objeto de usuario está fuera del ámbito o en el contenedor de la papelera de reciclaje).
- El buzón de usuario asociado a la cuenta de usuario de Azure Active Directory se ha eliminado permanentemente pero el buzón de Exchange Online está en retención por juicio o de exhibición de documentos electrónicos.
- El buzón de usuario asociado a la cuenta de usuario de Azure Active Directory se ha purgado en los últimos 30 días; la longitud máxima de retención de Exchange Online mantendrá el buzón de correo en un estado de eliminación temporal antes de que se purgue de forma permanente y no se puedan recuperar.

Un buzón de usuario eliminado permanentemente es un buzón que se ha eliminado de una de las siguientes maneras:
- El buzón de usuario se ha eliminado temporalmente durante más de 30 días y el usuario asociado de Azure Active Directory se ha eliminado permanentemente. Todo el contenido de los buzones de correo, como los correos electrónicos, los contactos y los archivos se eliminan permanentemente.
- La cuenta de usuario asociada con el buzón de usuario se ha eliminado permanentemente de Azure Active Directory. El buzón de usuario se ha eliminado temporalmente en Exchange Online y permanece en un estado de eliminación temporal durante 30 días. Si en el período de 30 días un nuevo usuario de Azure Active Directory se sincroniza desde la cuenta de destinatario original con el mismo **ExchangeGuid** o **ArchiveGuid**, y esa nueva cuenta tiene una licencia para Exchange Online, esto hará que se elimine de forma permanente el el buzón de correo del usuario original. Todo el contenido de los buzones de correo, como los correos electrónicos, los contactos y los archivos se eliminan permanentemente.
- Un buzón eliminado temporalmente se elimina mediante **Remove-Mailbox-PermanentlyDelete**.

En los escenarios de eliminación mencionados anteriormente se da por supuesto que el buzón de usuario no está en ninguno de los Estados de retención, como la retención por juicio o la retención de eDiscovery. Si hay algún tipo de retención en el buzón de correo, no se puede eliminar. Para todos los tipos de destinatarios de correo, se ignoran todas las opciones de configuración de [retención](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) y no tienen efecto en las eliminaciones o eliminaciones de software.

## <a name="soft-deleted-and-hard-deleted-items"></a>Elementos eliminados temporalmente y eliminados permanentemente
Cuando un usuario elimina un elemento de buzón (por ejemplo, un mensaje de correo electrónico, un contacto, una cita de calendario o una tarea), el elemento se mueve a la carpeta elementos recuperables y a una subcarpeta denominada eliminaciones. Esto se conoce como eliminación temporal. El tiempo que se mantienen los elementos eliminados en la carpeta Eliminaciones depende del período de retención de elementos eliminados configurado para el buzón. De forma predeterminada, los buzones de correo de Exchange Online mantienen los elementos eliminados durante 14 días, pero los administradores de Exchange online pueden cambiar esta configuración para aumentar el período hasta un máximo de 30 días. (Para conocer los pasos detallados para aumentar el período de retención de elementos eliminados para un buzón de correo de Exchange Online, vea [cambiar el tiempo que se conservan los elementos eliminados permanentemente para un buzón de correo de Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention)). Los usuarios pueden recuperar o purgar los elementos eliminados antes de que expire el tiempo de retención de un elemento eliminado. Para ello, use la característica recuperar elementos eliminados de Microsoft Outlook o Outlook en la Web.

Si un usuario depura un elemento eliminado mediante la característica recuperar elementos eliminados de Outlook o Outlook en la web, esto se conoce como una eliminación de hardware. En Exchange Online, la recuperación de un único elemento está habilitada de forma predeterminada cuando se crea un nuevo buzón, por lo que un administrador todavía puede [recuperar](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) los elementos eliminados permanentemente antes de que expire el período de retención de elementos eliminados. Además, si un usuario o un proceso modifican un mensaje, también se conservan copias del elemento original cuando se habilita la recuperación de un elemento único.

## <a name="page-zeroing"></a>Llenado con ceros de la página
El *llenado con ceros* es un mecanismo de seguridad que escribe ceros o un patrón binario sobre los datos eliminados para que los datos eliminados sean más difíciles de recuperar. En Exchange Online, las bases de datos de buzones de correo usan páginas como unidad de almacenamiento e implementan un proceso de sobrescritura denominado *llenado con ceros*de *las páginas* . El llenado con ceros de las páginas está habilitado de forma predeterminada y los clientes o Microsoft no pueden deshabilitarlo. Las operaciones de llenado con ceros de las páginas se registran en los archivos de registro de transacciones de modo que todas las copias de una base de datos determinada tienen ceros de página de forma similar. Al poner en cero una página de una copia de base de datos activa, la página se pone a cero en las copias pasivas de la base de datos.

El llenado con ceros de las páginas escribe un patrón binario sobre los registros eliminados de forma rígida. El patrón de llenado con ceros de páginas es específico de las operaciones del motor de almacenamiento extensible (ESE) (el nombre del motor de base de datos interno usado por los servidores de Exchange Online) y es diferente para las operaciones en tiempo de ejecución frente a las operaciones de mantenimiento de bases de datos en segundo plano. (El mantenimiento de bases de datos en segundo plano es un proceso que suma y examina continuamente cada base de datos. La función principal es realizar una suma de comprobación de las páginas de base de datos, pero también controla la limpieza del espacio y la puesta a cero de los registros y las páginas que no se han llenado en ceros debido a un bloqueo del almacén.)

La siguiente tabla muestra una lista de las tramas de relleno que corresponden a operaciones de tiempo de ejecución específicas.

| Operación de tiempo de ejecución de ESE   | Trama de relleno |
|--------------------------|--------------|
| Reemplazar                  | R            |
| Eliminación de valor de registro/largo | D            |
| Espacio de página liberado         | H            |


La siguiente tabla muestra una lista de las tramas de relleno que corresponden a operaciones específicas que ocurren durante el mantenimiento de la base de datos de ESE en segundo plano.

| Operación de mantenimiento de base de datos de ESE en segundo plano | Trama de relleno |
|-----------------------------------------------|--------------|
| Eliminación de registro                                 | D            |
| Eliminación de valor largo                             | L            |
| Espacio de página liberado de página parcialmente usada       | Z            |
| Espacio de página liberado de página no utilizada               | U            |


### <a name="page-zeroing-process"></a>Proceso de llenado con ceros de las páginas
El proceso de llenado con ceros de las páginas depende del escenario de eliminación. La siguiente tabla analiza los escenarios de eliminación de bases de datos y cuándo se produce el llenado con ceros de páginas.

| Escenario de eliminación de bases de datos | Proceso de ESE y datos de base de datos de período de tiempo a cero |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| El elemento expira en función del período de retención de elementos eliminados. | Un subproceso asincrónico escribe un patrón binario sobre los datos eliminados. Esta acción se produce en milisegundos durante la eliminación de registro. Si el proceso del almacén se bloquea cuando el trabajo de llenado con ceros asincrónico aún está pendiente (o se cancela la limpieza de almacenamiento de la versión debido al crecimiento del almacén), el llenado con ceros se completa cuando el mantenimiento de bases de datos en segundo plano procesa esa sección de la base de datos. |
| Ver escenario: expiración de elementos de Outlook/Outlook en la vista de la carpeta Web (por ejemplo, vista de conversación) | El llenado con ceros de datos se produce cuando el mantenimiento de la base de datos en segundo plano procesa esa sección de la base de datos. |
| Escenario de mover buzón o eliminar buzón de correo: buzón de origen eliminado (expiración del buzón de correo eliminado) | El llenado con ceros de datos se produce cuando el mantenimiento de la base de datos en segundo plano procesa esa sección de la base de datos. |

### <a name="mailbox-data-types-without-page-zeroing"></a>Tipos de datos de buzones de correo sin llenado con ceros de las páginas
Los siguientes tipos de datos de buzón no tienen ninguna disposición para llenado con ceros de las páginas:
- **Registros de transacciones de bases de datos** de buzones: cuando se eliminan registros de transacciones como parte de las operaciones normales, no hay ningún proceso para cero los bloques en el sistema de archivos que han almacenado los archivos de registro eliminados. Es probable que el sistema de archivos vuelva a usar rápidamente ese espacio libre para los registros recién creados, pero no hay ninguna garantía de que esto suceda.
- **Archivos de catálogo de índice de contenido** : Exchange online usa Search Foundation (también conocido como Fast) para la funcionalidad de indización de búsqueda. El catálogo del índice de búsqueda está compuesto por varias docenas de archivos almacenados en el mismo volumen que el archivo de base de datos del buzón de correo. Cuando se elimina de forma permanente un mensaje de la base de datos del buzón de correo, el contenido asociado al catálogo de búsqueda no se elimina de inmediato. La eliminación de contenido se produce cuando Search Foundation realiza una sombra (o combinación maestra) de muchos archivos de catálogo pequeños en un solo archivo más grande. Una vez finalizada la combinación maestra, se eliminan los archivos de catálogo más pequeños. No hay ningún proceso para llenar con ceros los bloques que almacenaban los archivos de catálogo eliminados.

## <a name="continuous-replication"></a>Replicación continua
La replicación continua (también conocida como el trasvase de registros y la reproducción) es la tecnología de Exchange online que crea y mantiene copias de todas las bases de datos de buzones de correo para proporcionar alta disponibilidad, resistencia de sitios y recuperación ante desastres. La replicación continua aprovecha la recuperación de bloqueo de la base de datos de Exchange Server para proporcionar tecnología que realice la actualización asincrónica de una o varias copias de una base de datos de buzones de correo. Cada servidor de buzones de correo registra las actualizaciones de bases de datos realizadas en una base de datos activa (por ejemplo, actividad de correo electrónico del usuario) como registros en un conjunto secuencial de 1 MB de archivos de registro de transacciones. Este conjunto de archivos se conoce como la secuencia de registro. En la replicación continua, la secuencia de registro también se usa para actualizar de forma asincrónica una o más copias de una base de datos. Esto se logra al transmitir los registros a una ubicación que contiene una copia pasiva de la base de datos activa y, a continuación, reproducirlos en la copia pasiva de la base de datos. Si todos los registros de la base de datos activa se reproducen en una copia pasiva de la base de datos, las dos bases de datos son equivalentes y es a través de este proceso que los cambios físicos realizados en una base de datos activa se replican en todas las copias pasivas de esa base de datos.

Cualquier eliminación de una base de datos de buzones de correo, ya sea un elemento de buzón o un buzón de correo completo, y si se trata de una eliminación temporal o de una eliminación permanente, representa un cambio físico en la base de datos activa. El llenado con ceros de las páginas también implica realizar cambios físicos en la base de datos activa. Estos cambios se escriben en los archivos de registro a través de un proceso denominado replicación continua y, cuando estos archivos de registro se reproducen en copias pasivas de la base de datos, se realizan los mismos cambios físicos en dichas bases de datos pasivas.