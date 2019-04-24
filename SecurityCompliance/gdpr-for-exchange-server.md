---
title: RGPD para Exchange Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en Exchange Server local.
ms.openlocfilehash: 8c66787c7da8eef9a580361848499f9f336b49b9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255628"
---
# <a name="gdpr-for-exchange-server"></a>RGPD para Exchange Server

Como parte de la protección de información personal, le recomendamos lo siguiente:

-   Use [Etiquetas de retención y directivas de retención](https://technet.microsoft.com/library/dd297955(v=exchg.160).aspx) en Exchange Server para implementar una directiva de ciclo de vida del correo electrónico.

-   Implemente [Information Rights Management](https://technet.microsoft.com/library/dd638140(v=exchg.160).aspx) para limitar quién tiene acceso a la información almacenada en Exchange Server.

-   Habilite [el cifrado de BitLocker](https://blogs.technet.microsoft.com/exchange/2015/10/20/enabling-bitlocker-on-exchange-servers/) en sus servidores.

## <a name="identifying-in-scope-content"></a>Identificar el contenido en el ámbito

Exchange usa dos repositorios de almacenamiento principales para el contenido generado por usuarios finales: buzones y carpetas públicas. El contenido almacenado en el buzón de un usuario individual se asocia exclusivamente a ese usuario y representa su repositorio predeterminado en Exchange. Los datos almacenados en el buzón de un usuario incluyen contenido creado con Outlook, Outlook en la Web (anteriormente conocido como Outlook Web App), Exchange ActiveSync, los clientes de Skype Empresarial y otras herramientas de terceros que se conectan a los servidores de Exchange mediante POP, IMAP o servicios Web Exchange (EWS). Algunos ejemplos de esos elementos incluyen: mensajes, elementos del calendario (reuniones y citas), contactos, tareas y notas. Eliminar el buzón de un usuario individual quita el contenido generado por o enviado directamente al usuario en el contexto de su buzón. Puede eliminar los buzones de usuario mediante el Centro de administración de Exchange (EAC) o el cmdlet [Remove-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/remove-mailbox?view=exchange-ps) en el Shell de administración de Exchange.\
Nota: El parámetro Permanente en el cmdlet Remove-Mailbox debe usarse con cuidado ya que los datos no se pueden recuperar si se usa esta opción.

Exchange también proporciona buzones compartidos que permiten a uno o más usuarios acceso a enviar y recibir contenido almacenado en un buzón común. El buzón compartido es una única entidad que no está asociada a una única cuenta. En su lugar, varios usuarios tienen acceso para enviar, recibir y revisar el contenido del correo electrónico en el buzón compartido. Los buzones compartidos se administran con el Centro de administración de Exchange y los mismos cmdlets que se usan para administrar buzones de usuario normales. Si quiere quitar mensajes individuales de un buzón, hay diferentes opciones disponibles según la versión de Exchange. En Exchange Server 2010 y 2013, puede usar el cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) con el parámetro DeleteContent para identificar y quitar los mensajes de un buzón. En Exchange Server 2016 y versiones posteriores, deberá usar la funcionalidad [New-ComplianceSearch](https://technet.microsoft.com/library/ff459253(v=exchg.160).aspx).

Las carpetas públicas son una implementación de almacenamiento compartido que no está asociada con un usuario específico. En su lugar, los usuarios tendrán acceso a las carpetas públicas para generar contenido. La implementación real de las carpetas públicas varía según la versión de Exchange (Exchange Server 2010 usa otra implementación de Exchange Server 2013 y versiones posteriores). Existen herramientas limitadas para administrar el contenido de las carpetas públicas. Las herramientas de cliente (por ejemplo, Outlook) son el principal mecanismo para administrar el contenido de las carpetas públicas. Hay cmdlets para administrar objetos de las carpetas públicas, pero no para administrar elementos específicos de contenido de la carpeta pública. Probablemente se necesitará un script personalizado que aprovecha los servicios Web Exchange (EWS) u otras herramientas de terceros para administrar los elementos de la carpeta pública.

El requisito principal es probable que sea administrar el contenido del buzón de usuarios individuales. Este requisito se enviará fácilmente a través de las herramientas gráficas o basada en cmdlet que usa regularmente para administrar buzones. Si necesita procesar el contenido en varios buzones o tipos de recursos, [eDiscovery](https://technet.microsoft.com/library/dd298021(v=exchg.160).aspx) es el mecanismo preferido en Exchange para identificar contenido en el ámbito.

## <a name="deleted-item-retention"></a>Retención de elementos eliminados

Al eliminar mensajes individuales o elementos de un buzón de correo (no todo el buzón o el recurso de la carpeta pública en sí) se retiene el contenido en un formulario que se puede recuperar en función del valor del parámetro DeletedItemRetention de la base de datos del buzón o la base de datos de la carpeta pública. El valor predeterminado es de 14 días, pero un administrador de Exchange puede configurar este valor.

## <a name="removing-soft-deleted-and-disconnected-mailboxes"></a>Quitar buzones eliminados temporalmente y desconectados

Cuando un buzón de Exchange se deshabilita, elimina o mueve entre bases de datos (por ejemplo, como parte de un equilibrio de carga), el buzón se establece en un estado deshabilitado, de eliminación temporal o desconectado dependiendo de la operación. Mientras el buzón se encuentre en cualquiera de estos estados, Exchange mantendrá el buzón (que incluye su contenido) según el valor actual del parámetro MailboxRetention especificado en la base de datos de buzón. El valor predeterminado es 30 días, pero un administrador de Exchange puede configurarlo. Puede usar el cmdlet [Remove-StoreMailbox](https://docs.microsoft.com/powershell/module/exchange/mailbox-databases-and-servers/remove-storemailbox?view=exchange-ps) para obligar a Exchange a eliminar (purgar) todos los datos asociados a un buzón antes de la expiración natural del período de retención.

> [!IMPORTANT]
> Use el cmdlet Remove-StoreMailbox con cuidado, ya que llevará a una pérdida irrecuperable de datos del buzón de correo de destino. 

## <a name="on-prem-to-cloud-migrations"></a>Migración de un entorno local a la nube

Mientras se migran datos de Exchange Server a Exchange Online, lo datos migrados pueden seguir residiendo en el origen local de Exchange Server en un formulario que puede recuperar un administrador de Exchange. De forma predeterminada, los datos se quitarán automáticamente de la base de datos después de 30 días (consulte la sección la anterior Quitar buzones eliminados temporalmente y desconectados).

## <a name="automatic-data-collection-reported-to-microsoft-by-exchange-server"></a>Recolección de datos automática notificada a Microsoft por Exchange Server

Los servidores de Exchange implementados en entornos locales no proporcionan ningún tipo de captura automática de datos de usuarios finales o informes a Microsoft. Los servidores de Exchange que tienen los informes de volcado de memoria de Watson habilitados en el sistema operativo Windows pueden recibir contenidos de memoria limitados en el momento en que se crea el informe de bloqueo.
