---
title: Configurar un servicio de EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Este tema explica cómo configurar Microsoft Exchange Online Protection (EOP). Si ha llegado hasta aquí desde el asistente de dominios de Office 365, regrese al asistente para dominios de Office 365 si no desea usar Exchange Online Protection. Si está buscando más información sobre cómo configurar los conectores, consulte Configure mail flow using connectors in Office 365.
ms.openlocfilehash: 6c9e3becf0f86deeee92ec7cf336bdbd950ac5e2
ms.sourcegitcommit: f49ab866e21da83a0be6cb23ab7b6b4366a6a7ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "25715906"
---
# <a name="set-up-your-eop-service"></a>Configurar un servicio de EOP

Este tema explica cómo configurar Microsoft Exchange Online Protection (EOP). Si ha llegado hasta aquí desde el asistente de dominios de Office 365, regrese al asistente para dominios de Office 365 si no desea usar Exchange Online Protection. Si está buscando más información sobre cómo configurar los conectores, consulte [Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx).
  
> [!NOTE]
> Se asume que tiene buzones locales y quiere protegerlos con EOP, lo que se conoce como un escenario independiente. Si desea hospedar todos los buzones de correo en la nube con Exchange Online, no es necesario completar todos los pasos indicados en este tema. Vaya a [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) para suscribirse y comprar buzones en la nube. Si quiere hospedar algunos buzones de correo de forma local y otros en la nube, esto se considera un escenario híbrido. Requiere configuraciones de flujo de correo más avanzadas. En [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx) se explica el flujo de correo híbrido y se incluyen vínculos a recursos que indican cómo configurarlo. 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para completar esta tarea: 1 hora
    
