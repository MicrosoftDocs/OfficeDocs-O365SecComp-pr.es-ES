---
title: Configurar un servicio de EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Este tema explica cómo configurar Microsoft Exchange Online Protection (EOP). Si ha llegado hasta aquí desde el asistente de dominios de Office 365, regrese al asistente para dominios de Office 365 si no desea usar Exchange Online Protection. Si está buscando más información sobre cómo configurar los conectores, consulte Configure mail flow using connectors in Office 365.
ms.openlocfilehash: 5c17e88784c5987d48930c26e9c4319256a95c43
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676540"
---
# <a name="set-up-your-eop-service"></a>Configurar un servicio de EOP

Este tema explica cómo configurar Microsoft Exchange Online Protection (EOP). Si ha llegado hasta aquí desde el asistente de dominios de Office 365, regrese al asistente para dominios de Office 365 si no desea usar Exchange Online Protection. Si está buscando más información sobre cómo configurar los conectores, consulte [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
> [!NOTE]
> Se asume que tiene buzones locales y quiere protegerlos con EOP, lo que se conoce como un escenario independiente. Si desea hospedar todos los buzones de correo en la nube con Exchange Online, no es necesario completar todos los pasos indicados en este tema. Vaya a [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) para suscribirse y comprar buzones en la nube. Si quiere hospedar algunos buzones de correo de forma local y otros en la nube, esto se considera un escenario híbrido. Requiere configuraciones de flujo de correo más avanzadas. [Exchange Server Hybrid Deployments](https://docs.microsoft.com/exchange/exchange-hybrid) explica el flujo de correo híbrido y contiene vínculos a recursos que muestran cómo configurarlo.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para completar esta tarea: 1 hora

- Para configurar conectores, la cuenta debe ser de un administrador global de Office 365 o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización). Para obtener más información, consulte [Feature Permissions in EOP](feature-permissions-in-eop.md).

- Si no se ha suscrito a EOP, visite [Protección en línea de Exchange](https://go.microsoft.com/fwlink/p/?LinkId=282660) y elija si quiere comprar o probar el servicio.

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Paso 1: usar el centro de administración de Microsoft 365 para agregar y comprobar el dominio

1. En el [centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=521888), vaya a **configuración** para agregar el dominio al servicio.

2. Siga los pasos para agregar los registros DNS correspondientes a su proveedor de host DNS para comprobar la propiedad del dominio.

> [!TIP]
> [Agregar un dominio a office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) y [crear registros DNS en cualquier proveedor de hospedaje dns para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) son recursos útiles para hacer referencia a medida que se agrega el dominio al servicio y se configura el DNS.
  
## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Paso 2: Agregar destinatarios y habilitar alternativamente DBEB

Antes de configurar el correo que circula hacia y desde el servicio EOP, se recomienda agregar los destinatarios al servicio. Hay varias maneras de hacerlo, tal y como se documenta en [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md). Además, si quiere habilitar el Bloqueo perimetral basado en directorios (DBEB) para aplicar la comprobación de destinatarios dentro del servicio después de agregarlos, debe establecer el tipo de dominio en Autoritativo. Para más información sobre DBEB, vea [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Paso 3: Usar el EAC para configurar el flujo de correo

Cree conectores en el Centro de administración de Exchange (EAC) que permitan el flujo de correo entre EOP y los servidores de correo locales. Para ver las instrucciones detalladas, consulte [Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).
  
### <a name="how-do-you-know-this-task-worked"></a>¿Cómo sabe si esta tarea funcionó?

Compruebe el flujo de correo entre el servicio y su entorno. Para obtener más información, vea [probar el flujo de correo mediante la validación de los conectores de Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Paso 4: Permitir el acceso SMTP entrante al puerto 25

Después de configurar los conectores, espere 72 horas para que las actualizaciones de los registros DNS se propaguen. A continuación, restrinja el tráfico SMTP entrante del puerto 25 en sus servidores de correo o de firewall para aceptar correo solo de los centros de datos EOP, especialmente de las direcciones IP de la lista en [Direcciones de IP para Exchange Online Protection](exchange-online-protection-ip-addresses.md). Esto protege su entorno local al limitar el ámbito de los mensajes entrantes que puede recibir. Además, si tiene una configuración en su servidor de correo que controla las direcciones IP que se pueden conectar para retransmitir correo, actualice también esta configuración.
  
> [!TIP]
> Establezca la configuración en el servidor SMTP con un tiempo de espera de conexión de 60 segundos. Esta configuración es aceptable en la mayoría de las situaciones, lo que permite un retraso en el caso de un mensaje enviado con datos adjuntos grandes, por ejemplo.
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Paso 5: Usar el Shell para asegurarse de que el correo no deseado se enrute a la carpeta de correo electrónico no deseado de cada usuario

Para asegurarse de que el correo no deseado se enrute correctamente a la carpeta de correo no deseado de cada usuario, debe realizar varios pasos de configuración. Los pasos se proporcionan [para asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).
  
Si no desea mover mensajes a la carpeta de correo no deseado de cada usuario, puede elegir otra acción si modifica las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](../configure-your-spam-filter-policies.md).
  
## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Paso 6: usar el centro de administración de Microsoft 365 para apuntar el registro MX a EOP

Siga los pasos de configuración de dominio de Office 365 para actualizar el registro MX de su dominio de forma que el correo entrante pase por EOP. Asegúrese de apuntar su registro MX directamente a EOP en lugar de tener un correo electrónico de retransmisión del servicio de filtro de terceros a EOP. Para más información, puede usar nuevamente como referencia el tema sobre [cómo crear registros DNS para Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).
  
### <a name="how-do-you-know-this-task-worked"></a>¿Cómo sabe si esta tarea funcionó?

En este punto, ha comprobado la entrega del servicio para un conector local saliente configurado correctamente, y ha comprobado que su registro MX apunta a EOP. Ahora puede elegir ejecutar las siguientes pruebas adicionales para comprobar que un correo electrónico se entregará correctamente por el servicio a su entorno local:
  
- Compruebe el flujo de correo entre el servicio y su entorno. Para obtener más información, vea [probar el flujo de correo mediante la validación de los conectores de Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Envíe un mensaje de correo desde cualquier cuenta de correo electrónico basada en web a un destinatario de correo de su organización cuyo dominio coincida con el dominio que agregó al servicio. Confirme la entrega del mensaje al buzón de correo local mediante Microsoft Outlook u otro cliente de correo electrónico.

- Si quiere ejecutar una prueba de correo electrónico saliente, puede enviar un mensaje de correo electrónico de un usuario de su organización a una cuenta de correo electrónico basada en web y confirmar si se recibe el mensaje.

> [!TIP]
> Una vez completada la configuración, no es necesario realizar pasos adicionales para que EOP Quite el correo no deseado y el malware. EOP elimina el correo no deseado y el malware automáticamente. Sin embargo, puede ajustar la configuración en el EAC en función de los requisitos empresariales. Para obtener más información, vea [protección contra correo electrónico no deseado y antimalware en Office 365](../anti-spam-and-anti-malware-protection.md). <br/><br/> Ahora que el servicio está en ejecución, se recomienda leer los [procedimientos recomendados para configurar EOP](best-practices-for-configuring-eop.md), que describe la configuración y las consideraciones recomendadas para después de configurar EOP.