- Para configurar conectores, la cuenta debe ser de un administrador global de Office 365 o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización). Para obtener información sobre cómo se relacionan los permisos de Office 365 con los permisos de Exchange, consulte [Permisos en Office 365](https://go.microsoft.com/fwlink/p/?LinkID=335814).
    
- Si no se ha suscrito a EOP, visite [Protección en línea de Exchange](https://go.microsoft.com/fwlink/p/?LinkId=282660) y elija si quiere comprar o probar el servicio. 
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
    
> [!TIP]
> ¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="how-do-you-do-this"></a>¿Cómo realiza esto?

### <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>Paso 1: Usar el Centro de administración de Office 365 para agregar y comprobar el dominio

1. En el Centro de administración de Office 365, vaya a **Instalación** para agregar el dominio al servicio. 
    
    ¿No sabe dónde encontrar el Centro de administración de Office 365? Lea más información en [Sobre el centro de administración de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=521888).
    
2. Siga los pasos para agregar los registros DNS correspondientes a su proveedor de host DNS para comprobar la propiedad del dominio.
    
> [!TIP]
> Los temas sobre cómo [agregar el dominio a Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) y [crear registros DNS para Office 365](https://support.office.com/en-us/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166) son recursos útiles que se pueden usar como referencia al agregar el dominio al servicio y configurar los registros DNS. 
  
### <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Paso 2: Agregar destinatarios y habilitar alternativamente DBEB

Antes de configurar el correo que circula hacia y desde el servicio EOP, se recomienda agregar los destinatarios al servicio. Hay varias maneras de hacerlo, tal y como se documenta en [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md). Además, si quiere habilitar el Bloqueo perimetral basado en directorios (DBEB) para aplicar la comprobación de destinatarios dentro del servicio después de agregarlos, debe establecer el tipo de dominio en Autoritativo. Para más información sobre DBEB, vea [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).
  
### <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Paso 3: Usar el EAC para configurar el flujo de correo

Cree conectores en el Centro de administración de Exchange (EAC) que permitan el flujo de correo entre EOP y los servidores de correo locales. Para ver las instrucciones detalladas, consulte [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx).
  
#### <a name="how-do-you-know-this-task-worked"></a>¿Cómo sabe si esta tarea se ha completado correctamente?

Use el analizador de conectividad remota para ejecutar una prueba que compruebe el flujo de correo entre el servicio y su entorno. Para más información, vea la sección "Usar Remote Conectivity Analyzer para probar la entrega del correo electrónico", en [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).
  
### <a name="step-4-allow-inbound-port-25-smtp-access"></a>Paso 4: Permitir el acceso SMTP entrante al puerto 25

Después de configurar los conectores, espere 72 horas para que las actualizaciones de los registros DNS se propaguen. A continuación, restrinja el tráfico SMTP entrante del puerto 25 en sus servidores de correo o de firewall para aceptar correo solo de los centros de datos EOP, especialmente de las direcciones IP de la lista en [Direcciones de IP para Exchange Online Protection](exchange-online-protection-ip-addresses.md). Esto protege su entorno local al limitar el ámbito de los mensajes entrantes que puede recibir. Además, si tiene una configuración en su servidor de correo que controla las direcciones IP que se pueden conectar para retransmitir correo, actualice también esta configuración.
  
> [!TIP]
> Establezca la configuración en el servidor SMTP con un tiempo de espera de conexión de 60 segundos. La mayoría de las situaciones aceptan esta configuración, lo que permite algo de retraso en el caso de un mensaje enviado con datos adjuntos muy grandes, por ejemplo. 
  
### <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Paso 5: Usar el Shell para asegurarse de que el correo no deseado se enrute a la carpeta de correo electrónico no deseado de cada usuario

Para asegurarse de que el correo electrónico de spam (no deseado) se enruta correctamente a la carpeta de correo electrónico no deseado de cada usuario, debe realizar un par de pasos de configuración. Los pasos se proporcionan en [asegurarse de que el correo no deseado se enrute a la carpeta de correo no deseado de cada usuario](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).
  
Si no desea mover los mensajes a la carpeta de correo no deseado de cada usuario, es posible que elija otra acción mediante la edición de las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, vea [configurar sus directivas de filtro de correo no deseado](../configure-your-spam-filter-policies.md).
  
### <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>Paso 6: Usar el Centro de administración de Office 365 para apuntar el registro MX a EOP

Siga los pasos de configuración de dominio de Office 365 para actualizar el registro MX de su dominio de forma que el correo entrante pase por EOP. Asegúrese de apuntar su registro MX directamente a EOP en lugar de tener un correo electrónico de retransmisión del servicio de filtro de terceros a EOP. Para más información, puede usar nuevamente como referencia el tema sobre [cómo crear registros DNS para Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219).
  
#### <a name="how-do-you-know-this-task-worked"></a>¿Cómo sabe si esta tarea se ha completado correctamente?

Use Remote Connectivity Analyzer para ejecutar una prueba que compruebe su registro MX. Para más información, vea la sección "Usar Remote Conectivity Analyzer para probar su registro MX y el conector saliente", en [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx). 
  
En este punto, ha comprobado la entrega del servicio para un conector local saliente configurado correctamente, y ha comprobado que su registro MX apunta a EOP. Ahora puede elegir ejecutar las siguientes pruebas adicionales para comprobar que un correo electrónico se entregará correctamente por el servicio a su entorno local:
  
- En Remote Connectivity Analyzer, haga clic en la pestaña **Office 365** y ejecute la prueba **Correo SMTP entrante** situada en **Pruebas de correo de Internet**. 
    
- Envíe un mensaje de correo desde cualquier cuenta de correo electrónico basada en web a un destinatario de correo de su organización cuyo dominio coincida con el dominio que agregó al servicio. Confirme la entrega del mensaje al buzón de correo local mediante Microsoft Outlook u otro cliente de correo electrónico.
    
- Si quiere ejecutar una prueba de correo electrónico saliente, puede enviar un mensaje de correo electrónico de un usuario de su organización a una cuenta de correo electrónico basada en web y confirmar si se recibe el mensaje.
    
> [!TIP]
> Una vez que ha completado la configuración, ya no es necesario realizar ningún otro paso para que EOP quite el malware y el correo no deseado, ya que lo hace de forma automática. No obstante, puede ajustar la configuración en el EAC, en función de las necesidades de su compañía. Para más información, vea [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx). > Ahora que el servicio está en ejecución, le recomendamos que lea [Procedimientos recomendados para configurar EOP](best-practices-for-configuring-eop.md), en donde se describe la configuración recomendada y otras consideraciones que se deben tener en cuenta después de configurar el servicio. 
  

